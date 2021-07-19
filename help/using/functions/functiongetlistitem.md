---
product: adobe campaign
title: getListItem
description: Läs mer om funktionen gstListItem
feature: Resor
role: Data Engineer
level: Experienced
exl-id: a3b24f25-5f6d-44fe-b755-3734e4fab944
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 15%

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
| lista | listString |
| lista | listBoolean |
| lista | listInteger |
| lista | listDecimal |
| lista | listDuration |
| lista | listDateTime |
| lista | listDateTimeOnly |
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
