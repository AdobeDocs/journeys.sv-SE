---
title: Importera beskrivning av export-API
description: Läs mer om import-API:t för export.
contentOwner: sauviat
products: journeys
audience: audiences
content-type: reference
topic-tags: journeys
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: c92d7a4e5ef02f87f705871cd0fdb8c2523966d2
workflow-type: tm+mt
source-wordcount: '1103'
ht-degree: 2%

---


# Arbeta med Export Import API

Exportera en reseversion och alla tillhörande objekt (resa, händelser, datakällor, fältgrupper, anpassade åtgärder) med ett enda API-anrop. Den resulterande nyttolasten kan användas för att enkelt importera resan till en annan miljö (instans eller sandlåda).
Med den här funktionen kan du hantera dina resor över flera instanser eller för flera arbetsflöden för testmiljöer.


## Resurser

API:t för export av Journey Orchestration beskrivs i en Swagger-fil som finns [här](https://adobedocs.github.io/JourneyAPI/docs/).

Om du vill använda detta API med din Journey Orchestration-instans måste du använda AdobeI/O-konsolen. Du kan börja med att följa detta [Komma igång med Adobe Developer Console](https://www.adobe.io/apis/experienceplatform/console/docs.html#!AdobeDocs/adobeio-console/master/getting-started.md) och sedan använda avsnitten på den här sidan.

För att testa och förbereda integreringen finns en Postman-samling [här](https://raw.githubusercontent.com/AdobeDocs/JourneyAPI/master/postman-collections/Journey-Orchestration_Export-import-API_postman-collection.json).


## Export-Import-flöde

Vi rekommenderar att du följer de här stegen för att exportera och importera dina resor mellan olika miljöer:

1. Skapa och parametera en resa i din startmiljö. [Mer information här](https://docs.adobe.com/content/help/sv-SE/journeys/using/building-journeys/about-journey-building/journey.html)
1. Kontrollera om reseversionen inte innehåller något fel. [Mer information här](https://docs.adobe.com/content/help/en/journeys/using/building-journeys/testing-the-journey.html)
1. Anropa **/lista/rese** -API för att hämta UID-resan och UID:t för den senaste reseversionen. Vid behov kan du ringa **/resa/`{uid}`/senaste** för att hitta UID:t för den senaste reseversionen.
1. Anropa **export** -API:t med dina startmiljöparametrar (orgID och sandboxName).
1. Öppna den returnerade nyttolasten och kontrollera följande objekt:
   * Om din exporterade resa innehåller **specifika autentiseringsuppgifter** måste du ersätta dessa med de som motsvarar den nya miljön.
   * Om den exporterade resan innehåller **händelser** som pekar på ett **XDM-schema** måste du uppdatera schema-ID-referensen manuellt med schema-ID:t för den nya miljön i xdmEntity-noden om ID:n är olika. Den här uppdateringen måste göras för varje händelse. [Mer information här](https://docs.adobe.com/content/help/en/journeys/using/events-journeys/experience-event-schema.html)
   * Om din resa innehåller e-post, sms eller push-åtgärder kan du behöva uppdatera mallnamnet eller namnet på mobileApp om namnet i målmiljön skiljer sig från det i startmiljön.
1. Anropa **import** -API:t med målmiljön. Observera att du kan anropa import-API:t så många gånger du vill. UUID:t och namnet på varje nod som ingår i resan genereras varje gång du anropar import-API:t.
1. När resan har importerats kan du publicera den i den nya sandlådan eller den nya miljön.


## Behörighet

### Konfigurera API-åtkomst

API-åtkomst för Journey Orchestration konfigureras genom stegen nedan. Var och en av dessa steg beskrivs i dokumentationen [för](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md)Adobe I/O.

>[!CAUTION]
>
>Om du vill hantera certifikat i Adobe I/O måste du ha <b>systemadministratörsbehörighet</b> för organisationen eller ett [utvecklarkonto](https://helpx.adobe.com/enterprise/using/manage-developers.html) i Admin Console.

1. **Kontrollera att du har ett digitalt certifikat** eller skapa ett om det behövs. De offentliga och privata nycklarna som tillhandahålls med certifikatet behövs i följande steg.
1. **Skapa en ny integrering för[!DNL Journey Orchestration]Service** i Adobe I/O och konfigurera den. Åtkomst till produktprofilen krävs för Journey Orchestration och Adobe Experience Platform. Dina autentiseringsuppgifter genereras sedan (API-nyckel, klienthemlighet...).
1. **Skapa en JSON Web Token (JWT)** utifrån de inloggningsuppgifter som tidigare genererats och signera den med din privata nyckel. JWT kodar all identitets- och säkerhetsinformation som Adobe behöver för att verifiera din identitet och ge dig åtkomst till API:t. Det här steget beskrivs i det här [avsnittet](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/JWT/JWT.md)
1. **Byt ut din JWT-fil mot en åtkomsttoken** via en POST-förfrågan eller via gränssnittet för Developer Console. Denna Access Token måste användas i varje rubrik för dina API-begäranden.

Om du vill skapa en säker tjänst-till-tjänst-API-session mellan Adobe måste varje begäran till en Adobe-tjänst innehålla informationen nedan i auktoriseringshuvudet.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANISATION>**: Detta är ditt personliga organisations-ID, och Adobe tillhandahåller ett organisations-ID för varje instans:

   * &lt;ORGANISATION>: din produktionsinstans
   Kontakta din administratör eller din Adobe tekniska kontakt för att få ditt organisations-ID-värde. Du kan även hämta den till Adobe när du skapar en ny integrering i licenslistan (se dokumentationen [för](https://www.adobe.io/authentication.html)Adobe).

* **&lt;ACCESS_TOKEN>**: Din personliga åtkomsttoken, som hämtades när du bytte din JWT via en POST.

* **&lt;API_KEY>**: din egen API-nyckel. Det tillhandahålls i Adobe I/O efter att en ny integrering till [!DNL Journey Orchestration] Service har skapats.



## API-beskrivning för export

Med detta API kan du exportera en reseversion och alla relaterade objekt (resa, händelser, datakällor, fältgrupper, anpassade åtgärder) via dess ID.
Den resulterande nyttolasten kan användas för att importera reseversionen till en annan miljö (sandlåda eller instans).

| Metod | Bana | Beskrivning |
|---|---|---|
| `[POST]` | /travelVersions/import | Importera innehåll från en reseversion som är ett resultat av en reseversionsexport |
| `[GET]` | /travelVersions/`{uid}`/export | Exportera en reseversion |
| `[GET]` | /neys/`{uid}`/latest | Skaffa den senaste versionen för en resa |
| `[POST]` | /list/travel | Ange metadata för resorna och deras resversioner |


### Exportegenskaper och skyddsräcken

* Referenserna exporteras inte och en platshållare (t.ex. INSERT_SECRET_HERE) infogas.
Efter nyttolastexporten måste du manuellt infoga de nya autentiseringsuppgifterna (som motsvarar målmiljön) innan du importerar nyttolasten i målmiljön.

* När datakällan innehåller parametern **builtIn:true** behöver du inte ersätta INSERT_SECRET_HERE. Det här är en systemdatakälla som hanteras automatiskt av resemiljön.

* Följande objekt exporteras men kommer aldrig att importeras i målmiljön:
   * **DataProviders**:  acsDataProvider och acppsDataProvider
   * **Fältgrupper**: acppsFieldGroup
   * **Anpassade åtgärder**: acsAction

* Resan måste vara giltig före export.

### Importegenskaper

* Under importen skapas färgobjekten med ett nytt UUID och ett nytt namn för att säkerställa att de är unika i målmiljön (instans eller sandlåda).

* Om importnyttolasten innehåller hemliga platshållare genereras ett fel. Du måste ersätta inloggningsuppgifterna innan POSTEN anropar för att kunna importera resan.

## Varningar och fel

Möjliga fel är:

* Vid **export**, om reseversionen inte är giltig: fel 500

* Vid **import**, om nyttolasten inte är giltig efter ändringar eller om autentiseringsuppgifterna inte är väl definierade i nyttolasten: fel 400

* Om du efter importsteget försöker publicera resan i målmiljön utan att ändra XDM-schema-ID för dina händelser, visas ett fel.

