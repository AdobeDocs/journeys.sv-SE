---
product: adobe campaign
solution: Journey Orchestration
title: antal
description: Läs mer om antalet funktioner
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '54'
ht-degree: 22%

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

## Underskrifter och returtyp

`count(<listAny>)`

Returnerar ett heltal.

## Exempel

`count([10,2,10,null])`

Returnerar 3.
