---
product: adobe campaign
title: Dokumentationsuppdateringar
description: Läs om dokumentationsuppdateringar
feature: Journeys
role: User
level: Beginner
hide: true
hidefromtoc: true
exl-id: ac5d2cec-0b48-4863-afe3-19ac5f61c9fd
source-git-commit: af224593ca69f79c3e4458f26f77b92197ad73a2
workflow-type: tm+mt
source-wordcount: '1010'
ht-degree: 96%

---

# Dokumentationsuppdateringar

På den här sidan listas alla dokumentationsuppdateringar för [!DNL Journey Orchestration].
Du kan även läsa [versionsinformationen](../release-notes/release-notes.md) om [!DNL Journey Orchestration].

## Juli 2022 {#july-2022}

* Alternativet **Tidszon för profil** är nu inaktiverat som standard i reseegenskaperna. [Läs mer](../building-journeys/timezone-management.md#timezone-from-profiles)
* Alternativet **Fast datum** är inte längre tillgängligt i aktiviteten **Vänta**. [Läs mer](../building-journeys/wait-activity.md)

## Juni 2022 {#june-2022}

* Nya frågeexempel har lagts till på [sidan](../building-journeys/query-examples.md)

## Mars 2022 {#march-2022}

* Ett exempel har lagts till om hur du lägger till ett uttryck som ett standardvärde i uttrycksredigeraren. [Läs mer](../expression/field-references.md#default-value)

## Februari 2022 {#feb-2022}

* Dokumentationssidorna för funktionerna [replace](../functions/functionreplace.md#example_2) och [replaceAll](../functions/functionreplaceall.md#example) har uppdaterats med ytterligare information och exempel angående målparametern.
* Bästa praxis har lagts till på sidan [Operatorer](../expression/operators.md#important-notes).

## September 2021

* Följande funktionssidor har uppdaterats: [sethours](../functions/functionsethours.md), [getListItem](../functions/functiongetlistitem.md), [inSegment](../functions/functioninsegment.md)

* Följande funktioner har lagts till: [filter](../functions/functionfilter.md), [intersect](../functions/functionintersect.md), [toDateOnly](../functions/functiontodateonly.md)

* Datumtypen dateOnly har lagts till i dokumentationen för utrycksredigering. [Läs mer](../expression/data-types.md)

* Tillagda uppgifter om anpassad cachelängd på åtgärd. [Läs mer](../datasource/external-data-sources.md#section_wjp_nl5_nhb)

* Tillagd information om standardportar för anpassade åtgärder. [Läs mer](../action/url-configuration.md)

* Tillagda vanligt förekommande exempel till frågor om Journey Step Events i Data Lake. [Läs mer](../building-journeys/query-examples.md)

## Augusti 2021

* Konfigurationsproceduren för anpassade åtgärder med dynamiska URL-sökvägar och dynamiska huvuden har uppdaterats. [Läs mer](../action/url-configuration.md)
* Ett avsnitt om hjälpmedelsfunktioner har lagts till. [Läs mer](../about/user-interface.md#accessibility)
* Ett avsnitt om metoder för segmentutvärdering har lagts till. [Läs mer](../segment/about-segments.md#evaluation-method-in-journey-orchestration)

## Mars 2021 {#march-2021}

* Vi har beskrivit hela proceduren för att skapa testprofiler i Adobe Experience Platform. [Läs mer](../building-journeys/creating-test-profiles.md).

## Januari 2021 {#january-2021}

* Bästa praxis när en resa utlöses samtidigt som en profil skapas, har lagts till. [Läs mer](../about/limitations.md#journeys-limitation-profile-creation).

## Oktober 2020 {#october-2020}

* Information har lagts till om hur du konfigurerar en timeout för en händelse. [Läs mer](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time).

## September 2020 {#september-2020}

* Avsnittet som beskriver gränssnittet har uppdaterats för att återspegla den nya menyn **Alla väljare**. [Läs mer](../about/user-interface.md)
* En anteckning om segmentbaserade resor med nya versioner som inte är återkommande, har lagts till.

## Augusti 2020 {#august-2020}

* Information har lagts till om hur du sorterar och väljer vilka kolumner som ska visas i segmentlistan. [Läs mer](../building-journeys/segment-qualification-events.md)
* Information har lagts till om hur du kopierar ett segments namn och ID när det har markerats. [Läs mer](../building-journeys/segment-qualification-events.md)
* Förekomster av Experience Platform har harmoniserats över de olika sidorna.

## Juli 2020 {#july-2020}

* En länk till en ny självstudievideo har lagts till som visar stegen hur du rapporterar till Adobe Experience Platform. [Läs mer](../building-journeys/sharing-overview.md)
* Avsnittet Händelseaktiviteter har omorganiserats i dedikerade underavsnitt för varje typ av händelser. [Läs mer](../building-journeys/event-activities.md)
* Bästa praxis har lagts till för att undvika överbelastning med segmentkvalificering. [Läs mer](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* En anteckning har lagts till som förklarar hur en resa fortsätter efter ett fel i en åtgärd eller ett villkor. [Läs mer](../about/troubleshooting.md#section_h3q_kqk_fhb)
* Ett nytt avsnitt har lagts till om de alfafunktioner som testas bland ett begränsat antal kunder.
* Ett nytt avsnitt har lagts till om integrationen med intelligenta tjänster. [Läs mer](../ai-services/ai-services-overview.md)
* Ett nytt avsnitt har lagts till om att skapa testprofiler. [Läs mer](../building-journeys/testing-the-journey.md)
* Information har lagts till om hur du använder noden **[!UICONTROL SegmentQualification]** i ett resevillkor eller en åtgärd. [Läs mer](../building-journeys/segment-qualification-events.md)
* En anteckning har lagts till om transaktionsmeddelanden och händelsepublicering i Campaign. Se [Arbeta med Adobe Campaign](../action/working-with-adobe-campaign.md) och [Använda Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md).
* Information har lagts till om de kontroller som utförs när instansens URL i Campaign Standard testas. [Läs mer](../action/working-with-adobe-campaign.md)
* Information har lagts till om kompatibilitet mellan reaktionshändelser och instanser i Campaign Standard som är värdbaserade på AWS- eller Azure-servrar. [Läs mer](../building-journeys/reaction-events.md)
* En anteckning har lagts till om behovet av att ställa in en begränsningsregel när man arbetar med transaktionsmeddelanden i Campaign Standard. [Läs mer](../action/working-with-adobe-campaign.md)
* En anteckning har lagts till om generering av verkliga händelser när händelser utlöses i testläget. [Läs mer](../building-journeys/testing-the-journey.md#firing_events)

## Juni 2020 {#june-2020}

* Information har lagts till om hur du ändrar cachevaraktigheten för en token för en anpassad autentiseringsdatakälla. [Läs mer](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* Skärmbilder och text har uppdaterats för att återspegla namnbytet på **[!UICONTROL Finished]**-resetillståndet som har ändrats till **[!UICONTROL Closed (no entrance)]**.
* Information har lagts till om hur språket definieras i gränssnittet. [Läs mer](../about/user-interface.md)
* Listan över status gällande en individs resa har flyttats till avsnittet [Testlägets loggar](../building-journeys/testing-the-journey.md#viewing_logs).

## April 2020 {#april-2020}

* Ett nytt avsnitt har lagts till om schemadefinitionen för en upplevelsehändelse för att hjälpa användare att konfigurera sin första händelse. [Läs mer](../event/experience-event-schema.md)
* Hemsidan för [!DNL Journey Orchestration] dokumentationen har uppdaterats med ytterligare användbara länkar. [Läs mer](../../journey-orchestration-home.md)

## Mars 2020 {#march-2020}

* Parameterbeskrivningar har lagts till för _actionExecutionErrors_ och _fetchErrors_ i avsnittet Testloggar. [Läs mer](../building-journeys/testing-the-journey.md#viewing_logs)
* Begränsningarna på anpassade åtgärder som används under en resa har uppdaterats. Du kan även ändra **[!UICONTROL URL]**-fältet och **[!UICONTROL Authentication]**-parametrarna. [Läs mer](../action/about-custom-action-configuration.md)
* Nya kontextuella hjälpposter har lagts till. Fönstret för anpassad autentisering av nyttolaster (i åtgärder och datakällor) innehåller nu en hjälpikon som länkar till det här [avsnittet](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
* Stängda resor kan nu stoppas. [Läs mer](../building-journeys/using-the-journey-designer.md)
* Avsnittet Beskrivning av gränssnitt har omstrukturerats. [Läs mer](../about/user-interface.md)
* Att aktivera flera händelser har lagts till i avsnittet Testläge. [Läs mer](../building-journeys/testing-the-journey.md#firing_events)
* Avsnittet Testläge har uppdaterats med avseende på den nya **[!UICONTROL Wait time in test]**-parametern. [Läs mer](../building-journeys/testing-the-journey.md)
* Avsnittet Testlogg har uppdaterats med externa felkoder för anrop och svar. [Läs mer](../building-journeys/testing-the-journey.md#viewing_logs)
* Hantering av tidszoner är nu centraliserad på panelen för reseegenskaper. Läs mer [här](../building-journeys/changing-properties.md#timezone) och [här](../building-journeys/timezone-management.md)
* Avsnittet Resedesignern har uppdaterats för att återspegla de senaste förbättringarna. [Läs mer](../building-journeys/using-the-journey-designer.md)
* Beskrivningen av gränssnitt har uppdaterats med information om sammanhangsberoende hjälp. [Läs mer](../about/user-interface.md#section_ksq_zr1_ffb)
* När du bläddrar bland **XDM-fält** visas det användarvänliga namnet. Relaterade avsnitt har uppdaterats. [Läs mer](../about/user-interface.md#friendly-names-display)

## Februari 2020 {#february-2020}

* Avsnittet för genvägar har uppdaterats. Med tangentbordsgenvägen **C** kan du skapa en ny post på alla listskärmar. [Läs mer](../about/user-interface.md#section_ksq_zr1_ffb)
* Översiktssidorna över [datakälla](../datasource/about-data-sources.md) och [åtgärd](../action/action.md) har förbättrats.

## Januari 2020 {#january-2020}

* Hämtningsbegränsningar har lagts till för [upplevelsehändelser](../datasource/adobe-experience-platform-data-source.md) och [segment](../functions/functioninsegment.md).
  <!--* The [getBestSendTime documentation](../functions/functiongetbestsendtime.md) has been updated.-->

## December 2019 {#december-2019}

* Alla skärmbilder har uppdaterats för att återspegla ändringar i gränssnitten.
* Avsnittet Testläge har uppdaterats. [Läs mer](../building-journeys/testing-the-journey.md)
  <!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).-->
* Stoppade resor kan nu raderas. Relaterade sidor i dokumentationen har uppdaterats.
* Två färger visas nu när fel upptäcks i en resa. Röd för fel och orange för varningar. [Läs mer](../about/troubleshooting.md)
* Avsnittet Avancerad uttrycksredigerare har uppdaterats. [Läs mer](../expression/expressionadvanced.md).
* Avsnitten [Villkorliga instruktioner](../expression/conditional-instruction.md) och [Hantera samlingar](../expression/collection-management-functions.md) har flyttats och uppdaterats.
* Avsnittet [Funktioner](../expression/functions.md) har uppdaterats med nya exempel.
* Dokumentationen om [funktionen toDateTime](../functions/functiontodatetime.md) har uppdaterats för att återspegla ändringar i syntaxen för tidszoner.
