---
product: adobe campaign
solution: Journey Orchestration
title: summa
description: Läs mer om funktionssumman
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 7%

---


# summa {#sum}

Returnerar summan av värdena för en uppsättning uttryck. Null-värden ignoreras.

## Kategori

Aggregera

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
