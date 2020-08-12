---
title: Komma igång
description: Komma igång med Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '291'
ht-degree: 95%

---


# Komma igång{#concept_y4b_4qt_52b}

I [!DNL Journey Orchestration] finns det två typer av användare som utför olika uppgifter: den **tekniska användaren** och **företagsanvändaren**. Användaråtkomst hanteras via produktprofiler och rättigheter. Se [](../about/access-management.md) för mer information om hur du konfigurerar användaråtkomster.

Här följer de viktigaste stegen för att konfigurera och använda [!DNL Journey Orchestration]:

1. **Konfigurera en händelse**

   Du måste definiera den förväntade informationen och hur den ska behandlas. Den här konfigurationen är obligatorisk. Det här steget utförs av en **teknisk användare**.

   Se [](../event/about-events.md) för mer information om detta.

   ![](../assets/journey7.png)

1. **Konfigurera datakällan**

   Du måste definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor, till exempel i dina villkor. En inbyggd Adobe Experience Platform-datakälla konfigureras också vid etablering. Det här steget är inte nödvändigt om du bara utnyttjar data från händelserna under din resa. Det här steget utförs av en **teknisk användare**.

   Se [](../datasource/about-data-sources.md) för mer information om detta.

   ![](../assets/journey22.png)

1. **Konfigurera en åtgärd**

   Om du använder ett tredjepartssystem för att skicka meddelanden måste du konfigurera anslutningen till din [!DNL Journey Orchestration]. Se [](../action/about-custom-action-configuration.md).

   Om du använder Adobe Campaign Standard för att skicka meddelanden måste du konfigurera den inbyggda åtgärden. Se [](../action/working-with-adobe-campaign.md).

   Dessa steg utförs av en **teknisk användare**.

   ![](../assets/custom2.png)

1. **Utforma din resa**

   Kombinera de olika händelserna, orkestreringen och åtgärderna för att skapa scenarier i flera steg över olika kanaler. Det här steget utförs av en **företagsanvändare**.

   Se [](../building-journeys/journey.md) för mer information.

   ![](../assets/journeyuc2_24.png)

1. **Testa och publicera resan**

   Du måste validera och aktivera resan. Det här steget utförs av en **företagsanvändare**.

   Se [](../building-journeys/testing-the-journey.md) och [](../building-journeys/publishing-the-journey.md) för mer information.

   ![](../assets/journeyuc2_32bis.png)

1. **Övervaka din resa**

   Använd de dedikerade rapporteringsverktygen för att mäta hur effektiv din resa är. Det här steget utförs av en **företagsanvändare**.

   Se [](../reporting/about-journey-reports.md) för mer information.

   ![](../assets/dynamic_report_journey_12.png)

