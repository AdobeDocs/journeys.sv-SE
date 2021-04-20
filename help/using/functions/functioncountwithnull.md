---
product: adobe campaign
solution: Journey Orchestration
title: countWithNull
description: Läs mer om funktionen countWithNull
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '51'
ht-degree: 23%

---


# countWithNull {#countWithNull}

Räknar alla element i listan inklusive null-värden.

## Kategori

Aggregera

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

## Signatur och returtyp

`countWithNull(<listAny>)`

Returnerar ett heltal.

## Exempel

`count([10,2,10,null])`

Returnerar 4.
