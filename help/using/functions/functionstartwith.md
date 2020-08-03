---
title: startWith
description: Läs mer om funktionen startWith
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608
workflow-type: tm+mt
source-wordcount: '43'
ht-degree: 0%

---


# startWith {#startWith}

Returnerar true om den andra parametern är ett prefix till den första.

## Kategori

Sträng

## Funktionssyntax

`startWith(<parameters>)`

## Parametrar

| Parameter | Typ |
|-------------|--------|
| string | string |
| prefix | string |

## Signatur och returtyp

`startWith(<string>,<string>)`

Returnera ett booleskt värde.

## Exempel

`startWith("Hello World", "Hello")`

Returnerar true.

`startWith("Hello World", "World")`

Returnerar false.
