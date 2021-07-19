---
product: adobe campaign
title: nowWithDelta
description: Läs mer om funktionen nowWithDelta
feature: Resor
role: Data Engineer
level: Experienced
exl-id: f23f729b-7edb-4efc-a7ea-904314a7b2e1
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 7%

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
