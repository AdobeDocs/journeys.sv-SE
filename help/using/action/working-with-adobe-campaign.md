---
title: Arbeta med Adobe Campaign
description: Läs om Adobe Campaign åtgärder
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 59b726388ee1c2c4b51ada9e7e5f7ca4eb6554b3
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 4%

---


# Arbeta med Adobe Campaign {#using_adobe_campaign_standard}

Du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Standard Transactional Messaging-funktioner.

[!DNL Journey Orchestration] levereras med en körklar åtgärd som möjliggör anslutning till Adobe Campaign Standard.

Campaign Standardens transaktionsmeddelande och tillhörande händelse måste publiceras för att kunna användas i Journey Orchestration. Om händelsen publiceras men meddelandet inte visas visas den inte i Journey Orchestration-gränssnittet. Om meddelandet publiceras men dess associerade händelse inte är det visas det i Journey Orchestration-gränssnittet, men det går inte att använda det.

>[!NOTE]
>
>Adobe Campaign Standard Transactional Messaging har en skala på högst 50 000 meddelanden per timme över alla kanaler för en viss instans. För att minska risken för överbelastning rekommenderar vi att du ställer in en **begränsningsregel** för integrering av Campaign Standarder.
>
>Läs mer om SLA för transaktionsmeddelanden i [Adobe Campaign Standard produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/campaign-standard.html).

Så här konfigurerar du den:

1. Klicka på den inbyggda **[!UICONTROL Actions]** åtgärden i **[!UICONTROL AdobeCampaignStandard]** listan. Åtgärdskonfigurationsrutan öppnas till höger på skärmen.

   ![](../assets/actioncampaign.png)

1. Kopiera din Adobe Campaign Standard-instans-URL och klistra in den i **[!UICONTROL URL]** fältet.

1. Klicka på **[!UICONTROL Test the instance URL]** för att testa instansens giltighet.

   >[!NOTE]
   >
   >Detta test verifierar att
   >
   >Värden är &quot;.campaign.adobe.com&quot; eller &quot;.campaign-sandbox.adobe.com&quot;,
   >
   >URL:en börjar med https,
   >
   >Den ORG som är associerad med den här Adobe Campaign Standard-instansen är samma som Journey Orchestration ORG.

När du utformar din resa kommer tre åtgärder att vara tillgängliga i **[!UICONTROL Action]** kategorin: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (se [Använda Adobe Campaign-åtgärder](../building-journeys/using-adobe-campaign-actions.md)). **Reaktionshändelsen** gör även att du kan reagera på meddelandeklickningar, öppningar osv. (se [Reaktioner, händelser](../building-journeys/reaction-events.md)).

![](../assets/journey58.png)

Om du använder ett tredjepartssystem för att skicka meddelanden måste du lägga till och konfigurera en anpassad åtgärd. See [About custom action configuration](../action/about-custom-action-configuration.md).
