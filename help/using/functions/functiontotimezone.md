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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 939cde1f30a946ba4c20984dd72dcd1526d6e608

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
