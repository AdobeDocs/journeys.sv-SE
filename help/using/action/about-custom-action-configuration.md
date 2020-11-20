---
product: adobe campaign
solution: Journey Orchestration
title: Om anpassad åtgärdskonfiguration
description: Lär dig hur du konfigurerar en anpassad åtgärd
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 15%

---


# Om anpassad åtgärdskonfiguration {#concept_sxy_bzs_dgb}

Om du använder ett system från en annan leverantör för att skicka meddelanden eller om du vill [!DNL Journey Orchestration] skicka API-anrop till ett system från en annan leverantör, är det här du konfigurerar anslutningen till [!DNL Journey Orchestration]. Den anpassade åtgärden som definieras av tekniska användare är sedan tillgänglig i den vänstra paletten på resan, i **[!UICONTROL Action]** kategorin (se [den här sidan](../building-journeys/about-action-activities.md)). Här är några exempel på system som du kan ansluta till med anpassade åtgärder: Epsilon, Facebook, Adobe.io, Firebase osv.
Begränsningar visas på [den här sidan](../about/limitations.md).

Här följer de huvudsteg som krävs för att konfigurera en anpassad åtgärd:

1. Klicka på i **[!UICONTROL Actions]** listan **[!UICONTROL Add]** för att skapa en ny åtgärd. Åtgärdskonfigurationsrutan öppnas till höger på skärmen.

   ![](../assets/custom2.png)

1. Ange ett namn för åtgärden.

   >[!NOTE]
   >
   >Använd inte blanksteg eller specialtecken. Använd maximalt 30 tecken.

1. Lägg till en beskrivning av åtgärden. Det här steget är valfritt.
1. The number of journeys that use this action is displayed in the **[!UICONTROL Used in]** field. You can click the **[!UICONTROL View journeys]** button to display the list of  journeys using this action.
1. Define the different **[!UICONTROL URL Configuration]** parameters. Läs [den här sidan](../action/url-configuration.md).
1. Konfigurera **[!UICONTROL Authentication]** avsnittet. Den här konfigurationen är densamma som för datakällor.  Se [det här avsnittet](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definiera **[!UICONTROL Message parameters]**. Läs [den här sidan](../action/defining-the-message-parameters.md).
1. Klicka på **[!UICONTROL Save]**.

   Den anpassade åtgärden är nu konfigurerad och klar att användas på dina resor. Läs [den här sidan](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >När en anpassad åtgärd används i en resa är de flesta parametrar skrivskyddade. Du kan bara ändra **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** fält och **[!UICONTROL Authentication]** avsnitt.
