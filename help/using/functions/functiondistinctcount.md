---
title: distinctCount
description: Lär dig mer om funktionen distinktCount
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
source-wordcount: '47'
ht-degree: 23%

---


# distinctCount{#distinctCount}

Räknar antalet olika värden som ignorerar null-värden.

## Kategori

Aggregera

## Funktionssyntax

`distinctCount(<listAny>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |

## Signatur och returtyp

`distinctCount(<listAny>)`

Returnerar ett heltal.

## Exempel

`distinctCount([10,2,10,null])`

Returnerar 2.
