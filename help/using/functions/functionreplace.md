---
product: adobe campaign
solution: Journey Orchestration
title: ersätt
description: Läs mer om funktionsersättningen
feature: Resor
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '80'
ht-degree: 6%

---


# ersätt {#replace}

Ersätter den första förekomsten som matchar målsträngen med ersättningssträngen i bassträngen.

Ersättningen fortsätter från början av strängen till slutet, t.ex. om&quot;a&quot; ersätts med&quot;b&quot; i strängen&quot;aaa&quot; resulterar det i&quot;ba&quot; i stället för&quot;ab&quot;.

## Kategori

Sträng

## Funktionssyntax

`replace(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|--------------|
| bas | string |
| target | string |
| ersättare | string |

## Signatur och returtyp

`replace(<base>,<target>,<replacement>)`

Returnera en sträng.

## Exempel

`replace("Hello World", "l", "x")`

Returnerar &quot;Hexlo World&quot;.
