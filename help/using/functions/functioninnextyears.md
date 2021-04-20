---
product: adobe campaign
solution: Journey Orchestration
title: inNextYears
description: Läs om funktionen iNextYears
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 10%

---


# inNextYears {#inNextYears}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-år.

## Kategori

Datum

## Funktionssyntax

`inNextYears(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inNextYears(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inNextYears(toDateTime('2021-12-12T01:11:00Z'), 4))`

Returnerar true.
