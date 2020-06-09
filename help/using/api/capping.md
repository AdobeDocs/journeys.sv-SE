---
title: Beskrivning av API för begränsning
description: Läs mer om API:t för tak.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '1065'
ht-degree: 0%

---


# Arbeta med API:t för begränsning

## Introduktion

[!DNL Journey Orchestration]API:er stöder 5000 händelser/sekunder, men vissa externa system eller API kunde inte ha ett ekvivalent dataflöde. Det är därför [!DNL Journey Orchestration] en dedikerad funktion som kallas Capping API för att övervaka och begränsa hastigheten som vi lägger på externa system.

Under en datakällkonfiguration definierar du en anslutning till ett system för att hämta ytterligare information som ska användas på dina resor, eller för en åtgärdsdefinition konfigurerar du anslutningen till ett tredjepartssystem för att skicka meddelanden eller API-anrop. Varje gång ett API-anrop utförs av Journey efterfrågas API:t för appning, sker anropet via API-motorn. Om det finns en definierad gräns avvisas anropet och det externa systemet överbelastas inte.

Mer information om åtgärder och konfiguration av datakälla finns i [Om åtgärder](https://docs.adobe.com/content/help/en/journeys/using/action-journeys/action.html) och [Om datakällor](https://docs.adobe.com/content/help/en/journeys/using/data-source-journeys/about-data-sources.html)


## Resurser

API:t för att [!DNL Journey Orchestration] hämta innehåll beskrivs i en Swagger-fil som finns [här](https://adobedocs.github.io/JourneyAPI/docs/).

Om du vill använda detta API med din [!DNL Journey Orchestration] instans måste du använda AdobeIO-konsolen. Du kan börja med att följa detta [Komma igång med Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) och sedan använda avsnitten på den här sidan.

För att testa och förbereda integreringen finns en Postman-samling [här](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

## Behörighet

### Konfigurera API-åtkomst

[!DNL Journey Orchestration] API-åtkomst konfigureras genom stegen nedan. Vart och ett av dessa steg beskrivs i [Adobe IO-dokumentationen](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Om du vill hantera certifikat i Adobe IO måste du ha <b>systemadministratörsbehörighet</b> för organisationen eller ett <a href="https://helpx.adobe.com/enterprise/using/manage-developers.html">utvecklarkonto</a> i Admin Console.

1. **Kontrollera att du har ett digitalt certifikat** eller skapa ett om det behövs. De offentliga och privata nycklarna som tillhandahålls med certifikatet behövs i följande steg.
1. **Skapa en ny integrering för[!DNL Journey Orchestration]Service** i Adobe IO och konfigurera den. Tillgång till produktprofiler krävs för [!DNL Journey Orchestration] och Adobe Experience Platform. Dina autentiseringsuppgifter genereras sedan (API-nyckel, klienthemlighet...).
1. **Skapa en JSON Web Token (JWT)** utifrån de inloggningsuppgifter som tidigare genererats och signera den med din privata nyckel. JWT kodar all identitets- och säkerhetsinformation som Adobe behöver för att verifiera din identitet och ge dig åtkomst till API:t. Det här steget beskrivs i det här [avsnittet](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Byt ut din JWT-fil mot en åtkomsttoken** via en POST-begäran eller via gränssnittet för Developer Console. Denna Access Token måste användas i varje rubrik för dina API-begäranden.

För att skapa en säker Adobe I/O API-session måste varje begäran till en Adobe-tjänst innehålla informationen nedan i auktoriseringshuvudet.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANISATION>**: Detta är ditt personliga organisations-ID, och Adobe tillhandahåller ett organisations-ID för varje instans:

   * &lt;ORGANISATION>: din produktionsinstans
   Kontakta administratören eller den tekniska kontaktpersonen på Adobe om du vill få ditt organisations-ID-värde. Du kan även hämta den till Adobe I/O när du skapar en ny integrering i licenslistan (se <a href="https://www.adobe.io/authentication.html">Adobe IO-dokumentationen</a>).

* **&lt;ACCESS_TOKEN>**: Din personliga åtkomsttoken, som hämtades när du bytte din JWT via en POST-begäran.

* **&lt;API_KEY>**: din egen API-nyckel. Det tillhandahålls i Adobe I/O efter att en ny integration till [!DNL Journey Orchestration] Service har skapats.



## Beskrivning av API för begränsning

Med API:t för att hämta innehåll kan du skapa, konfigurera och övervaka dina appkonfigurationer.

| Metod | Bana | Beskrivning |
|---|---|---|
| POST | list/endpointConfigs | Hämta en lista med konfigurationer för slutpunktsbegränsning |
| POST | /endpointConfigs | Skapa en konfiguration för begränsning av slutpunkter |
| POST | /endpointConfigs/{uid}/deploy | Distribuera en slutpunktskonfiguration |
| POST | /endpointConfigs/{uid}/undeploy | Avdistribuera en slutpunktskonfiguration |
| POST | /endpointConfigs/{uid}/canDeploy | Kontrollera om en slutpunktskonfiguration kan distribueras eller inte |
| PUT | /endpointConfigs/{uid} | Uppdatera en konfiguration för begränsning av slutpunkter |
| GET | /endpointConfigs/{uid} | Hämta en konfiguration för slutpunktsbegränsning |
| TA BORT | /endpointConfigs/{uid} | Ta bort en ändpunktskonfiguration |

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

När en **canDeploy** -metod anropas validerar processen konfigurationen och returnerar den verifieringsstatus som identifieras av dess unika ID, antingen:

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
* **ERR_ENDPOINTCONFIG_11**: capping config: det går inte att skapa slutpunktskonfiguration: ogiltig nyttolast
* **ERR_ENDPOINTCONFIG_112**: capping config: det går inte att skapa slutpunktskonfiguration: en JSON-nyttolast förväntas
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: ogiltigt tjänstnamn <!--<given value>-->: måste vara &#39;dataSource&#39; eller &#39;action&#39;


Den potentiella varningen är:

**ERR_ENDPOINTCONFIG_106**: capping config: max antal HTTP-anslutningar ej definierade: ingen begränsning som standard



## Användningsfall

I det här avsnittet hittar du de fem huvudsakliga användningsfall som du kan använda för att hantera din appkonfiguration i [!DNL Journey Orchestration].

För att du ska få hjälp med testning och konfiguration finns en Postman-samling [här](https://github.com/AdobeDocs/JourneyAPI/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Denna Postman Collection har konfigurerats för att dela den Postman Variable-samling som genereras via __[Adobe I/O Console’s Integrations](https://console.adobe.io/integrations)> Testa > Ladda ned för Postman__, som genererar en Postman Environment-fil med de valda integreringsvärdena.

När du har hämtat och överfört till Postman måste du lägga till två variabler: `{JO_HOST}` och `{Base_Path}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] Gateway-URL
* `{BASE_PATH}` : startpunkt för API. Värdet är /authoring



Användningsfall n°1: **Skapa och distribuera en ny takkonfiguration**

1. list
1. skapa
1. candeploy
1. driftsätta

Use-Case n°2: **Uppdatera och distribuera en capping-konfiguration som inte har distribuerats än**

1. list
1. get
1. uppdatera
1. candeploy
1. driftsätta

Användningsfall nr 3: **Avdistribuera och ta bort en distribuerad capping-konfiguration**

1. list
1. avdistribuera
1. delete

Användningsfall nr 4: **Ta bort en distribuerad capping-konfiguration.**

I endast ett API-anrop kan du avdistribuera och ta bort konfigurationen med hjälp av parametern forceDelete.
1. list
1. delete, with forceDelete param

Use-Case n°5: **Uppdatera en takkonfiguration som redan har distribuerats**

1. list
1. get
1. uppdatera
1. avdistribuera
1. candeploy
1. driftsätta

