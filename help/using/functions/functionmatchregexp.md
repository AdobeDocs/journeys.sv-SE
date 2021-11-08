---
product: adobe campaign
title: matchRegExp
description: Läs mer om funktionen matchRegExp
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 751fdcde-0af5-4f98-8cea-aae3ebefdb04
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 8%

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

`matchRegExp("Hello World", "Hello\s+World")`

Returnerar true.

Förklaring:

Här kontrollerar du om strängen uppfyller det reguljära uttrycket (java-syntax): börjar med &quot;Hello&quot;, sedan en valfri sträng och slutar med &quot;World&quot;.
