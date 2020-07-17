---
product: Journeys
audience: end-user
user-guide-title: Hjälp om Journey Orchestration
index: true
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '382'
ht-degree: 1%

---


# [!DNL Journey Orchestration] Hjälp {#using}

+ [Produktdokumentation](journey-orchestration-home.md)
+ Nyheter {#release-notes}
   + [Versionsinformation](using/release-notes/release-notes.md)
   + [Dokumentationsuppdateringar](using/release-notes/documentation-updates.md)
+ Börja med [!DNL Journey Orchestration] {#starting-with-journeys}
   + [Om [!DNL Journey Orchestration]](using/about/about-journey-orchestration.md)
   + [Kom igång](using/about/get-started.md)
   + [Användargränssnitt](using/about/user-interface.md)
   + [Åtkomsthantering](using/about/access-management.md)
   + [Felsökning](using/about/troubleshooting.md)
+ Konfigurera en händelse {#events-journeys}
   + [Om händelser](using/event/about-events.md)
   + [Om ExperienceEvent-scheman](using/event/experience-event-schema.md)
   + [Definiera nyttolastfält](using/event/defining-the-payload-fields.md)
   + [Markera namnutrymmet](using/event/selecting-the-namespace.md)
   + [Definiera händelsenyckeln](using/event/defining-the-event-key.md)
   + [Lägga till ett villkor](using/event/adding-a-condition.md)
   + [Förhandsgranska nyttolasten](using/event/previewing-the-payload.md)
   + [Ytterligare steg för att skicka händelser](using/event/additional-steps-to-send-events-to-journey-orchestration.md)
+ Konfigurera en datakälla {#data-source-journeys}
   + [Om datakällor](using/datasource/about-data-sources.md)
   + [Fältgrupper](using/datasource/field-groups.md)
   + [Adobe Experience Platform datakälla](using/datasource/adobe-experience-platform-data-source.md)
   + [Externa datakällor](using/datasource/external-data-sources.md)
+ Konfigurera en åtgärd {#action-journeys}
   + [Om funktionsmakron](using/action/action.md)
   + [Arbeta med Adobe Campaign](using/action/working-with-adobe-campaign.md)
   + Använda ett tredjepartssystem {#action-third-party}
      + [Om anpassad åtgärdskonfiguration](using/action/about-custom-action-configuration.md)
      + [Begränsningar för anpassade åtgärder](using/action/custom-action-limitations.md)
      + [URL-konfiguration](using/action/url-configuration.md)
      + [Definiera meddelandeparametrar](using/action/defining-the-message-parameters.md)
+ Använda segment {#configuring-segment}
   + [Om segment](using/segment/about-segments.md)
   + [Skapa ett segment](using/segment/creating-a-segment.md)
   + [Använda segment i villkor](using/segment/using-a-segment.md)
+ Bygga en resa {#building-journeys}
   + Om resebyggnad {#about-journey-building}
      + [Skapa en resa](using/building-journeys/journey.md)
      + [Använda resedesignern](using/building-journeys/using-the-journey-designer.md)
      + [Ändra egenskaper](using/building-journeys/changing-properties.md)
      + [Reseversioner](using/building-journeys/journey-versions.md)
      + [Avbryta en resa](using/building-journeys/terminating-a-journey.md)
      + [Tidszonshantering](using/building-journeys/timezone-management.md)
   + Verksamhet {#about-journey-building}
      + Evenemangsaktiviteter {#events-activities}
         + [Om händelseaktiviteter](using/building-journeys/event-activities.md)
         + [Allmänna händelser](using/building-journeys/general-events.md)
         + [Reaktionshändelser](using/building-journeys/reaction-events.md)
         + [Segmentkvalificeringshändelser](using/building-journeys/segment-qualification-events.md)
      + Orchestration-verksamhet {#orchestration-activities}
         + [Om orkestreringsaktiviteter](using/building-journeys/about-orchestration-activities.md)
         + [Villkorsaktivitet](using/building-journeys/condition-activity.md)
         + [Avsluta aktivitet](using/building-journeys/end-activity.md)
         + [Vänta på aktivitet](using/building-journeys/wait-activity.md)
      + Verksamheter {#action-activities}
         + [Om funktionsmakron](using/building-journeys/about-action-activities.md)
         + [Använda Adobe Campaign åtgärder](using/building-journeys/using-adobe-campaign-actions.md)
         + [Använda anpassade åtgärder](using/building-journeys/using-custom-actions.md)
   + [Testa resan](using/building-journeys/testing-the-journey.md)
   + [Publicera resan](using/building-journeys/publishing-the-journey.md)
   + Dela resesteg med Adobe Experience Platform {#sharing-journey-steps}
      + [Översikt över delning av resesteg](using/building-journeys/sharing-overview.md)
      + [resaSteg-händelser, vanliga fält](using/building-journeys/sharing-common-fields.md)
      + [roadStep-händelser, körningsfält för åtgärd](using/building-journeys/sharing-execution-fields.md)
      + [progressStep-händelsedatafält för hämtning](using/building-journeys/sharing-fetch-fields.md)
      + [travelStep, händelseidentitetsfält](using/building-journeys/sharing-identity-fields.md)
      + [resefält](using/building-journeys/sharing-journey-fields.md)
+ Använda den avancerade uttrycksredigeraren {#building-advanced-conditions-journeys}
   + [Om den avancerade uttrycksredigeraren](using/expression/expressionadvanced.md)
   + Syntax {#syntax}
      + [Allmänt](using/expression/generalities.md)
      + [Villkorlig instruktion](using/expression/conditional-instruction.md)
      + [Datatyper](using/expression/data-types.md)
      + [Fältreferenser](using/expression/field-references.md)
      + [Hanteringsfunktioner för samlingar](using/expression/collection-management-functions.md)
      + [Operatorer](using/expression/operators.md)
      + [Exempel](using/expression/advanced-editor-use-cases.md)
   + Funktioner {#main-functions-journey}
      + [Huvudfunktioner](using/expression/functions.md)
      + Adobe Experience Platform {#adobe-experience-platform}
         + [getBestSendTime](using/functions/functiongetbestsendtime.md)
         + [inSegment](using/functions/functioninsegment.md)
      + Aggregering {#aggregation}
         + [avg](using/functions/functionavg.md)
         + [antal](using/functions/functioncount.md)
         + [countOnlyNull](using/functions/functioncountonlynull.md)
         + [countWithNull](using/functions/functioncountwithnull.md)
         + [clearCount](using/functions/functiondistinctcount.md)
         + [clearCountWithNull](using/functions/functiondistinctcountwithnull.md)
         + [max](using/functions/functionmax.md)
         + [min](using/functions/functionmin.md)
         + [summa](using/functions/functionsum.md)
      + Konvertering {#conversion}
         + [toBool](using/functions/functiontobool.md)
         + [toDateTime](using/functions/functiontodatetime.md)
         + [toDateTimeOnly](using/functions/functiontodatetimeonly.md)
         + [toDecimal](using/functions/functiontodecimal.md)
         + [toDuration](using/functions/functiontoduration.md)
         + [toInteger](using/functions/functiontointeger.md)
         + [toString](using/functions/functiontostring.md)
      + Datum {#date}
         + [currentTime &#x200B; InMillis](using/functions/functioncurrenttimeinmillis.md)
         + [inLastDays](using/functions/functioninlastdays.md)
         + [inLastHours](using/functions/functioninlasthours.md)
         + [inLastMonths](using/functions/functioninlastmonths.md)
         + [inLastYears](using/functions/functioninlastyears.md)
         + [inNextDays](using/functions/functioninnextdays.md)
         + [inNextHours](using/functions/functioninnexthours.md)
         + [inNextMonths](using/functions/functioninnextmonths.md)
         + [inNextYears](using/functions/functioninnextyears.md)
         + [nu](using/functions/functionnow.md)
         + [nowWithDelta](using/functions/functionnowwithdelta.md)
         + [setHours](using/functions/functionsethours.md)
         + [setDays](using/functions/functionsetdays.md)
      + Lista {#list}
         + [distinkt](using/functions/functiondistinct.md)
         + [clearWithNull](using/functions/functiondistinctwithnull.md)
         + [in](using/functions/functionin.md)
         + [listSize](using/functions/functionlistsize.md)
         + [serializeList](using/functions/functionserializelist.md)
         + [sortera](using/functions/functionsort.md)
      + Matematik {#math}
         + [random](using/functions/functionrandom.md)
         + [rund](using/functions/functionround.md)
      + Sträng {#string}
         + [concat](using/functions/functionconcat.md)
         + [innehåller](using/functions/functioncontain.md)
         + [containWithIgnoreCase](using/functions/functioncontainwithignorecase.md)
         + [endWith](using/functions/functionendwith.md)
         + [endWithIgnorecase](using/functions/functionendwithignorecase.md)
         + [equalWithIgnoreCase](using/functions/functionequalignorecase.md)
         + [indexOf](using/functions/functionindexof.md)
         + [isEmpty](using/functions/functionisempty.md)
         + [isNotEmpty](using/functions/functionisnotempty.md)
         + [lastIndexOf](using/functions/functionlastindexof.md)
         + [length](using/functions/functionlength.md)
         + [nedre](using/functions/functionlower.md)
         + [matchRegExp](using/functions/functionmatchregexp.md)
         + [notEqualWithIgnoreCase](using/functions/functionnotequalignorecase.md)
         + [ersätt](using/functions/functionreplace.md)
         + [replaceAll](using/functions/functionreplaceall.md)
         + [startWith](using/functions/functionstartwith.md)
         + [startWithIgnoreCase](using/functions/functionstartwithignorecase.md)
         + [substr](using/functions/functionsubstr.md)
         + [trimma](using/functions/functiontrim.md)
         + [upper](using/functions/functionupper.md)
         + [uuid](using/functions/functionuuid.md)
+ Bygga rapporter{#journey-reports}
   + [Om reserapporter](using/reporting/about-journey-reports.md)
   + [Skapa reserapporter](using/reporting/creating-your-journey-reports.md)
   + [Mätvärden och dimensioner](using/reporting/metrics-and-dimensions.md)
+ Integrering med intelligenta tjänster{#use-case-advanced}
   + [Om AI-integrering](using/ai-services/ai-services-overview.md)
   + [Utnyttjar Journey AI](using/ai-services/leveraging-fatigue-scores.md)
   + [Utnyttja kundernas AI](using/ai-services/leveraging-customer-ai.md)
+ Användningsexempel{#use-cases-journeys}
   + Enkelt användningsfall{#use-case-simple}
      + [Om det enkla användningssättet](using/usecase/about-the-simple-use-case.md)
      + [Konfigurera händelsen](using/usecase/configuring-the-event.md)
      + [Konfigurera datakällan](using/usecase/configuring-the-data-source.md)
      + [Bygga resan](using/usecase/simple-uc-building-the-journey.md)
   + Avancerat användningsfall{#use-case-advanced}
      + [Om avancerat användningsfall](using/usecase/about-the-advanced-use-case.md)
      + [Konfigurera händelserna](using/usecase/configuring-the-events.md)
      + [Konfigurera datakällor](using/usecase/configuring-the-data-sources.md)
      + [Bygga resan](using/usecase/building-the-journey.md)
+ Arbeta med API:er{#working-with-apis}
   + [Fånga API:er](using/api/capping.md)
+ Alfavärden {#alpha}
   + [Översikt över alfavärden](using/alpha/alpha-overview.md)
   + [Användargränssnitt](using/alpha/alpha-interface.md)
   + [Aktivitet för utlösare av segment](using/alpha/alpha-segment-trigger.md)
   + [Regelbaserade händelser](using/alpha/alpha-events.md)

