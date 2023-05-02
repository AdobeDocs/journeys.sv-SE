---
product: adobe campaign
title: Arbeta med API:t för begränsning
description: Läs mer om API:t för begränsning
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: 76afe397-3e18-4e01-9b0b-c21705927ce2
source-git-commit: 7b8c9d2bfe244b040a9064a7a240ea6f43cc8b41
workflow-type: tm+mt
source-wordcount: '800'
ht-degree: 95%

---

# Arbeta med API:t för begränsning

API:t för begränsning hjälper dig att skapa, konfigurera och övervaka dina begränsningskonfigurationer för att begränsa antalet händelser som skickas per sekund.

>[!IMPORTANT]
>
>Endast en konfiguration är för närvarande tillåten per organisation. En konfiguration måste definieras i en produktionssandlåda (anges via x-sandbox-name i rubrikerna).
>
>En konfiguration tillämpas på organisationsnivå.
>
>När gränsvärdet i API:t har uppnåtts köas ytterligare händelser i upp till sex timmar. Detta värde kan inte ändras.

## Beskrivning av API:et för begränsing {#description}

| Metod | Sökväg | Beskrivning |
|---|---|---|
| [!DNL POST] | list/throttlingConfigs | Hämta en lista över begränsningskonfigurationer |
| [!DNL POST] | /throttlingConfigs | Skapa en begränsningskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/deploy | Driftsätt en begränsningskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/undeploy | Avbryta driftsättning för en begränsningskonfiguration |
| [!DNL POST] | /throttlingConfigs/`{uid}`/canDeploy | Kontrollera om en begränsningskonfiguration kan driftsättas eller inte |
| [!DNL PUT] | /throttlingConfigs/`{uid}` | Uppdatera en begränsningskonfiguration |
| [!DNL GET] | /throttlingConfigs/`{uid}` | Hämta en begränsningskonfiguration |
| [!DNL DELETE] | /throttlingConfigs/`{uid}` | Radera en begränsningskonfiguration |

## Begränsningskonfiguration {#configuration}

Här är strukturen för en begränsningskonfiguration. Attributen **name** och **description** är valfria.

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

När en konfiguration skapas eller uppdateras validerar processen den angivna konfigurationen och returnerar den valideringsstatus som identifieras av dess unika ID, antingen:

```
"ok" or "error"
```

>[!IMPORTANT]
>
>Attributen **maxThroughput**, **urlPattern** och **methods** är obligatoriska.
>
>Värdet **maxThroughput** måste vara i intervallet 200–5 000.

Följande fel kan uppstå när du skapar, raderar eller distribuerar en begränsningskonfiguration:

* **ERR_THROTTLING_CONFIG_100**: begränsningskonfiguration: `<mandatory attribute>` obligatoriskt
* **ERR_THROTTLING_CONFIG_101**: begränsningskonfiguration: maxThroughput krävs och måste vara större än eller lika med 200 och mindre än eller lika med 5 000
* **ERR_THROTTLING_CONFIG_104**: begränsningskonfiguration: felformat URL-mönster
* **ERR_THROTTLING_CONFIG_105**: begränsningskonfiguration: jokertecken tillåts inte i värddelen av URL-mönstret
* **ERR_THROTTLING_CONFIG_106**: begränsningskonfiguration: ogiltig nyttolast
* **THROTTLING_CONFIG_DELETE_FORBIDDEN_ERROR: 1456**, ”Det gick inte att radera en driftsatt begränsningskonfiguration. Avbryt driftsättning innan den tas bort”
* **THROTTLING_CONFIG_DELETE_ERROR: 1457**, ”Det gick inte att radera begränsningskonfigurationen: ett oväntat fel inträffade”
* **THROTTLING_CONFIG_DEPLOY_ERROR: 1458**, ”Det gick inte att driftsätta begränsningskonfigurationen: ett oväntat fel inträffade”
* **THROTTLING_CONFIG_UNDEPLOY_ERROR: 1459**, ”Det gick inte att avbryta driftsättningen av begränsningskonfigurationen: ett oväntat fel inträffade”
* **THROTTLING_CONFIG_GET_ERROR: 1460**, ”Det gick inte att hämta begränsningskonfigurationen: ett oväntat fel inträffade”
* **THROTTLING_CONFIG_UPDATE_NOT_ACTIVE_ERROR: 1461**, ”Det gick inte att uppdatera begränsningskonfigurationen: körningsversionen är inte aktiv”
* **THROTTLING_CONFIG_UPDATE_ERROR: 1462**, ”Det gick inte att uppdatera begränsningskonfigurationen: ett oväntat fel inträffade”
* **THROTTLING_CONFIG_NON_PROD_SANDBOX_ERROR: 1463**, ”Åtgärden tillåts inte för begränsningskonfiguration: sandlåda ej för produktion”
* **THROTTLING_CONFIG_CREATE_ERROR: 1464**, ”Det gick inte att skapa begränsningskonfigurationen: ett oväntat fel inträffade”
* **THROTTLING_CONFIG_CREATE_LIMIT_ERROR: 1465**, ”Det gick inte att skapa begränsningskonfigurationen: endast en konfiguration tillåts per organisation”
* **THROTTLING_CONFIG_ALREADY_DEPLOYED_ERROR: 14466**, ”Det gick inte att driftsätta begränsningskonfigurationen: den är redan driftsatt”
* **THROTTLING_CONFIG_NOT_FOUND_ERROR: 14467**, ”begränsningskonfigurationen hittades inte”
* **THROTTLING_CONFIG_NOT_DEPLOYED_ERROR: 14468**, ”Det gick inte att avbryta driftsättningen av begränsningskonfigurationen: den är inte ännu driftsatt”

**Exempel på fel**

När du försöker skapa en konfiguration i en sandlåda som är ej för produktion:

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

Det finns en Postman-samling som kan hjälpa dig med testning och konfiguration [här](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Throttling-API_postman-collection.json).

Den här Postman-samlingen har konfigurerats för att dela den samling med Postman-variabler som genererats via __[Integreringar i Adobe I/O Console](https://console.adobe.io/integrations) > Testa > Hämta för Postman__, som genererar en Postman-miljöfil med de valda integreringsvärdena.

När du hämtat och laddat upp till Postman måste du lägga till tre variabler: `{JO_HOST}`,`{BASE_PATH}` och `{SANDBOX_NAME}`.
* `{JO_HOST}`: [!DNL Journey Orchestration] Gateway-URL
* `{BASE_PATH}`: startpunkt för API:et. Värdet är ”/authoring”
* `{SANDBOX_NAME}`: sidhuvudet **x-sandbox-name** (till exempel ”produktion”) som motsvarar namnet på sandlådan där API-åtgärderna utförs. Se [översikten över sandlådor](https://experienceleague.adobe.com/docs/experience-platform/sandbox/home.html?lang=sv) för mer information.

I följande avsnitt hittar du listan över Rest API-anrop ordnade för att utföra fallstudien.

Första användningsfallet: **Skapa och driftsätt en ny begränsningskonfiguration**

1. list
1. create
1. candeploy
1. deploy

Andra användningsfallet: **Uppdatera och driftsätt en begränsningskonfiguration som inte har distribuerats ännu**

1. list
1. get
1. update
1. candeploy
1. deploy

Tredje användningsfallet: **Avbryta driftsättning och radera en driftsatt begränsningskonfiguration**

1. list
1. undeploy
1. delete

Fjärde användningsfallet: **Radera en driftsatt begränsningskonfiguration**

I endast ett API-anrop kan du avbryta driftsättning och radera konfigurationen med hjälp av parametern forceDelete.

1. list
1. radera med parametern forceDelete

Femte användningsfallet: **Uppdatera en begränsningskonfiguration som redan har driftsatts**

>[!NOTE]
>
>Du behöver inte avbryta driftsättningen av konfigurationen innan du uppdaterar

1. list
1. get
1. update

## Konfigurationens livscykel på körningsnivå {#config}

När en konfiguration inte driftsätts markeras den som inaktiv på körningsnivå och väntande händelser fortsätter bearbetas under 24 timmar. Den raderas sedan i körningstjänsten.

När driftsättningen av en konfiguration har avbrutits är det möjligt att uppdatera och driftsätta konfigurationen igen. Detta skapar en ny körningskonfiguration som beaktas i körandet av kommande åtgärder.

När du uppdaterar en konfiguration som redan har driftsatts beaktas de nya värdena omedelbart. De underliggande systemresurserna anpassas automatiskt. Detta är optimalt jämfört med att avbryta driftsättningen och sedan driftsätta konfigurationen igen.

## Exempel på svar {#responses}

**Skapa – POST**

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

**Uppdatera – PUT**

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

**Läs (efter uppdatering) – GET**

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

**Läs (efter driftsättning) – GET**

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
