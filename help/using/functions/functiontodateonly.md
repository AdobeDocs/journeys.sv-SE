---
product: adobe campaign
title: toDateOnly
description: Läs mer om funktionen toDateOnly
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: a9a129b1949d64c4a412d3ea4002b32e3563ea96
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# toDateOnly{#toDateOnly}

Konverterar ett argumentvärde till ett värde för endast datum.

## Kategori

Konvertering

## Funktionssyntax

`toDateOnly(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| datum i ISO-8601- eller &quot;YYY-MM-DD&quot;-format (XDM-datumformat) | string |
| datum | datum |

## Underskrifter och returnerade typer

`toDateOnly(<date>)`

`toDateOnly(<string>)`

Returnera en datetime utan att överväga tidszon.

## Exempel

`toDateOnly("2016-08-18")`

returnerar ett dateOnly-objekt som representerar 2016-08-18.
