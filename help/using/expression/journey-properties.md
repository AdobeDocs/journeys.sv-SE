---
product: adobe campaign
solution: Journey Orchestration
title: Reseegenskaper
description: Läs om reseegenskaper
translation-type: tm+mt
source-git-commit: 341138c31676870878099b4f4eecec200a614c69
workflow-type: tm+mt
source-wordcount: '559'
ht-degree: 0%

---


# Reseegenskaper {#journey-properties}

I den avancerade uttrycksredigeraren finns kategorin **Reseegenskaper** nedanför kategorierna event och datakälla. Denna kategori innehåller tekniska fält som rör resan för en viss profil. Det här är den information som hämtats av systemet från direktresor, till exempel rese-ID:t eller de specifika fel som påträffats.

![](../assets/journey-properties.png)

Du hittar t.ex. information om:

* reseversion: resa uid, reseversion uid, instansuid osv.
* fel: datahämtning, åtgärdskörning osv.
* aktuellt steg, senaste aktuella steg osv.
* ignorerade profiler

Du kan använda dessa fält för att skapa uttryck. Under körningen hämtas värdena direkt från resan.

Här är några exempel på användningsområden:

* **Logga ignorerade profiler**: Du kan skicka alla profiler som har uteslutits från ett meddelande med en begränsningsregel till ett tredjepartssystem för loggning. För detta anger du en sökväg i händelse av timeout och fel och lägger till ett villkor som ska filtreras efter en viss feltyp, till exempel: &quot;kasta bort personer genom att sätta på en regel&quot;. Du kan sedan överföra de borttagna profilerna till ett tredjepartssystem via en anpassad åtgärd.

* **Skicka varningar vid fel**: du kan skicka ett meddelande till ett tredjepartssystem varje gång ett fel inträffar i ett meddelande. För detta anger du en sökväg om ett fel uppstår, lägger till ett villkor och en anpassad åtgärd. Du kan till exempel skicka ett meddelande på en Slack-kanal med en beskrivning av det fel som påträffats.

* **Förfina fel i rapportering** : I stället för att bara ha en sökväg för felmeddelanden kan du definiera ett villkor per feltyp. På så sätt kan du förfina rapporteringen och visa alla feltyper.

## Lista med fält {#journey-properties-fields}

| Kategori | Fältnamn | Etikett | Beskrivning |
|---|---|---|------------|
| Reseversion | travelUID | Reseidentifierare |  |
|  | travelVersionUID | Reseversionsidentifierare |  |
|  | travelVersionName | Namn på reseversion |  |
|  | travelVersionDescription | Beskrivning av reseversion |  |
|  | travelVersion | Reseversion |  |
| Reseinstans | instanceUID | Journey-instans-ID | ID för instansen |
|  | externalKey | Extern nyckel | Individuell identifierare som utlöser resan |
| Identitet | profileId | Identifierare för profilidentitet | Identifierare för profilen i resan |
|  | namespace | Namnområde för profilidentitet | Profilens namnområde under resan (exempel: ECID) |
| Aktuell nod | currentNodeId | Aktuell nodidentifierare | Identifierare för den aktuella aktiviteten (nod) |
|  | currentNodeName | Aktuellt nodnamn | Namn på aktuell aktivitet (nod) |
| Föregående nod | previousNodeId | Föregående nodidentifierare | Identifierare för föregående aktivitet (nod) |
|  | previousNodeName | Föregående nodnamn | Namn på föregående aktivitet (nod) |
| Fel | lastNodeUIDInError | Senaste nodidentifierare i fel | Identifierare för den senaste aktiviteten (nod) vid fel |
|  | lastNodeNameInError | Senaste nodnamn i fel | Namn på den senaste aktiviteten (nod) med fel |
|  | lastNodeTypeInError | Senaste nodtyp i fel | Feltyp för den senaste aktiviteten (nod). Möjliga typer:<ul><li>Händelser: Händelser, reaktioner, SQ (exempel: Segmentkvalificering)</li><li>Flödeskontroll: Slut, Villkor, Vänta</li><li>Funktionsmakron: ACS-åtgärder, Jump, Custom Action</li></ul> |
|  | lastErrorCode | Senaste felkod | Felkod för den senaste aktiviteten (nod). Möjliga fel: <ul><li>HTTP-felkoder</li><li>mappad</li><li>timedOut</li><li>fel (exempel: standard om ett oväntat fel inträffar. Ska inte/mycket sällan inträffa)</li></ul> |
|  | lastExecutedActionErrorCode | Felkod för senaste körda åtgärd | Felkod för den senaste felåtgärden |
|  | lastDataFetchErrorCode | Felkod för senaste datainhämtning | Felkod för den senaste datahämtningen från datakällor |
| Tid | lastActionExecutionElapsedTime | Senaste körningstid för åtgärd | Tid som har använts för att köra den senaste åtgärden |
|  | lastDataFetchElapsedTime | Senaste tid för datahämtning | Den tid som har använts för att köra den senaste datahämtningen från datakällor |