---
title: Dokumentationsuppdateringar
description: Läs om dokumentationsuppdateringar
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
source-git-commit: 10d4fd57e9a801dab2310b2b511bf99cf1d9170a
workflow-type: tm+mt
source-wordcount: '724'
ht-degree: 80%

---


# Dokumentationsuppdateringar

På den här sidan listas alla dokumentationsuppdateringar för [!DNL Journey Orchestration].
Du kan även läsa [versionsinformationen](../release-notes/release-notes.md) om [!DNL Journey Orchestration].

## Augusti 2020 {#august-2020}

* Lagt till information om hur du sorterar och väljer vilka kolumner som ska visas i segmentlistan. [Läs mer](../building-journeys/segment-qualification-events.md)
* Lagt till information om hur du kopierar ett segments namn och ID när det har markerats. [Läs mer](../building-journeys/segment-qualification-events.md)
* Förekomsten av Experience Platform har harmoniserats på de olika sidorna.

## Juli 2020 {#july-2020}

* En länk till en ny självstudievideo om att rapportera om steghändelser till Adobe Experience Platform har lagts till. [Läs mer](../building-journeys/sharing-overview.md)
* Avsnittet med händelseaktiviteter har omorganiserats i dedikerade underavsnitt för varje typ av händelser. [Läs mer](../building-journeys/event-activities.md)
* Lagt till metodtips för att undvika överbelastning med segmentkvalificering. [Läs mer](../building-journeys/segment-qualification-events.md#speed-segment-qualification)
* En anteckning har lagts till som förklarar hur en resa fortsätter efter ett fel i en åtgärd eller ett villkor. [Läs mer](../about/troubleshooting.md#section_h3q_kqk_fhb)
* Ett nytt avsnitt har lagts till om de alfafunktioner som testas bland ett begränsat antal kunder. [Läs mer](../alpha/alpha-overview.md)
* Ett nytt avsnitt har lagts till om integrationen med intelligenta tjänster. [Läs mer](../ai-services/ai-services-overview.md)
* Ett nytt avsnitt har lagts till om att skapa testprofiler. [Läs mer](../building-journeys/testing-the-journey.md#create-test-profile)
* Information har lagts till om hur du använder noden **[!UICONTROL SegmentQualification]** i ett resevillkor eller en åtgärd. [Läs mer](../building-journeys/segment-qualification-events.md)
* En anteckning har lagts till om transaktionsmeddelanden och händelsepublicering i Campaign. Se [Arbeta med Adobe Campaign](../action/working-with-adobe-campaign.md) och [Använda Adobe Campaign](../building-journeys/using-adobe-campaign-actions.md).
* Information har lagts till om de kontroller som utförs när instansens URL i Campaign Standard testas. [Läs mer](../action/working-with-adobe-campaign.md)
* Information har lagts till om kompatibilitet mellan reaktionshändelser och instanser i Campaign Standard som är värdbaserade på AWS- eller Azure-servrar. [Läs mer](../building-journeys/reaction-events.md)
* En anteckning har lagts till om behovet av att ställa in en begränsningsregel när man arbetar med transaktionsmeddelanden i Campaign Standard. [Läs mer](../action/working-with-adobe-campaign.md)
* En anteckning har lagts till om generering av verkliga händelser när händelser utlöses i testläget. [Läs mer](../building-journeys/testing-the-journey.md#firing_events)

## Juni 2020 {#june-2020}

* Information har lagts till om hur du ändrar cachevaraktigheten för en token för en anpassad autentiseringsdatakälla. [Läs mer](../datasource/external-data-sources.md#section_wjp_nl5_nhb)
* Updated screenshots and text to reflect the renaming of the **[!UICONTROL Finished]** journey state which has been changed to **[!UICONTROL Closed (no entrance)]**.
* Information har lagts till om hur språket definieras i gränssnittet. [Läs mer](../about/user-interface.md)
* Listan över status gällande en individs resa har flyttats till avsnittet [Testlägets loggar](../building-journeys/testing-the-journey.md#viewing_logs).

## April 2020 {#april-2020}

* Ett nytt avsnitt har lagts till om schemadefinitionen för en upplevelsehändelse för att hjälpa användare att konfigurera sin första händelse. [Läs mer](../event/experience-event-schema.md)
* Hemsidan för dokumentation om [!DNL Journey Orchestration] har uppdaterats med ytterligare användbara länkar. [Läs mer](../../journey-orchestration-home.md)

## Mars 2020 {#march-2020}

* Parameterbeskrivningar har lagts till för _actionExecutionErrors_ och _fetchErrors_ i avsnittet Testloggar. [Läs mer](../building-journeys/testing-the-journey.md#viewing_logs)
* Begränsningarna på anpassade åtgärder som används under en resa har uppdaterats. You can also modify the **[!UICONTROL URL]** field and the **[!UICONTROL Authentication]** parameters. [Läs mer](../action/about-custom-action-configuration.md)
* Nya sammanhangsberoende hjälpposter har lagts till. Fönstret för anpassad autentisering av nyttolaster (i åtgärder och datakällor) innehåller nu en hjälpikon som länkar till det här [avsnittet](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
* Stängda resor kan nu stoppas. [Läs mer](../building-journeys/using-the-journey-designer.md)
* Avsnittet Beskrivning av gränssnitt har omstrukturerats. [Läs mer](../about/user-interface.md)
* Att aktivera flera händelser har lagts till i avsnittet Testläge. [Läs mer](../building-journeys/testing-the-journey.md#firing_events)
* Avsnittet Testläge har uppdaterats med avseende på den nya **[!UICONTROL Wait time in test]** parametern. [Läs mer](../building-journeys/testing-the-journey.md)
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
<!--* A warning has been added in the [email send time optimization](../building-journeys/wait-activity.md) and [predictive fatigue scores](../ai-services/leveraging-fatigue-scores.md) sections. These capabilities are only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).-->
* Stoppade resor kan nu raderas. Relaterade sidor i dokumentationen har uppdaterats.
* Två färger visas nu när fel upptäcks i en resa. Röd för fel och orange för varningar. [Läs mer](../about/troubleshooting.md)
* Avsnittet Avancerad uttrycksredigerare har uppdaterats. [Läs mer](../expression/expressionadvanced.md).
* Avsnitten [Villkorliga instruktioner](../expression/conditional-instruction.md) och [Hantera samlingar](../expression/collection-management-functions.md) har flyttats och uppdaterats.
* Avsnittet [Funktioner](../expression/functions.md) har uppdaterats med nya exempel.
* Dokumentationen om [funktionen toDateTime](../functions/functiontodatetime.md) har uppdaterats för att återspegla ändringar i syntaxen för tidszoner.
