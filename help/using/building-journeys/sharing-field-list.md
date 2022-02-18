---
title: Lista över steghändelsefält
description: Lista över steghändelsefält
feature: Journeys
topic: Content Management
role: User
level: Intermediate
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 12%

---

# Lista över steghändelsefält {#sharing-field-list}

Fälten för steghändelser är ordnade efter kategori.

* Felsöka informationsfält
* Resefält
* Profilfält
* Tjänstehändelsefält

## debugInfo

| Fältnamn | Typ | Beskrivning |
|---|---|------------|
| requestId | Sträng | Begärande-ID som används av Journey Orchestration för att spåra flödet för en begäran. |

## resa

Den här fältgruppen används i transportschemat (i relation till travelStepEvent). Den innehåller följande fält:

| Fältnamn | Typ | Beskrivning |
|---|---|------------|
| ID | Sträng | Identifierare för angiven resa |
| VersionID | Sträng | ID för reseversionen. Detta ID representerar identiteten på en resa |
| name | Sträng | Namn på resan |
| description | Sträng | Beskrivning av resan |
| version | Sträng | version, representerad som `major`.`minor` |

## profil

Den här fältgruppen är specifik för travelStepEvent: den här händelsen är relaterad till resan och har inte identityMap, som beskriver profidentiteten, om någon.

För travelStepEvent måste vi även lägga till fält som är relaterade till identiteten:

| Fältnamn | Typ | Beskrivning |
|---|---|------------|
| ID | Sträng | Profilidentifierare identifierar den profil som skickas/används under en resa. Exempel: foo@adobe.com. |
| namespace | Sträng | Det här fältet beskriver namnutrymmet som refereras av den profil som används i resan. Exempel: E-post, ECID |

## serviceEvents

Den här mixinen innehåller alla fält som motsvarar ett profilexportjobb.

| Fältnamn | Typ | Beskrivning |
|---|---|------------|
| ID | Sträng | Identifieraren för segmentexportjobbet som utlöses |
| status | Sträng | Status för segmentexportjobb: köad, startad, avslutad |
| exportCountTotal | Heltal | Det högsta möjliga värdet för segmentexportjobbet |
| exportCountRealized | Heltal | Det faktiska antalet segment som exporterats genom jobbet |
| exportCountFailed | Heltal | Antalet segment som misslyckades vid export via jobbet |
| exportSegmentID | Sträng | Identifieraren för segmentet som exporteras |
| eventType | Sträng | Händelsetypen som anger om det är en felhändelse för info-händelsen: Info, fel |
| eventCode | Sträng | Felkoden som anger orsaken till motsvarande eventType |

## stepEvents

Den här kategorin innehåller de ursprungliga fälten för steghändelser. Se detta [section](../building-journeys/sharing-legacy-fields.md).
