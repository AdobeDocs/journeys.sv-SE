---
product: adobe campaign
title: matchRegExp
description: Läs mer om funktionen matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: a5d063784b278120b61f8d2641264baf40e34a90
workflow-type: tm+mt
source-wordcount: '60'
ht-degree: 11%

---

# matchRegExp {#matchRegExp}

Returnerar true om strängen i den första parametern matchar det reguljära uttrycket i den andra parametern. Mer information finns i [den här sidan](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

## Kategori

Sträng

## Funktionssyntax

`matchRegExp(<parameters>)`

## Parametrar

| Parameter | Typ |
|--- |--- |
| string | string |
| regexp | string |

## Signatur och returtyp

`matchRegExp(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`matchRegExp("username@adobe.com", "*adobe")`

Returnerar true.
