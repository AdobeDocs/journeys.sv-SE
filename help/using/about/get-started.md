---
title: Kom igång
description: Kom igång med Journey Orchestration
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
ht-degree: 3%

---


# Kom igång{#concept_y4b_4qt_52b}

I [!DNL Journey Orchestration]finns det två typer av användare som utför olika uppgifter: den **tekniska användaren** och **affärsanvändaren**. Användaråtkomst hanteras via produktprofiler och rättigheter. Mer information [](../about/access-management.md) om hur du konfigurerar användaråtkomst finns i.

Här följer de viktigaste stegen för att konfigurera och använda [!DNL Journey Orchestration]:

1. **Konfigurera en händelse**

   Du måste definiera den förväntade informationen och hur den ska behandlas. Den här konfigurationen är obligatorisk. Det här steget utförs av en **teknisk användare**.

   For more on this, refer to [](../event/about-events.md).

   ![](../assets/journey7.png)

1. **Konfigurera datakällan**

   Du måste definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor, till exempel under dina förhållanden. En inbyggd Adobe Experience Platform-datakälla konfigureras också vid etablering. Det här steget är inte nödvändigt om du bara utnyttjar data från händelserna under din resa. Det här steget utförs av en **teknisk användare**.

   For more on this, refer to [](../datasource/about-data-sources.md).

   ![](../assets/journey22.png)

1. **Konfigurera en åtgärd**

   Om du använder ett tredjepartssystem för att skicka meddelanden måste du konfigurera anslutningen till det [!DNL Journey Orchestration]. Se [](../action/about-custom-action-configuration.md).

   Om du använder Adobe Campaign Standard för att skicka meddelanden måste du konfigurera den inbyggda åtgärden. Se [](../action/working-with-adobe-campaign.md).

   Dessa steg utförs av en **teknisk användare**.

   ![](../assets/custom2.png)

1. **Designa din resa**

   Kombinera de olika händelserna, samordningen och åtgärderna för att skapa flerstegsscenarier för olika kanaler. Det här steget utförs av en **företagsanvändare**.

   Mer information finns i [](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Testa och publicera resan**

   Ni måste validera och aktivera resan. Det här steget utförs av en **företagsanvändare**.

   Mer information finns i [](../building-journeys/testing-the-journey.md) och [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Övervaka din resa**

   Använd de dedikerade rapportverktygen för att mäta hur effektiv din resa är. Det här steget utförs av en **företagsanvändare**.

   Mer information finns i [](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)

