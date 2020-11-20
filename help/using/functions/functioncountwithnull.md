---
product: adobe campaign
solution: Journey Orchestration
title: countWithNull
description: Läs mer om funktionen countWithNull
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '47'
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
