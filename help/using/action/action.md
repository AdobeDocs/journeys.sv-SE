---
title: Om funktionsmakron
description: Lär dig hur du konfigurerar en åtgärd
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
source-git-commit: 87910a9f3dbf2c34776a8d2ab1f00426e8b0704c
workflow-type: tm+mt
source-wordcount: '289'
ht-degree: 0%

---


# Om funktionsmakron {#about_actions}

>[!CONTEXTUALHELP]
>id="jo_actions"
>title="Om funktionsmakron"
>abstract="Här definierar du anslutningen till systemet som ska skicka meddelanden. De åtgärder som definieras här kommer sedan att finnas tillgängliga på den vänstra paletten under din resa i kategorin Åtgärd. "

Åtgärder är kopplingar genom vilka ni levererar personaliserade upplevelser i realtid till kunder, till exempel push-meddelanden, e-post, SMS eller andra sätt för digitalt engagemang som ni använder i ert företag.

Med anpassade åtgärder kan du konfigurera anslutning av ett tredjepartssystem för att skicka meddelanden eller API-anrop. En åtgärd kan konfigureras med alla tjänster från alla leverantörer som kan anropas via ett REST API med en JSON-formaterad nyttolast.

Åtgärderna är tillgängliga i den vänstra paletten på din resa, i **[!UICONTROL Action]** kategorin (se [](../building-journeys/about-action-activities.md) ).

>[!NOTE]
>
>Konfigurationen av anpassade åtgärder utförs alltid av en **teknisk användare**.

I listan över **åtgärder** kan du trycka på c för att skapa en ny resa, åtgärd, datakälla eller händelse. Mer information om genvägar i Resesamordning finns i [](../about/user-interface.md#section_ksq_zr1_ffb).

Om du vill visa åtgärdslistan eller konfigurera en ny åtgärd klickar du på **[!UICONTROL Actions]** de översta menyerna. Listan med åtgärder visas. Mer information om gränssnittet finns [](../about/user-interface.md) i.

![](../assets/custom1.png)

Om du har Adobe Campaign Standard måste du konfigurera den körklara åtgärden för att skicka e-post, push-meddelanden och SMS med hjälp av Transactional Messaging-funktionerna i Adobe Campaign Standard. Se [](../action/working-with-adobe-campaign.md).

Om du använder ett tredjepartssystem för att skicka meddelanden som Epsilon, Facebook, Adobe.io, Firebase osv. måste du lägga till och konfigurera en anpassad åtgärd. Se [](../action/about-custom-action-configuration.md).

Titta på den här [videosjälvstudiekursen](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-actions.html)om du vill ha mer information om hur du konfigurerar en Action for Journey Orchestration och hur du använder den under en resa.
