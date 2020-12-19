---
product: adobe campaign
solution: Journey Orchestration
title: Om Adobe Analytics-data
description: Lär dig utnyttja Adobe Analytics data
translation-type: tm+mt
source-git-commit: 81bb0b5da38217f9290214901c64e90d7ec2ba0e
workflow-type: tm+mt
source-wordcount: '190'
ht-degree: 0%

---


# Utnyttja Adobe Analytics-data{#analytics-data}

>[!NOTE]
>
>Det här avsnittet gäller endast för regelbaserade händelser och kunder som behöver använda Adobe Analytics-data.

Ni kan utnyttja alla Adobe Analytics beteendehändelsedata som ni redan samlar in och strömmar till plattformen för att utlösa resor och automatisera kundernas upplevelser.

För att detta ska fungera måste du aktivera rapportsviten som du vill utnyttja i Adobe Experience Platform:

1. I Adobe Experience Platform väljer du **[!UICONTROL Sources]** och sedan **[!UICONTROL Add data]** i avsnittet Adobe Analytics. En lista över tillgängliga Adobe Analytics-rapportsviter visas.

1. Välj den rapportserie som du vill aktivera, klicka på **[!UICONTROL Next]** och klicka på **[!UICONTROL Finish]**.

1. Dela källdata-ID:t med alfaprogrammets kontaktpunkt.

Detta aktiverar Analytics-källkopplingen för den rapportsviten. När informationen kommer in omvandlas den till en Experience-händelse och skickas till Adobe Experience Platform.

![](../assets/alpha-event9.png)

Mer information om Adobe Analytics källanslutning finns i [dokumentationen](https://docs.adobe.com/help/en/experience-platform/sources/connectors/adobe-applications/analytics.html) och [självstudiekursen](https://docs.adobe.com/content/help/en/experience-platform/sources/ui-tutorials/create/adobe-applications/analytics.html).
