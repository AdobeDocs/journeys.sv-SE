---
product: adobe campaign
title: inLastMonths
description: Läs mer om funktionen i LastMonths
feature: Journeys
role: Developer
level: Experienced
exl-id: ff8effa9-404a-482b-8842-a276f029e2ed
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%

---

# inLastMonths {#inLastMonths}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu - delta-månader.

## Kategori

Datum

## Funktionssyntax

`inLastMonths(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inLastMonths(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returnerar true.
