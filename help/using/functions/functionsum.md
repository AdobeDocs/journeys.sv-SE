---
product: adobe campaign
title: sum
description: Läs mer om funktionssumman
feature: Journeys
role: Developer
level: Experienced
exl-id: 04289d72-aade-4725-b1f5-47cf55e3a40b
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 7%

---

# sum {#sum}

Returnerar summan av värdena för en uppsättning uttryck. Null-värden ignoreras.

## Kategori

Aggregering

## Funktionssyntax

`sum(<parameters>)`

## Parametrar

* listInteger
* listDecimal
* varaktighet
* heltal
* decimal

## Underskrifter och returnerade typer

`sum(<listDecimal>)`

Returnerar ett decimaltal.

`sum(<listInteger>)`

Returnerar ett heltal.

`sum(<integer>,<integer>)`

Returnerar ett heltal.

`sum(<decimal>,<decimal>)`

Returnerar ett decimaltal.

## Exempel

`sum(@{BarBeacon.inventory},5)`

`sum([10,3,8])`

Returnerar 21.

`sum([10.5,null,8.1])`

Returnerar 18.6.
