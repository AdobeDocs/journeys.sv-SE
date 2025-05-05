---
product: adobe campaign
title: Resans egenskaper
description: Lär dig mer om reseegenskaper
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 798e4207-5bef-4002-9c1f-608bb6243e43
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '631'
ht-degree: 0%

---

# Attribut för reseegenskaper {#journey-properties}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


I den avancerade uttrycksredigeraren hittar du kategorin **Reseegenskaper**, under kategorierna för händelsen och datakällan. Denna kategori innehåller tekniska fält som rör resan för en viss profil. Det här är den information som hämtats av systemet från direktresor, till exempel rese-ID:t eller de specifika fel som påträffats.

>[!NOTE]
>
>Attribut för reseegenskaper är också tillgängliga i redigeraren för enkla uttryck. Se [avsnittet](../building-journeys/condition-activity.md#about_condition)

![](../assets/journey-properties.png)

Du hittar information om:

* reseversion: reseversion, resversion-id, instansens-uid, osv.
* fel: datahämtning, åtgärdskörning osv.
* aktuellt steg, senaste aktuella steg osv.
* ignorerade profiler

Du kan använda dessa fält för att skapa uttryck. Under körningen hämtas värdena direkt från resan.

Här är några exempel på användningsområden:

* **Logga ignorerade profiler**: Du kan skicka alla profiler som har uteslutits från ett meddelande via en begränsningsregel till ett tredjepartssystem för loggning. För detta anger du en sökväg i händelse av timeout och fel och lägger till ett villkor som ska filtreras efter en viss feltyp, t.ex.&quot;ignorera personer genom att appa regel&quot;. Du kan sedan överföra de borttagna profilerna till ett tredjepartssystem via en anpassad åtgärd.

* **Skicka aviseringar vid fel**: du kan skicka ett meddelande till ett tredjepartssystem varje gång ett fel inträffar i ett meddelande. För detta anger du en sökväg om ett fel uppstår, lägger till ett villkor och en anpassad åtgärd. Du kan till exempel skicka ett meddelande på en Slack-kanal med en beskrivning av det fel som uppstod.

* **Förfina fel i rapportering** : I stället för att bara ha en sökväg för felmeddelanden kan du definiera ett villkor per feltyp. På så sätt kan du förfina rapporteringen och visa alla feltyper och data.

## Fältlista {#journey-properties-fields}

| Kategori | Fältnamn | Etikett | Beskrivning |
|---|---|---|------------|
| Reseversion | travelUID | Reseidentifierare | |
| | travelVersionUID | Reseversionsidentifierare | |
| | travelVersionName | Namn på reseversion | |
| | travelVersionDescription | Beskrivning av reseversion | |
| | travelVersion | Reseversion | |
| Reseinstans | instanceUID | Journey-instans-ID | ID för instansen |
| | externalKey | Extern nyckel | Individuell identifierare som utlöser resan |
| | organizationId | Organisationens identifierare | Varumärkesorganisation |
| | sandboxName | Namn på sandlåda | Namn på sandlådan |
| Identitet | profileId | Identifierare för profilidentitet | Identifierare för profilen i resan |
| | namespace | Namnområde för profilidentitet | Profilens namnområde under resan (exempel: ECID) |
| Aktuell nod | currentNodeId | Aktuell nodidentifierare | Identifierare för den aktuella aktiviteten (nod) |
| | currentNodeName | Aktuellt nodnamn | Namn på aktuell aktivitet (nod) |
| Föregående nod | previousNodeId | Föregående nodidentifierare | Identifierare för föregående aktivitet (nod) |
| | previousNodeName | Tidigare nodnamn | Namn på föregående aktivitet (nod) |
| Fel | lastNodeUIDInError | Senaste nodidentifierare i fel | Identifierare för den senaste aktiviteten (nod) vid fel |
| | lastNodeNameInError | Senaste nodnamn i fel | Namn på den senaste aktiviteten (nod) med fel |
| | lastNodeTypeInError | Senaste nodtyp i fel | Feltyp för den senaste aktiviteten (nod). Möjliga typer:<ul><li>Händelser: Händelser, reaktioner, SQ (exempel: Segmentkvalificering)</li><li>Flödeskontroll: Slut, Villkor, Vänta</li><li>Åtgärder: ACS-åtgärder, Hoppa, Anpassad åtgärd</li></ul> |
| | lastErrorCode | Senaste felkod | Felkod för den senaste aktiviteten (nod). Möjliga fel: <ul><li>HTTP-felkoder</li><li>mappad</li><li>timedOut</li><li>fel (exempel: standard om ett oväntat fel inträffar. Ska inte/mycket sällan inträffa)</li></ul> |
| | lastExecutedActionErrorCode | Felkod för senaste körda åtgärd | Felkod för den senaste felåtgärden |
| | lastDataFetchErrorCode | Felkod för senaste datainhämtning | Felkod för den senaste datahämtningen från datakällor |
| Tid | lastActionExecutionElapsedTime | Senaste körningstid för åtgärd | Tid som har använts för att köra den senaste åtgärden |
| | lastDataFetchElapsedTime | Senaste tid för datahämtning | Den tid som har använts för att köra den senaste datahämtningen från datakällor |
