---
product: adobe campaign
solution: Journey Orchestration
title: dela
description: Lär dig mer om funktionsdelningen
translation-type: tm+mt
source-git-commit: 135485c097f99483c2ddb3d03e0552f9ac134b44
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 4%

---


# dela {#split}

Delar den första argumentsträngen med en avgränsningssträng (den andra argumentsträngen, som kan vara ett reguljärt uttryck) för att skapa en lista med strängar (tokens).

## Kategori

Sträng

## Funktionssyntax

`split(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| indatasträng | string |
| avgränsarsträng | string |

## Underskrifter och returtyp

`split(<input string>, <separator string>)`

Returnerar en listString.

## Exempel

`split(["A_B_C"], "_")`

Returnerar `["A","B","C"]`

Exempel med ett händelsefält &#39;event.appVersion&#39; med värdet: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Returnerar `["20", "45", "2", "3434"]`
