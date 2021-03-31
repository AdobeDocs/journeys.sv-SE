---
product: adobe campaign
solution: Journey Orchestration
title: Skapa en testprofil
description: 'Läs om hur du skapar testprofiler '
translation-type: tm+mt
source-git-commit: 86df088c3e2da43318de16b7ae51ff0e3a20d55b
workflow-type: tm+mt
source-wordcount: '728'
ht-degree: 1%

---


# Skapa testprofiler {#create-test-profiles}

Testprofiler krävs när testläget används under en resa. Mer information om hur du använder testläget finns i [det här avsnittet](../building-journeys/testing-the-journey.md).

Det finns olika sätt att skapa en testprofil i Adobe Experience Platform. I den här dokumentationen fokuserar vi på två metoder: överföra en [csv-fil](../building-journeys/creating-test-profiles.md#create-test-profiles-csv) och använda [API-anrop](../building-journeys/creating-test-profiles.md#create-test-profiles-api). Du kan också överföra en json-fil i en datauppsättning, se [dokumentationen för datainmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/ingest-batch-data.html#add-data-to-dataset).

Med de här importmetoderna kan du även uppdatera profilattribut. På så sätt kan du omvandla en befintlig profil till en testprofil. Använd bara ett liknande fil- eller API-anrop och inkludera bara fältet&quot;testProfile&quot; med värdet&quot;true&quot;.

Att skapa en testprofil liknar att skapa vanliga profiler i Adobe Experience Platform. Mer information finns i [dokumentationen för kundprofilen i realtid](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html).

## Förutsättningar{#test-profile-prerequisites}

För att kunna skapa profiler måste du först skapa ett schema och en datauppsättning i Adobe Experience Platform.

Först måste du **skapa ett schema**. Följ de här stegen:

1. I Adobe Experience Platform klickar du på **Scheman** på den vänstra menyn.
   ![](../assets/test-profiles-0.png)
1. Klicka på **Skapa schema** i det övre högra hörnet och välj sedan en schematyp, till exempel **XDM Individual Profile**.
   ![](../assets/test-profiles-1.png)
1. Välj ett namn för schemat.
1. Klicka på **Lägg till** i avsnittet **Blandningar**.
   ![](../assets/test-profiles-1-bis.png)
1. Välj lämpliga mixar. Se till att du lägger till **profiltestinformationen**-blandningen. Klicka på **Lägg till blandning**.
   ![](../assets/test-profiles-1-ter.png)
Listan med mixar visas på schemaöversiktsskärmen.

   ![](../assets/test-profiles-2.png)
1. I listan med fält klickar du på det fält som du vill definiera som primär identitet.
   ![](../assets/test-profiles-3.png)
1. I den högra panelen **Fältegenskaper** kontrollerar du alternativen **Identitet** och **Primär identitet** och väljer ett namnutrymme. Om du vill att den primära identiteten ska vara en e-postadress väljer du namnutrymmet **E-post**. Klicka på **Använd**.
   ![](../assets/test-profiles-4.png)
1. Markera schemat och aktivera alternativet **Profil** i **Schemaegenskaperna**.
   ![](../assets/test-profiles-5.png)
1. Klicka på **Spara**.

>[!NOTE]
>
>Mer information om schemaskapande finns i [XDM-dokumentationen](https://experienceleague.adobe.com/docs/experience-platform/xdm/ui/resources/schemas.html#prerequisites).

Sedan måste du **skapa datauppsättningen** som profilerna ska importeras i. Följ de här stegen:

1. I Adobe Experience Platform klickar du på **Datauppsättningar** på den vänstra menyn och sedan på **Skapa datauppsättning**.
   ![](../assets/test-profiles-6.png)
1. Välj **Skapa datauppsättning från schema**.
   ![](../assets/test-profiles-7.png)
1. Markera det tidigare skapade schemat och klicka sedan på **Nästa**.
   ![](../assets/test-profiles-8.png)
1. Välj ett namn och klicka sedan på **Slutför**.
   ![](../assets/test-profiles-9.png)
1. Aktivera alternativet **Profil**.
   ![](../assets/test-profiles-10.png)

>[!NOTE]
>
> Mer information om hur du skapar datauppsättningar finns i [dokumentationen för katalogtjänsten](https://experienceleague.adobe.com/docs/experience-platform/catalog/datasets/user-guide.html#getting-started).

## Skapa en testprofil med en CSV-fil{#create-test-profiles-csv}

I Adobe Experience Platform kan du skapa profiler genom att överföra en CSV-fil som innehåller de olika profilfälten till datauppsättningen. Det här är den enklaste metoden.

1. Skapa en enkel csv-fil med ett kalkylprogram.
1. Lägg till en kolumn för varje fält som behövs. Se till att du lägger till det primära identitetsfältet (&quot;personID&quot; i exemplet ovan) och att fältet&quot;testProfile&quot; är inställt på&quot;true&quot;.
   ![](../assets/test-profiles-11.png)
1. Lägg till en rad per profil och fyll i värdena för varje fält.
   ![](../assets/test-profiles-12.png)
1. Spara kalkylbladet som en CSV-fil. Se till att kommatecken används som avgränsare.
1. Klicka på **Arbetsflöden** i den vänstra menyn i Adobe Experience Platform.
   ![](../assets/test-profiles-14.png)
1. Välj **Mappa CSV till XDM-schema** och klicka sedan på **Starta**.
   ![](../assets/test-profiles-16.png)
1. Markera den datauppsättning som du vill importera profilerna till. Klicka på **Nästa**.
   ![](../assets/test-profiles-17.png)
1. Klicka på **Välj filer** och välj din CSV-fil. När filen har överförts klickar du på **Nästa**.
   ![](../assets/test-profiles-18.png)
1. Mappa CSV-källfälten till schemafälten och klicka sedan på **Slutför**.
   ![](../assets/test-profiles-19.png)
1. Dataimporten börjar. Statusen kommer att flyttas från **Bearbetning** till **Lyckades**. Klicka på **Förhandsgranska datauppsättning** i det övre högra hörnet.
   ![](../assets/test-profiles-20.png)
1. Kontrollera att testprofilerna har lagts till korrekt.
   ![](../assets/test-profiles-21.png)

Testprofilerna läggs till och kan nu användas när du testar en resa. Se [det här avsnittet](../building-journeys/testing-the-journey.md).
>[!NOTE]
>
> Mer information om csv-import finns i [dokumentationen för datainmatning](https://experienceleague.adobe.com/docs/experience-platform/ingestion/tutorials/map-a-csv-file.html#tutorials).

## Skapa testprofiler med API-anrop{#create-test-profiles-api}

Du kan också skapa testprofiler via API-anrop. Se den här [sidan](https://docs.adobe.com/content/help/sv-SE/experience-platform/profile/home.html).

Du måste använda ett profilschema som innehåller blandningen &quot;Profiltestinformation&quot;. Flaggan testProfile ingår i den här mixinen.

När du skapar en profil måste du skicka värdet: testProfile = true.

Observera att du även kan uppdatera en befintlig profil för att ändra dess testProfile-flagga till &quot;true&quot;.

Här är ett exempel på ett API-anrop för att skapa en testprofil:

```
curl -X POST \
'https://dcs.adobedc.net/collection/xxxxxxxxxxxxxx' \
-H 'Cache-Control: no-cache' \
-H 'Content-Type: application/json' \
-H 'Postman-Token: xxxxx' \
-H 'cache-control: no-cache' \
-H 'x-api-key: xxxxx' \
-H 'x-gw-ims-org-id: xxxxx' \
-d '{
"header": {
"msgType": "xdmEntityCreate",
"msgId": "xxxxx",
"msgVersion": "xxxxx",
"xactionid":"xxxxx",
"datasetId": "xxxxx",
"imsOrgId": "xxxxx",
"source": {
"name": "Postman"
},
"schemaRef": {
"id": "https://example.adobe.com/mobile/schemas/xxxxx",
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"body": {
"xdmMeta": {
"schemaRef": {
"contentType": "application/vnd.adobe.xed-full+json;version=1"
}
},
"xdmEntity": {
"_id": "xxxxx",
"_mobile":{
"ECID": "xxxxx"
},
"testProfile":true
}
}
}'
```

