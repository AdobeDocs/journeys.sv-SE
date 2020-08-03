---
title: summa
description: Läs mer om funktionssumman
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
source-git-commit: 654888ee62a7b9b6e3d34fc3963fb83cac719003
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 0%

---


# summa {#sum}

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
