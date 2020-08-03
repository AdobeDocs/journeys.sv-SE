---
title: min
description: Läs mer om min-funktionen
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 0%

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
