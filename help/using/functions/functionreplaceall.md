---
product: adobe campaign
title: replaceAll
description: Läs om funktionen replaceAll
feature: Resor
role: Data Engineer
level: Experienced
exl-id: d60059e5-6bf8-4a57-88a4-5323d5f0fa0b
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '76'
ht-degree: 10%

---

# replaceAll {#replaceAll}

Ersätter alla förekomster som matchar målsträngen med ersättningssträngen i bassträngen.

Ersättningen fortsätter från början av strängen till slutet, t.ex. om&quot;a&quot; ersätts med&quot;b&quot; i strängen&quot;aaa&quot; resulterar det i&quot;ba&quot; i stället för&quot;ab&quot;.

## Kategori

Sträng

## Funktionssyntax

`replaceAll(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|--------------|
| bas | string |
| target | string |
| ersättare | string |

## Signatur och returtyp

`replaceAll(<baseString>,<sourceString>,<replacementString>)`

Returnerar en sträng.

## Exempel

`replaceAll("Hello World", "l", "x")`

Returnerar &quot;Hexo Worxd&quot;.
