---
product: adobe campaign
title: setDays
description: Läs mer om funktionen setDays
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: eee7bf61-9101-4959-aa93-27d0f221c517
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 6%

---

# setDays {#setDays}

Anger endast dag för datum och tid. Om du t.ex. vill vänta till en viss dag i månaden kan du tvinga fram dagen.

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
