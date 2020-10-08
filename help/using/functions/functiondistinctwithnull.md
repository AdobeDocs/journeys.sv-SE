---
title: distinctWithNull
description: Lär dig mer om funktionen distinktMedNull
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
source-wordcount: '99'
ht-degree: 11%

---


# distinctWithNull {#distinctWithNull}

Returnerar de distinkta värdena i listan. Om listan har minst ett null-värde kommer ett null-värde att finnas i den returnerade listan.

## Kategori

Lista

## Funktionssyntax

`distinctWithNull(<parameter>)`

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

## Underskrifter och returnerade typer

`distinctWithNull(<listInteger>)`

Returnerar en lista med heltal.

`distinctWithNull(<listDecimal>)`

Returnerar en lista med decimaler.

`distinctWithNull(<listString>)`

Returnerar en lista med strängar.

`distinctWithNull(<listDateTimeOnly>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`distinctWithNull(<listDateTime>)`

Returnerar en lista med datetimes.

`distinctWithNull(<listBoolean>)`

Returnerar en lista med boolesk.

`distinctWithNull(<listDuration>)`

Returnerar en lista med varaktigheter.

## Exempel

`distinctWithNull([10,2,10,null])`

Returnerar [10, 2, null]
