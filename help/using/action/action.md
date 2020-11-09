---
title: Om åtgärder
description: Läs om hur du konfigurerar en åtgärd
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '295'
ht-degree: 89%

---


# Om åtgärder {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="Om åtgärder"
>abstract="Här definierar du anslutningen till systemet som ska skicka meddelanden. De åtgärder som definieras här finns sedan tillgängliga på den vänstra paletten under din resa i kategorin Instruktioner. "

Åtgärder är anslutningar genom vilka du levererar personaliserade upplevelser till kunder i realtid såsom push-meddelanden, e-post, SMS eller andra sätt för digitalt engagemang som du använder i företaget.

Med anpassade åtgärder kan du konfigurera anslutningar med ett tredjepartssystem för att skicka meddelanden eller API-anrop. En åtgärd kan konfigureras med alla tjänster från alla leverantörer som kan anropas via ett REST API med en JSON-formaterad nyttolast.

The actions are available in the left palette of your journey, in the **[!UICONTROL Action]** category. Läs [den här sidan](../building-journeys/about-action-activities.md).

>[!NOTE]
>
>Konfigurationen av anpassade åtgärder utförs alltid av en **teknisk användare**.

I listan över **åtgärder** kan du trycka på c för att skapa en ny resa, åtgärd, datakälla eller händelse. For more information on shortcuts in [!DNL Journey Orchestration], see [this section](../about/user-interface.md#section_ksq_zr1_ffb).

Klicka på **[!UICONTROL Actions]** på de övre menyerna för att se åtgärdslistan eller konfigurera en ny åtgärd. Listan med åtgärder visas. See [this page](../about/user-interface.md) for more information on the interface.

![](../assets/custom1.png)

Om du har Adobe Campaign Standard måste du konfigurera den redan skapade åtgärden för att skicka e-postmeddelanden, push-meddelanden och SMS med funktionen Transaktionsmeddelanden i Adobe Campaign Standard. Se [den här sidan](../action/working-with-adobe-campaign.md).

Om du använder ett tredjepartssystem för att skicka meddelanden såsom Epsilon, Facebook, Adobe.io, Firebase osv. måste du lägga till och konfigurera en anpassad åtgärd. Se [den här sidan](../action/about-custom-action-configuration.md).

Titta på den här [videosjälvstudiekursen](https://docs.adobe.com/content/help/sv-SE/journey-orchestration-learn/tutorials/configure-actions.html) för att få mer information om hur du konfigurerar en åtgärd för [!DNL Journey Orchestration] och hur den används under en resa.
