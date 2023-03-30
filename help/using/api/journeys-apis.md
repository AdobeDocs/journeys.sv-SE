---
product: adobe campaign
title: Kom igång med rese-API:er
description: Läs mer om rese-API:er
products: journeys
feature: Journeys
role: User
level: Intermediate
source-git-commit: 137637a753ba44cc4f8e397b77c3fc076ec3de3f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 1%

---

# Kom igång med rese-API:er

## Om API:er för begränsning och begränsning

När du konfigurerar en datakälla eller en åtgärd upprättar du en anslutning till ett system för att antingen hämta ytterligare information som ska användas under dina resor eller skicka meddelanden eller API-anrop.

Journeys API:er har stöd för upp till 5 000 händelser per sekund, men vissa externa system eller API har kanske inte samma genomströmning. Om du vill förhindra att dessa system överbelastas kan du använda **Takning** och **Begränsning** API:er som begränsar antalet händelser som skickas per sekund.

Varje gång ett API-anrop utförs via resor, skickas det via API-motorn. Om gränsvärdet i API:t nås, avvisas anropet antingen om du använder API:t för begränsning, eller köas och behandlas så snart som möjligt i den ordning de togs emot om du använder API:t för begränsning.

Anta till exempel att du har definierat en begränsning eller begränsning på 100 anrop per sekund för det externa systemet. Ditt system anropas av en anpassad åtgärd på tio olika resor. Om en resa tar emot 200 samtal per sekund används de 100 tillgängliga kortplatserna och de 100 återstående kortplatserna tas bort eller köas. Eftersom den högsta nivån har överskridits kommer de övriga nio resorna inte att ha några platser kvar. Denna granularitet hjälper till att skydda det externa systemet från överbelastning och krascher.

>[!IMPORTANT]
>
>**Begränsningsregler** är konfigurerade på sandlådenivå, för en specifik slutpunkt (den anropade URL:en), men globala till alla resor i den sandlådan.
>
>**Begränsningsregler** konfigureras endast för produktionssandlådor, för en specifik slutpunkt, men globalt för alla resor över alla sandlådor. Du kan bara ha en begränsningskonfiguration per organisation.

Mer information om hur du arbetar med dessa API:er finns i följande avsnitt:

* [API för begränsning](capping.md)
* [Begränsnings-API](throttling.md)

Båda API:erna beskrivs också i en tillgänglig Swagger-fil [här](https://adobedocs.github.io/JourneyAPI/docs/).

## Datakällor och kapacitet för anpassade åtgärder {#capacity}

För **externa datakällor**, är det maximala antalet anrop per sekund begränsat till 15. Om den här gränsen överskrids, ignoreras eller köas eventuella ytterligare anrop beroende på vilket API som används. Det är möjligt att öka denna gräns för privata externa datakällor genom att kontakta Adobe för att inkludera slutpunkten i tillåtelselista, men detta är inte ett alternativ för offentliga externa datakällor. * [Lär dig konfigurera datakällor](../datasource/about-data-sources.md).

>[!NOTE]
>
>Om en datakälla använder en anpassad autentisering med en annan slutpunkt än den som används för datakällan måste du kontakta Adobe för att även inkludera den slutpunkten i tillåtelselista.

För **anpassade åtgärder** måste du utvärdera kapaciteten för ditt externa API. Om Journey Optimizer t.ex. skickar 1 000 samtal per sekund och systemet bara har stöd för 100 samtal per sekund, måste du definiera en konfiguration för begränsning eller begränsning så att systemet inte blir mättat. [Lär dig hur du konfigurerar åtgärder](../action/action.md)

## Konfigurera API-åtkomst {#api}

Så här använder du dessa API:er med [!DNL Journey Orchestration] Du måste till exempel använda AdobeI/O-konsolen. [!DNL Journey Orchestration] API-åtkomst konfigureras genom stegen nedan. Varje steg beskrivs i [Adobe I/O dokumentation](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

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

* **&lt;organization>**: Detta är ditt personliga organisations-ID, och Adobe tillhandahåller ett organisations-ID för varje instans. Kontakta din administratör eller din Adobe tekniska kontakt för att få ditt organisations-ID-värde. Du kan även hämta den till Adobe I/O när du skapar en ny integrering i licenslistan (se <a href="https://www.adobe.io/authentication.html">Adobe I/O dokumentation</a>).

* **&lt;access_token>**: Din personliga åtkomsttoken, som hämtades när du bytte din JWT via en POST.

* **&lt;api_key>**: din egen API-nyckel. Det tillhandahålls i Adobe I/O efter att en ny integrering av [!DNL Journey Orchestration] Tjänst.
