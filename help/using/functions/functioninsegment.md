---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Läs mer om funktionen inSegment
feature: Resor
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '110'
ht-degree: 7%

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

Funktionen returnerar **[!UICONTROL true]** om personen i reseinstansen är en del av Adobe Experience Platform-segmentet med namnet &quot;men över 50&quot;, annars **[!UICONTROL false]**.
