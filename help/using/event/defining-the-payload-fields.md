---
title: Definiera nyttolastfält
description: Lär dig hur du definierar nyttolastfälten
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '279'
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
   >Fältet läggs automatiskt till i listan med markerade fält så att **[!UICONTROL eventID]** händelsen [!DNL Journey Orchestration] kan identifieras. Det system som skickar händelsen ska inte generera ett ID, det ska använda det som finns i nyttolastförhandsvisningen. Läs [den här sidan](../event/previewing-the-payload.md).

1. När du är klar med att markera önskade fält klickar du på **[!UICONTROL Save]** eller trycker **[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   Antalet markerade fält visas i **[!UICONTROL Payload]** fältet.

   ![](../assets/journey12.png)
