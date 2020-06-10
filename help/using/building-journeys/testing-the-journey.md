---
title: Testa resan
description: 'Läs om testning av resan '
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
source-git-commit: be21573973600758cbf13bd25bc3b44ab4cd08ca
workflow-type: tm+mt
source-wordcount: '1090'
ht-degree: 0%

---


# Testa resan{#testing_the_journey}

Innan du kan testa din resa måste du åtgärda eventuella fel. Se [](../about/troubleshooting.md#section_h3q_kqk_fhb).

Du kan testa din resa innan den publiceras med testprofiler. På så sätt kan ni analysera hur individer flödar in på resan och felsöka före publicering.

Så här använder du testläget:

1. Kontrollera att resan är giltig och att det inte finns något fel innan du testar den. Du kommer inte att kunna starta ett test av en resa med fel. Se [](../about/troubleshooting.md#section_h3q_kqk_fhb). En varningssymbol visas om det finns fel.

1. Aktivera testläget genom att klicka på **[!UICONTROL Test]** växlingsknappen i det övre högra hörnet.

   ![](../assets/journeytest1.png)

1. Använd parametern **Väntetid i testparametern** , i det nedre vänstra hörnet, för att definiera den tid som varje vänteaktivitet ska vara i testläge. Standardtiden är 10 sekunder. Detta säkerställer att du får testresultaten snabbt. Den här parametern visas bara om du har släppt en eller flera vänteaktiviteter under din resa.

   ![](../assets/journeytest_wait.png)

1. Klicka **[!UICONTROL Trigger an event]** för att konfigurera och skicka händelser till resan. Se till att skicka händelser som rör testprofiler. Se [Bekräfta dina händelser](#firing_events).

   ![](../assets/journeyuctest1.png)

1. När du har fått händelserna klickar du på **[!UICONTROL Show log]** knappen för att visa testresultatet och verifiera dem. Se [Visa loggarna](#viewing_logs).

   ![](../assets/journeyuctest2.png)

1. Om något fel uppstår kan du inaktivera testläget, ändra din resa och testa det igen. När testet är klart kan du publicera din resa. Se [](../building-journeys/publishing-the-journey.md).

## Viktiga anteckningar {#important_notes}

* Det finns ett gränssnitt för att utlösa händelser till den testade resan, men händelser kan också skickas av tredjepartssystem som Postman.
* Endast personer som markerats som&quot;testprofiler&quot; i kundprofiltjänsten i realtid får delta i den testade resan. Processen för att skapa en testprofil är densamma som processen att skapa en profil i dataplattformen. Du behöver bara kontrollera att testprofilflaggan är sann. Du kan använda segmentavsnittet i gränssnittet för dataplattformen för att skapa ett segment med testprofiler i din dataplattform och se en icke-uttömmande lista. Det går inte att visa den uttömmande listan just nu.
* Testläget är bara tillgängligt i utkastresor som använder ett namnutrymme. Testläget måste kontrollera om en person som deltar i resan är en testprofil eller inte och därmed måste kunna nå dataplattformen.
* Det högsta antalet testprofiler som kan gå in på en resa under en testsession är 100.
* När du inaktiverar testläget töms resorna från alla som har gått in i det tidigare eller som befinner sig i det.
* Du kan aktivera/inaktivera testläget så många gånger som behövs.
* Du kan inte ändra din resa när testläget är aktiverat. När du är i testläge kan du publicera resan direkt, du behöver inte inaktivera testläget tidigare.

## Aktivera händelser {#firing_events}

Med **[!UICONTROL Trigger an event]** knappen kan du konfigurera en händelse som får en person att komma in på resan.

Som en förutsättning måste du veta vilka profiler som är flaggade som testprofiler i dataplattformen. Testläget tillåter bara dessa profiler under resan och händelsen måste innehålla ett ID. Det förväntade ID:t beror på händelsekonfigurationen. Det kan till exempel vara ett ECID.

Om resan innehåller flera händelser använder du listrutan för att välja en händelse. Konfigurera sedan de fält som skickats och körningen av den händelse som skickats för varje händelse. Med gränssnittet kan du skicka rätt information i händelsens nyttolast och kontrollera att informationstypen är korrekt. Testläget sparar de senaste parametrarna som användes i en testsession för senare bruk.

![](../assets/journeytest4.png)

Med gränssnittet kan du skicka enkla händelseparametrar. Om du vill skicka samlingar eller andra avancerade objekt i händelsen kan du klicka på den för **[!UICONTROL Code View]** att se hela koden för nyttolasten och ändra den. Du kan till exempel kopiera och klistra in händelseinformation som har förberetts av en teknisk användare.

![](../assets/journeytest5.png)

En teknisk användare kan också använda det här gränssnittet för att komponera händelsenyttolaster och utlösa händelser utan att behöva använda något tredjepartsverktyg.

När du klickar på knappen **Skicka** börjar testet. Personens förlopp under resan representeras av ett visuellt flöde. Vägen blir progressivt grön allt eftersom personen rör sig över resan. Om ett fel inträffar visas en varningssymbol i motsvarande steg. Du kan placera markören på den för att visa mer information om felet och få tillgång till fullständig information (när den är tillgänglig).

![](../assets/journeytest6.png)

När du väljer en annan testprofil på händelsekonfigurationsskärmen och kör testet igen rensas det visuella flödet och den nya personens sökväg visas.

När du öppnar en resa i ett test motsvarar den visade sökvägen det senaste testet som utfördes.

Det visuella flödet fungerar oavsett om händelsen aktiveras via gränssnittet eller externt (med till exempel Postman).

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
* _currentStep_ > _extraInfo_: beskrivning av felet och annan sammanhangsbaserad information.
* _currentStep_ > _fetchErrors_: information om hämtning av datafel som inträffade under det här steget.
* _externalKeys_: värdet för den nyckelformel som definieras i händelsen.
* _enrichedData_: de data som resan har hämtat om resan använder datakällor.
* _transitionHistory_: en lista med steg som personen följde. För händelser visas nyttolasten.
* _actionExecutionErrors_ : information om de fel som uppstått.

Här är en persons olika status:

* _Körs_: personen för närvarande befinner sig på resan.
* _Slutförd_: personen befinner sig i slutet av resan.
* _Fel_: Personen stoppas på resan på grund av ett fel.
* _Timeout_: Personen stoppas på resan på grund av ett steg som tog för mycket tid.
