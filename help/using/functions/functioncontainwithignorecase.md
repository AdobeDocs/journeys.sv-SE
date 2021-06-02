---
product: adobe campaign
title: containWithIgnoreCase
description: Läs mer om funktionen containWithIgnoreCase
feature: Resor
role: Data Engineer
level: Experienced
exl-id: ebec646e-9dbb-4432-a430-ab69fb7d75cf
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '49'
ht-degree: 12%

---

# containWithIgnoreCase {#containWithIgnoreCase}

Kontrollerar om den andra argumentsträngen finns i den första argumentsträngen, utan att ta hänsyn till skiftläget.

## Kategori

Sträng

## Funktionssyntax

`containWithIgnoreCase(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| string | string |
| sträng genomsöktes | string |

## Signatur och returtyp

`containWithIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`containWithIgnoreCase("rowing is great', "GREAT")`

Returnerar true.
