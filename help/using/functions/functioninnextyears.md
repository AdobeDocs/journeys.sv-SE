---
product: adobe campaign
solution: Journey Orchestration
title: inNextYears
description: Läs om funktionen iNextYears
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

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
