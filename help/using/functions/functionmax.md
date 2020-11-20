---
product: adobe campaign
solution: Journey Orchestration
title: max
description: Läs mer om funktionen max
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 4%

---

# max{#max}

Returnerar det maximala värdet bland en uppsättning uttryck, givet antingen som en lista eller två uttryck. Null-värden ignoreras.

## Kategori

Aggregera

## Funktionssyntax

`max(<parameter>)`

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

`max(<listDuration>)`

Returnerar en varaktighet.

`max(<listInteger>)`

Returnerar en varaktighet.

`max(<listDateTimeOnly>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

`max(<listDateTime>)`

Returnerar en datetime.

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
