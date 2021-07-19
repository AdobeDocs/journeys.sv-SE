---
product: adobe campaign
title: notEqualWithIgnoreCase
description: Läs mer om funktionen notEqualWithIgnoreCase
feature: Resor
role: Data Engineer
level: Experienced
exl-id: d99601cf-2ba8-4150-afa7-df6b8af47bf6
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '38'
ht-degree: 18%

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
