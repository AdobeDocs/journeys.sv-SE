---
title: Ytterligare steg för att skicka händelser till Journey Orchestration
description: Läs mer om ytterligare steg för att skicka händelser till Journey Orchestration
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '318'
ht-degree: 0%

---



# Ytterligare steg för att skicka händelser till [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>När du skapar en händelse genererar [!DNL Journey Orchestration] automatiskt ett ID för den här händelsen. Det system som skickar händelsen ska inte generera ett ID, det ska använda det som finns i nyttolastförhandsvisningen. Se [](../event/previewing-the-payload.md).

Om du vill konfigurera händelser som ska skickas till **[!UICONTROL Streaming Ingestion APIs]** och användas i [!DNL Journey Orchestration]måste du göra följande:

1. Hämta URL:en för inmatning från API:erna för dataplattformen (se API:er för [direktuppspelning av inmatning](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/overview.html)).
1. Kopiera nyttolasten från nyttolastförhandsvisningen på **[!UICONTROL Event]** menyn. Se [](../event/defining-the-payload-fields.md).

Sedan måste du konfigurera det datasystem som överför händelser till API:er för direktuppspelning av inmatning med den nyttolast som du kopierade:

1. Konfigurera ett POST API-anrop till API:n för direktuppspelning (kallas för inlopp).
1. Använd den nyttolast du kopierade från [!DNL Journey Orchestration] i brödtexten (&quot;dataavsnittet&quot;) för API-anropet till API:er för Streaming Ingput. Se nedan för ett exempel
1. Bestäm var alla variabler som finns i nyttolasten ska hämtas. Exempel: om händelsen ska förmedla adressen, kommer nyttolasten som klistras in att visa&quot;adress&quot;: &quot;string&quot;. &quot;string&quot; ska ersättas med variabeln som automatiskt fyller i rätt värde, e-postadressen till den person som meddelandet ska skickas till. Observera att vi i förhandsvisningen av nyttolasten, i avsnittet, automatiskt fyller i många värden som förväntas underlätta ditt arbete. **[!UICONTROL Header]**
1. Välj &quot;application/json&quot; som en texttyp.
1. Skicka ditt IMS ORG ID i huvudet med tangenten &quot;x-gw-ims-org-id&quot;. Använd ditt IMS ORG ID (&quot;XXX@AdobeOrg&quot;) för värdet.

Här är ett exempel på en API-händelse för direktuppspelning:

```
{
    "header": {
        "msgType": "xdmEntityCreate",
        "msgId": "c25585b9-252e-431d-b562-e73da70c04e7",
        "msgVersion": "1.0",
        "xactionId": "f5995abe-c49d-4848-9577-a7a4fc2996fb",
        "datasetId": "string - required if you want the data to land in a specific dataset - not mandatory",
        "imsOrgId": "XXX@AdobeOrg",
        "schemaRef": {
            "id": "XXX",
            "contentType": "application/vnd.adobe.xed-full+json;version=1"
        },
        "source": {
            "name": "Journeys"
        }
    },
    "body": {
        "xdmMeta": {
            "schemaRef": {
                "id": "XXX",
                "contentType": "application/vnd.adobe.xed-full+json;version=1"
            }
        },
        "xdmEntity": {
            "_instance_name": {
                "person": {
                    "firstName": "string",
                    "lastName": "string",
                    "gender": "string",
                    "birthYear": 10,
                    "emailAddress": "string"
                }
            },
            "identityMap": {
                "Email": [
                {
                    "id": "string"
                    }
                ]
            },
            "_id": "string",
            "timestamp": "2018-05-29T00:00:00.000Z",
            "_experience": {
                "campaign": {
                    "orchestration": {
                    "eventID": "XXX"
                    }
                }
            }
        }
    }
}
```

För att underlätta identifieringen av den plats där delen&quot;data&quot; ska klistras in kan du använda ett JSON-visualiseringsverktyg som [https://jsonformatter.curiousconcept.com](https://jsonformatter.curiousconcept.com)

Information om hur du felsöker API:er för direktuppspelning finns på den här [sidan](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/troubleshooting.html).
