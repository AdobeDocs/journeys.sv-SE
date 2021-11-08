---
product: adobe campaign
title: setHours
description: Läs mer om funktionen setHours
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d4fe578f-c3be-4c8b-98b3-090dab0c41d1
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '101'
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

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returnerar 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Returnerar imorgon kl. 8:XY PM, XY är minuter vid tidpunkten för den aktuella tidsutvärderingen. Om utvärderingen görs kl. 02.45 blir den returnerade tiden 08.45.
