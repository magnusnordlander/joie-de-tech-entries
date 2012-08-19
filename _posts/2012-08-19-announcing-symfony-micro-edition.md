---
category: symfony
title: Announcing Symfony2 Micro Edition
---

*I'm simply gonna keep writing in English whenever I feel like it.*

We all love Symfony2. It's by far the best PHP framework a by the time of writing. It's fast, it allows you to write great code, and if you're a beginner it's easy to get started with the Symfony2 Standard Edition.

As much as we all love that it's easy for newcomers to get started, if you're an experienced Symfony2 user starting a new project, you don't need all the demo stuff. You also don't necessarily need all the vendors shipped with the standard edition.

If you're an experienced Symfony2 user starting a new project, the first thing to do is to start clearing out all the stuff you don't need from the Standard Edition.

**That is, until now.**

I've created [Symfony2 Micro Edition](https://github.com/magnusnordlander/symfony-micro). Basically, it's just the standard edition with pretty much everything removed. No demo bundle, no Doctrine 2 (however, Doctrine Common is there). 

It's just Symfony, Twig, Monolog, Doctrine Common and the Symfony Distribution Bundle (for generating the bootstrap).

To use it, just get a zipball from Github, extract it, and use composer to install the vendors.

If you don't know how to use it, don't, just use the Standard Edition instead.