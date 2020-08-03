---
title: endWithIgnoreCase
description: Läs mer om funktionen endWithIgnoreCase
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: a844adc1a073aebfb7fd8a719e52f305079260b7
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 0%

---


# endWithIgnoreCase {#endWithIgnoreCase}

Kontrollerar om den första argumentsträngen slutar med en viss sträng (den andra argumentsträngen), utan att ta hänsyn till skiftläget.

## Kategori

Sträng

## Funktionssyntax

`endWithIgnoreCase(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| string | string |
| suffix | string |

## Signatur och returtyp

`endWithIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`endWithIgnoreCase("rowing is great', "AT")`

Returnerar true.
