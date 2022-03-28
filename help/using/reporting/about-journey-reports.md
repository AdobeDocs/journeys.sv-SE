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
source-wordcount: '0'
ht-degree: 0%

---

# Om reserapporter {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Leveransdata och segmentkomponenter fylls bara i om du har Adobe Campaign Standard.

I det här avsnittet beskrivs hur du får tillgång till och använder rapporter för att mäta hur effektiva dina resor är.

## Rapporteringsgränssnitt {#reporting-interface}

I det övre verktygsfältet kan du till exempel ändra, spara eller skriva ut rapporten.

![](../assets/dynamic_report_toolbar.png)

Använd **[!UICONTROL Project]** till:

* **[!UICONTROL Open]**: öppnar en tidigare skapad rapport eller mall.
* **[!UICONTROL Save As]**: duplicerar mallar för att kunna ändra dem.
* **[!UICONTROL Refresh project]**: uppdaterar din rapport baserat på nya data och ändringar i filter.
* **[!UICONTROL Download CSV]**: exporterar dina rapporter till en CSV-fil.
* **[!UICONTROL Print]**: skriver ut rapporten.

The **[!UICONTROL Edit]** kan du

* **[!UICONTROL Undo]**: avbryter din senaste åtgärd på instrumentpanelen.
* **[!UICONTROL Redo]**: avbryter ditt senaste **[!UICONTROL Undo]** på din instrumentpanel.
* **[!UICONTROL Clear all]**: tar bort alla paneler på kontrollpanelen.

The **[!UICONTROL Insert]** Med tabell kan du anpassa rapporter genom att lägga till diagram och tabeller på kontrollpanelen:

* **[!UICONTROL New Blank Panel]**: lägger till en ny tom panel på instrumentpanelen.
* **[!UICONTROL New Freeform]**: lägger till en ny friformstabell på kontrollpanelen.
* **[!UICONTROL New Line]**: lägger till ett nytt linjediagram på instrumentpanelen.
* **[!UICONTROL New Bar]**: lägger till ett nytt stapeldiagram på instrumentpanelen.

Med de vänstra flikarna kan du skapa en rapport och filtrera data efter behov.

![](../assets/dynamic_report_interface.png)

Med de här flikarna får du tillgång till följande objekt:

* **[!UICONTROL Panels]**: lägg till en tom panel eller ett frihandsritat i rapporten för att börja filtrera dina data. Mer information finns i [Lägga till paneler](../reporting/creating-your-journey-reports.md#adding-panels) section
* **[!UICONTROL Visualizations]**: dra och släpp ett urval av visualiseringsobjekt för att ge rapporten en grafisk dimension. Mer information finns i [Lägga till visualiseringar](../reporting/creating-your-journey-reports.md#adding-visualizations) -avsnitt.
* **[!UICONTROL Components]**: anpassa era rapporter med olika dimensioner, mätvärden, segment och tidsperioder. Mer information finns i [Lägga till komponenter](../reporting/creating-your-journey-reports.md#adding-components) -avsnitt.

## Översiktsmall för resa {#ootb-template}

Rapporterna är uppdelade i två kategorier: en färdig mall och anpassade rapporter.
färdiga mallar, **[!UICONTROL Journey summary]**, ger en tydlig bild av de viktigaste spårningsdata.

![](../assets/dynamic_report_journey_8.png)

Varje tabell representeras av sammanfattande nummer och diagram. Du kan ändra hur detaljerna visas i deras respektive visualiseringsinställningar.

Följande nyckeltal finns högst upp i rapporten:

* **[!UICONTROL Journey - Entered]**: Totalt antal personer som har nått resans inträde.
* **[!UICONTROL Journey - Completion rate]**: det totala antalet personer som har nått slutet av resan (eller om en person inte uppfyller något villkor) jämfört med det totala antalet personer som har passerat resan.
* **[!UICONTROL Journey - Current]**: det totala antalet personer som för närvarande befinner sig på resan.
* **[!UICONTROL Journey - Failed rate]**: det totala antalet resor som inte har slutförts, jämfört med antalet körningar.
* **[!UICONTROL Delivery - Messages sent]**: totalt antal skickade meddelanden.
* **[!UICONTROL Delivery rate]**: Totalt antal meddelanden som har levererats jämfört med skickade meddelanden.
* **[!UICONTROL Delivery - Bounce rate]**: Totalt antal meddelanden som studsade jämfört med skickade meddelanden.
* **[!UICONTROL Delivery - Unsubscribed rate]**: Totalt antal avbeställningar per mottagare jämfört med levererade meddelanden.
* **[!UICONTROL Delivery - Open rate]**: Totalt antal öppnade meddelanden jämfört med antalet levererade meddelanden.
* **[!UICONTROL Delivery - Click rate]**: Totalt antal klick i en leverans jämfört med antalet levererade meddelanden.

Med hjälp av reseflödesvisualiseringen kan ni se vägen för era målprofiler steg för steg under hela kundresan. Detta är endast tillgängligt när man riktar in sig på en resa. Den genereras automatiskt och kan inte ändras.

![](../assets/dynamic_report_journey_10.png)

The **[!UICONTROL Journey summary]** tabellen innehåller de data som är tillgängliga för din resa, till exempel:

* **[!UICONTROL Entered]**: Totalt antal personer som har nått resans inträde.
* **[!UICONTROL Completion rate]**: det totala antalet personer som har nått slutflödeskontrollen för resan jämfört med det totala antalet personer som har passerat resan.
* **[!UICONTROL Current]**: det totala antalet personer som för närvarande befinner sig på resan.
* **[!UICONTROL Failed]**: Totalt antal resor som inte har slutförts.
* **[!UICONTROL Failed rate]**: det totala antalet resor som inte har slutförts, jämfört med antalet körningar.

The **[!UICONTROL Top events]** tabellen visar de mest framgångsrika händelserna och **[!UICONTROL Top action]**, de mest framgångsrika åtgärderna på era resor.

![](../assets/dynamic_report_journey_11.png)

The **[!UICONTROL Delivery - Sending summary]** tabellen innehåller de data som är tillgängliga för kundens leveranser, till exempel:

* **[!UICONTROL Processed/sent]**: totalt antal skickade meddelanden.
* **[!UICONTROL Delivered rate]**: Totalt antal meddelanden som har levererats jämfört med skickade meddelanden.
* **[!UICONTROL Delivered]**: antalet meddelanden som har skickats, i relation till det totala antalet skickade meddelanden.
* **[!UICONTROL Bounce + error rate]**: Totalt antal meddelanden som studsade jämfört med skickade meddelanden.
* **[!UICONTROL Bounces + errors]**: det totala antalet fel som sammanställts under leveransen och den automatiska returbearbetningen i förhållande till det totala antalet skickade meddelanden.

The **[!UICONTROL Delivery - Tracking summary]** tabellen innehåller tillgängliga uppgifter för att spåra hur väl resorna har lyckats, t.ex.

* **[!UICONTROL Open Rate]**: procentandel öppnade meddelanden.
* **[!UICONTROL Open]**: antal gånger ett meddelande öppnades i en leverans.
* **[!UICONTROL Click trough rate]**: Totalt antal klick i en leverans jämfört med antalet levererade meddelanden.
* **[!UICONTROL Click]**: antalet gånger som ett innehåll klickades i en leverans.
* **[!UICONTROL Unsubscribe rate]**: Andel av mottagarens uppsägning av prenumerationen jämfört med de levererade meddelandena.
* **[!UICONTROL Unsubscribed]**: Totalt antal avbeställningar per mottagare jämfört med levererade meddelanden.
