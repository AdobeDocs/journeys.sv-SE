---
title: Använda ett segment
description: Lär dig hur du använder ett segment
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
source-git-commit: a65a5db5b35291cbc2635f9ae67fd8c8c5284575
workflow-type: tm+mt
source-wordcount: '141'
ht-degree: 0%

---



# Skapa ett segment {#creating-a-segment}

Du kan antingen skapa ett segment med [Adobe Experience Platform segmenteringstjänsten](https://docs.adobe.com/content/help/en/experience-platform/segmentation/home.html) eller så kan du komma åt och skapa dem direkt i [!DNL Journey Orchestration].

1. Klicka på fliken på den översta menyn **[!UICONTROL Segments]** . Listan över segment i Adobe Experience Platform visas. Du kan söka efter ett visst segment i listan.

![](../assets/segment1.png)

1. Klicka **[!UICONTROL Add]** för att skapa ett nytt segment. På segmentdefinitionsskärmen kan du konfigurera alla obligatoriska fält för att definiera ditt segment. Konfigurationen är densamma som i segmenteringstjänsten. Se användarhandboken för [Segment Builder](https://docs.adobe.com/content/help/en/experience-platform/segmentation/ui/overview.html).

![](../assets/segment2.png)

Ditt segment kan nu användas i dina resor för att skapa villkor eller lägga till en **[!UICONTROL Segment qualification]** händelse. Se [Använda segment i villkor](../segment/using-a-segment.md) och [händelseaktiviteter](../building-journeys/segment-qualification-events.md).