---
product: adobe campaign
solution: Journey Orchestration
title: notEqualWithIgnoreCase
description: Läs mer om funktionen notEqualWithIgnoreCase
feature: Resor
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '41'
ht-degree: 12%

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
