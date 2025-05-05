---
product: adobe campaign
title: Använda segment i villkor
description: Lär dig använda ett segment
feature: Journeys
role: User
level: Intermediate
exl-id: 9a0490c8-c940-44d2-af1a-d1863c51465d
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 4%

---

# Använda segment i villkor {#using-a-segment}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


I det här avsnittet beskrivs hur du använder ett segment i ett resevillkor. Mer information om hur du använder en **[!UICONTROL Segment qualification]**-händelse under din resa finns i det här [avsnittet](../building-journeys/segment-qualification-events.md).

Följ de här stegen om du vill använda ett segment i ett resevillkor:

1. Öppna en resa, släpp en **[!UICONTROL Condition]**-aktivitet och välj **Data Source Condition**.
   ![](../assets/journey47.png)

1. Klicka på **[!UICONTROL Add a path]** för varje extra sökväg som behövs. Klicka på fältet **[!UICONTROL Expression]** för varje sökväg.

   ![](../assets/segment3.png)

1. Till vänster kan du visa **[!UICONTROL Segments]**-noden. Dra och släpp det segment som du vill använda för villkoret. Som standard är villkoret i segmentet sant.

   ![](../assets/segment4.png)

   >[!NOTE]
   >
   >Endast personer med segmentdeltagarstatus **Realiserad** och **Befintlig** betraktas som medlemmar i segmentet. Mer information om hur du utvärderar ett segment finns i [dokumentationen för segmenteringstjänsten](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=sv-SE#interpret-segment-results).

Mer information om resevillkor och hur du använder redigeraren för enkla uttryck finns i [Villkorsaktivitet](../building-journeys/condition-activity.md#about_condition).
