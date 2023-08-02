---
product: adobe campaign
title: Beskrivning av API för begränsning
description: Läs mer om API:t för tak.
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 6f28e62d-7747-43f5-a360-1d6af14944b6
source-git-commit: 861c6bd8ce65793b6009e220d88f105c75ea3008
workflow-type: tm+mt
source-wordcount: '580'
ht-degree: 29%

---


# Arbeta med API:t för tak {#work}

Med API:t för att hämta innehåll kan du skapa, konfigurera och övervaka dina appkonfigurationer.

## Beskrivning av API för begränsning

| Metod | Sökväg | Beskrivning |
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
            "maxHttpConnections": <max connections count to the endpoint (optional)>
            "rating": {          
                "maxCallsCount": <max calls to be performed in the period defined by period/timeUnit>,
                "periodInMs": <integer value greater than 0>
            }
        },
        ...
    }
}
```

>[!IMPORTANT]
>
>The **maxHttpConnections** parametern är valfri. Du kan begränsa antalet anslutningar som Journey Optimizer öppnar till det externa systemet.
>
>Det högsta värdet som kan anges är 400. Om inget anges kan systemet öppna upp till flera tusen anslutningar beroende på systemets dynamiska skalning.

### Exempel:

```
`{
  "url": "https://api.example.org/data/2.5/*",
  "methods": [
    "GET"
  ],
  "services": {
    "dataSource": {
      "maxHttpConnections": 50,
      "rating": {
        "maxCallsCount": 500,
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

* **ERR_ENDPOINTCONFIG_100**: capping config: URL saknas eller är ogiltig
* **ERR_ENDPOINTCONFIG_101**: capping config: felaktig URL
* **ERR_ENDPOINTCONFIG_102**: capping config: felaktig url: wildchar in url not allowed in host:port
* **ERR_ENDPOINTCONFIG_103**: capping config: HTTP-metoder saknas
* **ERR_ENDPOINTCONFIG_104**: capping config: ingen anropsklassificering har definierats
* **ERR_ENDPOINTCONFIG_107**: capping config: ogiltigt antal anrop (maxCallCount)
* **ERR_ENDPOINTCONFIG_108**: capping config: ogiltigt antal anrop (periodInms)
* **ERR_ENDPOINTCONFIG_111**: capping config: kan inte skapa slutpunktskonfiguration: ogiltig nyttolast
* **ERR_ENDPOINTCONFIG_112**: capping config: kan inte skapa slutpunktskonfiguration: en JSON-nyttolast förväntas
* **ERR_AUTHORING_ENDPOINTCONFIG_1**: ogiltigt tjänstnamn `<!--<given value>-->`: måste vara &#39;dataSource&#39; eller &#39;action&#39;

Den potentiella varningen är:

**ERR_ENDPOINTCONFIG_106**: capping config: max HTTP connections not defined: no limit as default

## Användningsfall

I det här avsnittet hittar du de fem huvudsakliga användningsområdena som du kan använda för att hantera din appkonfiguration i [!DNL Journey Orchestration].

Det finns en Postman-samling som kan hjälpa dig med testning och konfiguration [här](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Capping-API_postman-collection.json).

Den här Postman-samlingen har konfigurerats för att dela den samling med Postman-variabler som genererats via __[Integreringar i Adobe I/O Console](https://console.adobe.io/integrations) > Testa > Hämta för Postman__, som genererar en Postman-miljöfil med de valda integreringsvärdena.

När du hämtat och laddat upp till Postman måste du lägga till tre variabler: `{JO_HOST}`,`{BASE_PATH}` och `{SANDBOX_NAME}`.
* `{JO_HOST}`: [!DNL Journey Orchestration] Gateway-URL
* `{BASE_PATH}`: startpunkt för API:et. Värdet är ”/authoring”
* `{SANDBOX_NAME}`: sidhuvudet **x-sandbox-name** (till exempel ”produktion”) som motsvarar namnet på sandlådan där API-åtgärderna utförs. Se [översikten över sandlådor](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=sv) för mer information.

I följande avsnitt hittar du listan över Rest API-anrop ordnade för att utföra fallstudien.

Användningsfall n°1: **Skapa och distribuera en ny takkonfiguration**

1. list
1. create
1. candeploy
1. deploy

Use-Case n°2: **Uppdatera och distribuera en capping-konfiguration som inte har distribuerats än**

1. list
1. get
1. update
1. candeploy
1. deploy

Användningsfall nr 3: **Avdistribuera och ta bort en distribuerad capping-konfiguration**

1. list
1. undeploy
1. delete

Användningsfall nr 4: **Ta bort en distribuerad capping-konfiguration.**

I endast ett API-anrop kan du avbryta driftsättning och radera konfigurationen med hjälp av parametern forceDelete.
1. list
1. radera med parametern forceDelete

Use-Case n°5: **Uppdatera en takkonfiguration som redan distribuerats**

1. list
1. get
1. update
1. undeploy
1. candeploy
1. deploy
