---
product: adobe campaign
title: inNextDays
description: Läs mer om funktionen i NextDays
feature: Journeys
role: Developer
level: Experienced
exl-id: 47d31b56-b0ed-426d-bd79-3db3e441454b
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%

---

# inNextDays {#inNextDays}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-dagar.

## Kategori

Datum

## Funktionssyntax

`inNextDays(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inNextDays(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inNextDays(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returnerar true.
