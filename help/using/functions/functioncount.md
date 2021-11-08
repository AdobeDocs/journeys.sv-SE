---
product: adobe campaign
title: count
description: Läs mer om antalet funktioner
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 46528642-18d5-4ca9-a344-de2c7f939d00
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '52'
ht-degree: 28%

---

# antal {#count}

Räknar elementen i listan utan att ta hänsyn till null-värden.

## Kategori

Aggregera

## Funktionssyntax

`count(<listAny>)`

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

## Underskrifter och returtyp

`count(<listAny>)`

Returnerar ett heltal.

## Exempel

`count([10,2,10,null])`

Returnerar 3.
