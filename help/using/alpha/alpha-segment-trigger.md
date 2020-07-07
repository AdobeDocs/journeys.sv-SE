---
title: Aktivitet för utlösare av segment
description: Lär dig xxxx
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
source-git-commit: c8d28b51f14ba511a860874e45d341a6977c58fa
workflow-type: tm+mt
source-wordcount: '453'
ht-degree: 0%

---


# Aktivitet för utlösare av segment {#segment-trigger-activity}

## Om aktiviteten Utlösare för segment {#about-segment-trigger-actvitiy}

Med aktiviteten Segmentutlösare kan du göra så att alla personer som tillhör ett Experience Platform-segment kan ta sig in på en resa. Ingången till en resa kan genomföras antingen en gång eller regelbundet.

Säg att du har ett Guldkundssegment på Experience Platform. Med aktiviteten Segment Trigger kan ni få alla personer som tillhör kundsegmentet Gold att komma in på en resa och få dem att flöda in i personaliserade resor som utnyttjar alla resefunktioner: villkor, timers, events, actions.

>[!NOTE]
>
>På grund av fördröjningar för segmentexport går det inte att utlösa en segmentbaserad resa inom en kortare tidsram än en timme.

## Konfigurera aktiviteten {#configuring-segment-trigger-activity}

1. Ge kategorin en ny **[!UICONTROL Orchestration]** dimension och släpp en **[!UICONTROL Segment Trigger]** aktivitet på arbetsytan.

   Aktiviteten måste placeras som det första steget i en resa.

1. Konfigurera aktiviteten **[!UICONTROL Scheduler type]**.

   Som standard kommer segmentet att gå in i resan, **[!UICONTROL As soon as possible]** vilket innebär en timme efter det att resan har publicerats. Om du vill att segmentet ska anges på en viss dag/tid eller på en återkommande basis, väljer du önskat alternativ i listan.

   Vid återkommande resor kan du också definiera resans början och slut.

   ![](../assets/segment-trigger-schedule.png)

1. I **[!UICONTROL Segment]** fältet väljer du det Experience Platform-segment som ska användas för resan och klickar sedan på **[!UICONTROL Save]**.

   ![](../assets/segment-trigger-segment-selection.png)

1. I **[!UICONTROL Namespace]** fältet väljer du det namnutrymme som ska användas för att identifiera personerna. For more on namespaces, refer to [this section](../event/selecting-the-namespace.md).

   >[!NOTE]
   >
   >Individer som tillhör ett segment som inte har den valda identiteten (namnutrymmet) bland sina olika identiteter kan inte ta sig in på resan.

1. Bekräfta genom **[!UICONTROL Ok]** att klicka. Sedan kan ni utnyttja tillgängliga aktiviteter för att skapa er resa.

1. När resan är klar kan du testa den (se [Testa resan](../building-journeys/testing-the-journey.md)).

   När testläget aktiveras på en resa som börjar med en **[!UICONTROL Segment Trigger]** aktivitet väljs 100 testprofiler slumpmässigt bland de profiler som är kvalificerade för det valda segmentet. Testloggarna gör att du kan se sökvägen till personer på resan och eventuella fel som uppstått (se [Visa loggarna](../building-journeys/testing-the-journey.md#viewing_logs)).

   >[!NOTE]
   >
   >Observera att du inte kommer att kunna se de 100 personer som följer resan med hjälp av funktionen för visuellt flöde som finns på enhetsresor.

1. Du kan sedan publicera din resa (se [Publicera resan](../building-journeys/publishing-the-journey.md)). Individer som tillhör segmentet kommer att gå in i resan det datum/den tid som anges i aktivitetsplaneraren för utlösare för segment.

   >[!IMPORTANT]
   >
   >Tänk på att segment i Experience Platform beräknas antingen en gång om dagen (**gruppsegment** ) eller i realtid (**direktuppspelade** segment).
   >
   >Om det valda segmentet direktuppspelas kan de personer som tillhör det segmentet komma in på resan i realtid. Om segmentet är en batch kan personer som nyligen är kvalificerade för det här segmentet komma in på resan när segmentberäkningen görs på Experience Platform.
