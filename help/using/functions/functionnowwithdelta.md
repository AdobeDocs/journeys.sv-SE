---
product: adobe campaign
solution: Journey Orchestration
title: nowWithDelta
description: Läs mer om funktionen nowWithDelta
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 5%

---


# nowWithDelta {#nowWithDelta}

Returnerar aktuell datetime inklusive en förskjutning. Om ett tidszon-ID anges används tidszonsförskjutningen. Mer information om datatyper finns på [den här sidan](../expression/data-types.md).

## Kategori

Datum

## Funktionssyntax

`nowWithDelta(<parameters>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| delta | positivt eller negativt heltalsvärde |
| datumdel | år, månader, dagar, timmar, minuter eller sekunder som en sträng |
| tidszon-id | strängbeteckning för tidszonsvärdet. Mer information finns i [Datatyper](../expression/data-types.md). Tidszons-ID måste vara en strängkonstant. Det kan inte vara en fältreferens eller ett uttryck. |

## Underskrifter och returtyp

`nowWithDelta(<delta>,<date part>`

`nowWithDelta(<delta>,<date part>,"<timeZone id>")`

Returnerar ett dateTime.

## Exempel

`nowWithDelta(-2, "hours")`

`nowWithDelta(-2, "hours", "Europe/Paris")`

Returnerar ett dateTime för exakt 2 timmar sedan.
