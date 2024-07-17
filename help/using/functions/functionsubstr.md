---
product: adobe campaign
title: substr
description: Läs mer om funktionssubstr
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: dda01de5-b865-4323-ac36-2e3d90d213ee
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 4%

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
