---
product: adobe campaign
title: toDateTimeOnly
description: Läs mer om funktionen toDateTime
feature: Resor
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 12%

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
| datum och tid i ISO-8601-format | string |
| tid | dateTime |

## Underskrifter och returnerade typer

`toDateTimeOnly(<dateTime>)`

`toDateTimeOnly(<string>)`
<!--`toDateTimeOnly(<integer>,<integer>,<integer>)`
`toDateTimeOnly(<integer>,<integer>,<integer>,<integer>,<integer>,<integer>)`-->

Returnera en datetime utan att överväga tidszon.

## Exempel

`toDateTimeOnly ("2016-08-18T23:17:59.123Z")`

Returnerar 2016-08-18T23:17:59.123.

`toDateTimeOnly(now())`

<!--`toDateTimeOnly(2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000.

`toDateTimeOnly(2016,8,18)`

Returns 2016-08-18T00:00:00.000.-->
