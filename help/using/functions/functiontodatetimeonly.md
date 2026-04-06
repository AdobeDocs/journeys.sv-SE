---
product: adobe campaign
title: toDateTimeOnly
description: Läs mer om funktionen toDateTime
feature: Journeys
role: Developer
level: Experienced
exl-id: b19adbd0-8449-4bd4-bc4d-f1f305f87cb0
source-git-commit: 58514d6757f9705f5baa71cfbbe0bdfe65c8e16c
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 5%

---

# toDateTimeOnly{#toDateTimeOnly}

Konverterar ett argumentvärde till ett värde för endast datum och tid.

## Kategori

Konvertering

## Funktionssyntax

`toDateTimeOnly(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| datumtid i ISO-8601- eller &quot;YYY-MM-DD&quot;-format (XDM-datumformat) | string |
| tid | dateTime |

## Underskrifter och returnerade typer

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--
`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`
-->

Returnera en datetime utan att överväga tidszon.

## Exempel

`toDateTimeOnly ("2016-08-18")`

returnerar ett dateTime som representerar 2016-08-18T00:00:00.000

`toDateTimeOnly(now())`

<!--
`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.
-->
