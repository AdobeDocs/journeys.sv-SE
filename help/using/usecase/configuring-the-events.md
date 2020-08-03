---
title: Konfigurera händelserna
description: Lär dig hur du konfigurerar händelser för resan med avancerad användning
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470
workflow-type: tm+mt
source-wordcount: '390'
ht-degree: 0%

---


# Konfigurera händelserna {#concept_sbp_5cy_w2b}

I vårt scenario måste vi få ett event varje gång en person kommer in på Marlton-hotellet och restaurangen. Den **tekniska användaren** måste konfigurera de två händelser som vi vill att systemet ska lyssna på under vår resa.

Mer information om händelsekonfiguration finns i [](../event/about-events.md).

1. Klicka på **[!UICONTROL Events]** fliken i den övre menyn och klicka på **[!UICONTROL Add]** för att skapa en ny händelse.

   ![](../assets/journeyuc1_1.png)

1. Vi anger namnet utan mellanslag eller specialtecken: &quot;LobbyBeacon&quot;.

   ![](../assets/journeyuc2_1.png)

<!--li>Select the **[!UICONTROL Mobile - Streaming Ingestion APIs]** event type. Events are sent from the customers' mobile phone through the Mobile SDK.![](../assets/journeyuc2_3.png" placement="break" width="800" id="image_is5_2sn_z2b"/></li-->

1. Vi väljer sedan schemat och definierar den nyttolast som förväntas för den här händelsen. Vi väljer de fält som behövs i den normaliserade XDM-modellen. Vi behöver Experience Cloud-ID:t för att kunna identifiera personen i kundprofildatabasen i realtid: &quot;endUserIDs > _experience > mcid > id&quot;.

   Vi behöver också en registreringstoken för att skicka push-meddelanden: &quot;_experience > campaign > message > profile > pushNotificationTokens > token&quot;

   Ett ID genereras automatiskt för den här händelsen. Detta ID lagras i **[!UICONTROL eventID]** fältet (&quot;_experience > campaign > orchestration > eventID&quot;). Det system som skickar händelsen ska inte generera ett ID, det ska använda det som finns i nyttolastförhandsvisningen. I det här fallet används det här ID:t för att identifiera var beacon finns. Varje gång en person går nära lobbybeacon skickas en händelse som innehåller detta specifika händelse-ID. Samma princip gäller för restaurangfynden. På så sätt kan systemet veta vilken signal som utlöste den skickade händelsen.

   ![](../assets/journeyuc2_2.png)

   >[!NOTE]
   >
   >Listan med fält varierar mellan olika scheman. Enligt schemadefinitionen kan vissa fält vara obligatoriska och förmarkerade.

1. Vi måste välja ett namnutrymme. Ett namnutrymme är förvalt baserat på schemaegenskaper. Du kan behålla den förmarkerade. Mer information om namnutrymmen finns i [](../event/selecting-the-namespace.md).

   ![](../assets/journeyuc2_4.png)

1. En tangent är förvald baserat på schemaegenskaper och det namnområde som har valts. Du kan behålla den.

   ![](../assets/journeyuc2_4bis.png)

1. Klicka på **[!UICONTROL Save]**.

1. Klicka på **[!UICONTROL View Payload]** ikonen för att förhandsgranska den nyttolast som systemet förväntar sig och dela den med den person som ansvarar för händelsen som skickar.  Den här nyttolasten måste konfigureras i bakåtgången av administrationskonsolen för Mobile Services.

   ![](../assets/journeyuc2_5.png)

På samma sätt skapar du händelsen&quot;RestaurantBeacon&quot;. Dina två beacon-händelser skapas och kan nu användas under vår resa. Nu måste du konfigurera mobilprogrammet så att det kan skicka den förväntade nyttolasten till API:ernas slutpunkt för direktuppspelningsinmatning. Se [](../event/additional-steps-to-send-events-to-journey-orchestration.md).
