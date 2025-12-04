---
product: adobe campaign
title: now
description: Läs om funktionen nu
feature: Journeys
role: Developer
level: Experienced
exl-id: ab1f9efe-cbb7-4e3a-ace0-24f2fb6165cb
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 9%

---

# now {#now}

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

Returnerar 2019-06-03T08 :30+02:00.
