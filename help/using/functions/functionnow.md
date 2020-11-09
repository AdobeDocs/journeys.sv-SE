---
title: nu
description: Läs om funktionen nu
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: bcb8a71a27e2b9e37af7d0260cec04ed0fda24ee
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 10%

---


# nu {#now}

Returnerar aktuellt datum i tidsformat för datum. For more information on data types, refer to [this page](../expression/data-types.md).

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