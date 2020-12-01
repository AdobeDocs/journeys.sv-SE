---
product: adobe campaign
solution: Journey Orchestration
title: Reseegenskaper
description: Läs om reseegenskaper
translation-type: tm+mt
source-git-commit: 1fd02fcc2a535046cfbcdb5d1c52850ee93370af
workflow-type: tm+mt
source-wordcount: '560'
ht-degree: 0%

---


# Reseegenskaper {#journey-properties}

I den avancerade uttrycksredigeraren hittar du kategorin **Reseegenskaper** , under kategorierna för händelse och datakälla. Denna kategori innehåller tekniska fält som rör resan för en viss profil. Det här är den information som hämtats av systemet från direktresor, till exempel rese-ID:t eller de specifika fel som påträffats.

![](../assets/journey-properties.png)

Du hittar t.ex. information om:

* reseversion: resa uid, reseversion uid, instansuid osv.
* fel: datahämtning, åtgärdskörning osv.
* aktuellt steg, senaste aktuella steg osv.
* ignorerade profiler

Du kan använda dessa fält för att skapa uttryck. Under körningen hämtas värdena direkt från resan.

Här är några exempel på användningsområden:

* **Logga ignorerade profiler**: Du kan skicka alla profiler som har uteslutits från ett meddelande med en begränsningsregel till ett tredjepartssystem för loggning. För detta anger du en sökväg i händelse av timeout och fel och lägger till ett villkor som ska filtreras efter en viss feltyp, till exempel: &quot;kasta bort personer genom att sätta på en regel&quot;. Du kan sedan överföra de borttagna profilerna till ett tredjepartssystem via en anpassad åtgärd.

* **Skickade push-varningar vid fel**: du kan skicka ett meddelande till ett tredjepartssystem varje gång ett fel inträffar i ett meddelande. För detta anger du en sökväg om ett fel uppstår, lägger till ett villkor och en anpassad åtgärd. Du kan till exempel skicka ett meddelande på en Slack-kanal med en beskrivning av det fel som påträffats.

* **Förfina fel i rapportering** : I stället för att bara ha en sökväg för felmeddelanden kan du definiera ett villkor per feltyp. På så sätt kan du förfina rapporteringen och visa alla feltyper.

## Fältlista {#journey-properties-fields}

|Kategori|Fältnamn|Etikett|Beskrivning|
|-|-|-|—|
|Reseversion|resaUID|Reseidentifierare| |
| |travelVersionUID|Identifierare för reseversion| |
| |travelVersionName|Resursversionsnamn| |
| |travelVersionDescription|Beskrivning av reseversion| |
| |travelVersion|Resversion| |
|Journey-instans|instanceUID|Journey-instans-ID|ID för instans|
| |externalKey|Extern nyckel|Individuell identifierare som utlöser resan|
|Identitet|profileId|Identity-ID för profil|Identifierare för profilen i resan|
| |namespace|Profile Identity Namespace|Namnområde för profilen i resan (exempel: ECID)|
|Aktuell nod|currentNodeId|Aktuell nod-ID|Identifierare för aktuell aktivitet (nod)|
| |currentNodeName|Aktuellt nodnamn|Namn på aktuell aktivitet (nod)|
|Föregående nod|previousNodeId|Föregående nodidentifierare|Identifierare för föregående aktivitet (nod)|
| |previousNodeName|Föregående nodnamn|Namn på föregående aktivitet (nod)|
|Fel|lastNodeUIDInError|Senaste nodidentifierare i fel|Identifierare för den senaste aktiviteten (nod) i fel|
| |lastNodeNameInError|Senaste nodnamn i fel|Namnet på den senaste aktiviteten (nod) i fel|
| |lastNodeTypeInError|Senaste nodtyp i Error|Feltyp för den senaste aktiviteten (nod) i fel. Möjliga typer:<ul><li>Händelser: Händelser, reaktioner, SQ (exempel: Segmentkvalificering)</li><li>Flödeskontroll: Slut, Villkor, Vänta</li><li>Funktionsmakron: ACS-åtgärder, Jump, Custom Action</li></ul>|
| |lastErrorCode|Senaste felkod|Felkod för den senaste aktiviteten (nod) i fel. Möjliga fel: <ul><li>HTTP-felkoder</li><li>mappad</li><li>timedOut</li><li>fel (exempel: standard om ett oväntat fel inträffar. Ska inte/mycket sällan inträffa)</li></ul>|
| |lastExecutedActionErrorCode|Senaste körda felkod|Felkod för senaste felåtgärd |
| |lastDataFetchErrorCode|Felkod för senaste datainhämtning|Felkod för senaste datainhämtning från datakällor|
|Time|lastActionExecutionElapsedTime|Senaste körningstid|Tid som har använts för att köra den senaste åtgärden|
| |lastDataFetchElapsedTime|Senaste tid för datahämtning|Tid för att köra den senaste datahämtningen från datakällor|
