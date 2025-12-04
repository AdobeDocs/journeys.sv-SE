---
product: adobe campaign
title: inLastYears
description: Läs om funktionen iLastYears
feature: Journeys
role: Developer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%

---

# inLastYears {#inLastYears}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu - delta-år.

## Kategori

Datum

## Funktionssyntax

`inLastYears(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inLastYears(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returnerar true.
