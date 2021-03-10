---
product: adobe campaign
solution: Journey Orchestration
title: nu
description: Läs om funktionen nu
feature: Resor
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '53'
ht-degree: 11%

---


# nu {#now}

Returnerar aktuellt datum i tidsformat för datum. Mer information om datatyper finns på [den här sidan](../expression/data-types.md).

## Kategori

Datum

## Funktionssyntax

`now(<parameter>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string |  |

## Underskrifter och returtyp

`now()`

`now("<timeZone id>")`

Returnerar ett dateTime.

## Exempel

`now()`

Returnerar 2019-06-03T06:30Z.

`toString(now())`

Returnerar &quot;2019-06-03T06:30Z&quot;

`now("Europe/Paris")`

Returnerar 2019-06-03T08:30+02:00.