---
title: toString
description: Läs mer om funktionen toString
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
source-git-commit: 239efa9592b011c70e2fc331df8f33820301253d

---


# toString {#toString}

Konverterar ett argumentvärde till ett strängvärde, beroende på dess typ. Mer information om datatyper finns i [](../expression/data-types.md).

## Kategori

Konvertering

## Funktionssyntax

`toString(<parameter>)`

## Parametrar

| Parameter | Beskrivning |
|--- |--- |
| dateTime | konverterar datumet i UTC-datumformat |
| dateTimeOnly | konverterar datumet i UTC-datumformat |
| varaktighet | konvertera till motsvarande antal millisekunder som en sträng |
| tidszon | konvertera till strängrepresentation av tidszon-id (JODA-id) |
| heltal | konverterar till strängbeteckning för värdet (1 blir &quot;1&quot;) |
| decimal | konverterar till strängbeteckning för värdet (1.5 blir &quot;1.5&quot;) |
| boolesk | konvertera det booleska värdet till true om true, false om false |

## Underskrifter och returtyp

`toString(<dateTimeOnly>)`

`toString(<dateTime>)`

`toString(<duration>)`

`toString(<timeZone>)`

`toString(<boolean>)`

`toString(<integer>)`

`toString(<decimal>)`

Returnera en sträng.

## Exempel

`toString(4)`

Returnerar &quot;4&quot;.
