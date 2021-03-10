---
product: adobe campaign
solution: Journey Orchestration
title: serializeList
description: Läs mer om funktionen serializeList
feature: Resor
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '90'
ht-degree: 15%

---


# serializeList {#serializeList}

Konverterar listan (valfri typ) som ges i den första parametern till en sträng. Den andra parametern representerar den avgränsare som ska användas. Den tredje parametern är ett booleskt värde som anger om varje element i uttrycket ska innehålla citattecken.

## Kategori

Lista

## Funktionssyntax

`serializeList(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| Sträng | Sträng |
| Boolean | Boolean |
| DateTimeOnly | DateTimeOnly |
| Lista | listString |
| Lista | listBoolean |
| Lista | listPoint |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |

## Signatur och returtyp

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

Returnera en sträng.

## Exempel

`serializeList(["Hello","World"], " ", false)`

Returnerar &quot;Hello World&quot;.

`serializeList(["Hello", "World"], ",", true)`

Returnerar &quot;&quot;Hello&quot;,&quot;World&quot;&quot;.
