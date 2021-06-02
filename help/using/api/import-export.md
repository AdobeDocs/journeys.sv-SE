---
product: adobe campaign
title: Importera beskrivning av export-API
description: Läs mer om import-API:t för export.
products: journeys
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '1131'
ht-degree: 2%

---


# Arbeta med Export-Import API

Exportera en reseversion och alla tillhörande objekt (resa, händelser, datakällor, fältgrupper, anpassade åtgärder) med ett enda API-anrop. Den resulterande nyttolasten kan användas för att enkelt importera resan till en annan miljö (instans eller sandlåda).
Med den här funktionen kan du hantera dina resor över flera instanser eller för flera arbetsflöden för testmiljöer.


## Resurser

API:t för export/import av Journey Orchestration beskrivs i en Swagger-fil som är tillgänglig [här](https://adobedocs.github.io/JourneyAPI/docs/).

Om du vill använda detta API med din Journey Orchestration-instans måste du använda AdobeI/O-konsolen. Du kan börja med att följa detta [Komma igång med Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) och sedan använda avsnitten på den här sidan.

För att testa och förbereda integreringen finns en Postman-samling [här](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Export-Import-flöde

Vi rekommenderar att du följer de här stegen för att exportera och importera dina resor mellan olika miljöer:

1. Skapa och parametera en resa i din startmiljö. [Mer information här](https://docs.adobe.com/content/help/sv-SE/journeys/using/building-journeys/about-journey-building/journey.html)
1. Kontrollera om reseversionen inte innehåller något fel. [Mer information här](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. Ring **/list/travel** API för att hämta UID-resan och UID:t för den senaste reseversionen. Om det behövs kan du ringa **/neys/`{uid}`/latest** för att hitta UID:t för din senaste reseversion.
1. Anropa **export**-API:t med dina startmiljöparametrar (orgID och sandboxName).
1. Öppna den returnerade nyttolasten och kontrollera följande objekt:
   * Om din exporterade resa innehåller **specifika autentiseringsuppgifter** måste du ersätta dessa autentiseringsuppgifter med de som motsvarar den nya miljön.
   * Om din exporterade resa innehåller **händelser** som pekar på ett **XDM-schema**, måste du uppdatera schema-ID-referensen manuellt med schema-ID:t för den nya miljön i xdmEntity-noden om ID:n-värdena är olika. Den här uppdateringen måste göras för varje händelse. [Mer information här](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * Om din resa innehåller e-post, sms eller push-åtgärder kan du behöva uppdatera mallnamnet eller namnet på mobileApp om namnet i målmiljön skiljer sig från det i startmiljön.
1. Anropa **Import**-API:t med målmiljöparametrarna (orgID och sandboxName). Observera att du kan anropa import-API:t så många gånger du vill. UUID och namnet på varje objekt som ingår i resan genereras varje gång du anropar import-API:t.
1. När resan har importerats kan du publicera den i programmet Journey Orchestration. Mer information [här](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/publishing-the-journey.html)


## Behörighet

### Konfigurera API-åtkomst

API-åtkomst för Journey Orchestration konfigureras genom stegen nedan. Var och en av dessa steg beskrivs i [Adobe I/O-dokumentationen](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Om du vill hantera certifikat i Adobe I/O måste du ha <b>systemadministratörsbehörighet</b> för organisationen eller ett [utvecklarkonto](https://helpx.adobe.com/enterprise/using/manage-developers.html) i Admin Console.

1. **Kontrollera att du har ett digitalt certifikat** eller skapa ett om det behövs. De offentliga och privata nycklarna som tillhandahålls med certifikatet behövs i följande steg.
1. **Skapa en ny integrering för  [!DNL Journey Orchestration]** ServiceIn Adobe I/O och konfigurera den. Åtkomst till produktprofilen krävs för Journey Orchestration och Adobe Experience Platform. Dina autentiseringsuppgifter genereras sedan (API-nyckel, klienthemlighet...).
1. **Skapa en JSON Web Token (JWT)** utifrån de inloggningsuppgifter som tidigare genererats och signera den med din privata nyckel. JWT kodar all identitets- och säkerhetsinformation som Adobe behöver för att verifiera din identitet och ge dig åtkomst till API:t. Det här steget beskrivs närmare i det här [avsnittet](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Byt ut din JWT mot en Access-** token via en POST-förfrågan eller via gränssnittet för Developer Console. Denna Access Token måste användas i varje rubrik för dina API-begäranden.

Om du vill skapa en säker tjänst-till-tjänst-API-session mellan Adobe I/O måste varje begäran till en Adobe-tjänst innehålla informationen nedan i auktoriseringshuvudet.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;organization>**: Detta är ditt personliga organisations-ID, och Adobe tillhandahåller ett organisations-ID för varje instans:

   * &lt;organization> : din produktionsinstans
   Kontakta din administratör eller din Adobe tekniska kontakt för att få ditt organisations-ID-värde. Du kan även hämta den till Adobe I/O när du skapar en ny integrering i licenslistan (se [Adobe I/O-dokumentationen](https://www.adobe.io/authentication.html)).

* **&lt;access_token>**: Din personliga åtkomsttoken, som hämtades när du bytte din JWT via en POST.

* **&lt;api_key>**: din egen API-nyckel. Det tillhandahålls i Adobe I/O efter att en ny integrering till [!DNL Journey Orchestration]-tjänsten har skapats.



## API-beskrivning för export-import

Med det här API:t kan du exportera en reseversion som identifieras av dess UID och alla relaterade objekt (resa, händelser, datakällor, fältgrupper, anpassade åtgärder) via dess uid.
Den resulterande nyttolasten kan användas för att importera reseversionen till en annan miljö (sandlåda eller instans).

| Metod | Bana | Beskrivning |
|---|---|---|
| `[POST]` | /travelVersions/import | Importera innehåll från en reseversion som är ett resultat av en reseversionsexport |
| `[GET]` | /travelVersions/`{uid}`/export | Exportera en reseversion |
| `[GET]` | /neys/`{uid}`/senaste | Skaffa den senaste versionen för en resa |
| `[POST]` | /list/travel | Ange metadata för resorna och deras resversioner |


### Exportegenskaper och skyddsräcken

* Resan måste vara giltig före export.

* Referenserna exporteras inte och en platshållare (t.ex. INSERT_SECRET_HERE) infogas i svarsnyttolasten.
Efter exportanropet måste du manuellt infoga de nya autentiseringsuppgifterna (som motsvarar målmiljön) innan du importerar nyttolasten i målmiljön.

* Följande objekt exporteras, men de kommer aldrig att importeras i målmiljön. Det här är systemresurser som hanteras automatiskt av Journey Orchestration. Du behöver inte ersätta INSERT_SECRET_HERE.
   * **DataProviders**: &quot;Adobe Campaign Standard Data Provider&quot; (acsDataProvider) och &quot;Experience Platform&quot; (acppsDataProvider)
   * **Fältgrupper** (dataEntities): &quot;ProfileFieldGroup&quot; (acppsDataPack)



### Importegenskaper

* Under importen skapas färgobjekten med ett nytt UID och ett nytt namn för att säkerställa att de är unika i målmiljön (instans eller sandlåda).

* Om importnyttolasten innehåller hemliga platshållare genereras ett fel. Du måste ersätta inloggningsuppgifterna innan POSTEN anropar för att kunna importera resan.

## Varningar och fel

Möjliga fel är:

* Vid **exporttid**, om reseversionen inte är giltig: fel 500

* Vid **importtid**, om nyttolasten inte är giltig efter ändringar eller om autentiseringsuppgifterna inte är väl definierade i nyttolasten: fel 400

* Om XDM-schema-ID:t för dina händelser inte är giltigt i målmiljön efter importsteget visas ett fel i programmet Journey Orchestration. I så fall kommer det inte att vara möjligt att offentliggöra resan.