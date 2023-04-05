---
product: adobe campaign
title: Arbeta med begränsnings-API
description: Läs mer om API:t för begränsning
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: fa493cf1e856378e4d79a6932c30cebf5e11e028
workflow-type: tm+mt
source-wordcount: '788'
ht-degree: 1%

---

# Arbeta med begränsnings-API

API:t för begränsning hjälper dig att skapa, konfigurera och övervaka dina begränsningskonfigurationer.

>[!IMPORTANT]
>
>Endast en konfiguration är för närvarande tillåten per organisation. En konfiguration måste definieras i en produktionssandlåda (anges via x-sandbox-name i rubrikerna).
>
>En konfiguration används på organisationsnivå.
>
>När gränsvärdet i API:t har uppnåtts köas ytterligare händelser i upp till 6 timmar. Detta värde kan inte ändras.

## Beskrivning av begränsnings-API {#description}

| Metod | Bana | Beskrivning |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | Hämta en lista med begränsningskonfigurationer |
| [!DNL POST] | /throttlingConfigs | Skapa en begränsningskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | Distribuera en begränsningskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | Avdistribuera en begränsningskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | Kontrollera om en begränsningskonfiguration kan distribueras eller inte |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | Uppdatera en begränsningskonfiguration |
| [!DNL GET] | /throttlingConfigs/`{uid}` | Hämta en begränsningskonfiguration |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | Ta bort en begränsningskonfiguration |

## Begränsningskonfiguration {#configuration}

Här är strukturen för en strypningskonfiguration. **name** och **description** attribut är valfria.

```
{
    "name": "<given name - free text>",
    "description": "<given description - free text>"
    "urlPattern": "<endpoint URL - wildcards are allowed>",
    "methods": [ "<HTTP method such as GET, POST, PUT>" ],
    "maxThroughput": <max call throughput>
}
```

Exempel:

```
{
  "name": "throttling-config-external",
  "description": "example of throttling config for an external endpoint",
  "urlPattern": "https://api.example.org/data/2.5/*",
  "methods": ["POST", "PUT"],
  "maxThroughput": 4000
}
```

## Fel

När en konfiguration skapas eller uppdateras validerar processen den angivna konfigurationen och returnerar den verifieringsstatus som identifieras av dess unika ID, antingen:

```
"ok" or "error"
```

>[!IMPORTANT]
>
>Attributen **maxThrottput**, **urlPattern** och **metoder** är obligatoriska.
>
>**maxThrottput** värdet måste vara i intervallet 200-5000.

Följande fel kan uppstå när du skapar, tar bort eller distribuerar begränsningskonfiguration:

* **ERR_THROTTLING_CONFIG_100**: strypningskonfiguration: `<mandatory attribute>` obligatoriskt
* **ERR_THROTTLING_CONFIG_101**: strypningskonfiguration: maxThoutput krävs och måste vara större än eller lika med 200 och mindre än eller lika med 5000
* **ERR_THROTTLING_CONFIG_104**: strypningskonfiguration: felformat url-mönster
* **ERR_THROTTLING_CONFIG_105**: strypningskonfiguration: jokertecken tillåts inte i värddelen av URL-mönstret
* **ERR_THROTTLING_CONFIG_106**: strypningskonfiguration: ogiltig nyttolast
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**,&quot;Det går inte att ta bort en distribuerad begränsningskonfiguration. Avdistribuera den innan den tas bort&quot;
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**, &quot;Can&#39;t delete Throttling config: oväntat fel inträffar&quot;
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**, &quot;Can&#39;t deploy throttling config: oväntat fel inträffar&quot;
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**, &quot;Det går inte att avdistribuera begränsningskonfiguration: oväntat fel inträffar&quot;
* **THROTTLING_CONFIG_GET_ERROR: 1460**, &quot;Can&#39;t get throttling config: oväntat fel inträffar&quot;
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**, &quot;Can&#39;t update throttling config: Körningsversionen är inte aktiv&quot;
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**, &quot;Can&#39;t update throttling config: oväntat fel inträffar&quot;
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**, &quot;Åtgärden tillåts inte för strypningskonfiguration: ej känd sandlåda&quot;
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**, &quot;Det går inte att skapa strypningskonfiguration: oväntat fel inträffar&quot;
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**, &quot;Det går inte att skapa strypningskonfiguration: endast en konfiguration tillåts per organisation&quot;
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**, &quot;Can&#39;t deploy throttling config: redan distribuerad&quot;
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**, &quot;strypningen config not found&quot;
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**, &quot;Det går inte att avdistribuera begränsningskonfiguration: inte distribuerat ännu&quot;

**Exempel på fel**

När du försöker skapa en konfiguration i en icke-prod sandlåda:

```
{
    "status": 400,
    "error": "{\"code\":1463,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Operation not allowed on throttling config: non prod sandbox\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:384\",\"schema\":\"throttlingConfigs$ui-tests\"}",
    "requestId": "5sgnAYXs8mpswwjAFEIaAU2faQYbtyHc"
}
```

Om den angivna sandlådan inte finns:

```
{
    "status": 500,
    "error": "{\"code\":4000,\"family\":\"INTERNAL_ERROR\",\"message\":\"INTERNAL ERROR\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.common.exceptions.ApiErrorException:43\"}",
    "requestId": "04ZJ4e5ki4bYs3lfO17a7hovRGewjvdK"
}
```

När du försöker skapa en annan konfiguration:

```
{
    "status": 400,
    "error": "{\"code\":1465,\"family\":\"INPUT_OUTPUT_ERROR\",\"message\":\"Can't create throttling config: only one config allowed per org\",\"service\":\"vyg-authoring-api\",\"version\":\"ed87515\",\"context\":\"com.adobe.voyager.service.authoring.restapis.v1_0.ThrottlingConfigService:108\",\"schema\":\"throttlingConfigs$prod\"}",
    "requestId": "A7ezT8JhOQT4WIAf1Fv7K2wCDA8281qM"
}
```

## Användningsfall {#uc}

Det finns en Postman-samling som kan hjälpa dig med testning och konfiguration [här](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Throttling-API_postman-collection.json).

Den här Postman Collection har konfigurerats för att dela den Postman Variable-samling som genererats via __[Integreringar i Adobe I/O Console](https://console.adobe.io/integrations) > Testa > Ladda ned för Postman__, som genererar en Postman-miljöfil med de valda integreringsvärdena.

När du laddat ned och överfört till Postman måste du lägga till tre variabler: `{JO_HOST}`,`{BASE_PATH}` och `{SANDBOX_NAME}`.
* `{JO_HOST}` : [!DNL Journey Orchestration] Gateway-URL
* `{BASE_PATH}` : startpunkt för API. Värdet är /authoring
* `{SANDBOX_NAME}` : sidhuvudet **x-sandbox-name** (till exempel prod) som motsvarar namnet på sandlådan där API-åtgärderna ska utföras. Se [översikt över sandlådor](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html) för mer information.

I följande avsnitt hittar du listan med Rest API-anrop ordnade för att utföra fallstudien.

Användningsfall n°1: **Skapa och distribuera en ny begränsningskonfiguration**

1. lista
1. skapa
1. candeploy
1. driftsätta

Use-Case n°2: **Uppdatera och distribuera en begränsningskonfiguration som inte har distribuerats ännu**

1. lista
1. get
1. uppdatera
1. candeploy
1. driftsätta

Användningsfall nr 3: **Avdistribuera och ta bort en distribuerad begränsningskonfiguration**

1. lista
1. avdistribuera
1. delete

Användningsfall nr 4: **Ta bort en distribuerad begränsningskonfiguration**

I endast ett API-anrop kan du avdistribuera och ta bort konfigurationen med hjälp av parametern forceDelete.

1. lista
1. delete, with forceDelete param

Use-Case n°5: **Uppdatera en begränsningskonfiguration som redan har distribuerats**

>[!NOTE]
>
>Du behöver inte avdistribuera konfigurationen innan du uppdaterar

1. lista
1. get
1. uppdatera

## Konfigurationens livscykel på körningsnivå {#config}

När en konfiguration inte distribueras markeras den som inaktiv på körningsnivå och väntande händelser bearbetas under 24 timmar. Den tas sedan bort i runtime-tjänsten.

När en konfiguration har avdistribuerats är det möjligt att uppdatera och distribuera om konfigurationen. Detta skapar en ny runtime-konfiguration som kommer att beaktas i kommande åtgärder.

När du uppdaterar en konfiguration som redan har distribuerats beaktas de nya värdena omedelbart. De underliggande systemresurserna anpassas automatiskt. Detta är optimalt jämfört med att avdistribuera och sedan distribuera om konfigurationen.

## Exempel på svar {#responses}

**Skapa - POST**

```
{
    "canDeploy": {
        "validationStatus": "ok"
    },
    "createdElement": {
        "name": "throttling-config-external",
        "description": "example of throttling config for an external endpoint",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "PUT",
            "POST"
        ],
        "maxThroughput": 4000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T10:48:16.099647Z"
        },
        "state": "created",
        "authoringFormatVersion": "1.0"
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "created"
}
```

**Uppdatera - PUT**

```
{
    "updatedElement": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    },
    "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "uri": "/voyager/apis/throttlingConfigs/043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
    "resStatus": "updated",
    "canDeploy": {
        "validationStatus": "ok"
    }
}
```

**Läs (efter uppdatering) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z"
        },
        "state": "updated",
        "authoringFormatVersion": "1.0",
        "hasBeenDeployed": false
    }
}
```

**Läs (efter driftsättning) - GET**

```
{
    "result": {
        "_id": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6_8872a010-f91e-11ea-895c-11ef8f98ba52",
        "orgId": "AC202A3A5F615BD30A495FDE@AdobeOrg",
        "sandboxId": "8872a010-f91e-11ea-895c-11ef8f98ba52",
        "sandboxName": "prod",
        "uid": "043a1aea-2dfd-4965-b93a-cb9a1eced0e6",
        "urlPattern": "https://api.example.org/data/2.5/*",
        "methods": [
            "POST"
        ],
        "maxThroughput": 5000,
        "authoringFormatVersion": "1.0",
        "name": "throttling-config-external -- optional",
        "description": "example of throttling config for an external endpoint -- optional",
        "version": "1.0",
        "state": "deployed",
        "metadata": {
            "createdBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "createdById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "createdAt": "2023-03-22T10:48:16.099647Z",
            "lastModifiedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastModifiedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastModifiedAt": "2023-03-22T11:39:14.212983Z",
            "lastDeployedBy": "dacce1c3-d08b-4862-b434-2a4449c7e642@techacct.adobe.com",
            "lastDeployedById": "309F2A46640B0B300A495C83@techacct.adobe.com",
            "lastDeployedAt": "2023-03-22T11:46:07.532648Z"
        },
        "hasBeenDeployed": true
    }
}
```
