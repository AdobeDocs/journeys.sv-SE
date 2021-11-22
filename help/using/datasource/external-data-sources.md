---
product: adobe campaign
title: 'Externa datakällor '
description: 'Läs om hur du konfigurerar externa datakällor '
feature: Journeys
role: User
level: Intermediate
exl-id: 9b666c15-2215-4ca5-bc72-40109749dc15
source-git-commit: 7805ee4beb056ba84bc994162da2b0e54db60ca3
workflow-type: tm+mt
source-wordcount: '1318'
ht-degree: 93%

---

# Externa datakällor {#concept_t2s_kqt_52b}

Med externa datakällor kan du definiera en anslutning till tredjepartssystem om du till exempel använder ett bokningssystem för hotell som kontrollerar om personen har registrerat ett rum. I motsats till den inbyggda datakällan i Adobe Experience Platform kan du skapa så många externa datakällor som behövs.

Stöd finns för REST API:er som använder POST eller GET och returnerar JSON. API-nyckel samt grundläggande och anpassade autentiseringslägen stöds.

Låt oss använda en API-tjänst för väder som exempel. Jag vill använda den för att anpassa resans beteenden beroende på väderdata i realtid.

Här är två exempel på API-anropet:

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

Anropet består av en huvud-URL (_https://api.adobeweather.org/weather_), två parameteruppsättningar (&quot;city&quot; för staden och &quot;lat/long&quot; för latitud och longitud) och API-nyckeln (appid).

Här följer de viktigaste stegen för att skapa och konfigurera en ny extern datakälla:

1. Klicka på i listan över datakällor **[!UICONTROL Create data source]** för att skapa en ny extern datakälla.

   ![](../assets/journey25.png)

   Detta öppnar konfigurationsfönstret för datakällan till höger på skärmen.

   ![](../assets/journey26.png)

1. Ange ett namn för datakällan.

   >[!NOTE]
   >
   >Använd inte blanksteg eller specialtecken. Använd maximalt 30 tecken.

1. Lägg till en beskrivning om datakällan. Det här steget är valfritt.
1. Lägg till den externa tjänstens URL. I vårt exempel: _https://api.adobeweather.org/weather_.

   >[!CAUTION]
   >
   >Vi rekommenderar starkt att HTTPS används av säkerhetsskäl. Observera också att vi endast tillåter att Adobe-adresser som är allmänt tillgängliga samt IP-adresser används.

   ![](../assets/journey27.png)

1. Konfigurera autentiseringen beroende på den externa tjänstens konfiguration: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** eller **[!UICONTROL API key]**. Mer information om det anpassade autentiseringsläget finns i [det här avsnittet](../datasource/external-data-sources.md#section_wjp_nl5_nhb). I vårt exempel väljer vi:


   * **[!UICONTROL Type]**: &quot;API-nyckel&quot;
   * **[!UICONTROL Value]**: &quot;1234&quot; (det här är värdet på vår API-nyckel)
   * **[!UICONTROL Name]**: &quot;appid&quot; (det här är API-nyckelns parameternamn)
   * **[!UICONTROL Location]**: &quot;Frågeparameter&quot; (API-nyckeln finns i webbadressen)

   ![](../assets/journey28.png)

1. Klicka på **[!UICONTROL Add a New Field Group]** för att lägga till en ny fältgrupp för varje API-parameteruppsättning. Använd inte blanksteg eller specialtecken i fältgruppens namn. I vårt exempel behöver vi skapa två fältgrupper. En för varje parameteruppsättning (&quot;city&quot; och &quot;long/lat&quot;).

För parameteruppsättningen &quot;long/lat&quot; skapar vi en fältgrupp med följande information:

* **[!UICONTROL Used in]**: visar antalet resor som använder en fältgrupp. Du kan klicka på ikonen **[!UICONTROL View journeys]** för att visa en lista över resor som använder den här fältgruppen.
* **[!UICONTROL Method]**: välj metoden POST eller GET. I vårt fall väljer vi metoden GET.
* **[!UICONTROL Response Payload]**: klicka inuti fältet **[!UICONTROL Payload]** och klistra in ett exempel på nyttolasten som returneras av anropet. Vi har till exempel använt en nyttolast som finns på en API-webbplats för väder. Kontrollera att fälttyperna är korrekta. Varje gång API:et anropas hämtas alla fält som ingår i exemplets nyttolast. Observera att du kan klicka på **[!UICONTROL Paste a new payload]** för att ändra den nyttolast som för närvarande används.
* **[!UICONTROL Dynamic Values]**: ange de olika parametrarna avgränsade med kommatecken – &quot;long,lat&quot; i vårt exempel. Eftersom parameterns värden är beroende av körningens sammanhang definieras de i resorna. Läs [den här sidan](../expression/expressionadvanced.md).
* **[!UICONTROL Sent Payload]**: det här fältet visas inte i vårt exempel. Det är endast tillgängligt om du väljer metoden POST. Klistra in nyttolasten som ska skickas till tredjepartssystemet.

Om ett GET-anrop som kräver parametrar används ska du ange parametrarna i fältet **[!UICONTROL Dynamic Values]** och de läggs sedan till automatiskt i slutet av anropet. Om ett POST-anrop används måste du:

* lista de parametrar som ska skickas vid anrop i fältet **[!UICONTROL Dynamic Values]** (i exemplet nedan: &quot;identifier&quot;).
* även ange dem med exakt samma syntax i brödtexten i den skickade nyttolasten. För att göra detta måste du lägga till: &quot;param&quot; – &quot;namn på parametern&quot; (i exemplet nedan: &quot;identifier&quot;). Följ syntaxen nedan:

   ```
   {"id":{"param":"identifier"}}
   ```

![](../assets/journey29.png)

Klicka på **[!UICONTROL Save]**.

Datakällan är nu konfigurerad och redo att användas i dina resor. Du kan till exempel använda den i dina villkor eller för att personalisera ett e-postmeddelande. Om temperaturen är över 30 °C kan du välja att skicka ett visst meddelande.

## Anpassat autentiseringsläge{#section_wjp_nl5_nhb}

>[!CONTEXTUALHELP]
>id="jo_authentication_payload"
>title="Om anpassad autentisering"
>abstract="Det anpassade autentiseringsläget används vid komplex autentisering för att anropa API-omslutningsprotokoll som OAuth2. Körningen av åtgärden är en process i två steg. Först görs ett anrop till slutpunkten för att generera en åtkomsttoken. Denna åtkomsttoken injiceras sedan i åtgärdens HTTP-begäran."

Det här autentiseringsläget används vid komplex autentisering som ofta används för att anropa API-omslutningsprotokoll som OAuth2 och för att hämta en åtkomsttoken som ska injiceras i den faktiska HTTP-begäran för åtgärden.

När du konfigurerar den anpassade autentiseringen kan du klicka på knappen nedan för att kontrollera om den anpassade autentiserade nyttolasten är korrekt konfigurerad.

![](../assets/journey29-bis.png)

Om testet godkänns blir knappen grön.

![](../assets/journey29-ter.png)

Med den här autentiseringen blir åtgärdskörningen en process med två steg:

1. Anropa slutpunkten för att generera en åtkomsttoken.
1. Anropa REST API:et genom att injicera åtkomsttoken på rätt sätt.

Denna autentisering består av två delar.

Definitionen av slutpunkten som ska anropas för att generera en åtkomsttoken:

* slutpunkt: URL som ska användas för att generera slutpunkten
* metoden för HTTP-begäran på slutpunkten (GET eller POST)
* rubriker: nyckel-/värdepar som vid behov ska injiceras som rubriker i detta anrop
* brödtext: beskriver anropets brödtext om metoden är POST. Vi har stöd för en begränsad struktur i brödtexten som definieras i bodyParams (nyckel/värde-par). Brödtextens typ beskriver formatet och kodningen för brödtexten i anropet:
   * &quot;form&quot;: innebär att innehållstypen är application/x-www-form-urlencoded (charset UTF-8) och nyckel/värde-paren serialiseras som de är: key1=value1&amp;key2=value2&amp; ...
   * &quot;json&quot;: innebär att innehållstypen är application/json (charset UTF-8) och nyckel-/värdeparen serialiseras som ett json-objekt som det är: _{ &quot;key1&quot;: &quot;value1&quot;, &quot;key2&quot;: &quot;value2&quot;, ...}_

Definitionen av hur en åtkomsttoken måste injiceras i åtgärdens HTTP-begäran:

* authorizationType: definierar hur den genererade åtkomsttoken måste injiceras i HTTP-anropet för åtgärden. Möjliga värden är:

   * innehavare: anger att en åtkomsttoken måste injiceras i auktoriseringsrubriken såsom: _behörighet: innehavare &lt;åtkomsttoken>_
   * rubrik: anger att en åtkomsttoken måste injiceras som en rubrik där dess namn definieras av egenskapen tokenTarget. Om till exempel tokenTarget är myHeader injiceras åtkomsttoken som en rubrik som: _myHeader: &lt;åtkomsttoken>_
   * queryParam: anger att en åtkomsttoken måste injiceras som en queryParam där dess namn definieras av egenskapen tokenTarget. Om till exempel tokenTarget är myQueryParam blir webbadressen för åtgärdsanropet: _&lt;url>?myQueryParam=&lt;åtkomsttoken>_

* tokenInResponse: anger hur du extraherar åtkomsttoken från autentiseringsanropet. Den här egenskapen kan vara:
   * &quot;response&quot;: anger att HTTP-svaret är åtkomsttoken
   * en väljare i en json (förutsatt att svaret är en json. Vi har inte stöd för andra format som XML). Den här väljarens format är _json://&lt;sökväg till åtkomsttokens egenskap>_. Om svaret på anropet till exempel är: _{ &quot;access_token&quot;: &quot;theToken&quot;, &quot;timestamp&quot;: 12323445656 }_, kommer tokenInResponse att vara: _json: //access_token_

Autentiseringsformatet är:

```
{
    "type": "customAuthorization",
    "authorizationType": "<value in 'bearer', 'header' or 'queryParam'>",
    (optional, mandatory if authorizationType is 'header' or 'queryParam') "tokenTarget": "<name of the header or queryParam if the authorizationType is 'header' or 'queryParam'>",
    "endpoint": "<URL of the authentication endpoint>",
    "method": "<HTTP method to call the authentication endpoint, in 'GET' or 'POST'>",
    (optional) "headers": {
        "<header name>": "<header value>",
        ...
    },
    (optional, mandatory if method is 'POST') "body": {
        "bodyType": "<'form'or 'json'>,
        "bodyParams": {
            "param1": value1,
            ...

        }
    },
    "tokenInResponse": "<'response' or json selector in format 'json://<field path to access token>'"
}
```

Du kan ändra cachevaraktigheten på en token för en anpassad autentiseringsdatakälla. Nedan visas ett exempel på en anpassad autentiseringsnyttolast. Cachevaraktigheten definieras i parametern &quot;cacheDuration&quot;. Den anger varaktigheten för den genererade token i cachen. Enheten kan vara millisekunder, sekunder, minuter, timmar, dagar, månader och år.

```
"authentication": {
    "type":"customAuthorization",
    "authorizationType":"Bearer",
    "endpoint":"http://localhost:${port}/epsilon/oauth2/access_token",
    "method":"POST",
    "headers": {
        "Authorization":"Basic EncodeBase64(${epsilonClientId}:${epsilonClientSecret})"
        },
    "body": {
        "bodyType":"form",
        "bodyParams": {
             "scope":"cn mail givenname uid employeeNumber",
             "grant_type":"password",
             "username":"${epsilonUserName}",
             "password":"${epsilonUserPassword}"
             }
        },
    "tokenInResponse":"json://access_token",
    "cacheDuration":
             { "duration":5, "timeUnit":"seconds" }
    }
```

>[!NOTE]
>
>Cachens varaktighet hjälper till att undvika för många anrop till slutpunkterna för autentisering. Kvarhållande av autentiseringstoken cachelagras i tjänster, det finns ingen beständighet. Om en tjänst startas om börjar den med ett rent cacheminne. Cachevaraktigheten är som standard 1 timme. I den anpassade åtgärdsnyttolasten kan den anpassas genom att ange en annan kvarhållningstid.