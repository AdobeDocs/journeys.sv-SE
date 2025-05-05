---
product: adobe campaign
title: inSegment
description: Läs mer om funktionen inSegment
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 7f756ec5-d787-4024-aaf8-5b4f1d4ddece
source-git-commit: e56e6f5dcb8a4680851858355ac18a70bd832b73
workflow-type: tm+mt
source-wordcount: '185'
ht-degree: 4%

---

# inSegment {#inSegment}

Kontrollerar om en individ tillhör ett visst segment.

>[!NOTE]
>
>Du kan hämta upp till 100 segment.

Segmentnamnet måste vara en strängkonstant. Det kan inte vara en fältreferens eller ett uttryck.

Segment definieras i [Adobe Experience Platform](https://platform.adobe.com/segment/overview). Uttrycksredigeraren innehåller en lista över segment som fylls i automatiskt.

Segment kan ha tre statusar:

* existing: entiteten fortsätter att vara i segmentet.
* realiserad: företaget går in i segmentet.
* avslutad: entiteten avslutar segmentet.

Endast personer med segmentdeltagarstatus **Realiserad** och **Befintlig** betraktas som medlemmar i segmentet. Mer information om hur du utvärderar ett segment finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=sv-SE#interpret-segment-results).

`IF inSegment('segmentName') == true` betyder att du har ett segmentMembership med den angivna/befintliga statusen.

`ELSE inSegment('segmentName') == false` betyder att du har ett segmentMembership med statusen avslutad.

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

Funktionen returnerar **[!UICONTROL true]** om personen i reseinstansen är en del av Adobe Experience Platform-segmentet med namnet&quot;män över 50&quot;, annars **[!UICONTROL false]**.
