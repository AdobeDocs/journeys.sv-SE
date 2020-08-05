---
title: Om anpassad åtgärdskonfiguration
description: Lär dig hur du konfigurerar en anpassad åtgärd
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
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 0%

---


# Om anpassad åtgärdskonfiguration {#concept_sxy_bzs_dgb}

Om du använder ett system från en annan leverantör för att skicka meddelanden eller om du vill [!DNL Journey Orchestration] skicka API-anrop till ett system från en annan leverantör, är det här du konfigurerar anslutningen till [!DNL Journey Orchestration]. Den anpassade åtgärden som definieras av tekniska användare är sedan tillgänglig i den vänstra paletten på resan, i **[!UICONTROL Action]** kategorin (se [](../building-journeys/about-action-activities.md). Här är några exempel på system som du kan ansluta till med anpassade åtgärder: Epsilon, Facebook, Adobe.io, Firebase osv.
Begränsningar anges här: [](../action/custom-action-limitations.md).

Här följer de huvudsteg som krävs för att konfigurera en anpassad åtgärd:

1. Klicka på i **[!UICONTROL Actions]** listan **[!UICONTROL Add]** för att skapa en ny åtgärd. Åtgärdskonfigurationsrutan öppnas till höger på skärmen.

   ![](../assets/custom2.png)

1. Ange ett namn för åtgärden.

   >[!NOTE]
   >
   >Använd inte blanksteg eller specialtecken. Använd inte fler än 30 tecken.

1. Lägg till en beskrivning av åtgärden. Det här steget är valfritt.
1. Antalet resor som använder den här åtgärden visas i **[!UICONTROL Used in]** fältet. Du kan klicka på **[!UICONTROL View journeys]** knappen om du vill visa en lista över resor med den här åtgärden.
1. Define the different **[!UICONTROL URL Configuration]** parameters. Se [](../action/url-configuration.md).
1. Konfigurera **[!UICONTROL Authentication]** avsnittet. Den här konfigurationen är densamma som för datakällor.  Se [](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definiera **[!UICONTROL Message parameters]**. Se [](../action/defining-the-message-parameters.md).
1. Klicka på **[!UICONTROL Save]**.

   Den anpassade åtgärden är nu konfigurerad och klar att användas på dina resor. Se [](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >När en anpassad åtgärd används i en resa är de flesta parametrar skrivskyddade. Du kan bara ändra **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** fält och **[!UICONTROL Authentication]** avsnitt.
