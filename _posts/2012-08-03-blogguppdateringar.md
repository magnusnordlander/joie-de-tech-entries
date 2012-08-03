---
title: Blogguppdateringar
---

Jag har filat lite på koden för min blogg. Som ni kanske märker så är den totala upplevelsen nu betydligt snabbare. Mycket av det tidigare problemet (som kunde ge upplevda sidladdningstider på runt 800ms) berodde på bildhanteringen, eller snarare avsaknaden av bildhantering. Bilderna låg uppladdade på Droplr (som i sin tur verkar använda Amazon Cloudfront) som inte ens skickade vettiga cache-headers på bilderna, och det blev helt enkelt långsamt i jämförelse med att hosta bilderna på samma server.

Dessutom gjorde det nya bildhanteringssystemet det enkelt att göra hela sidan retina enabled, så alla bilder är knivskarpa på min rMBP.

Bildhanteringssystemet har alla vanliga bells and whistles. Det kan skala bilder, croppa, välja kvalitet. Det klarar av att läsa bilder från typ varsomhelst (via Gaufrette, jag läser bilder från Git via Gittern), och det klarar även av att cacha de skalade bilderna typ var som helst (också via Gaufrette), och det kan till och med hålla koll på om den cachade skalade bilden får en ny adress.

Däremot ligger inte det nya bildhanteringssystemet open sourcat någon stans än. Det är helt enkelt inte redo för prime-time än, utan det får ligga och puttra lite på min blogg. Det blev dock ett par schyssta ändringar i Bloghoven för att passa in det snyggt.

Nästa steg för Bloghoven är Atompub-stöd, så man kan publicera bloginlägg över HTTP, och sedan kanske det är dags att börja med någon slags admingränssnitt. Admin-gränssnittet kommer dock inte funka i gamla versioner av IE (i dagsläget lutar det åt IE10 och uppåt, men vem vet, det kan ju alltid bli IE11 istället). Tydligen har de horribelt stöd för XML Namespaces, vilket ju är förståeligt. Jag menar, standarden kom ju till så sent som 1999, och över 10 år räcker ju inte för att få ens grundläggande stöd för något i Internet Explorer.

Jag känner lite som karaktären Michael Bolton i filmen Office Space när han svarar på frågan varför han inte byter namn, om han ogillar att bli associerad med artisten Michael Bolton så mycket.

> **Samir Nagheenanajar**: You know, there is nothing wrong with that name.  
> **Michael Bolton**: No, there was nothing wrong with it, until I was about 12 years old and that no talent ass-clown became famous and started winning Grammys.  
> **Samir Nagheenanajar**: Why don't you just go by Mike instead of Michael.  
> **Michael Bolton**: No way, why should I change? He's the one who sucks.