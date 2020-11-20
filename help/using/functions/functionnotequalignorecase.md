---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: Läs mer om funktionen notEqualWithIgnoreCase
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 10%

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
