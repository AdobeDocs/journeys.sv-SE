---
product: adobe campaign
title: random
description: Lär dig mer om funktionen slumpmässigt
feature: Resor
role: Data Engineer
level: Experienced
exl-id: c47dc5f0-ea69-4814-863b-e0e483ba7770
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 7%

---

# random {#random}

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
