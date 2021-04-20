---
product: adobe campaign
solution: Journey Orchestration
title: setHours
description: Läs mer om funktionen setHours
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 6%

---


# setHours {#setHours}

Anger endast timmar för datum och tid. Om du till exempel vill vänta en viss timme i morgon kan du tvinga timmen.

## Kategori

Datum

## Funktionssyntax

`setHours(<parameter>)`

## Parametrar

| Parameter | Typ |
|--- |--- |
| tid | dateTime |
| datum tid utan att överväga tidszon | dateTimeOnly |
| timmar | heltal |

## Underskrifter och returtyp

`setHours(<dateTime>,<hours>)`

Returnerar en datetime.

`setHours(<dateTimeOnly>,<hours>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

## Exempel

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Returnerar 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Returnerar imorgon klockan åtta.
