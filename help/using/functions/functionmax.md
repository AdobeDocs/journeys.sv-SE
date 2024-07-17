---
product: adobe campaign
title: max
description: Läs mer om funktionen max
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 116713e0-7bbd-4150-8495-f87034eafb5f
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 4%

---

# max{#max}

Returnerar det maximala värdet bland en uppsättning uttryck, givet antingen som en lista eller två uttryck. Null-värden ignoreras.

## Kategori

Aggregering

## Funktionssyntax

`max(<parameter>)`

## Parametrar

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
* listDateOnly
* varaktighet
* heltal
* decimal
* dateTime
* dateTimeOnly

## Underskrifter och returnerade typer

`max(<listDuration>)`

Returnerar en varaktighet.

`max(<listInteger>)`

Returnerar en varaktighet.

`max(<listDateTimeOnly>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

`max(<listDateTime>)`

Returnerar en datetime.

`max(<listDateOnly>)`

Returnerar ett datum.

`max(<listDecimal>)`

Returnerar ett decimaltal.

`max(<decimal>,<decimal>)`

Returnerar ett decimaltal.

`max(<duration>,<duration>)`

Returnerar en varaktighet.

`max(<dateTime>,<dateTime>)`

Returnerar en datetime.

`max(<dateTimeOnly>,<dateTimeOnly>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

`max(<integer>,<integer>)`

Returnerar ett heltal.

## Exempel

`max(@{BarBeacon.inventory},5)`

`max([10,3,8])`

Returnerar 10.

`max([10,null,8])`

Returnerar 10.
