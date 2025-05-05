---
title: Lista över steghändelsefält
description: Lista över steghändelsefält
feature: Journeys
topic: Content Management
role: User
level: Intermediate
exl-id: b7568080-b88c-415c-9d3f-cc1361664838
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '351'
ht-degree: 5%

---

# Lista över steghändelsefält {#sharing-field-list}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


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

Den här fältgruppen är specifik för travelStepEvent: den här händelsen är relaterad till resan och har inte identityMap, som beskriver profilens identitet, om sådan finns.

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
| status | Sträng | Status för segmentexportjobbet: köat, startat, avslutat |
| exportCountTotal | Heltal | Det högsta möjliga värdet för segmentexportjobbet |
| exportCountRealized | Heltal | Det faktiska antalet segment som exporterats genom jobbet |
| exportCountFailed | Heltal | Antalet segment som misslyckades vid export via jobbet |
| exportSegmentID | Sträng | Identifieraren för segmentet som exporteras |
| eventType | Sträng | Händelsetypen anger om det är en felhändelse för info-händelsen: Info, Error |
| eventCode | Sträng | Felkoden som anger orsaken till motsvarande eventType |

## stepEvents

Den här kategorin innehåller de ursprungliga fälten för steghändelser. Se det här [avsnittet](../building-journeys/sharing-legacy-fields.md).
