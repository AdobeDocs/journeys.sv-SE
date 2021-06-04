---
product: adobe campaign
user-guide-title: Journey Orchestration
title: Guide till Journey Orchestration
user-guide-description: Tillhandahåller anvisningar för hur man implementerar och bygger resor.
index: true
feature: Resor
source-git-commit: c17808a4cae7ebbd1129f6b28ad2ea945098f826
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 93%

---


# [!DNL Journey Orchestration] Guide {#using}

+ [Produktdokumentation](journey-orchestration-home.md)
+ Nyheter {#release-notes}
   + [Versionsinformation](using/release-notes/release-notes.md)
   + [Dokumentationsuppdateringar](using/release-notes/documentation-updates.md)
+ Börja med [!DNL Journey Orchestration] {#starting-with-journeys}
   + [Om [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [Begränsningar](using/about/limitations.md)
   + [Kom igång](using/about/get-started.md)
   + [Användargränssnitt](using/about/user-interface.md)
   + [Åtkomsthantering](using/about/access-management.md)
   + [Felsökning](using/about/troubleshooting.md)
   + [Integrering med externa system](using/about/external-systems.md)
+ Konfigurera en händelse {#events-journeys}
   + Om händelser {#about-events}
      + [Allmän princip](using/event/about-events.md)
      + [Datacykel](using/event/about-data-cycle.md)
      + [Skapa en händelse](using/event/about-creating.md)
      + [Dra nytta av Adobe Analytics](using/event/about-analytics.md)
      + [Om scheman i ExperienceEvent](using/event/experience-event-schema.md)
      + [Ytterligare steg för att skicka händelser](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
   + [Definiera nyttolastfält](using/event/defining-the-payload-fields.md)
   + [Välja namnrymden](using/event/selecting-the-namespace.md)
   + [Definiera händelsenyckeln](using/event/defining-the-event-key.md)
   + [Lägga till ett villkor](using/event/adding-a-condition.md)
   + [Förhandsgranska nyttolasten](using/event/previewing-the-payload.md)
+ Konfigurera en datakälla {#data-source-journeys}
   + [Om datakällor](using/datasource/about-data-sources.md)
   + [Fältgrupper](using/datasource/field-groups.md)
   + [Datakällan i Adobe Experience Platform](using/datasource/adobe-experience-platform-data-source.md)
   + [Externa datakällor](using/datasource/external-data-sources.md)
+ Konfigurera en åtgärd {#action-journeys}
   + [Om åtgärder](using/action/action.md)
   + [Arbeta med Adobe Campaign Standard](using/action/working-with-adobe-campaign.md)
   + [Arbeta med Adobe Campaign Classic](using/action/acc-action.md)
   + Använda ett tredjepartssystem {#action-third-party}
      + [Om anpassad åtgärdskonfiguration](using/action/about-custom-action-configuration.md)
      + [URL-konfiguration](using/action/url-configuration.md)
      + [Definiera meddelandeparametrar](using/action/defining-the-message-parameters.md)
+ Använda plattformssegment {#configuring-segment}
   + [Om plattformssegment](using/segment/about-segments.md)
   + [Skapa ett segment](using/segment/creating-a-segment.md)
   + [Använda segment i villkor](using/segment/using-a-segment.md)
+ Bygga en resa {#building-journeys}
   + Om att bygga en resa {#about-journey-building}
      + [Skapa en resa](using/building-journeys/journey.md)
      + [Använda resedesignern](using/building-journeys/using-the-journey-designer.md)
      + [Ändra egenskaper](using/building-journeys/changing-properties.md)
      + [Reseversioner](using/building-journeys/journey-versions.md)
      + [Avsluta en resa](using/building-journeys/terminating-a-journey.md)
      + [Hantering av tidszoner](using/building-journeys/timezone-management.md)
      + [Testprofiler](using/building-journeys/creating-test-profiles.md)
   + Aktiviteter {#about-journey-building}
      + Händelseaktiviteter {#events-activities}
         + [Om händelseaktiviteter](using/building-journeys/event-activities.md)
         + [Allmänna händelser](using/building-journeys/general-events.md)
         + [Reaktionshändelser](using/building-journeys/reaction-events.md)
         + [Segment med kvalificeringshändelser](using/building-journeys/segment-qualification-events.md)
      + Orkestreringsaktiviteter {#orchestration-activities}
         + [Om orkestreringsaktiviteter](using/building-journeys/about-orchestration-activities.md)
         + [Villkorsaktivitet](using/building-journeys/condition-activity.md)
         + [Avsluta aktivitet](using/building-journeys/end-activity.md)
         + [Vänta på aktivitet](using/building-journeys/wait-activity.md)
      + Åtgärdsaktiviteter {#action-activities}
         + [Om åtgärdsaktiviteter](using/building-journeys/about-action-activities.md)
         + [Använda Adobe Campaign Standard](using/building-journeys/using-adobe-campaign-actions.md)
         + [Använda Adobe Campaign Classic](using/building-journeys/using-adobe-campaign-classic.md)
         + [Använda anpassade åtgärder](using/building-journeys/using-custom-actions.md)
         + [Hoppa från en resa till en annan](using/building-journeys/jump.md)
         + [Uppdatera profil](using/building-journeys/update-profiles.md)
   + [Testa resan](using/building-journeys/testing-the-journey.md)
   + [Publicera resan](using/building-journeys/publishing-the-journey.md)
   + Dela resesteg med Adobe Experience Platform {#sharing-journey-steps}
      + [Översikt över att dela steg i resan](using/building-journeys/sharing-overview.md)
      + [journeySteps, händelser, vanliga fält](using/building-journeys/sharing-common-fields.md)
      + [journeyStep, händelser, körningsfält för åtgärder](using/building-journeys/sharing-execution-fields.md)
      + [journeyStep, händelser, datafält för hämtning](using/building-journeys/sharing-fetch-fields.md)
      + [journeyStep, händelser, identitetsfält](using/building-journeys/sharing-identity-fields.md)
      + [Resefält](using/building-journeys/sharing-journey-fields.md)
+ Använda den avancerade uttrycksredigeraren {#building-advanced-conditions-journeys}
   + [Om den avancerade uttrycksredigeraren](using/expression/expressionadvanced.md)
   + Syntax {#syntax}
      + [Allmänt](using/expression/generalities.md)
      + [Villkorlig instruktion](using/expression/conditional-instruction.md)
      + [Datatyper](using/expression/data-types.md)
      + [Fältreferenser](using/expression/field-references.md)
      + [Funktioner för att hantera samlingar](using/expression/collection-management-functions.md)
      + [Operatorer](using/expression/operators.md)
      + [Resans egenskaper](using/expression/journey-properties.md)
      + [Exempel](using/expression/advanced-editor-use-cases.md)
   + Funktioner {#main-functions-journey}
      + [Huvudfunktioner](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [inSegment](using/functions/functioninsegment.md)
      + Aggregera {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [count](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [distinctCount](using/functions/functiondistinctcount.md)
         + [distinctCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [sum](using/functions/functionsum.md)
      + Konvertering {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Datum {#date}
         + [currentTime&#x200B;InMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [now](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + Lista {#list}
         + [distinct](using/functions/functiondistinct.md)
         + [distinctWithNull](using/functions/functiondistinctwithnull.md)
         + [getListItem](using/functions/functiongetlistitem.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sort](using/functions/functionsort.md)
      + Matematik {#math}
         + [random](using/functions/functionrandom.md)
         + [round](using/functions/functionround.md)
      + Sträng {#string}
         + [concat](using/functions/functionconcat.md)
         + [contain](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [lower](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [replace](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [split](using/functions/functionsplit.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trim](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Bygga rapporter{#journey-reports}
   + [Om reserapporter](using/reporting/about-journey-reports.md)
   + [Skapa reserapporter](using/reporting/creating-your-journey-reports.md)
   + [Mätvärden och mått](using/reporting/metrics-and-dimensions.md)
+ Integrering med intelligenta tjänster{#use-case-advanced}
   + [Om AI-integrering](using/ai-services/ai-services-overview.md)
   + [Utnyttja kund-AI](using/ai-services/leveraging-customer-ai.md)
+ Användningsfall{#use-cases-journeys}
   + Skicka ett personligt e-postmeddelande{#use-case-simple}
      + [Om det enkla användningsfallet](using/usecase/about-the-simple-use-case.md)
      + [Konfigurera händelsen](using/usecase/configuring-the-event.md)
      + [Konfigurera datakällan](using/usecase/configuring-the-data-source.md)
      + [Bygga resan](using/usecase/simple-uc-building-the-journey.md)
   + Bygga en resa över flera kanaler{#use-case-advanced}
      + [Om det avancerade användningsfallet](using/usecase/about-the-advanced-use-case.md)
      + [Konfigurera händelserna](using/usecase/configuring-the-events.md)
      + [Konfigurera datakällorna](using/usecase/configuring-the-data-sources.md)
      + [Bygga resan](using/usecase/building-the-journey.md)
   + [Skicka ett meddelande med Campaign Classic](using/usecase/campaign-classic-use-case.md)
+ Arbeta med API:er{#working-with-apis}
   + [Begränsa API:er](using/api/capping.md)
