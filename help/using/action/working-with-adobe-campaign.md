---
title: Arbeta med Adobe Campaign
description: Läs om Adobe Campaign-åtgärder
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994

---


# Arbeta med Adobe Campaign {#using_adobe_campaign_standard}

Du kan skicka e-postmeddelanden, push-meddelanden och SMS med hjälp av Transactional Messaging-funktionerna i Adobe Campaign Standard.

Journey Orchestration innehåller en körklar åtgärd som möjliggör anslutning till Adobe Campaign Standard. Så här konfigurerar du den:

1. Klicka på den inbyggda **[!UICONTROL Actions]**åtgärden i**[!UICONTROL AdobeCampaignStandard]** listan. Åtgärdskonfigurationsrutan öppnas till höger på skärmen.

   ![](../assets/actioncampaign.png)

1. Kopiera din instans-URL för Adobe Campaign Standard och klistra in den i **[!UICONTROL URL]**fältet.

1. Klicka på **[!UICONTROL Test the instance URL]**för att testa instansens giltighet.

När du utformar din resa kommer tre åtgärder att vara tillgängliga i **[!UICONTROL Action]**kategorin:**[!UICONTROL Email]**, **[!UICONTROL Push]**,**[!UICONTROL SMS]** (se [](../building-journeys/using-adobe-campaign-actions.md)).

![](../assets/journey58.png)

Om du använder ett tredjepartssystem för att skicka meddelanden måste du lägga till och konfigurera en anpassad åtgärd. Se [](../action/about-custom-action-configuration.md).
