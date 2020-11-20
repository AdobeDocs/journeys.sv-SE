---
product: adobe campaign
solution: Journey Orchestration
title: toTimeZone
description: Läs mer om funktionen toTimeZone
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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
