---
product: adobe campaign
title: Ytterligare steg för att skicka händelser till Journey Orchestration
description: Läs mer om hur du skickar händelser till Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: 11e337c6-5e05-4898-9953-b6b821af8fd1
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '319'
ht-degree: 4%

---

# Ytterligare steg för att skicka händelser till [!DNL Journey Orchestration] {#concept_xrz_n1q_y2b}

>[!NOTE]
>
>När du skapar en händelse [!DNL Journey Orchestration] genererar automatiskt ett ID för den här händelsen. Det system som skickar händelsen ska inte generera ett ID, det ska använda det som finns i nyttolastförhandsvisningen. Läs [den här sidan](../event/previewing-the-payload.md).

Så här konfigurerar du händelser som ska skickas till **[!UICONTROL Streaming Ingestion APIs]** och ska användas i [!DNL Journey Orchestration]måste du följa dessa steg:

1. Hämta inlopps-URL:en från Adobe Experience Platform API:er (se [API:er för direktuppspelande inmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/overview.html?lang=sv)).
1. Kopiera nyttolasten från nyttolastförhandsvisningen i **[!UICONTROL Event]** -menyn. Läs [den här sidan](../event/defining-the-payload-fields.md).

Sedan måste du konfigurera det datasystem som överför händelser till API:er för direktuppspelning av inmatning med den nyttolast som du kopierade:

1. Konfigurera ett POST-API-anrop till API:n för direktuppspelning (kallas för ett inlopp).
1. Använd nyttolasten som du kopierade från [!DNL Journey Orchestration] i brödtexten (&quot;dataavsnittet&quot;) för API-anropet till API:er för Streaming Ingmit. Se nedan för ett exempel
1. Bestäm var alla variabler som finns i nyttolasten ska hämtas. Exempel: om händelsen ska förmedla adressen, kommer nyttolasten som klistras in att visa&quot;adress&quot;: &quot;string&quot;. &quot;string&quot; ska ersättas med variabeln som automatiskt fyller i rätt värde, e-postadressen till den person som meddelandet ska skickas till. Observera att i nyttolastförhandsvisningen i **[!UICONTROL Header]** fyller vi automatiskt i många värden som förväntas underlätta arbetet.
1. Välj &quot;application/json&quot; som en texttyp.
1. Skicka ditt IMS-organisations-ID i huvudet med tangenten &quot;x-gw-ims-org-id&quot;. Använd ditt IMS-organisations-ID (&quot;XXX@AdobeOrg&quot;) för värdet.

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

Information om hur du felsöker API:er för direktuppspelning finns i detta [page](https://experienceleague.adobe.com/docs/experience-platform/ingestion/streaming/troubleshooting.html).
