---
product: adobe campaign
title: Om anpassad åtgärdskonfiguration
description: Lär dig hur du konfigurerar en anpassad åtgärd
feature: Journeys
role: User
level: Intermediate
exl-id: 8b24abef-700d-4f68-a921-d7299c939439
source-git-commit: 7ad2419854b4fcecae7fbb20bdd6a6f2fbc04988
workflow-type: tm+mt
source-wordcount: '301'
ht-degree: 12%

---

# Om anpassad åtgärdskonfiguration {#concept_sxy_bzs_dgb}

Om du använder ett tredjepartssystem för att skicka meddelanden eller om du vill [!DNL Journey Orchestration] om du vill skicka API-anrop till ett system från en annan tillverkare konfigurerar du anslutningen till [!DNL Journey Orchestration]. Den anpassade åtgärden som definieras av tekniska användare är sedan tillgänglig på den vänstra paletten av din resa, i **[!UICONTROL Action]** kategori (se [den här sidan](../building-journeys/about-action-activities.md). Här är några exempel på system som du kan ansluta till med anpassade åtgärder: Epsilon, Facebook, Adobe.io, Firebase osv.

Begränsningar visas i [den här sidan](../about/limitations.md).

I anpassade åtgärdsparametrar kan du skicka en enkel samling samt en samling med objekt. Vad gäller begränsningarna, se [den här sidan](../usecase/collections.md#limitations). Observera också att parametrarna har ett förväntat format (exempel: sträng, decimal osv.). Du måste vara försiktig med att ta hänsyn till dessa förväntade format. Se detta [användningsfall](../usecase/collections.md).

Här följer de huvudsteg som krävs för att konfigurera en anpassad åtgärd:

1. Från **[!UICONTROL Actions]** lista, klicka på **[!UICONTROL Add]** för att skapa en ny åtgärd. Åtgärdskonfigurationsrutan öppnas till höger på skärmen.

   ![](../assets/custom2.png)

1. Ange ett namn för åtgärden.

   >[!NOTE]
   >
   >Använd inte blanksteg eller specialtecken. Använd maximalt 30 tecken.

1. Lägg till en beskrivning av åtgärden. Det här steget är valfritt.
1. Antalet resor som använder den här åtgärden visas i **[!UICONTROL Used in]** fält. Du kan klicka på **[!UICONTROL View journeys]** om du vill visa en lista över resor som använder den här åtgärden.
1. Definiera de olika **[!UICONTROL URL Configuration]** parametrar. Läs [den här sidan](../action/url-configuration.md).
1. Konfigurera **[!UICONTROL Authentication]** -avsnitt. Den här konfigurationen är densamma som för datakällor.  Se [det här avsnittet](../datasource/external-data-sources.md#section_wjp_nl5_nhb).
1. Definiera **[!UICONTROL Action parameters]**. Läs [den här sidan](../action/defining-the-message-parameters.md).
1. Klicka på **[!UICONTROL Save]**.

   Den anpassade åtgärden är nu konfigurerad och klar att användas på dina resor. Läs [den här sidan](../building-journeys/about-action-activities.md).

   >[!NOTE]
   >
   >När en anpassad åtgärd används i en resa är de flesta parametrar skrivskyddade. Du kan bara ändra **[!UICONTROL Name]**, **[!UICONTROL Description]**, **[!UICONTROL URL]** fält och **[!UICONTROL Authentication]** -avsnitt.
