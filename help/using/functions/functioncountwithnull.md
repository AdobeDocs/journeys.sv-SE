---
product: adobe campaign
title: countWithNull
description: Läs mer om funktionen countWithNull
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ea72dc20-8183-4661-8e08-ddb4f3727d3d
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '50'
ht-degree: 8%

---

# countWithNull {#countWithNull}

Räknar alla element i listan inklusive null-värden.

## Kategori

Aggregering

## Funktionssyntax

`countWithNull(<listAny>)`

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

## Signatur och returtyp

`countWithNull(<listAny>)`

Returnerar ett heltal.

## Exempel

`countWithNull([10,2,10,null])`

Returnerar 4.
