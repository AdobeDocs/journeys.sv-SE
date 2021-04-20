---
product: adobe campaign
solution: Journey Orchestration
title: substr
description: Läs mer om funktionssubstr
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '68'
ht-degree: 7%

---


# substr {#substr}

Returnerar delsträngen för stränguttrycket mellan startindexvärdet och slutindexvärdet. Om slutindexvärdet inte är definierat ligger det mellan startindexet och slutet.

## Kategori

Sträng

## Funktionssyntax

`substr(<parameters>)`

## Parametrar

| Parameter | type |
|-------------|----------|
| string | string |
| beginIndex | heltal |
| endIndex | heltal |

## Signatur och returtyp

`substr(<string>,<beginIndex>)`

`substr(<string>,<beginIndex>,<endIndex>)`

Returnera en sträng.

## Exempel

`substr("Hello World",6)`

Returnerar &quot;World&quot;.

`substr("Hello World", 0, 5)`

Returnerar &quot;Hello&quot;.