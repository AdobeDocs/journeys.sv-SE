---
product: adobe campaign
title: containIgnoreCase
description: Läs mer om funktionen containIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 8%

---

# containIgnoreCase {#containIgnoreCase}

Kontrollerar om den andra argumentsträngen finns i den första argumentsträngen, utan att ta hänsyn till skiftläget.

## Kategori

Sträng

## Funktionssyntax

`containIgnoreCase(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| string | string |
| sträng genomsöktes | string |

## Signatur och returtyp

`containIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`containIgnoreCase("rowing is great", "GREAT")`

Returnerar true.
