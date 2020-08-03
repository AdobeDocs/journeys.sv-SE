---
title: sortera
description: Lär dig mer om funktionssortering
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 0%

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
