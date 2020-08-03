---
title: setHours
description: Läs mer om funktionen setHours
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 0%

---


# setHours {#setHours}

Anger endast timmar för datum och tid. Om du till exempel vill vänta en viss timme i morgon kan du tvinga timmen.

## Kategori

Datum

## Funktionssyntax

`setHours(<parameter>)`

## Parametrar

| Parameter | Typ |
|--- |--- |
| tid | dateTime |
| datum tid utan att överväga tidszon | dateTimeOnly |
| timmar | heltal |

## Underskrifter och returtyp

`setHours(<dateTime>,<hours>)`

Returnerar en datetime.

`setHours(<dateTimeOnly>,<hours>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

## Exempel

`setHours(toDateTime('2010-12-12T01:11:00Z'), 4))`

Returnerar 2010-12-12T04:11:00Z.

`setHours(nowWithDelta(1, "days"), 20)`

Returnerar imorgon klockan åtta.
