---
title: updateTimeZone
description: Läs mer om funktionen updateTimeZone
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
source-wordcount: '41'
ht-degree: 2%

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
