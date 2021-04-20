---
product: adobe campaign
solution: Journey Orchestration
title: toDecimal
description: Läs mer om funktionen toDecimal
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 8%

---


# toDecimal {#toDecimal}

Konverterar ett argumentvärde till ett decimalvärde, beroende på dess typ.

## Kategori

Konvertering

## Funktionssyntax

`toDecimal(<parameter>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string | konverterar strängvärdet som ett decimaltal |
| dateTime | konverterar datumet som antal millisekunder (epok millisekunder) |
| boolesk | konverterar det booleska värdet till 1 om true, 0 om false |
| heltal | konverterar till ett decimaltal (exempel.: 1 blir 1.0) |

## Underskrifter och returnerade typer

`toDecimal(<integer>)`

`toDecimal(<decimal>)`

`toDecimal(<string>)`

`toDecimal(<boolean>)`

Returnera ett decimaltal.

## Exempel

`toDecimal("4.0")`

Returnerar 4.0.
