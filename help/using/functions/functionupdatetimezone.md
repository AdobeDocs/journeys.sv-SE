---
product: adobe campaign
title: updateTimeZone
description: Läs mer om funktionen updateTimeZone
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 9%

---


# updateTimeZone {#updateTimeZone}

Returnerar en ny datumtid, med en ny tidszon på samma gång.

## Kategori

Datum

## Funktionssyntax

`updateTimeZone(<parameters>)`

## Parametrar

* tidszon-ID: string
* dateTime

## Signatur och returtyp

`updateTimeZone(<dateTime>,<timeZone id>)`

Returnerar en datetime.

## Exempel

`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), "Europe/Paris"))`

Returnerar 2019-08-28T17:15:30.123+02:00.

<!--`updateTimeZone( toDateTime("2019-08-28T08:15:30.123-07:00"), toTimeZone("Europe/Paris")))`

Returns "2019-08-28T17:15:30.123+02:00".-->
