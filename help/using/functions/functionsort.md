---
product: adobe campaign
title: sort
description: Lär dig mer om funktionssortering
feature: Resor
role: Data Engineer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 14%

---

# sortera {#sort}

Sorterar en lista med värden i den naturliga ordningen. Det första argumentet är listan med värden, det andra är ett booleskt värde som anger om sorteringen är stigande (true) eller fallande (false).

## Kategori

Lista

## Funktionssyntax

`sort(<parameters>)`

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
| Boolean | Boolean |

## Signatur och returtyp

`sort(<listInteger>,<boolean>)`

Returnerar en lista med heltal.

`sort(<listDecimal>,<boolean>)`

Returnerar en lista med decimaler.

`sort(<listString>,<boolean>)`

Returnerar en lista med strängar.

`sort(<listDateTimeOnly>,<boolean>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`sort(<listDateTime>,<boolean>)`

Returnerar en lista med datetimes.

`sort(<listBoolean>,<boolean>)`

Returnerar en lista med boolesk.

## Exempel

`sort(["A", "C", "B"], true)`

Returnerar `["A","B","C"]`.

`sort([1, 3, 2], false)`

Returnerar `[3, 2, 1]`.
