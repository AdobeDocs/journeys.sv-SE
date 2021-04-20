---
product: adobe campaign
solution: Journey Orchestration
title: inSegment
description: Läs mer om funktionen inSegment
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: a99ad6a589bcd1f3083eabbcac35dd5c0497093d
workflow-type: tm+mt
source-wordcount: '153'
ht-degree: 5%

---


# inSegment {#inSegment}

Kontrollerar om en individ tillhör ett visst segment.

>[!NOTE]
>
>Du kan hämta upp till 100 segment.

Segmentnamnet måste vara en strängkonstant. Det kan inte vara en fältreferens eller ett uttryck.

Segment definieras i [Adobe Experience Platform](https://platform.adobe.com/segment/overview). Uttrycksredigeraren innehåller en lista över segment som fylls i automatiskt.

>[!NOTE]
>
>Endast individer med segmentdeltagarstatus **Realiserad** och **Befintlig** betraktas som medlemmar i segmentet. Mer information om hur du utvärderar ett segment finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

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
