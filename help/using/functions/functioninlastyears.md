---
product: adobe campaign
title: inLastYears
description: Läs om funktionen iLastYears
feature: Resor
role: Data Engineer
level: Experienced
exl-id: 95ca3d7d-2340-4378-9af4-aa1188bed614
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '45'
ht-degree: 13%

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

`inLastYears(toDateTime('2010-12-12T01:11:00Z'), 4))`

Returnerar true.
