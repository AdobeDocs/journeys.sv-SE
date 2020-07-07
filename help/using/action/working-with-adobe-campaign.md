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
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 6685565797a6cdc43b9c8fc39c9354ae6d213f1f
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---


# Arbeta med Adobe Campaign {#using_adobe_campaign_standard}

Du kan skicka e-postmeddelanden, push-meddelanden och SMS med Adobe Campaign Standardens Transactional Messaging-funktioner.

[!DNL Journey Orchestration] levereras med en körklar åtgärd som tillåter anslutning till Adobe Campaign Standard.

Campaign Standardens transaktionsmeddelande och tillhörande händelse måste publiceras för att kunna användas i Journey Orchestration. Om händelsen publiceras men meddelandet inte visas visas den inte i Journey Orchestration-gränssnittet. Om meddelandet publiceras men dess associerade händelse inte är det visas det i Journey Orchestration-gränssnittet, men det går inte att använda det.

>[!NOTE]
>
>För att undvika överbelastning av Adobe Campaign Standarden Transactional Messaging rekommenderar vi att du ställer in en **begränsningsregel** för Campaign Standarden.
>
>Läs mer om SLA för transaktionsmeddelanden i [Adobe Campaign Standardens produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html).

Så här konfigurerar du den:

1. Klicka på den inbyggda **[!UICONTROL Actions]** åtgärden i **[!UICONTROL AdobeCampaignStandard]** listan. Åtgärdskonfigurationsrutan öppnas till höger på skärmen.

   ![](../assets/actioncampaign.png)

1. Kopiera webbadressen för din Adobe Campaign Standard-instans och klistra in den i **[!UICONTROL URL]** fältet.

1. Klicka på **[!UICONTROL Test the instance URL]** för att testa instansens giltighet.

   >[!NOTE]
   >
   >Detta test verifierar att
   >
   >* Värden är &quot;.campaign.adobe.com&quot; eller &quot;.campaign-sandbox.adobe.com&quot;,
   >* URL:en börjar med https,
   >* ORG som är associerad med den här Adobe Campaign Standardens instans är samma som Journey Orchestration ORG.


När du utformar din resa kommer tre åtgärder att vara tillgängliga i **[!UICONTROL Action]** kategorin: **[!UICONTROL Email]**, **[!UICONTROL Push]**, **[!UICONTROL SMS]** (se [Använda funktionsmakron](../building-journeys/using-adobe-campaign-actions.md)i Adobe Campaign). **Reaktionshändelsen** gör även att du kan reagera på meddelandeklickningar, öppningar osv. (se [Reaktioner, händelser](../building-journeys/event-activities.md#section_dhx_gss_dgb)).

![](../assets/journey58.png)

Om du använder ett tredjepartssystem för att skicka meddelanden måste du lägga till och konfigurera en anpassad åtgärd. Se [Om konfiguration](../action/about-custom-action-configuration.md)av anpassad åtgärd.
