---
product: adobe campaign
title: Beskrivning av API för begränsning
description: Läs mer om API:t för tak.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: a32a208fcaef9a408c850c0ad74ab44e3eb44709
workflow-type: tm+mt
source-wordcount: '1173'
ht-degree: 1%

---

# Arbeta med API:t för begränsning

## Introduktion

[!DNL Journey Orchestration]API:er stöder 5000 händelser/sekunder, men vissa externa system eller API kunde inte ha ett ekvivalent dataflöde. Det är därför [!DNL Journey Orchestration] har en dedikerad funktion som kallas Capping API för att övervaka och begränsa hastigheten som vi lägger på externa system.

Under en datakällkonfiguration definierar du en anslutning till ett system för att hämta ytterligare information som ska användas på dina resor, eller för en åtgärdsdefinition konfigurerar du anslutningen till ett tredjepartssystem för att skicka meddelanden eller API-anrop. Varje gång ett API-anrop utförs av Journey efterfrågas API:t för appning, sker anropet via API-motorn. Om det finns en definierad gräns avvisas anropet och det externa systemet överbelastas inte.

För externa datakällor är det maximala antalet anrop per sekund satt till 15. Om antalet anrop överstiger 15 per sekund ignoreras de återstående samtalen. Du kan öka den här gränsen för privata externa datakällor. Kontakta Adobe för att inkludera slutpunkten i tillåtelselista. Detta är inte möjligt för offentliga externa datakällor. Om du vill veta mer om bästa praxis och riktlinjer när du integrerar externa system kan du läsa detta [page](../about/external-systems.md).

Mer information om åtgärder eller konfiguration av datakälla finns i [Om funktionsmakron](https://experienceleague.adobe.com/docs/journeys/using/action-journeys/action.html) eller [Om datakällor](https://experienceleague.adobe.com/docs/journeys/using/data-source-journeys/about-data-sources.html)

## Resurser

>[!NOTE]
>
>The [!DNL Journey Orchestration] API för att hämta innehåll beskrivs i en tillgänglig Swagger-fil [här](https://adobedocs.github.io/JourneyAPI/docs/).

Så här använder du detta API med [!DNL Journey Orchestration] Du måste till exempel använda AdobeI/O-konsolen. Du kan börja med att följa detta [Komma igång med Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) och sedan använda avsnitten på den här sidan.

En Postman-samling finns tillgänglig för att testa och förbereda integreringen [här](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Behörighet

### Konfigurera API-åtkomst

[!DNL Journey Orchestration] API-åtkomst konfigureras genom stegen nedan. Varje steg beskrivs i [Adobe I/O dokumentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Kontrollera att du har <b>Systemadministratör</b> rättigheter till organisationen eller [utvecklarkonto](https://helpx.adobe.com/enterprise/using/manage-developers.html) i Admin Console.

1. **Kontrollera att du har ett digitalt certifikat** eller skapa en vid behov. De offentliga och privata nycklarna som tillhandahålls med certifikatet behövs i följande steg.
1. **Skapa en ny integrering för att [!DNL Journey Orchestration] Tjänst** i Adobe I/O och konfigurera det. Du behöver åtkomst till produktprofilen för [!DNL Journey Orchestration] och Adobe Experience Platform. Dina autentiseringsuppgifter genereras sedan (API-nyckel, klienthemlighet...).
1. **Skapa en JSON-webbtoken (JWT)** från de inloggningsuppgifter som tidigare genererats och signera med din privata nyckel. JWT kodar all identitets- och säkerhetsinformation som Adobe behöver för att verifiera din identitet och ge dig åtkomst till API:t. Det här steget beskrivs närmare i det här [section](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Byt ut din JWT mot en åtkomsttoken** via en POST eller via Developer Console Interface. Denna Access Token måste användas i varje rubrik för dina API-begäranden.

Om du vill skapa en säker Adobe I/O-till-tjänst-API-session måste alla förfrågningar till en Adobe-tjänst innehålla informationen nedan i auktoriseringshuvudet.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Detta är ditt personliga organisations-ID, och Adobe tillhandahåller ett organisations-ID för varje instans:

   * &lt;organization> : din produktionsinstans

   Kontakta din administratör eller din Adobe tekniska kontakt för att få ditt organisations-ID-värde. Du kan även hämta den till Adobe I/O när du skapar en ny integrering i licenslistan (se <a href="https://www.adobe.io/authentication.html">Adobe I/O dokumentation</a>).

* **&lt;access_token>**: Din personliga åtkomsttoken, som hämtades när du bytte din JWT via en POST.

* **&lt;api_key>**: din egen API-nyckel. Det tillhandahålls i Adobe I/O efter att en ny integrering av [!DNL Journey Orchestration] Tjänst.



## Beskrivning av API för begränsning

Med API:t för att hämta innehåll kan du skapa, konfigurera och övervaka dina appkonfigurationer.

| Metod | Bana | Beskrivning |
|---|---|---|
| [!DNL POST] | list/endpointConfigs | Hämta en lista över konfigurationer för slutpunktsbegränsning |
| [!DNL POST] | /endpointConfigs | Skapa en konfiguration för begränsning av slutpunkter |
| [!DNL POST] | /endpointConfigs/`{uid}`/deploy | Distribuera en slutpunktskonfiguration |
| [!DNL POST] | /endpointConfigs/`{uid}`/undeploy | Avdistribuera en slutpunktskonfiguration |
| [!DNL POST] | /endpointConfigs/`{uid}`/canDeploy | Kontrollera om en slutpunktskonfiguration kan distribueras eller inte |
| [!DNL PUT] | /endpointConfigs/`{uid}` | Uppdatera en konfiguration för begränsning av slutpunkter |
| [!DNL GET] | /endpointConfigs/`{uid}` | Hämta en konfiguration för slutpunktsbegränsning |
| [!DNL DELETE] | /endpointConfigs/`{uid}` | Ta bort en ändpunktskonfiguration |

När en konfiguration skapas eller uppdateras utförs en kontroll automatiskt för att garantera nyttolastens syntax och integritet.
Om det uppstår problem returneras en varning eller felmeddelanden som hjälper dig att korrigera konfigurationen.



## Konfiguration av slutpunkt

Här är den grundläggande strukturen för en slutpunktskonfiguration:

```
{
    "url": "<endpoint URL>",  //wildcards are allowed in the endpoint URL
    "methods": [ "<HTTP method such as GET, POST, >, ...],
    "services": {
        "<service name>": { . //must be "action" or "dataSource" 
            "maxHttpConnections": <max connections count to the endpoint>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

### Exempel:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 30000,
      "rating": {
        "maxCallsCount": 5000,
        "periodInMs": 1000
      }
    }
  },
  "orgId": "<IMS Org Id>"
}
```


## Varningar och fel

När en **canDeploy** metoden anropas, validerar processen konfigurationen och returnerar den valideringsstatus som identifieras av dess unika ID, antingen:

```
"ok" or "error"
```

Möjliga fel är:

* **ERR_ENDPOINTCONFIG_100**: capping config: saknad eller ogiltig URL
* **ERR_ENDPOINTCONFIG_101**: capping config: felaktig URL
* **ERR_ENDPOINTCONFIG_102**: capping config: felaktig URL: wildchar in url not allowed in host:port
* **ERR_ENDPOINTCONFIG_103**: capping config: saknade HTTP-metoder
* **ERR_ENDPOINTCONFIG_104**: capping config: ingen anropsklassificering har definierats
* **ERR_ENDPOINTCONFIG_107**: capping config: ogiltigt max antal anrop (maxCallCount)
* **ERR_ENDPOINTCONFIG_108**: capping config: ogiltigt max antal anrop (periodInms)
* **ERR_ENDPOINTCONFIG_111**: capping config: det går inte att skapa slutpunktskonfiguration: ogiltig nyttolast
* **ERR_ENDPOINTCONFIG_112**: capping config: det går inte att skapa slutpunktskonfiguration: en JSON-nyttolast förväntas
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: ogiltigt tjänstnamn `<!--<given value>-->`: måste vara &#39;dataSource&#39; eller &#39;action&#39;


Den potentiella varningen är:

**ERR_ENDPOINTCONFIG_106**: capping config: max antal HTTP-anslutningar ej definierade: ingen begränsning som standard



## Användningsfall

I det här avsnittet hittar du de fem huvudsakliga användningsområdena som du kan använda för att hantera din appkonfiguration i [!DNL Journey Orchestration].

Det finns en Postman-samling som kan hjälpa dig med testning och konfiguration [här](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Den här Postman Collection har konfigurerats för att dela den Postman Variable-samling som genererats via __[Integreringar i Adobe I/O Console](https://console.adobe.io/integrations) > Testa > Ladda ned för Postman__, som genererar en Postman-miljöfil med de valda integreringsvärdena.

När du laddat ned och överfört till Postman måste du lägga till tre variabler: `{JO_HOST}`,`{Base_Path}` och `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] Gateway-URL
* `{BASE_PATH}` : startpunkt för API. Värdet är /authoring
* `{SANDBOX_NAME}` : sidhuvudet **x-sandbox-name** (till exempel prod) som motsvarar namnet på sandlådan där API-åtgärderna ska utföras. Se [översikt över sandlådor](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) för mer information.

I följande avsnitt hittar du listan med Rest API-anrop ordnade för att utföra fallstudien.

Användningsfall n°1: **Skapa och distribuera en ny takkonfiguration**

1. lista
1. skapa
1. candeploy
1. driftsätta

Use-Case n°2: **Uppdatera och distribuera en capping-konfiguration som inte har distribuerats än**

1. lista
1. get
1. uppdatera
1. candeploy
1. driftsätta

Användningsfall nr 3: **Avdistribuera och ta bort en distribuerad capping-konfiguration**

1. lista
1. avdistribuera
1. delete

Användningsfall nr 4: **Ta bort en distribuerad capping-konfiguration.**

I endast ett API-anrop kan du avdistribuera och ta bort konfigurationen med hjälp av parametern forceDelete.
1. lista
1. delete, with forceDelete param

Use-Case n°5: **Uppdatera en takkonfiguration som redan har distribuerats**

1. lista
1. get
1. uppdatera
1. avdistribuera
1. candeploy
1. driftsätta
