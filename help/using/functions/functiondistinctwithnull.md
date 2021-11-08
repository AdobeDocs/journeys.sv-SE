---
product: adobe campaign
title: distinctWithNull
description: Lär dig mer om funktionen distinktMedNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 65a904c1-14ff-42b3-8f03-abb97ef47625
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '106'
ht-degree: 14%

---

# clearWithNull {#distinctWithNull}

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
| Lista | listDateOnly |

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

`distinctWithNull(<listDateOnly>)`

Returnerar en lista med datum.

`distinctWithNull(<listBoolean>)`

Returnerar en lista med boolesk.

`distinctWithNull(<listDuration>)`

Returnerar en lista med varaktigheter.

## Exempel

`distinctWithNull([10,2,10,null])`

Returnerar [10, 2, null]
