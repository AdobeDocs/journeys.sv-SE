---
title: toTimeZone
description: Läs mer om funktionen toTimeZone
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
source-wordcount: '51'
ht-degree: 5%

---


# toTimeZone {#toTimeZone}

Konverterar ett strängvärde till en tidszon.

## Kategori

Konvertering

## Funktionssyntax

`toTimeZone(<parameter>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| string | Strängvärdet måste innehålla zon-ID:t. Det kan vara en fältreferens eller ett uttryck |

## Underskrifter och returnerade typer

`toTimeZone(<string>)`

Returnerar en tidszon.

## Exempel

`toTimeZone("UTC")`

Returnerar UTC.
