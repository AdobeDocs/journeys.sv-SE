---
product: adobe campaign
title: inNextMonths
description: Läs mer om funktionen i NextMonths
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b5e8d514-a24d-42a2-b422-ec5d6617048a
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 11%

---

# inNextMonths {#inNextMonths}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-månader.

## Kategori

Datum

## Funktionssyntax

`inNextMonths(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inNextMonths(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4)`

Returnerar true.
