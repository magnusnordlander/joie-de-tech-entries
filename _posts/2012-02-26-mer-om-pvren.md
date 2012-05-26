---
layout: post
title: "Mer om PVR:en"
category: Tech
tags: [tv, comhem]
permalink: Tech/2012/02/08/mer-om-pvren
---
{% include JB/setup %}

Nu har jag fått min PVR. Några saker är jag väldigt nöjd med. Jag har inte längre några problem med avkodningsfel, och inspelningsfunktionen funkar klanderfritt. Timeshifting är väldigt schysst. Funktionaliteten som finns är robust. Det finns ingen risk för att man exempelvis sabbar en inspelning oavsiktligt.

Andra saker är jag mindre nöjd med. Det främsta problemet är att UI:t på PVR:en på något vis lyckas vara samtidigt avskalat och krångligt. Jag var tvungen att läsa i manualen för att kunna göra en egen kanallista, något som alla som inte råkar ha tillgång till samtliga kanaler i ComHems utbud kan antas vilja göra.

Något jag visste tidigare, men som ju är störigt är att det inte går att klippa i inspelade program. Skulle man vilja klippa bort de minutrarna man spelar in innan programmet börjar, reklamen mitt i och minutrarna efter så är det tough luck. Förhoppningsvis kan jag få tag på inspelningarna ifrån disken, framöver.

Jag har gjort ytterligare research. Jag skulle tro att Samsung SMT-C7160 är en comhemspecifik modell av Samsung SMT-C7140. Boxen använder Linux, och Samsung har släppt källkoden till sin GPLade mjukvara, men det finns vad jag såg inget sätt att ladda in en ny image.

Boxen lagrar sin firmware i ett flashminne, något som jag såg när den uppgraderade, så om flashminnet sitter i ett eget package så borde det ju gå att läsa ut imagen ur det, med rätt utrustning, och eventuellt även programmera om den.

Jag har inte monterat ur disken än, men inspelningarna verkar vara en dump av transportströmmen, något som indikeras av att även EPG:n för det inspelade programmet sparas ned.

Jag läste på något forum att någon monterade ur disken och att den enligt Windows var i "RAW"-format, vilket naturligtvis innebär att Windows inte känner igen dess filsystem. Det säger självklart inget annat än att disken inte använder NTFS eller FAT32 som filsystem, men det är ju inte direkt någon högoddsare.

Jag skulle gissa att disken kör ext3, inga krusiduller. Eftersom funktionaliteten för att flytta inspelningar finns men är avslagen i Comhems variant så skulle jag tro att Samsung inte sett något värde i att köra heldiskkryptering eller att försöka sig på security by obscurity genom att ändra i filsystemet.

Fortsättning följer, helt enkelt.