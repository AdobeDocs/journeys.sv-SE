---
title: setDays
description: Läs mer om funktionen setDays
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
source-wordcount: '74'
ht-degree: 1%

---


# setDays {#setDays}

Anger endast dag för datum och tid. Om du till exempel vill vänta till en viss dag i månaden kan du tvinga fram dagen.

## Kategori

Datum

## Funktionssyntax

`setDays(<parameter>)`

## Parametrar

| Parameter | Typ |
|--- |--- |
| tid | dateTime |
| datum tid utan att överväga tidszon | dateTimeOnly |
| dagar | heltal |

## Underskrifter och returtyp

`setDays(<dateTime>,<days>)`

Returnerar en datetime.

`setDays(<dateTimeOnly>,<days>)`

Returnerar en datetime utan att ta hänsyn till tidszon.

## Exempel

`setDays(toDateTime('2010-12-12T01:11:00Z'), 25)`

Returnerar 2010-12-25T01:11:00Z.

`setDays(toDateTimeOnly(@{MyEvent.registrationDate}), 1)`
