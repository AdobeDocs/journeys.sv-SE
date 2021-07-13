---
product: adobe campaign
title: Om anpassad åtgärdskonfiguration
description: Lär dig hur du konfigurerar en anpassad åtgärd
feature: Resor
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '250'
ht-degree: 15%

---

# Om anpassad åtgärdskonfiguration {#concept_sxy_bzs_dgb}

Om du använder ett tredjepartssystem för att skicka meddelanden eller om du vill att [!DNL Journey Orchestration] ska skicka API-anrop till ett tredjepartssystem, konfigurerar du anslutningen till [!DNL Journey Orchestration]. Den anpassade åtgärden som definieras av tekniska användare är sedan tillgänglig på den vänstra paletten på din resa i kategorin **[!UICONTROL Action]** (se [den här sidan](../building-journeys/about-action-activities.md). Här är några exempel på system som du kan ansluta till med anpassade åtgärder: Epsilon, Facebook, Adobe.io, Firebase osv.
Begränsningar visas i [den här sidan](../about/limitations.md).

Här följer de huvudsteg som krävs för att konfigurera en anpassad åtgärd:

1. Klicka på **[!UICONTROL Add]** i listan **[!UICONTROL Actions]** för att skapa en ny åtgärd. Åtgärdskonfigurationsrutan öppnas till höger på skärmen.

   ![](../assets/custom2.png)

1. Ange ett namn för åtgärden.

   >[!NOTE]
   >
   >Använd inte blanksteg eller specialtecken. Använd maximalt 30 tecken.

1. Lägg till en beskrivning av åtgärden. Det här steget är valfritt.
1. Antalet resor som använder den här åtgärden visas i fältet **[!UICONTROL Used in]**. Du kan klicka på knappen **[!UICONTROL View journeys]** för att visa listan över resor med den här åtgärden.
1. Definiera de olika **[!UICONTROL URL Configuration]**-parametrarna. Läs [den här sidan](../action/url-configuration.md).
1. Konfigurera avsnittet **[!UICONTROL Authentication]**. Den här konfigurationen är densamma som för datakällor.  Se [det här avsnittet](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definiera **[!UICONTROL Message parameters]**. Läs [den här sidan](../action/defining-the-message-parameters.md).
1. Klicka på **[!UICONTROL Save]**.

   Den anpassade åtgärden är nu konfigurerad och klar att användas på dina resor. Läs [den här sidan](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >När en anpassad åtgärd används i en resa är de flesta parametrar skrivskyddade. Du kan bara ändra fälten **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** och **[!UICONTROL Authentication]**.
