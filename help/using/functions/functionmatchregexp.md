---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: Läs mer om funktionen matchRegExp
feature: Resor
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '89'
ht-degree: 5%

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

Returnerar ett sant värde.

## Exempel

`matchRegExp("Hello World", "Hello\s+World")`

Returnerar true.

Förklaring:

Här kontrollerar du om strängen uppfyller det reguljära uttrycket (java-syntax): börjar med &quot;Hello&quot;, sedan en valfri sträng och slutar med &quot;World&quot;.
