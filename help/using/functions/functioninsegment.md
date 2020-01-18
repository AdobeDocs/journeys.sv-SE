---
title: inSegment
description: Läs mer om funktionen inSegment
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
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa

---


# inSegment {#inSegment}

Kontrollerar om en individ tillhör ett visst segment.

Segmentnamnet måste vara en strängkonstant. Det kan inte vara en fältreferens eller ett uttryck.

Segment definieras i [Adobe Experience Platform](https://platform.adobe.com/segment/overview). Uttrycksredigeraren innehåller en lista över segment som fylls i automatiskt.

>[!NOTE]
>
>Du kan hämta upp till 100 segment.

## Kategori

Adobe Experience Platform

## Funktionssyntax

`inSegment(<parameter>)`

## Parametrar

| Parameter | Beskrivning | Typ |
|--- |--- |--- |
| Segment | Segmentnamnet | `<string>` |

## Signatur och returtyp

`inSegment(<string>)`

Returnerar ett booleskt värde.

## Exempel

`inSegment("men over 50")`

Förklaring:

Funktionen returneras **[!UICONTROL true]**om personen i reseinstansen är en del av plattformssegmentet med namnet&quot;män över 50&quot;,**[!UICONTROL false]** annars returneras .
