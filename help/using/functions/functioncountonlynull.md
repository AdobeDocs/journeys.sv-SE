---
title: countOnlyNull
description: Läs mer om funktionen countOnlyNull
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
source-wordcount: '46'
ht-degree: 23%

---


# countOnlyNull {#countOnlyNull}

Räknar antalet null-värden i listan.

## Kategori

Aggregera

## Funktionssyntax

`countOnlyNull(<listAny>)`

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

`countOnlyNull(<listAny>)`

Returnerar ett heltal.

## Exempel

`count([10,2,10,null])`

Returnerar 1.
