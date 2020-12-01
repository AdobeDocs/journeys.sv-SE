---
product: adobe campaign
solution: Journey Orchestration
title: Definiera nyttolastfält
description: Lär dig hur du definierar nyttolastfälten
translation-type: tm+mt
source-git-commit: 81bb0b5da38217f9290214901c64e90d7ec2ba0e
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 6%

---


# Definiera nyttolastfält {#concept_yrw_3qt_52b}

Nyttolastdefinitionen gör att du kan välja vilken information systemet förväntar sig från händelsen under din resa och nyckeln för att identifiera vilken person som är associerad med händelsen. Nyttolasten baseras på Experience Cloud XDM-fältdefinitionen. For more information on XDM, refer to [this page](https://docs.adobe.com/content/help/sv-SE/experience-platform/xdm/home.html).

1. Välj ett XDM-schema i listan och klicka på **[!UICONTROL Payload]** fältet eller på **[!UICONTROL Edit]** -ikonen.

   ![](../assets/journey8.png)

   Alla fält som definieras i schemat visas. Listan med fält varierar mellan olika scheman. Du kan söka efter ett specifikt fält eller använda filtren för att visa alla noder och fält eller endast de markerade fälten. Enligt schemadefinitionen kan vissa fält vara obligatoriska och förmarkerade. Du kan inte avmarkera dem.

   >[!NOTE]
   >
   >Kontrollera att du har lagt till&quot;orchestration&quot;-blandningen i XDM-schemat. Detta säkerställer att schemat innehåller all information som krävs för att arbeta med [!DNL Journey Orchestration].

   ![](../assets/journey9.png)

1. Markera de fält som du förväntar dig ska tas emot från händelsen. Det här är de områden som affärsanvändaren kommer att utnyttja under resan. De måste även innehålla den nyckel som ska användas för att identifiera den person som är associerad med händelsen (se [den här sidan](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >För systemgenererade händelser läggs **[!UICONTROL eventID]** fältet automatiskt till i listan över valda fält så att händelsen kan [!DNL Journey Orchestration] identifieras. Det system som skickar händelsen ska inte generera ett ID, det ska använda det som finns i nyttolastförhandsvisningen. Läs [den här sidan](../event/previewing-the-payload.md).

1. När du är klar med att markera önskade fält klickar du på **[!UICONTROL Save]** eller trycker **[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   Antalet markerade fält visas i **[!UICONTROL Payload]** fältet.

   ![](../assets/journey12.png)
