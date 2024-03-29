---
product: adobe campaign
title: Skapa reserapporter
description: Lär dig skapa reserapporter
feature: Journeys
role: User
level: Intermediate
exl-id: 0d2417e9-5b3f-442d-a00d-8b4df239d952
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 2%

---

# Skapa reserapporter {#concept_rfj_wpt_52b}

## Få åtkomst till och skapa rapporter {#accessing-reports}

>[!NOTE]
>
>När du har tagit bort en resa är alla tillhörande rapporter inte längre tillgängliga.

I det här avsnittet beskrivs hur du skapar eller använder färdiga rapporter. Kombinera paneler, komponenter och visualiseringar för att bättre kunna spåra framgången i dina resor.

Så här får du tillgång till reserapporter och kan börja följa upp hur bra dina leveranser är:

1. Klicka på fliken **[!UICONTROL Home]** på den övre menyn.

1. Välj den resa du vill rapportera om.

   Observera att du även kan komma åt dina rapporter genom att klicka på **Rapport** när du hovrar över en resa i listan över resor.

   ![](../assets/dynamic_report_journey.png)

1. Klicka på **[!UICONTROL Report]** ikonen längst upp till höger på skärmen.

   ![](../assets/dynamic_report_journey_2.png)

1. The **[!UICONTROL Journey summary]** en färdig rapport visas på skärmen. Klicka på **[!UICONTROL Close]** -knappen.

   ![](../assets/dynamic_report_journey_12.png)

1. Klicka på **[!UICONTROL Create new project]** för att skapa en helt ny rapport.

   ![](../assets/dynamic_report_journey_3.png)

1. Från **[!UICONTROL Panels]** kan du dra och släppa så många paneler eller frihandstabeller som behövs. Mer information finns i [section](#adding-panels).

   ![](../assets/dynamic_report_journey_4.png)

1. Du kan sedan börja filtrera dina data genom att dra och släppa mått och mätvärden från **[!UICONTROL Components]** till din frihandstabell. Mer information finns i [section](#adding-components).

   ![](../assets/dynamic_report_journey_5.png)

1. Om du vill få en tydligare bild av dina data kan du lägga till visualiseringar från **[!UICONTROL Visualizations]** -fliken. Mer information finns i [section](#adding-visualizations).

## Lägga till paneler{#adding-panels}

### Lägga till en tom panel {#adding-a-blank-panel}

För att starta rapporten kan du lägga till en uppsättning paneler i en färdig eller anpassad rapport. Varje panel innehåller olika datauppsättningar och består av frihandstabeller och visualiseringar.

Med den här panelen kan du skapa rapporter efter behov. Du kan lägga till så många paneler du vill i dina rapporter för att filtrera data med olika tidsperioder.

1. Klicka på **[!UICONTROL Panels]** ikon. Du kan också lägga till en panel genom att klicka på **[!UICONTROL Insert tab]** och markera **[!UICONTROL New Blank Panel]**.

   ![](../assets/dynamic_report_panel_1.png)

1. Dra och släpp **[!UICONTROL Blank Panel]** till din instrumentpanel.

   ![](../assets/dynamic_report_panel.png)

Nu kan du lägga till en friformstabell på panelen för att börja målinrikta data.

### Lägga till en frihandstabell {#adding-a-freeform-table}

Med frihandstabeller kan du skapa en tabell för att analysera data med hjälp av de olika mätvärden och dimensioner som finns i **[!UICONTROL Component]** tabell.

Det går att ändra storlek på alla tabeller och visualiseringar och de kan flyttas för att bättre anpassa rapporten.

1. Klicka på **[!UICONTROL Panels]** ikon.

   ![](../assets/dynamic_report_panel_1.png)

1. Dra och släpp **[!UICONTROL Freeform]** objekt på kontrollpanelen.

   Du kan också lägga till en tabell genom att klicka på **[!UICONTROL Insert]** flik och markera **[!UICONTROL New Freeform]** eller genom att klicka **[!UICONTROL Add a freeform table]** i en tom panel.

   ![](../assets/dynamic_report_panel_2.png)

1. Dra och släpp objekt från **[!UICONTROL Components]** i kolumnerna och raderna för att skapa tabellen.

   ![](../assets/dynamic_report_freeform_3.png)

1. Klicka på **[!UICONTROL Settings]** om du vill ändra hur data visas i kolumnerna.

   ![](../assets/dynamic_report_freeform_4.png)

   The **[!UICONTROL Column settings]** består av

   * **[!UICONTROL Number]**: I kan du visa eller dölja sammanfattningsnummer i kolumnen.
   * **[!UICONTROL Percent]**: I kan du visa eller dölja procentsatser i kolumnen.
   * **[!UICONTROL Interpret zero as no value]**: gör att du kan visa eller dölja när värdet är lika med noll.
   * **[!UICONTROL Background]**: I kan du visa eller dölja den vågräta förloppsindikatorn i celler.
   * **[!UICONTROL Include retries]**: gör att du kan inkludera återförsök i resultatet. Detta är endast tillgängligt för **[!UICONTROL Sent]** och **[!UICONTROL Bounces + Errors]**.

1. Markera en eller flera rader och klicka på **[!UICONTROL Visualize]** ikon. En visualisering läggs till för att återspegla de rader du har valt.

   ![](../assets/dynamic_report_freeform_5.png)

Nu kan du lägga till så många komponenter du behöver och även lägga till visualiseringar för att ge grafiska representationer av dina data.

## Lägga till komponenter{#adding-components}

Med komponenter kan du anpassa rapporter med olika dimensioner, mätvärden och tidsperioder.

1. Klicka på **[!UICONTROL Components]** för att komma åt komponentlistan.

   ![](../assets/dynamic_report_components.png)

1. Varje kategori som presenteras i **[!UICONTROL Components]** -fliken visar de fem mest använda objekten. Klicka på namnet på en kategori för att få tillgång till dess fullständiga lista över komponenter.

   Komponenttabellen är uppdelad i tre kategorier:

   * **[!UICONTROL Dimensions]**: Hämta information från leveransloggen, t.ex. mottagarens webbläsare eller domän, eller leveransens framgångar.
   * **[!UICONTROL Metrics]**: Hämta information om status för ett meddelande. Om ett meddelande till exempel har levererats och användaren har öppnat det.
   * **[!UICONTROL Time]**: Ange en tidsperiod för tabellen.

1. Dra och släpp komponenter på en panel för att börja filtrera data.

Du kan dra och släppa så många komponenter som behövs och jämföra dem med varandra.

## Lägga till visualiseringar{#adding-visualizations}

The **[!UICONTROL Visualizations]** Med -fliken kan du dra och släppa visualiseringsobjekt, till exempel område, munstycke och diagram. Visualiseringar ger er grafiska representationer av era data.

1. I **[!UICONTROL Visualizations]** drar och släpper du ett visualiseringsobjekt på en panel.

   ![](../assets/dynamic_report_visualization_1.png)

1. När du har lagt till en visualisering på panelen kommer dina rapporter automatiskt att identifiera data i din frihandstabell. Välj inställningar för visualiseringen.
1. Om du har fler än en friformstabell väljer du den datakälla som du vill lägga till i diagrammet i **[!UICONTROL Data Source Settings]** -fönstret. Det här fönstret är också tillgängligt genom att klicka på den färgade punkten bredvid din visualiseringstitel.

   ![](../assets/dynamic_report_visualization_2.png)

1. Klicka på **[!UICONTROL Visualization]** inställningsknapp för att direkt ändra diagramtyp eller vad som visas på den, till exempel:

   * **[!UICONTROL Percentages]**: Visar värdena i procent.
   * **[!UICONTROL Anchor Y Axis at Zero]**: Tvingar y-axeln att vara noll även om värdena ligger över noll.
   * **[!UICONTROL Legend visible]**: Gör att du kan dölja teckenförklaringen.
   * **[!UICONTROL Normalization]**: Tvingar värdena att matcha.
   * **[!UICONTROL Display Dual Axis]**: Lägger till en annan axel i diagrammet.
   * **[!UICONTROL Limit Max Items]**: Begränsar antalet diagram som visas.
   * **[!UICONTROL Threshold]**: Gör att du kan ange ett tröskelvärde för diagrammet. Det visas som en svart prickad linje.

   ![](../assets/dynamic_report_visualization_3.png)

Med den här visualiseringen kan ni få en tydligare bild av era data i era rapporter.
