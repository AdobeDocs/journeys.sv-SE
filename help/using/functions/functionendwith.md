---
product: adobe campaign
solution: Journey Orchestration
title: endWith
description: Läs mer om funktionen endWith
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 9%

---


# endWith {#endWith}

Returnerar true om den andra parametern är ett suffix till den första.

## Kategori

Sträng

## Funktionssyntax

`endWith(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| string | string |
| suffix | string |

## Signatur och returtyp

`endWith(<string>,<string>)`

Returnerar ett booleskt värde.

## Exempel

`endWith("Hello World", "World")`

Returnerar true.

`endWith("Hello World", "Hello")`

Returnerar false.
