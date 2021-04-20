---
product: adobe campaign
solution: Journey Orchestration
title: getListItem
description: Läs mer om funktionen gstListItem
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '101'
ht-degree: 4%

---


# getListItem {#gestListItem}

Returnerar objektet i listan vid det angivna indexvärdet.

## Kategori

Lista

## Funktionssyntax

`getListItem(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| list | listString |
| list | listBoolean |
| list | listInteger |
| list | listDecimal |
| list | listDuration |
| list | listDateTime |
| list | listDateTimeOnly |
| index | heltal |

## Underskrifter och returtyp

`getListItem(<listInteger>,<index>)`

Returnerar en lista med heltal.

`getListItem(<listDecimal>,<index>)`

Returnerar en lista med decimaler.

`getListItem(<listString>,<index>)`

Returnerar en lista med strängar.

`getListItem(<listDateTimeOnly>,<index>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`getListItem(<listDateTime>,<index>)`

Returnerar en lista med datetimes.

`getListItem(<listBoolean>,<index>)`

Returnerar en lista med boolesk.

`getListItem(<listDuration>,<index>)`

Returnerar en lista med varaktigheter.

## Exempel

`getListItem([10, 2, 3], 1)`

Returnerar &quot;2&quot;

`getListItem(["A", "B", "C"], 3)`
Returnerar &quot;C&quot;

Exempel med ett händelsefält &#39;event.appVersion&#39; med värdet: &quot;20.45.2.3434&quot;

`split(@{event.appVersion}, "\\.")`

Returnerar `["20", "45", "2", "3434"]`

`getListItem(split(@{event.appVersion}, "\\."), 0)`

Returnerar &quot;20&quot;