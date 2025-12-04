---
product: adobe campaign
title: sort
description: Lär dig mer om funktionssortering
feature: Journeys
role: Developer
level: Experienced
exl-id: 8e86b919-41f5-45f9-a6af-9fe290405095
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '131'
ht-degree: 3%

---

# sort {#sort}

Sorterar en lista med värden eller objekt i den naturliga ordningen.

## Kategori

Lista

## Funktionssyntax

`sort(<parameters>)`

## Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToSort | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista att sortera ut. För listObject måste det vara en fältreferens. |
| keyAttributeName | string | Den här parametern är bara för listObject. Attributnamnet i objekten i den angivna listan används som nyckel för sorteringen. |
| sortingOrder | boolesk | Stigande (true) eller fallande (false) |

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

`sort(<listDateOnly>,<boolean>)`

Returnerar en lista med datum.

`sort(<listBoolean>,<boolean>)`

Returnerar en lista med boolesk.

`sort(<listObject>,<string>,<boolean>)`

Returnerar en lista med objekt.

## Exempel

`sort(["A", "C", "B"], true)`

Returnerar `["A","B","C"]`.

`sort([1, 3, 2], false)`

Returnerar `[3, 2, 1]`.

