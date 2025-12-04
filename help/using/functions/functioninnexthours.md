---
product: adobe campaign
title: inNextHours
description: Läs mer om funktionen i NextHours
feature: Journeys
role: Developer
level: Experienced
exl-id: 4bcbfdbc-fc95-4089-8abc-f9314dde2c06
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%

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
