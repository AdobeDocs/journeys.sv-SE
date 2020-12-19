---
product: adobe campaign
solution: Journey Orchestration
title: Komma igång
description: Upptäck de viktigaste stegen för att konfigurera Journey Orchestration och bygga din första resa.
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 87%

---


# Komma igång{#concept_y4b_4qt_52b}

I [!DNL Journey Orchestration] finns det två typer av användare som utför olika uppgifter: den **tekniska användaren** och **företagsanvändaren**. Användaråtkomst hanteras via produktprofiler och rättigheter. Läs [den här sidan](../about/access-management.md) om du vill veta mer om hur du konfigurerar användaråtkomst.

Här följer de viktigaste stegen för att konfigurera och använda [!DNL Journey Orchestration]:

1. **Konfigurera en händelse**

   Du måste definiera den förväntade informationen och hur den ska behandlas. Den här konfigurationen är obligatorisk. Det här steget utförs av en **teknisk användare**.

   Se denna [sida](../event/about-events.md) för mer information om detta.

   ![](../assets/journey7.png)

1. **Konfigurera datakällan**

   Du måste definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor, till exempel i dina villkor. En inbyggd datakälla i Adobe Experience Platform konfigureras även vid tidpunkten för etablering. Det här steget är inte nödvändigt om du bara utnyttjar data från händelserna under din resa. Det här steget utförs av en **teknisk användare**.

   Se denna [sida](../datasource/about-data-sources.md) för mer information om detta.

   ![](../assets/journey22.png)

1. **Konfigurera en åtgärd**

   Om du använder ett tredjepartssystem för att skicka meddelanden måste du konfigurera anslutningen till din [!DNL Journey Orchestration]. Läs [den här sidan](../action/about-custom-action-configuration.md).

   Om du använder Adobe Campaign Standard för att skicka meddelanden måste du konfigurera den inbyggda åtgärden. Läs [den här sidan](../action/working-with-adobe-campaign.md).

   Dessa steg utförs av en **teknisk användare**.

   ![](../assets/custom2.png)

1. **Utforma din resa**

   Kombinera de olika händelserna, orkestreringen och åtgärderna för att skapa scenarier i flera steg över olika kanaler. Det här steget utförs av en **företagsanvändare**.

   Mer information finns på [den här sidan](../building-journeys/journey.md).

   ![](../assets/journeyuc2_24.png)

1. **Testa och publicera resan**

   Du måste validera och aktivera resan. Det här steget utförs av en **företagsanvändare**.

   Mer information finns på sidorna [Testa resan](../building-journeys/testing-the-journey.md) och [Publicera resan](../building-journeys/publishing-the-journey.md).

   ![](../assets/journeyuc2_32bis.png)

1. **Övervaka din resa**

   Använd de dedikerade rapporteringsverktygen för att mäta hur effektiv din resa är. Det här steget utförs av en **företagsanvändare**.

   Mer information finns på [den här sidan](../reporting/about-journey-reports.md).

   ![](../assets/dynamic_report_journey_12.png)

