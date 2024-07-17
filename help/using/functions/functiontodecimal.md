---
product: adobe campaign
title: toDecimal
description: Läs mer om funktionen toDecimal
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 11d7013c-2190-4654-8466-920861c836f5
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 6%

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
