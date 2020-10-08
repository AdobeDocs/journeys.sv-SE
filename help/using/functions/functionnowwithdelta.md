---
title: nowWithDelta
description: Läs mer om funktionen nowWithDelta
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 4%

---


# nowWithDelta {#nowWithDelta}

Returnerar aktuell datetime inklusive en förskjutning. Om ett tidszon-ID anges används tidszonsförskjutningen. Mer information om datatyper finns i [](../expression/data-types.md).

## Kategori

Datum

## Funktionssyntax

`nowWithDelta(<parameters>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| delta | positivt eller negativt heltalsvärde |
| datumdel | år, månader, dagar, timmar, minuter eller sekunder som en sträng |
| tidszon-id | strängbeteckning för tidszonsvärdet. Mer information finns [](../expression/data-types.md). Tidszons-ID måste vara en strängkonstant. Det kan inte vara en fältreferens eller ett uttryck. |

## Underskrifter och returtyp

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Returnerar ett dateTime.

## Exempel

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Returnerar ett dateTime för exakt 2 timmar sedan.
