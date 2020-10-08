---
title: toInteger
description: Läs mer om funktionen toInteger
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '70'
ht-degree: 7%

---


# toInteger {#toInteger}

Konverterar ett argumentvärde till ett heltal.

## Kategori

Konvertering

## Funktionssyntax

`toInteger(<parameter>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string | konverterar strängvärdet som ett heltal |
| dateTime | konverterar datumet som antal millisekunder (epok millisekunder) |
| decimal | konverterar till heltal genom att ta bort decimaldelen (exempel: 1,5 blir 1) |
| boolesk | konverterar det booleska värdet till 1 om true, 0 om false |

## Underskrifter och returtyp

`toInteger(<dateTime>)`

`toInteger(<decimal>)`

`toInteger(<integer>)`

`toInteger(<string>)`

`toInteger(<boolean>)`

Returnera ett heltal.

## Exempel

`toInteger(4)`

Returnerar 4.
