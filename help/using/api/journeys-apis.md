---
product: adobe campaign
title: Kom igång med API:er för resor
description: Läs mer om API:er för resor
products: journeys
feature: Journeys
role: User
level: Intermediate
exl-id: a5dd3d23-c820-4ab7-bc6c-b1dcfe15022c
source-git-commit: 8f409fe6e37a3b80527d9a5514b066e539dcd9f3
workflow-type: tm+mt
source-wordcount: '828'
ht-degree: 84%

---

# Kom igång med API:er för resor

## Om API:er för reglering och begränsning

När du konfigurerar en datakälla eller en åtgärd upprättar du en anslutning till ett system för att antingen hämta ytterligare information som ska användas under dina resor eller skicka meddelanden eller API-anrop.

API:er för resor har stöd för upp till 5 000 händelser per sekund, men vissa externa system eller API:er har kanske inte samma genomströmning. Om du vill förhindra att dessa system överbelastas kan du använda API:erna **Reglering** och **Begränsning** som begränsar antalet händelser som skickas per sekund.

Varje gång ett API-anrop utförs via resor skickas det via API-motorn. Om gränsvärdet i API:et nås avvisas anropet om du använder API:et för reglering, eller köas upp till sex timmar och behandlas så snart som möjligt i den ordning som de togs emot om du använder API:et för begränsning.

Anta till exempel att du har definierat en begränsning eller begränsning på 100 anrop per sekund för det externa systemet. Ditt system anropas av en anpassad åtgärd på tio olika resor. Om en resa tar emot 200 anrop per sekund används de 100 tillgängliga facken och de 100 återstående facken tas bort eller köas. Eftersom den högsta nivån har överskridits har de övriga nio resorna inte några fack kvar. Denna precision hjälper till att skydda det externa systemet från överbelastning och krascher.

>[!IMPORTANT]
>
>**Regleringsregler** är konfigurerade på sandlådenivå, för en specifik slutpunkt (den anropade URL:en), men är globala till alla resor i den sandlådan.
>
>**Begränsningsregler** konfigureras endast för produktionssandlådor, för en specifik slutpunkt, men är globala för alla resor över alla sandlådor. Du kan bara ha en begränsningskonfiguration per organisation.

Mer information om hur du arbetar med dessa API:er finns i följande avsnitt:

* [API för reglering](capping.md)
* [API för begränsning](throttling.md)

Båda API:erna beskrivs också i en tillgänglig Swagger-fil [här](https://adobedocs.github.io/JourneyAPI/docs/).

## Datakällor och kapacitet för anpassade åtgärder {#capacity}

För **externa datakällor** är det maximala antalet anrop per sekund begränsat till femton. Om den här gränsen överskrids, ignoreras eller köas eventuella ytterligare anrop beroende på vilket API som används. Det är möjligt att öka denna gräns för privata externa datakällor genom att kontakta Adobe för att inkludera slutpunkten i tillåtelselistan, men detta är inte ett alternativ för offentliga externa datakällor. * [Läs mer om hur du konfigurerar datakällor](../datasource/about-data-sources.md).

>[!NOTE]
>
>Om en datakälla använder en anpassad autentisering med en annan slutpunkt än den som används för datakällan måste du kontakta Adobe för att även inkludera den slutpunkten i tillåtelselistan.

För **anpassade åtgärder** måste du utvärdera kapaciteten för ditt externa API. Om Journey Optimizer t.ex. skickar 1 000 anrop per sekund och systemet bara har stöd för 100 anrop per sekund, måste du definiera en konfiguration för reglering eller begränsning så att systemet inte blir mättat. [Läs mer om hur du konfigurerar åtgärder](../action/action.md)

## Konfigurera API-åtkomst {#api}

För att använda dessa API:er med instansen [!DNL Journey Orchestration] måste du till exempel använda Adobe I/O Console. [!DNL Journey Orchestration] API-åtkomst konfigureras genom stegen nedan. Varje steg beskrivs i [Dokumentation för Adobe I/O](https://www.adobe.io/authentication/auth-methods.html#!AdobeDocs/adobeio-auth/master/AuthenticationOverview/ServiceAccountIntegration.md).

>[!CAUTION]
>
>Kontrollera att du är en berättigad <b>systemadministratör</b> i organisationen eller att du har ett [utvecklarkonto](https://helpx.adobe.com/se/enterprise/using/manage-developers.html) i Admin Console för att hantera certifikat i Adobe I/O.

1. **Kontrollera att du har ett digitalt certifikat** eller skapa ett vid behov. De offentliga och privata nycklarna som tillhandahålls med certifikatet behövs i följande steg.
1. **Skapa en ny integrering med [!DNL Journey Orchestration] Tjänst** i Adobe I/O och konfigurera den. Du behöver åtkomst till produktprofilen för [!DNL Journey Orchestration] och till Adobe Experience Platform. Dina autentiseringsuppgifter genereras sedan (API-nyckel, klienthemlighet ...).

>[!CAUTION]
>
>JWT-metoden för att generera åtkomsttoken har tagits bort. Alla nya integreringar måste skapas med [OAuth Server-till-Server-autentiseringsmetod](https://experienceleague.adobe.com/docs/experience-platform/landing/platform-apis/api-authentication.html#select-oauth-server-to-server). Adobe rekommenderar också att du migrerar dina befintliga integreringar till OAuth-metoden.
>
>Läs följande viktiga dokumentation:
>[Migreringsguide för program från JWT till OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/),
>[Implementeringsguide för nya och gamla program med OAuth](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/implementation/),
>[Fördelar med att använda inloggningsmetoden OAuth Server-till-Server](https://developer.adobe.com/developer-console/docs/guides/authentication/ServerToServerAuthentication/migration/#why-oauth-server-to-server-credentials)

För att upprätta en säker tjänst-till-tjänst Adobe I/O API-session måste varje begäran till en Adobe-tjänst innehålla informationen nedan i auktoriseringshuvudet.

```
curl -X GET https://journey.adobe.io/authoring/XXX \
 -H 'Authorization: Bearer <ACCESS_TOKEN>' \
 -H 'x-api-key: <API_KEY>' \
 -H 'x-gw-ims-org-id: <ORGANIZATION>'
```

* **&lt;ORGANIZATION>**: Detta är ditt personliga organisations-ID, och Adobe tillhandahåller ett organisations-ID för varje instans. Kontakta din administratör eller din teknikkunniga Adobe-kontakt för att få ditt organisations-ID-värde. Du kan även hämta det till Adobe I/O när du skapar en ny integrering i licenslistan (se <a href="https://www.adobe.io/authentication.html">Dokumentation för Adobe I/O</a>).

* **&lt;access_token>**: Din personliga åtkomsttoken

* **&lt;API_KEY>**: Din egen API-nyckel. Det tillhandahålls i Adobe I/O efter att en ny integrering av tjänsten [!DNL Journey Orchestration] har skapats.
