---
title: inNextMonths
description: Läs om funktionen i NextMonths
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
source-wordcount: '44'
ht-degree: 9%

---


# inNextMonths {#inNextMonths}

Returnerar true om ett givet datum eller dateTime är mellan nu och nu + delta-månader.

## Kategori

Datum

## Funktionssyntax

`inNextMonths(<dateTime>,<delta>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| tid | dateTime |
| delta | heltal |

## Underskrifter och returtyp

`inNextMonths(<dateTime>,<integer>)`

Returnerar ett booleskt värde.

## Exempel

`inNextMonths(toDateTime('2020-01-12T01:11:00Z'), 4))`

Returnerar true.
