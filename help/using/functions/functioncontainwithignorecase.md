---
product: adobe campaign
solution: Journey Orchestration
title: containWithIgnoreCase
description: Läs mer om funktionen containWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '48'
ht-degree: 8%

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
