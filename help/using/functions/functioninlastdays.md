---
product: adobe campaign
solution: Journey Orchestration
title: inLastDays
description: Läs mer om funktionen inLastDays
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inLastDays {#inLastDays}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu - delta-dagar.

## Kategori

Datum

## Funktionssyntax

`inLastDays(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inLastDays(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inLastDays(toDateTime('2019-12-12T01:11:00Z'), 4))`

Returnerar true.
