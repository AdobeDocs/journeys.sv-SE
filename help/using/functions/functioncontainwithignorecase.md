---
title: containWithIgnoreCase
description: Läs mer om funktionen containWithIgnoreCase
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
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
