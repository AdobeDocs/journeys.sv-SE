---
product: adobe campaign
title: distinctCount
description: Lär dig mer om funktionen distinktCount
feature: Journeys
role: Developer
level: Experienced
exl-id: b7844bce-1286-4d9e-b9e6-619c2d467c91
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 8%

---

# distinctCount{#distinctCount}

Räknar antalet olika värden som ignorerar null-värden.

## Kategori

Aggregering

## Funktionssyntax

`distinctCount(<listAny>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |
| Lista | listDateOnly |

## Signatur och returtyp

`distinctCount(<listAny>)`

Returnerar ett heltal.

## Exempel

`distinctCount([10,2,10,null])`

Returnerar 2.
