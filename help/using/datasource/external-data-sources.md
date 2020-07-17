---
title: 'Externa datakällor '
description: 'Lär dig konfigurera externa datakällor '
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '1271'
ht-degree: 0%

---



# Externa datakällor {#concept_t2s_kqt_52b}

Med externa datakällor kan du definiera en anslutning till tredjepartssystem, till exempel om du använder ett bokningssystem för hotell för att kontrollera om personen har registrerat ett rum. I motsats till den inbyggda Adobe Experience Platform-datakällan kan du skapa så många externa datakällor du behöver.

REST API:er som använder POST eller GET och returnerar JSON stöds. API-nyckel, grundläggande och anpassade autentiseringslägen stöds.

Låt oss ta ett exempel på en API-tjänst för väder som jag vill använda för att anpassa kundens beteenden efter väderdata i realtid.

Här är två exempel på API-anropet:

* _https://api.adobeweather.org/weather?city=London,uk&amp;appid=1234_
* _https://api.adobeweather.org/weather?lat=35&amp;lon=139&amp;appid=1234_

Anropet består av en huvud-URL (_https://api.adobeweather.org/weather_), två parameteruppsättningar (&quot;city&quot; för staden och&quot;lat/long&quot; för latitud och longitud) och API-nyckeln (appid).

Här följer de viktigaste stegen för att skapa och konfigurera en ny extern datakälla:

1. I listan med datakällor klickar du på **[!UICONTROL Add]** för att skapa en ny extern datakälla.

   ![](../assets/journey25.png)

   Då öppnas konfigurationsfönstret för datakällan till höger på skärmen.

   ![](../assets/journey26.png)

1. Ange ett namn för datakällan.

   >[!NOTE]
   >
   >Använd inte blanksteg eller specialtecken. Använd inte fler än 30 tecken.

1. Lägg till en beskrivning till datakällan. Det här steget är valfritt.
1. Lägg till den externa tjänstens URL. In our example: _https://api.adobeweather.org/weather_.

   >[!CAUTION]
   >
   >Vi rekommenderar starkt att du använder HTTPS av säkerhetsskäl. Observera också att vi inte tillåter användning av Adobe-adresser som inte är allmänt tillgängliga och användning av IP-adresser.

   ![](../assets/journey27.png)

1. Konfigurera autentiseringen beroende på den externa tjänstens konfiguration: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** eller **[!UICONTROL API key]**. Mer information om det anpassade autentiseringsläget finns i [](../datasource/external-data-sources.md#section_wjp_nl5_nhb). I vårt exempel väljer vi:


   * **[!UICONTROL Type]**: &quot;API-nyckel&quot;
   * **[!UICONTROL Value]**: &quot;1234&quot; (det här är värdet på vår API-nyckel)
   * **[!UICONTROL Name]**: &quot;appid&quot; (det här är API-nyckelparameternamnet)
   * **[!UICONTROL Location]**: &quot;Frågeparameter&quot; (API-nyckeln finns i URL:en)

   ![](../assets/journey28.png)

1. Lägg till en ny fältgrupp för varje API-parameteruppsättning genom att klicka **[!UICONTROL Add a New Field Group]**. Använd inte blanksteg eller specialtecken i fältgruppsnamnet. I vårt exempel måste vi skapa två fältgrupper, en för varje parameteruppsättning (city och long/lat).

För parameteruppsättningen&quot;long/lat&quot; skapar vi en fältgrupp med följande information:

* **[!UICONTROL Used in]**: visar antalet resor som använder en fältgrupp. You can click the **[!UICONTROL View journeys]** icon to display the list of journeys using this field group.
* **[!UICONTROL Method]**: välj metoden POST eller GET. I vårt fall väljer vi metoden GET.
* **[!UICONTROL Cache duration]**: Vi vill att vädret ska cachas i tio minuter.
* **[!UICONTROL Response Payload]**: click inside the **[!UICONTROL Payload]** field and paste an example of the payload returned by the call. For our example, we used a payload found on a weather API website. Kontrollera att fälttyperna är korrekta. Varje gång API anropas hämtas alla fält som ingår i nyttolastexemplet. Observera att du kan klicka på **[!UICONTROL Paste a new payload]** om du vill ändra den nyttolast som har skickats.
* **[!UICONTROL Dynamic Values]**: Ange de olika parametrarna avgränsade med kommatecken &quot;long,lat&quot; i vårt exempel. Eftersom parametervärdena är beroende av körningskontexten, kommer de att definieras i resorna. Se [](../expression/expressionadvanced.md).
* **[!UICONTROL Sent Payload]**: det här fältet visas inte i vårt exempel. Det är bara tillgängligt om du väljer metoden POST. Klistra in nyttolasten som ska skickas till tredjepartssystemet.

Om det gäller ett GET-anrop som kräver parametrar anger du parametern/parametrarna i **[!UICONTROL Parameters]** fältet och de läggs automatiskt till i slutet av anropet. Om du har ett POST-samtal måste du:

* Ange de parametrar som ska skickas vid anrop i **[!UICONTROL Parameter]** fältet (i exemplet nedan: &quot;identifier&quot;).
* ange dem också med exakt samma syntax i texten för den skickade nyttolasten. Om du vill göra det måste du lägga till: &quot;param&quot;: &quot;namn på parametern&quot; (i exemplet nedan: &quot;identifier&quot;). Följ syntaxen nedan:

   ```
   {"id":{"param":"identifier"}}
   ```

![](../assets/journey29.png)

Klicka på **[!UICONTROL Save]**.

Datakällan är nu konfigurerad och klar att användas i dina resor, till exempel under dina förhållanden eller för att anpassa ett e-postmeddelande. Om temperaturen är över 30°C kan du välja att skicka ett visst meddelande.

## Anpassat autentiseringsläge{#section_wjp_nl5_nhb}

>[!CONTEXTUALHELP]
>id="jo_authentication_payload"
>title="Om anpassad autentisering"
>abstract="Det anpassade autentiseringsläget används för komplex autentisering för att anropa API-omslutningsprotokoll som OAuth2. Körningen av funktionsmakrot är en tvåstegsprocess. Först görs ett anrop till slutpunkten för att generera åtkomsttoken. Then, the access token is injected in the the HTTP request of the action."

This authentication mode is used for complex authentication, frequently used to call API wrapping protocols such as OAuth2, to retrieve an access token to be injected in the real HTTP request for the action.

När du konfigurerar den anpassade autentiseringen kan du klicka på knappen nedan för att kontrollera om den anpassade autentiseringsnyttolasten är korrekt konfigurerad.

![](../assets/journey29-bis.png)

Om testet lyckas blir knappen grön.

![](../assets/journey29-ter.png)

Med den här autentiseringen är körningen av åtgärden en tvåstegsprocess:

1. Anropa slutpunkten för att generera åtkomsttoken.
1. Anropa REST API genom att mata in åtkomsttoken på rätt sätt.

This authentication has two parts.

The definition of the endpoint to be called to generate the access token:

* endpoint: URL to use to generate the endpoint
* method of the HTTP request on the endpoint (GET or POST)
* headers: key/value pairs to be injected as headers in this call if required
* brödtext: beskriver anropets brödtext om metoden är POST. Vi stöder en begränsad brödstruktur, som definieras i bodyParams (nyckel/värde-par). The bodyType describes the format and encoding of the body in the call:
   * &#39;form&#39;: vilket innebär att innehållstypen kommer att vara application/x-www-form-urlencoded (charset UTF-8) och nyckel/värde-paren kommer att serialiseras som: key1=value1&amp;key2=value2&amp;...
   * &#39;json&#39;: vilket innebär att innehållstypen blir application/json (charset UTF-8) och nyckelvärdepar kommer att serialiseras som ett json-objekt som är: _{ &quot;key1&quot;: &quot;value1&quot;, &quot;key2&quot;: &quot;value2&quot;, ...}_

Definitionen av hur åtkomsttoken måste matas in i åtgärdens HTTP-begäran:

* authenticationType: definierar hur den genererade åtkomsttoken måste matas in i HTTP-anropet för åtgärden. Möjliga värden är:

   * innehavare: anger att åtkomsttoken måste matas in i auktoriseringshuvudet, som: _Behörighet: Bearer &lt;åtkomsttoken>_
   * header: anger att åtkomsttoken måste matas in som ett huvud, det rubriknamn som definieras av egenskapen tokenTarget. Om till exempel tokenTarget är myHeader, kommer åtkomsttoken att matas in som ett huvud som: _myHeader: &lt;åtkomsttoken>_
   * queryParam: anger att åtkomsttoken måste matas in som queryParam, frågeparameternamnet som definieras av egenskapen tokenTarget. Om till exempel tokenTarget är myQueryParam blir URL:en för åtgärdsanropet: _&lt;url>?myQueryParam=&lt;åtkomsttoken>_

* tokenInResponse: visar hur du extraherar åtkomsttoken från autentiseringsanropet. Den här egenskapen kan vara:
   * &#39;response&#39;: anger att HTTP-svaret är åtkomsttoken
   * en väljare i en json (förutsatt att svaret är en json, stöder vi inte andra format som XML). Den här väljarens format är _json://&lt;path to the access token property>_. Om svaret på anropet till exempel är: _{ &quot;access_token&quot;: &quot;theToken&quot;, &quot;timestamp&quot;: 12323445656 }_, kommer tokenInResponse att vara: _json: //access_token_

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

Du kan ändra cachevaraktigheten för token för en anpassad autentiseringsdatakälla. Nedan visas ett exempel på en anpassad autentiseringsnyttolast. Cachevaraktigheten definieras i parametern &quot;cacheDuration&quot;. Den anger kvarhållningstiden för den genererade token i cachen. Enheten kan vara millisekunder, sekunder, minuter, timmar, dagar, månader, år.

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
