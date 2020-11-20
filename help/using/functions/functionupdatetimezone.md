---
product: adobe campaign
solution: Journey Orchestration
title: updateTimeZone
description: Läs mer om funktionen updateTimeZone
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 4%

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
