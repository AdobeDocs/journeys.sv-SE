---
product: adobe campaign
title: min
description: Läs mer om min-funktionen
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7e13a08c-c51a-4d40-a3e2-ef70bd3edca5
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 4%

---

# min {#min}

Returnerar det minsta värdet bland en uppsättning uttryck, givet antingen som en lista eller två uttryck. Null-värden ignoreras.

## Kategori

Aggregering

## Funktionssyntax

`min(<parameters>)`

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

`min(<listDuration>)`

Returnerar en varaktighet.

`min(<listInteger>)`

Returnerar en varaktighet.

`min(<listDateTimeOnly>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

`min(<listDateTime>)`

Returnerar en datetime.

`min(<listDateOnly>)`

Returnerar ett datum.

`min(<listDecimal>)`

Returnerar ett decimaltal.

`min(<decimal>,<decimal>)`

Returnerar ett decimaltal.

`min(<duration>,<duration>)`

Returnerar en varaktighet.

`min(<dateTime>,<dateTime>)`

Returnerar en datetime.

`min(<dateTimeOnly>,<dateTimeOnly>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

`min(<integer>,<integer>)`

Returnerar ett heltal.

## Exempel

`min(@{BarBeacon.inventory},5)`

`min([10,3,8])`

Returnerar 3.

`min([10,null,8])`

Returnerar 8.
