---
product: adobe campaign
title: notEqualIgnoreCase
description: Läs mer om funktionen notEqualIgnoreCase
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '37'
ht-degree: 2%

---

# notEqualIgnoreCase {#notEqualIgnoreCase}

Kontrollera om den första argumentsträngen med den andra argumentsträngen är annorlunda och ignorerar skiftlägeskänslighet.

## Kategori

Sträng

## Funktionssyntax

`notEqualIgnoreCase(<parameters>)`

## Parametrar

* string

## Signatur och returtyp

`notEqualIgnoreCase(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`notEqualIgnoreCase(@{iOSPushPermissionAllowed.device.model}, "iPad")`
