---
product: adobe campaign
title: inLastHours
description: Läs om funktionen iLastHours
feature: Resor
role: Data Engineer
level: Experienced
exl-id: 9baeb836-e029-4e19-b08e-7b7b5f27ff8f
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '46'
ht-degree: 13%

---

# inLastHours {#inLastHours}

Returnerar true om den angivna datumtiden är mellan nu och nu - deltatimmar.

## Kategori

Datum

## Funktionssyntax

`inLastHours(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inLastHours(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inLastHours(toDateTime('2019-12-12T01:11:00Z'), 4))`

Returnerar true.

`inLastHours(@{MyEvent.timestamp}, 4)`

Returnerar true.
