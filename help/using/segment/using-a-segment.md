---
product: adobe campaign
title: Använda ett segment
description: Lär dig hur du använder ett segment
feature: Resor
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '163'
ht-degree: 3%

---

# Använda segment i villkor {#using-a-segment}

I det här avsnittet beskrivs hur du använder ett segment i ett resevillkor. Mer information om hur du använder en **[!UICONTROL Segment qualification]**-händelse under din resa finns i det här [avsnittet](../building-journeys/segment-qualification-events.md).

Följ de här stegen om du vill använda ett segment i ett resevillkor:

1. Öppna en resa, släpp en **[!UICONTROL Condition]**-aktivitet och välj **Villkor för datakälla**.
   ![](../assets/journey47.png)

1. Klicka på **[!UICONTROL Add a path]** för varje extra sökväg som behövs. Klicka på fältet **[!UICONTROL Expression]** för varje sökväg.

   ![](../assets/segment3.png)

1. Till vänster kan du visa noden **[!UICONTROL Segments]**. Dra och släpp det segment som du vill använda för villkoret. Som standard är villkoret i segmentet sant.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Endast individer med segmentdeltagarstatus **Realiserad** och **Befintlig** betraktas som medlemmar i segmentet. Mer information om hur du utvärderar ett segment finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

Mer information om resevillkor och hur du använder redigeraren för enkla uttryck finns i [Villkorsaktivitet](../building-journeys/condition-activity.md#about_condition).
