---
product: adobe campaign
title: Definiera nyttolastfält
description: Lär dig hur du definierar nyttolastfälten
feature: Journeys
role: User
level: Intermediate
exl-id: 9d385b64-46cd-489b-9c18-352fa2a2dbba
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '294'
ht-degree: 4%

---

# Definiera nyttolastfält {#concept_yrw_3qt_52b}

Nyttolastdefinitionen gör att du kan välja vilken information systemet förväntar sig från händelsen under din resa och nyckeln för att identifiera vilken person som är associerad med händelsen. Nyttolasten baseras på Experience Cloud XDM-fältdefinitionen. Mer information om XDM finns på [den här sidan](https://experienceleague.adobe.com/docs/experience-platform/xdm/home.html?lang=sv).

1. Välj ett XDM-schema i listan och klicka på fältet **[!UICONTROL Payload]** eller på ikonen **[!UICONTROL Edit]** .

   ![](../assets/journey8.png)

   Alla fält som definieras i schemat visas. Listan med fält varierar mellan olika scheman. Du kan söka efter ett specifikt fält eller använda filtren för att visa alla noder och fält eller endast de markerade fälten. Enligt schemadefinitionen kan vissa fält vara obligatoriska och förmarkerade. Du kan inte avmarkera dem. Alla fält som är obligatoriska för att händelsen ska kunna tas emot av Journey Orchestration är som standard markerade.

   >[!NOTE]
   >
   >Kontrollera att du har lagt till&quot;orchestration&quot;-blandningen i XDM-schemat. Detta garanterar att schemat innehåller all nödvändig information som kan användas med [!DNL Journey Orchestration].

   ![](../assets/journey9.png)

1. Markera de fält som du förväntar dig ska tas emot från händelsen. Det här är de områden som affärsanvändaren kommer att utnyttja under resan. De måste även innehålla den nyckel som ska användas för att identifiera den person som är associerad med händelsen (se [den här sidan](../event/defining-the-event-key.md)).

   ![](../assets/journey10.png)

   >[!NOTE]
   >
   >För systemgenererade händelser läggs fältet **[!UICONTROL eventID]** automatiskt till i listan med markerade fält så att [!DNL Journey Orchestration] kan identifiera händelsen. Det system som skickar händelsen ska inte generera ett ID, det ska använda det som finns i nyttolastförhandsvisningen. Läs [den här sidan](../event/previewing-the-payload.md).

1. När du är klar med att markera de fält som behövs klickar du på **[!UICONTROL Save]** eller trycker på **[!UICONTROL Enter]**.

   ![](../assets/journey11.png)

   Antalet markerade fält visas i fältet **[!UICONTROL Payload]**.

   ![](../assets/journey12.png)
