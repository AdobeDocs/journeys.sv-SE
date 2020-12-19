---
product: adobe campaign
solution: Journey Orchestration
title: Läsa segmentaktivitet
description: Läs mer om Läs segment-aktiviteten.
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '651'
ht-degree: 4%

---


# Läsa segmentaktivitet {#segment-trigger-activity}

## Om aktiviteten Läs segment {#about-segment-trigger-actvitiy}

>[!NOTE]
>
>Om det finns en färdig Adobe Campaign Standard-åtgärd på arbetsytan vid publiceringstid eller aktiveringstid i testläge kommer resan att strypas vid 13 ingångar per sekund. Annars begränsas resan till 1 000 händelser per sekund.

Med Läs segment-aktiviteten kan alla personer som tillhör ett Adobe Experience Platform-segment delta i en resa. Inträde i en resa kan genomföras antingen en gång eller regelbundet.

Säg att du har ett Guldkundssegment på Adobe Experience Platform. Med aktiviteten Läs segment kan alla personer som tillhör kundsegmentet Gold ta sig in på en resa och få dem att flöda in i personaliserade resor som utnyttjar alla resefunktioner: villkor, timers, events, actions.

>[!NOTE]
>
>Du kan inte ha ett hopp och ett **Lässegment**-aktivitet på samma resa. Du kan inte hoppa till en resa som börjar med en **Read segment**-händelse.

## Konfigurerar aktiviteten {#configuring-segment-trigger-activity}

>[!NOTE]
>
>På grund av fördröjningar för segmentexport går det inte att utlösa en segmentbaserad resa inom en kortare tidsram än en timme.

1. Ta fram kategorin **[!UICONTROL Orchestration]** och släpp en **[!UICONTROL Read Segment]**-aktivitet på arbetsytan.

   Aktiviteten måste placeras som det första steget i en resa.

1. Lägg till en **[!UICONTROL Label]** till aktiviteten (valfritt).

1. I fältet **[!UICONTROL Segment]** väljer du det Adobe Experience Platform-segment som ska passera resan och klickar sedan på **[!UICONTROL Save]**.

   >[!NOTE]
   >
   >Observera att du kan anpassa kolumnerna som visas i listan och sortera dem.

   ![](../assets/segment-trigger-segment-selection.png)

   När segmentet har lagts till kan du med knappen **[!UICONTROL Copy]** kopiera dess namn och ID:

   `{"name":"Gold customers,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-trigger-copy.png)

1. I fältet **[!UICONTROL Namespace]** väljer du det namnutrymme som ska användas för att identifiera personerna. Mer information om namnutrymmen finns i [det här avsnittet](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >Individer som tillhör ett segment som inte har den valda identiteten (namnutrymmet) bland sina olika identiteter kan inte ta sig in på resan.

1. Med aktiviteten **[!UICONTROL Read Segment]** kan du ange den tidpunkt då segmentet ska gå in i resan. Om du vill göra det klickar du på länken **[!UICONTROL Edit journey schedule]** för att komma åt resans egenskaper och konfigurerar sedan fältet **[!UICONTROL Scheduler type]**.

   ![](../assets/segment-trigger-schedule.png)

   Som standard anges resan **[!UICONTROL As soon as possible]** i segment, vilket innebär en timme efter att resan har publicerats. Om du vill att segmentet ska anges på en viss dag/tid eller på en återkommande basis, väljer du önskat värde i listan.

   >[!NOTE]
   >
   >Observera att avsnittet **[!UICONTROL Schedule]** bara är tillgängligt när en **[!UICONTROL Read Segment]**-aktivitet har släppts på arbetsytan.

   ![](../assets/segment-trigger-properties.png)

## Testa och publicera resan {#testing-publishing}

Med aktiviteten **[!UICONTROL Read Segment]** kan du testa resan antingen med en enhetsprofil eller med 100 slumpmässiga testprofiler som valts bland de profiler som är kvalificerade för segmentet.

Aktivera testläget och välj sedan önskat alternativ i den vänstra rutan.

![](../assets/segment-trigger-test-modes.png)

Sedan kan du konfigurera och köra testläget som vanligt. Detaljerade anvisningar om hur du testar en resa finns i [det här avsnittet](../building-journeys/testing-the-journey.md).

När testet är klart kan du med **[!UICONTROL Show logs]**-knappen se testresultaten enligt det valda testalternativet:

* **[!UICONTROL Single profile at a time]**: testloggarna visar samma information som när det enhetstestläget används. Mer information om detta finns i [det här avsnittet](../building-journeys/testing-the-journey.md#viewing_logs)

* **[!UICONTROL Up to 100 profiles at once]**: Med testloggarna kan du följa hur segmentexporten från Adobe Experience Platform fortskrider samt hur alla personer som passerat resan fortskrider.

   Observera att det inte går att följa förloppet för de personer som befinner sig på resan med hjälp av det visuella flödet om du testar resan med upp till 100 profiler samtidigt.

   ![](../assets/read-segment-log.png)

När testerna är slutförda kan du publicera din resa (se [Publicera resan](../building-journeys/publishing-the-journey.md)). Individer som tillhör segmentet kommer att gå in i resan det datum/den tidpunkt som anges i avsnittet **[!UICONTROL Scheduler]** för färdens egenskaper.

>[!NOTE]
>
>När du gör en ny version av en segmentbaserad resa som inte är återkommande (med början så snart som möjligt eller &quot;en gång&quot;) kommer alla personer som tidigare passerat resan inte att ange sin nya version igen när du kommer att publicera den. Om du vill att de ska kunna resa igen bör du duplicera resan.
