---
title: getBestSendTime
description: Läs mer om funktionen getBestSendTime
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
source-git-commit: d6360d616199d597255610959432c7b93fd4e25c

---


# getBestSendTime {#getBestSendTime}

Tillhandahåller en prediktiv tid för den bästa tidpunkten för att leverera ett e-postmeddelande till en individ.

Den här funktionen använder en poäng som beräknas i plattformen. Poängen beräknar sannolikheten för att klicka eller öppna ett e-postmeddelande i framtiden baserat på tidigare beteenden. Observera att algoritmen som beräknar poängen behöver en viss mängd data för att fungera. Därför gäller standardtiden när det inte finns tillräckligt med data. Mer information finns i [](../building-journeys/wait-activity.md).

För att den här funktionen ska kunna användas krävs ett [namnutrymme](../event/selecting-the-namespace.md) .

>[!NOTE]
>
>Observera att det bästa sändningstidsresultatet inte är tillgängligt om det inte finns tillräckligt med data för att utföra beräkningen. I så fall kommer du att informeras om att standardtiden gäller vid publiceringen.

## Kategori

Adobe Experience Platform

## Funktionssyntax

`getBestSendTime(<parameters>)`

## Parametrar

| Parameter | Beskrivning | Typ |
|--- |--- |--- |
| tidsmängd | Antal timmar att ta hänsyn till från den aktuella tiden (max: 168) för att optimera e-postutskick | `<integer>` |
| optimeringstyp | &quot;open&quot; eller &quot;click&quot; | `<string>` |
| standardtid i timmar att vänta | Om prediktiva sändningstider inte är tillgängliga | `<integer>` |

## Signatur och returtyp

`getBestSendTime(<integer>,<string>,<integer>)`

Returnerar ett dateTime.

## Exempel

getBestSendTime(12,&quot;open&quot;,8)

Förklaring:

Funktionen returnerar den bästa tiden för att skicka ett meddelande inom de kommande 12 timmarna för att optimera sannolikheten för att personen i reseinstansen ska kunna öppna det. Om det inte finns tillräckligt med data för att utföra beräkningen är den returnerade tiden i 8 timmar från den aktuella tiden.
