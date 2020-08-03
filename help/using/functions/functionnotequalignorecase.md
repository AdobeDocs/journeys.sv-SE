---
title: notEqualWithIgnoreCase
description: Läs mer om funktionen notEqualWithIgnoreCase
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
source-wordcount: '37'
ht-degree: 0%

---


# notEqualWithIgnoreCase {#notEqualWithIgnoreCase}

Kontrollera om den första argumentsträngen med den andra argumentsträngen är annorlunda och ignorerar skiftlägeskänslighet.

## Kategori

Sträng

## Funktionssyntax

`notEqualWithIgnoreCase(<parameters>)`

## Parametrar

* string

## Signatur och returtyp

`notEqualWithIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`notEqualWithIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad"))`
