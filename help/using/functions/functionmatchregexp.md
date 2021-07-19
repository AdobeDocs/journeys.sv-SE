---
product: adobe campaign
title: matchRegExp
description: Läs mer om funktionen matchRegExp
feature: Resor
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '86'
ht-degree: 9%

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
