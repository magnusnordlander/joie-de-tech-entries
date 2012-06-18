---
title: Dynamic range och dagens musik
---

Jag gillar musik. Indie pop/rock mestadels. Som jag skrivit om tidigare så har jag ganska bra utrustning att lyssna på musik med, ett par Denon AH-D2000. Man skulle ju kunna tro att med fin utrustning så vore allt frid och fröjd, bara att lyssna på, men idag är jag dock rädd att jag behöver prata om ett allvarligt ämne. Jag behöver prata om hur dagens inspelningar av musik förstör musik. 

Det låter kanske allvarligt, men jag ska ta ett konkret exempel. The Royal Concept kom nyligen ut med en ny singel, [World on fire](http://open.spotify.com/track/422Ms9CCWo84Nf4nnQBBa6). Det är en bra låt, men som vi kommer se så har den förstörts i produktionen.

Jag köpte låten på iTunes (som 256 kbps AAC) för att demonstrera det här, så det är förvisso från en komprimerad källa, men det är inte på långa vägar det största problemet.

Min tanke var att visa er en Masvis-rapport för låten och sedan gå igenom lite snabbt vad som är problemet, men redan innan dess, när jag skulle konvertera låten till wav i Audacity stötte jag på patrull.

### Audacity

[![Audacity-bild över låten](http://d.pr/i/YBVx+)](http://d.pr/i/bVd3)

Ni kan klicka på bilden för att se den i full storlek. Ser ni de där röda strecken? De röda strecken är [clipping](http://en.wikipedia.org/wiki/Clipping_(audio)). När musikinformation har gått förlorad för att man har "slått i taket" på en inspelning. Musik är som ni säkert vet vågor i luften, och när man kodar musik digitalt så har man en helt godtyckligt satt nivå av vad som är högsta tillåtna höjden på en våg. Clipping är när man går över den höjden. Det resulterar i distorsion, och inte i distorsion på något bra sätt, som ni kanske associerar med "distade elgitarrer" eller något sånt, utan distorsion som i att man inte hör ljudet som musikerna försökt förmedla.

Som om inte det här var oroväckande nog gick jag dock vidare till Masvis.

### Masvis

![Masvis-bild över låten](http://d.pr/i/kTYL+)

Här är dock den verkligen skrämmande läsningen. I både höger och vänsterkanalerna har vi runt 10 dB crest, något som tyder på låg dynamisk range, och om vi tittar på histogrammet är det bara en kulle! I en låt med hög dynamisk range så ser histogrammet snarare ut som en pyramid. Det där är mer hobbithål än pyramid.

Masvis-bilden bekräftar det som jag misstänkte från början. Det här är en låt som har fått dynamic range compression. 

### Vad gör det för skillnad?

Som alltid när det gäller ljud så är det ju mycket svårare att förklara i text vad som är skillnaden på en låt som har fått dynamic range compression, och en som inte har det. Lyckligtvis så har andra gjort jobbet åt mig, något ni kan beskåda (och framförallt höra) i följande Youtube-video:

<iframe width="480" height="360" src="http://www.youtube.com/embed/3Gmex_4hreQ?rel=0" frameborder="0" allowfullscreen></iframe>

Hör ni skillnaden? Jag skulle tro att om ni lyssnar med något annat än typ en brödrost så gör ni det. Jag gör det i alla fall på de inbyggda laptophögtalarna jag har här.

Vad föredrar ni? Musik utan dynamic range, eller med? Jag föredrar definitivt med, och det finns [gott om forskning](http://dynamicrangeday.co.uk/research/) som visar att de flesta lyssnare också föredrar mer dynamic range.

### Slutord

Det är inte bara "World on fire" som lider av det här problemet, tyvärr. Dynamic range compression har förstört stora delar av den musik som släppts de senaste åren, och det är vi lyssnare som får lida, även fast vi inte föredrar det. Man skulle kunna tro att artisterna borde lida också, jag kan inte förstå hur de antingen kan låta andra eller själva förstör frukten av sina mödor på det här sättet.

Dynamic range compression är tyvärr ett problem som inte kommer försvinna förrän vi konsumenter kräver det, och det är synd, för det gör skillnad för kvaliteten på musik. Så berätta för era vänner om vad som händer med musiken och vad de går miste om. Berätta för skivbolagen, berätta för artisterna.

Låt oss hoppas att musikmassakern snart är över...