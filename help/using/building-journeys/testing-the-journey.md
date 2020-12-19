---
product: adobe campaign
solution: Journey Orchestration
title: Testa resan
description: 'Läs om testning av resan '
translation-type: tm+mt
source-git-commit: 5e97f511872a924cc8c2c3a6904859d63ebeddcd
workflow-type: tm+mt
source-wordcount: '1442'
ht-degree: 3%

---


# Testa resan{#testing_the_journey}

Innan du kan testa din resa måste du åtgärda eventuella fel. Se [det här avsnittet](../about/troubleshooting.md#section_h3q_kqk_fhb).

Du kan testa din resa innan den publiceras med testprofiler. På så sätt kan ni analysera hur individer flödar in på resan och felsöka före publicering.

Så här använder du testläget:

1. Innan du testar din resa kontrollerar du att den är giltig och att det inte finns något fel. Du kommer inte att kunna starta ett test av en resa med fel. Se [det här avsnittet](../about/troubleshooting.md#section_h3q_kqk_fhb). En varningssymbol visas om det finns fel.

1. Aktivera testläget genom att klicka på växlingsknappen **[!UICONTROL Test]** i det övre högra hörnet.

   ![](../assets/journeytest1.png)

1. Använd parametern **[!UICONTROL Wait time in test]** i det nedre vänstra hörnet för att definiera den tid som varje vänteaktivitet ska vara i testläge. Den förinställda tiden är tio sekunder. Detta säkerställer att du får testresultaten snabbt. Den här parametern visas bara om du har släppt en eller flera vänteaktiviteter under din resa.

   ![](../assets/journeytest_wait.png)

1. Klicka på **[!UICONTROL Trigger an event]** för att konfigurera och skicka händelser till resan. Se till att skicka händelser som rör testprofiler. Se [Bekräfta dina händelser](#firing_events).

   ![](../assets/journeyuctest1.png)

1. När händelserna har tagits emot klickar du på knappen **[!UICONTROL Show log]** för att visa testresultatet och verifiera dem. Se [Visa loggarna](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. Om något fel uppstår kan du inaktivera testläget, ändra din resa och testa den igen. När testet är klart kan du publicera din resa. Läs [den här sidan](../building-journeys/publishing-the-journey.md).

## Viktiga anteckningar {#important_notes}

* Det finns ett gränssnitt för att utlösa händelser till den testade resan, men händelser kan också skickas av tredjepartssystem som Postman.
* Endast personer som markerats som&quot;testprofiler&quot; i kundprofiltjänsten i realtid får delta i den testade resan. Se [det här avsnittet](../building-journeys/testing-the-journey.md#create-test-profile).
* Testläget är bara tillgängligt i utkastresor som använder ett namnutrymme. Testläget måste kontrollera om en person som deltar i resan är en testprofil eller inte och därför måste kunna nå Adobe Experience Platform.
* Det högsta antalet testprofiler som kan gå in på en resa under en testsession är 100.
* När du inaktiverar testläget töms resorna från alla som har gått in i det tidigare eller som befinner sig i det. Rapporten blir också tydligare.
* Du kan aktivera/inaktivera testläget så många gånger som behövs.
* Du kan inte ändra din resa när testläget är aktiverat. När du är i testläge kan du publicera resan direkt, du behöver inte inaktivera testläget tidigare.

## Skapa en testprofil{#create-test-profile}

Processen för att skapa en testprofil är densamma som när du skapar en profil i Adobe Experience Platform. Den utförs via API-anrop. Se den här [sidan](https://docs.adobe.com/content/help/sv-SE/experience-platform/profile/home.html)

Du måste använda ett profilschema som innehåller blandningen &quot;information om profiltester&quot;. Flaggan testProfile ingår i den här mixinen.

När du skapar en profil måste du skicka värdet: testprofile = true.

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

## Aktivera aktiviteter {#firing_events}

Med knappen **[!UICONTROL Trigger an event]** kan du konfigurera en händelse som får en person att komma in på resan.

>[!NOTE]
>
>När du utlöser en händelse i testläge genereras en verklig händelse, vilket innebär att den även kommer att drabba andra resor som lyssnar på den här händelsen.

Du måste veta vilka profiler som är flaggade som testprofiler i Adobe Experience Platform. Testläget tillåter bara dessa profiler under resan och händelsen måste innehålla ett ID. Det förväntade ID:t beror på händelsekonfigurationen. Det kan till exempel vara ett ECID.

Om resan innehåller flera händelser använder du listrutan för att välja en händelse. Konfigurera sedan de fält som skickats och körningen av den händelse som skickats för varje händelse. Med gränssnittet kan du skicka rätt information i händelsens nyttolast och kontrollera att informationstypen är korrekt. Testläget sparar de senaste parametrarna som användes i en testsession för senare bruk.

![](../assets/journeytest4.png)

Med gränssnittet kan du skicka enkla händelseparametrar. Om du vill skicka samlingar eller andra avancerade objekt i händelsen kan du klicka på **[!UICONTROL Code View]** för att se hela koden för nyttolasten och ändra den. Du kan till exempel kopiera och klistra in händelseinformation som har förberetts av en teknisk användare.

![](../assets/journeytest5.png)

En teknisk användare kan också använda det här gränssnittet för att komponera händelsenyttolaster och utlösa händelser utan att behöva använda något tredjepartsverktyg.

När du klickar på knappen **[!UICONTROL Send]** påbörjas testet. Personens förlopp under resan representeras av ett visuellt flöde. Vägen blir progressivt grön allt eftersom personen rör sig över resan. Om ett fel inträffar visas en varningssymbol i motsvarande steg. Du kan placera markören på den för att visa mer information om felet och få tillgång till fullständig information (när den är tillgänglig).

![](../assets/journeytest6.png)

När du väljer en annan testprofil på händelsekonfigurationsskärmen och kör testet igen rensas det visuella flödet och den nya personens sökväg visas.

När du öppnar en resa i ett test motsvarar den visade sökvägen det senaste testet som utfördes.

Det visuella flödet fungerar oavsett om händelsen aktiveras via gränssnittet eller externt (med till exempel Postman).

## Testläge för regelbaserade resor {#test-rule-based}

Testläget är även tillgängligt för resor som använder en regelbaserad händelse. Mer information om regelbaserade händelser finns på [den här sidan](../event/about-events.md).

När du utlöser en händelse kan du med hjälp av skärmen **Händelsekonfiguration** definiera de händelseparametrar som ska passera i testet. Du kan visa händelse-ID-villkoret genom att klicka på verktygstipsikonen i det övre högra hörnet. Det finns också ett verktygstips bredvid varje fält som ingår i regelutvärderingen.

![](../assets/alpha-event8.png)

Mer information om hur du använder testläget finns på [den här sidan](../building-journeys/testing-the-journey.md).

## Visa loggarna {#viewing_logs}

Med knappen **[!UICONTROL Show log]** kan du visa testresultaten. På den här sidan visas resans aktuella information i JSON-format. Med en knapp kan du kopiera hela noder. Du måste uppdatera sidan manuellt för att kunna uppdatera resans testresultat.

![](../assets/journeytest3.png)

>[!NOTE]
>
>I testloggarna visas felkoden och felsvaret om ett fel uppstår vid anrop till ett tredjepartssystem (datakälla eller åtgärd).

Antalet personer (tekniskt sett kallas de instanser) som för närvarande befinner sig under resan visas. Här är användbar information som visas för varje individ:

* _ID_: Personens interna ID under resan. Detta kan användas för felsökning.
* _aktuellt steg_: det steg där personen befinner sig på resan. Vi rekommenderar att du lägger till etiketter till dina aktiviteter för att lättare kunna identifiera dem.
* _currentstep_ > phase: Status för den enskilda personens resa (körning, slutförd, fel eller timeout). Mer information finns nedan.
* _currentstep_ >  _extraInfo_: beskrivning av felet och annan sammanhangsbaserad information.
* _currentstep_ >  _fetchErrors_: information om hämtning av datafel som inträffade under det här steget.
* _externalKeys_: värdet för den nyckelformel som definieras i händelsen.
* _enrichedData_: de data som resan har hämtat om resan använder datakällor.
* _transitionHistory_: en lista med steg som personen följde. För händelser visas nyttolasten.
* _actionExecutionErrors_ : information om de fel som uppstått.

Här är en persons olika status:

* _Körs_: personen för närvarande befinner sig på resan.
* _Slutförd_: personen befinner sig i slutet av resan.
* _Fel_: Personen stoppas på resan på grund av ett fel.
* _Timeout_: Personen stoppas på resan på grund av ett steg som tog för mycket tid.

När en händelse aktiveras i testläget genereras en datauppsättning automatiskt med källans namn.

När en händelse aktiveras i testläget genereras en datauppsättning automatiskt med källans namn.

Testläget skapar automatiskt en Experience Event och skickar den till Adobe Experience Platform. Källan för upplevelsehändelsen heter&quot;Journey Orchestration Test Events&quot;.

Vid flera händelser som triggas av flera resor

Det finns ett scenario när flera händelser skickas från flera resor som kommer att ha olika scheman. Kan ett schema mappas till en datauppsättning? Annars behöver vi flera datauppsättningar.

Dessa datauppsättningar skapas och namnges automatiskt om en måldatauppsättning inte ingår i upplevelsehändelsen. Därför ser vi dagens&quot;Automatiskt skapade datauppsättningar för resenärer&quot;.

Namngivningen av vår källa skapar automatiskt. Om vi har flera händelser bör vi sammanfoga och låta det vara &quot;Journey Orchestration Test Event - NAME OF SCHEMA&quot;. Detta blir automatiskt&quot;Automatiskt genererad datauppsättning för testhändelsen Journey Orchestration - SCHEMAS NAMN&quot;.

