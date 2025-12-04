---
product: adobe campaign
title: toDateOnly
description: Läs mer om funktionen toDateOnly
feature: Journeys
role: Developer
level: Experienced
exl-id: 2d7b132e-5ee0-4fa0-bacc-ce4c6ec7e794
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 9%

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
