---
product: adobe campaign
title: serializeList
description: Läs mer om funktionen serializeList
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 84912d38-32ee-4cfe-8cb4-bad12f9c52af
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '88'
ht-degree: 19%

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
| Lista | listDateOnly |

## Signatur och returtyp

`serializeList(<listInteger>,<string>,<boolean>)`

`serializeList(<listDecimal>,<string>,<boolean>)`

`serializeList(<listString>,<string>,<boolean>)`

`serializeList(<listBoolean>,<string>,<boolean>)`

`serializeList(<listDateTimeOnly>,<string>,<boolean>)`

`serializeList(<listDateTime>,<string>,<boolean>)`

`serializeList(<listDateOnly>,<string>,<boolean>)`

`serializeList(<listDuration>,<string>,<boolean>)`

`serializeList(<listPoint>,<string>,<boolean>)`

Returnera en sträng.

## Exempel

`serializeList(["Hello","World"], " ", false)`

Returnerar &quot;Hello World&quot;.

`serializeList(["Hello", "World"], ",", true)`

Returnerar &quot;&quot;Hello&quot;,&quot;World&quot;&quot;.
