---
product: adobe campaign
title: Om reserapporter
description: Lär dig hur du skapar reserapporter
feature: Journeys
role: User
level: Intermediate
exl-id: 93768321-b171-4338-a440-6ea189a85a4a
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '732'
ht-degree: 1%

---

# Om reserapporter {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Leveransdata och segmentkomponenter fylls bara i om du har Adobe Campaign Standard.

I det här avsnittet beskrivs hur du får tillgång till och använder rapporter för att mäta hur effektiva dina resor är.

## Rapporteringsgränssnitt {#reporting-interface}

I det övre verktygsfältet kan du till exempel ändra, spara eller skriva ut rapporten.

![](../assets/dynamic_report_toolbar.png)

Använd fliken **[!UICONTROL Project]** för att:

* **[!UICONTROL Open]**: öppnar en rapport eller mall som skapats tidigare.
* **[!UICONTROL Save As]**: Mallar dupliceras för att kunna ändra dem.
* **[!UICONTROL Refresh project]**: uppdaterar din rapport baserat på nya data och ändringar i filter.
* **[!UICONTROL Download CSV]**: exporterar dina rapporter till en CSV-fil.
* **[!UICONTROL Print]**: skriver ut din rapport.

På fliken **[!UICONTROL Edit]** kan du:

* **[!UICONTROL Undo]**: avbryter din senaste åtgärd på instrumentpanelen.
* **[!UICONTROL Redo]**: avbryter din senaste **[!UICONTROL Undo]**-åtgärd på instrumentpanelen.
* **[!UICONTROL Clear all]**: tar bort alla paneler på instrumentpanelen.

I tabellen **[!UICONTROL Insert]** kan du anpassa dina rapporter genom att lägga till diagram och tabeller på kontrollpanelen:

* **[!UICONTROL New Blank Panel]**: lägger till en ny tom panel på instrumentpanelen.
* **[!UICONTROL New Freeform]**: lägger till en ny friformstabell på instrumentpanelen.
* **[!UICONTROL New Line]**: lägger till ett nytt linjediagram på instrumentpanelen.
* **[!UICONTROL New Bar]**: lägger till ett nytt stapeldiagram på instrumentpanelen.

Med de vänstra flikarna kan du skapa en rapport och filtrera data efter behov.

![](../assets/dynamic_report_interface.png)

Med de här flikarna får du tillgång till följande objekt:

* **[!UICONTROL Panels]**: lägg till en tom panel eller ett frihandsformulär i rapporten för att börja filtrera dina data. Mer information finns i avsnittet [Lägga till paneler](../reporting/creating-your-journey-reports.md#adding-panels)
* **[!UICONTROL Visualizations]**: dra och släpp ett urval av visualiseringsobjekt för att ge rapporten en grafisk dimension. Mer information finns i avsnittet [Lägga till visualiseringar](../reporting/creating-your-journey-reports.md#adding-visualizations).
* **[!UICONTROL Components]**: anpassa dina rapporter med olika dimensioner, mätvärden, segment och tidsperioder. Mer information finns i avsnittet [Lägga till komponenter](../reporting/creating-your-journey-reports.md#adding-components).

## Översiktsmall för resa {#ootb-template}

Rapporterna är uppdelade i två kategorier: en färdig mall och anpassade rapporter.
Den färdiga mallen **[!UICONTROL Journey summary]** ger dig en tydlig bild av de viktigaste spårningsdata.

![](../assets/dynamic_report_journey_8.png)

Varje tabell representeras av sammanfattande nummer och diagram. Du kan ändra hur detaljerna visas i deras respektive visualiseringsinställningar.

Följande nyckeltal finns högst upp i rapporten:

* **[!UICONTROL Journey - Entered]**: Totalt antal personer som har nått resans anmälningshändelse.
* **[!UICONTROL Journey - Completion rate]**: Totalt antal personer som har nått slutet av resan (eller om en person inte uppfyller något villkor) jämfört med det totala antalet personer som har passerat resan.
* **[!UICONTROL Journey - Current]**: totalt antal personer som för närvarande befinner sig på resan.
* **[!UICONTROL Journey - Failed rate]**: Totalt antal resor som inte utfördes korrekt jämfört med antalet körningar.
* **[!UICONTROL Delivery - Messages sent]**: totalt antal skickade meddelanden.
* **[!UICONTROL Delivery rate]**: Totalt antal meddelanden som har levererats jämfört med skickade meddelanden.
* **[!UICONTROL Delivery - Bounce rate]**: Totalt antal meddelanden som studsade jämfört med skickade meddelanden.
* **[!UICONTROL Delivery - Unsubscribed rate]**: Totalt antal prenumerationer per mottagare jämfört med levererade meddelanden.
* **[!UICONTROL Delivery - Open rate]**: Totalt antal öppnade meddelanden jämfört med antalet levererade meddelanden.
* **[!UICONTROL Delivery - Click rate]**: Totalt antal klick i en leverans jämfört med antalet levererade meddelanden.

Med hjälp av reseflödesvisualiseringen kan ni se vägen för era målprofiler steg för steg under hela kundresan. Detta är endast tillgängligt när man riktar in sig på en resa. Den genereras automatiskt och kan inte ändras.

![](../assets/dynamic_report_journey_10.png)

Tabellen **[!UICONTROL Journey summary]** innehåller tillgängliga data för din resa, till exempel:

* **[!UICONTROL Entered]**: Totalt antal personer som har nått resans anmälningshändelse.
* **[!UICONTROL Completion rate]**: Totalt antal personer som har uppnått flödeskontrollen för färdens slut jämfört med det totala antalet personer som har passerat resan.
* **[!UICONTROL Current]**: totalt antal personer som för närvarande befinner sig på resan.
* **[!UICONTROL Failed]**: Totalt antal resor som inte kördes.
* **[!UICONTROL Failed rate]**: Totalt antal resor som inte utfördes korrekt jämfört med antalet körningar.

Tabellen **[!UICONTROL Top events]** visar de mest framgångsrika händelserna och **[!UICONTROL Top action]**, de mest framgångsrika åtgärderna på dina resor.

![](../assets/dynamic_report_journey_11.png)

Tabellen **[!UICONTROL Delivery - Sending summary]** innehåller de data som är tillgängliga för kundresan, till exempel:

* **[!UICONTROL Processed/sent]**: totalt antal skickade meddelanden.
* **[!UICONTROL Delivered rate]**: Totalt antal meddelanden som har levererats jämfört med skickade meddelanden.
* **[!UICONTROL Delivered]**: antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.
* **[!UICONTROL Bounce + error rate]**: Totalt antal meddelanden som studsade jämfört med skickade meddelanden.
* **[!UICONTROL Bounces + errors]**: Totalt antal fel som har ackumulerats under leverans och automatisk returbearbetning i relation till det totala antalet skickade meddelanden.

Tabellen **[!UICONTROL Delivery - Tracking summary]** innehåller tillgängliga data för att spåra om dina resor har levererats, till exempel:

* **[!UICONTROL Open Rate]**: procentandel öppnade meddelanden.
* **[!UICONTROL Open]**: antal gånger ett meddelande öppnades i en leverans.
* **[!UICONTROL Click trough rate]**: Totalt antal klick i en leverans jämfört med antalet levererade meddelanden.
* **[!UICONTROL Click]**: antal gånger ett innehåll klickades i en leverans.
* **[!UICONTROL Unsubscribe rate]**: procent av mottagarens avbeställning jämfört med de meddelanden som levererats.
* **[!UICONTROL Unsubscribed]**: Totalt antal prenumerationer per mottagare jämfört med levererade meddelanden.
