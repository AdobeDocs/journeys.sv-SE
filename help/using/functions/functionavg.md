---
product: adobe campaign
title: avg
description: Läs mer om avg för funktioner
feature: Journeys
role: Developer
level: Experienced
exl-id: 6c9f3a5d-20b4-4c0a-b17f-5221f5db51be
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 7%

---

# avg {#avg}

Returnerar det genomsnittliga värdet bland en uppsättning uttryck, givet antingen som en lista eller två uttryck. Null-värden ignoreras.


## Kategori

Aggregering

## Funktionssyntax

`avg(<parameter>)`

## Parametrar

Typer som stöds:

* listInteger
* listDecimal
* decimal
* heltal

## Underskrifter och returtyp

`avg(<listInteger>)`

`avg(<listDecimal>)`

`avg(<decimal>,<decimal>)`

`avg(<decimal>,<integer>)`

`avg(<integer>,<decimal>)`

`avg(<integer>,<integer>)`

Returnerar ett decimaltal.

## Exempel

`avg(@{BarBeacon.inventory},5)`

`avg([10,3,8])`

Returnerar 7.0.

`avg(10.2, 3)`

Returnerar 6,6.
