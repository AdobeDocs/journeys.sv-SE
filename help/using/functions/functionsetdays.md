---
product: adobe campaign
solution: Journey Orchestration
title: setDays
description: Läs mer om funktionen setDays
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '78'
ht-degree: 6%

---


# setDays {#setDays}

Anger endast dag för datum och tid. Om du till exempel vill vänta till en viss dag i månaden kan du tvinga fram dagen.

## Kategori

Datum

## Funktionssyntax

`setDays(<parameter>)`

## Parametrar

| Parameter | Typ |
|--- |--- |
| tid | dateTime |
| datum tid utan att överväga tidszon | dateTimeOnly |
| dagar | heltal |

## Underskrifter och returtyp

`setDays(<dateTime>,<days>)`

Returnerar en datetime.

`setDays(<dateTimeOnly>,<days>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

## Exempel

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Returnerar 2010-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
