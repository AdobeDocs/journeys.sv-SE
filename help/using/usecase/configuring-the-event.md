---
product: adobe campaign
title: Konfigurera händelsen
description: Lär dig hur du konfigurerar händelsen för det enkla användningsfallet under resan
feature: Journeys
role: User
level: Intermediate
exl-id: 7423f4eb-005d-43a5-a403-97bee1e8d480
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '402'
ht-degree: 7%

---

# Konfigurera händelsen{#concept_y44_hcy_w2b}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


I vårt scenario måste vi ta emot en händelse varje gång en person går nära en fyr som är placerad intill spat. Den **tekniska användaren** måste konfigurera händelsen som systemet ska lyssna på under vår resa.

Mer information om händelsekonfiguration finns på [den här sidan](../event/about-events.md).

1. Klicka på fliken **[!UICONTROL Events]** på den översta menyn och klicka på **[!UICONTROL Add]** för att skapa en ny händelse.

   ![](../assets/journeyuc1_1.png)

1. Vi anger namnet utan mellanslag eller specialtecken: &quot;SpaBeacon&quot;.

   ![](../assets/journeyuc1_2.png)

1. Vi väljer sedan schemat och definierar den nyttolast som förväntas för den här händelsen. Vi väljer de fält som behövs i den normaliserade XDM-modellen. Vi behöver ett Experience Cloud-id för att identifiera personen i kundprofildatabasen i realtid: _endUserID:n > experience > mcid > id_. Ett ID genereras automatiskt för den här händelsen. Detta ID lagras i fältet **[!UICONTROL eventID]** (_upplevelse > kampanj > samordning > eventID_). Det system som skickar händelsen ska inte generera ett ID, det ska använda det som finns i nyttolastförhandsvisningen. I det här fallet används det här ID:t för att identifiera var beacon finns. Varje gång en person går i närheten av spaltbeacon skickas en händelse som innehåller detta specifika händelse-ID. På så sätt kan systemet veta vilken signal som utlöste den skickade händelsen.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >Listan med fält varierar mellan olika scheman. Enligt schemadefinitionen kan vissa fält vara obligatoriska och förmarkerade.

1. Vi måste välja en namnrymd. En namnrymd är förvald baserat på schemats egenskaper. Du kan behålla den som är förmarkerad. Mer information om namnutrymmen finns på [den här sidan](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. En tangent är förvald baserat på schemaegenskaper och det namnområde som har valts. Du kan behålla den.

   ![](../assets/journeyuc1_5.png)

1. Klicka på **[!UICONTROL Save]**.

1. Klicka på ikonen **[!UICONTROL View Payload]** för att förhandsgranska den nyttolast som systemet förväntar sig och dela den med den person som ansvarar för händelsen som skickar. Den här nyttolasten måste konfigureras i bakåtgången av administrationskonsolen för Mobile Services.

   ![](../assets/journeyuc1_7.png)

   Evenemanget är klart att användas under din resa. Nu måste du konfigurera mobilprogrammet så att det kan skicka den förväntade nyttolasten till API:erna för direktuppspelning. Läs [den här sidan](../event/additional-steps-to-send-events-to-journey-orchestration.md).
