---
product: adobe campaign
solution: Journey Orchestration
title: slumpmässig
description: Lär dig mer om funktionen slumpmässigt
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '51'
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
