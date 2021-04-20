---
product: adobe campaign
solution: Journey Orchestration
title: slumpmässig
description: Lär dig mer om funktionen slumpmässigt
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '55'
ht-degree: 5%

---


# slumpmässig {#random}

Genererar ett slumpmässigt tal mellan 0 och 1.

## Kategori

Maths

## Funktionssyntax

`random(<parameters>)`

## Signatur och returtyp

`random()`

Returnerar ett decimaltal.

## Exempel

`#{MarltonReservation.statistics.successRatio, defaultValue : random() * 100}`

Förklaring: Om resultatkvoten inte har något värde/är null används standardvärdet och blir en slumpmässig siffra mellan 0 och 1 * 100 (vilket innebär 0 till 100).
