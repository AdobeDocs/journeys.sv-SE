---
product: adobe campaign
solution: Journey Orchestration
title: matchRegExp
description: Läs mer om funktionen matchRegExp
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '85'
ht-degree: 4%

---


# matchRegExp {#matchRegExp}

Returnerar true om strängen i den första parametern matchar det reguljära uttrycket i den andra parametern. Mer information finns på [den här sidan](https://docs.oracle.com/javase/7/docs/api/java/util/regex/Pattern.html).

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
