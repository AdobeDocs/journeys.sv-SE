---
title: random
description: Lär dig mer om funktionen slumpmässigt
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 1%

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
