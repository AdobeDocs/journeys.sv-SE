---
product: adobe campaign
solution: Journey Orchestration
title: inNextHours
description: Läs mer om funktionen i NextHours
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---


# inNextHours {#inNextHours}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-timmar.

## Kategori

Datum

## Funktionssyntax

`inNextHours(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inNextHours(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inNextHours(toDateTime('2010-12-12T01:11:00Z'), 4)`

Returnerar true.
