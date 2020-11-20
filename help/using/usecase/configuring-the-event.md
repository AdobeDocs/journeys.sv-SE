---
product: adobe campaign
solution: Journey Orchestration
title: Konfigurera händelsen
description: Lär dig hur du konfigurerar händelsen för det enkla användningsfallet under resan
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 8%

---


# Konfigurera händelsen{#concept_y44_hcy_w2b}

I vårt scenario måste vi ta emot en händelse varje gång en person går nära en fyr som är placerad intill spat. Den **tekniska användaren** måste konfigurera händelsen som systemet ska lyssna på under vår resa.

Mer information om händelsekonfiguration finns på [den här sidan](../event/about-events.md).

1. In the top menu, click the **[!UICONTROL Events]** tab and click **[!UICONTROL Add]** to create a new event.

   ![](../assets/journeyuc1_1.png)

1. Vi anger namnet utan mellanslag eller specialtecken: &quot;SpaBeacon&quot;.

   ![](../assets/journeyuc1_2.png)

1. Vi väljer sedan schemat och definierar den nyttolast som förväntas för den här händelsen. Vi väljer de fält som behövs i den normaliserade XDM-modellen. Vi behöver Experience Cloud-ID:t för att identifiera personen i kundprofildatabasen i realtid: _endUserIDs > experience > mcid > id_. Ett ID genereras automatiskt för den här händelsen. Detta ID lagras i **[!UICONTROL eventID]** fältet (_upplevelse > kampanj > samordning > eventID_). Det system som skickar händelsen ska inte generera ett ID, det ska använda det som finns i nyttolastförhandsvisningen. I det här fallet används det här ID:t för att identifiera var beacon finns. Varje gång en person går i närheten av spaltbeacon skickas en händelse som innehåller detta specifika händelse-ID. På så sätt kan systemet veta vilken signal som utlöste den skickade händelsen.

   ![](../assets/journeyuc1_3.png)

   >[!NOTE]
   >
   >Listan med fält varierar mellan olika scheman. Enligt schemadefinitionen kan vissa fält vara obligatoriska och förmarkerade.

1. Vi måste välja en namnrymd. En namnrymd är förvald baserat på schemats egenskaper. Du kan behålla den som är förmarkerad. For more information on namespaces, see [this page](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc1_6.png)

1. En tangent är förvald baserat på schemaegenskaper och det namnområde som har valts. Du kan behålla den.

   ![](../assets/journeyuc1_5.png)

1. Klicka på **[!UICONTROL Save]**.

1. Klicka på **[!UICONTROL View Payload]** ikonen för att förhandsgranska den nyttolast som systemet förväntar sig och dela den med den person som ansvarar för händelsen som skickar. Den här nyttolasten måste konfigureras i bakåtgången av administrationskonsolen för Mobile Services.

   ![](../assets/journeyuc1_7.png)

   Evenemanget är klart att användas under din resa. Nu måste du konfigurera mobilprogrammet så att det kan skicka den förväntade nyttolasten till API:ernas slutpunkt för direktuppspelningsinmatning. Läs [den här sidan](../event/additional-steps-to-send-events-to-journey-orchestration.md).