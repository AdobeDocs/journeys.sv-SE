---
product: adobe campaign
solution: Journey Orchestration
title: distinctCountWithNull
description: Lär dig mer om funktionen distinktCountWithNull
feature: Resor
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 23%

---


# distinctCountWithNull {#distinctCountWithNull}

Räknar antalet olika värden inklusive null-värden.

## Kategori

Aggregera

## Funktionssyntax

`distinctCountWithNull(<listAny>)`

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

## Signatur och returtyp

`distinctCountwithNull(<listAny>)`

Returnerar ett heltal.

## Exempel

`distinctCountWithNull([10,2,10,null])`

Returnerar 3.
