---
product: adobe campaign
solution: Journey Orchestration
title: inLastMonths
description: Läs mer om funktionen i LastMonths
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

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

`inLastMonths(toDateTime('2010-12-12T01:11:00Z'), 4))`

Returnerar true.
