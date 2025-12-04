---
product: adobe campaign
title: startWithIgnoreCase
description: Läs mer om funktionen startWithIgnoreCase
feature: Journeys
role: Developer
level: Experienced
exl-id: 0ef098d8-b56c-4509-bbbd-2688ecc547bf
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '44'
ht-degree: 9%

---

# startWithIgnoreCase {#startWithIgnoreCase}

Returnerar true om den andra parametern är ett prefix till den första utan att ta hänsyn till skiftläge.

## Kategori

Sträng

## Funktionssyntax

`startWithIgnoreCase(<parameters>)`

## Parametrar

| Parameter | Typ |
|-------------|--------|
| string | string |
| prefix | string |

## Signatur och returtyp

`startWithIgnoreCase(<string>,<string>)`

Returnera ett booleskt värde.

## Exempel

`startWithIgnoreCase("rowing is great", "RO")`

Returnerar true.
