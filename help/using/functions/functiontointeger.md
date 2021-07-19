---
product: adobe campaign
title: toInteger
description: Läs mer om funktionen toInteger
feature: Resor
role: Data Engineer
level: Experienced
exl-id: 3fcbf4dd-3ca5-4f4b-b774-af6ac3170768
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '71'
ht-degree: 11%

---

# toInteger {#toInteger}

Konverterar ett argumentvärde till ett heltal.

## Kategori

Konvertering

## Funktionssyntax

`toInteger(<parameter>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string | konverterar strängvärdet som ett heltal |
| dateTime | konverterar datumet som antal millisekunder (epok millisekunder) |
| decimal | konverterar till heltal genom att ta bort decimaldelen (exempel: 1,5 blir 1) |
| boolesk | konverterar det booleska värdet till 1 om true, 0 om false |

## Underskrifter och returtyp

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Returnera ett heltal.

## Exempel

`toInteger("4")`

Returnerar 4.
