---
product: adobe campaign
solution: Journey Orchestration
title: countOnlyNull
description: Läs mer om funktionen countOnlyNull
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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
