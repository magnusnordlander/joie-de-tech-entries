---
categories: [Fervo, Symfony]
title: Improving Symfony workers
---
I've been doing workers in Symfony for quite a while now. E-butik used workers that were written as a daemon in PHP, polling from a beanstalkd server. Because that worked poorly (memory leaks, crashing, mysterious behaviour etc.), we also used Scala workers.

At Redeye, we're using Sidekiq, launching a Symfony console command for each job. This works well, but that's because the worker load is low. Launching a console command is quite expensive.

A few weeks ago I heard that OpenSky forwards Symfony events to their message queue, and their worker simply dispatching events back into the event dispatcher (but of course in a separate process). More information about the OpenSky architecture (seriously recommended read!) is available in Jonathan Wage's ([@jwage](https://twitter.com/jwage)) presentation "[Building OpenSky with Symfony2](https://speakerdeck.com/jwage/building-opensky-with-symfony2)"

This friday at [November Camp](http://www.symfony.se/november-camp) I listened to Ville Mattilla's ([@vjom](https://twitter.com/vjom)) presentation "Running scalable and reliable Symfony2 applications", and found out that they're basically doing the same thing as we did at Redeye, they're launching a command from their worker daemon.

Up until then it had seemed there were basically three options.

1. Use a single PHP worker process to run the jobs, and deal with stability problems
2. Launch a new process for each job, and have bad performance
3. Use another language for your workers

That's when it hit me like a slippery fish. This performance problem is already solved, by PHP-FPM. You see, this is *exactly* the same problem that people had with CGI. Launching a new process for every request is slow, FPM was created to allow the PHP engine to keep running between requests, but to still clear PHP's internal state between requests, nipping any memory leaks or crashes in the bud.

## FervoDeferredEventBundle
Having some [previous experience](https://github.com/fervo/FCGIKit) with FastCGI I took it upon myself to fix this problem once and for all, and the result is FervoDeferredEventBundle.

FervoDeferredEventBundle allows you to defer execution of events, either by dispatching a wrapping event, or by calling a method on a service:

Events:

```
$evt = new DeferEvent('foo.action', new FooActionEvent());
$eventDispatcher->dispatch('fervo.defer', $evt);
```
Service:

```
$evt = new FooActionEvent();
$evt->setName('foo.action');
$container->get('fervo_dispatch.queue')->deferEvent($evt);
```

As if by magic, at some later time, a worker will dispatch your event into the event dispatcher. Pretty much the only caveats you'll need to keep in mind is that it is in another process, and that the code isn't executing in the request scope anymore.

Of course FervoDeferredEventBundle required some kind of a message queue and a worker. I decided upon using Sidekiq, but the bundle itself is fairly backend agnostic, and should be easily portable to other MQs.

Using PHP-FPM brings two other advantages. First of all, you can set up a separate FPM pool for your workers, making sure that workers cannot run amok and crash your server. Secondly, since FastCGI uses TCP Sockets, you can have your FPM pool on a separate machine from your workers, allowing you to keep your PHP machines free from the Ruby runtime and vice versa.

[FervoDeferredEventBundle](https://github.com/fervo/FervoDeferredEventBundle) is available at Github, along with [the worker](https://github.com/fervo/deferred-event-worker). While the bundle is pretty nice, there's probably some work to be done on the worker. I'm not a Ruby programmer, and I'm fairly sure it shows :)

## Performance
I decided to also create a performance test in order to see what kind of a speedup this might get. The listener for the deferred event is very simple, just doing a ```usleep(5)``` to simulate a database transaction or whatever.

I wrote up a small command to dispatch 1000 deferred events, and did some simple measurements comparing using FastCGI to launching new processes. Since FervoDispatchBundle uses a command to dispatch the deferred event, the only PHP code difference is how that command is invoked (and even that is very similar). This means that pretty much the entire difference comes from using FastCGI vs. creating a new process. I took the measurements using Sidekiq's built in logging.

|             | **FastCGI** | **Popen** |
|------------ | ----------- | --------- |
| **Average** | 0.515       | 0.909     |
| **Median**  | 0.085       | 0.911     |
| **Min**     | 0.016       | 0.446     |
| **Max**     | 2.246       | 1.041     |
| **Stdev**   | 0.747       | 0.046     |

As you can see, the FastCGI implementation fluctuates a lot, but is on average 2x faster, and has a 10x median speedup. I also noted that using popen maxed out my CPUs, while the FastCGI implementation barely made a dent on the CPU load. The tests were run on my Quad Core Retina Macbook Pro (2011) with 16 GB RAM.

For all you number crunchers out there, the raw data is available in a [Google Spreadsheet](https://docs.google.com/spreadsheet/ccc?key=0AtTQNwkuI5jvdEMtTm9KUGRDY1g4QTVlb2IwNWhyU1E&usp=sharing).

## Conclusion
I'm not claiming that my numbers are definite, I'm sure there's plenty to do implementation-wise, and that my setup isn't at all tuned for running workers, but it should serve well as an indicator that using FastCGI for running your workers is worth pursuing.

Like I said, the code is available on Github, and will probably be going into production soon. Feel free to send pull requests!