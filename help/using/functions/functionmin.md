---
product: adobe campaign
solution: Journey Orchestration
title: min
description: Läs mer om min-funktionen
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '92'
ht-degree: 5%

---


# min {#min}

Returnerar det minsta värdet bland en uppsättning uttryck, givet antingen som en lista eller två uttryck. Null-värden ignoreras.

## Kategori

Aggregera

## Funktionssyntax

`min(<parameters>)`

## Parametrar

* listDuration
* listInteger
* listDecimal
* listDateTime
* listDateTimeOnly
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
