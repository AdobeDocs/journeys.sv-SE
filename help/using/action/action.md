---
product: adobe campaign
title: Om åtgärder
description: Läs om hur du konfigurerar en åtgärd
feature: Journeys
role: User
level: Intermediate
exl-id: 34f7666b-1c91-4edd-b5d6-4c0513b9c4f3
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 72%

---

# Om åtgärder {#about_actions}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


>[!CONTEXTUALHELP]
>id="jo_actions"
>title="Om åtgärder"
>abstract="Här definierar du anslutningen till systemet som ska skicka meddelanden. De åtgärder som definieras här finns sedan tillgängliga på den vänstra paletten under din resa i kategorin Instruktioner. "

Åtgärder är anslutningar genom vilka du levererar personaliserade upplevelser till kunder i realtid såsom push-meddelanden, e-post, SMS eller andra sätt för digitalt engagemang som du använder i företaget.

Med anpassade åtgärder kan du konfigurera anslutningar med ett tredjepartssystem för att skicka meddelanden eller API-anrop. En åtgärd kan konfigureras med alla tjänster från alla leverantörer som kan anropas via ett REST API med en JSON-formaterad nyttolast.

Åtgärderna är tillgängliga på den vänstra paletten på din resa i kategorin **[!UICONTROL Action]**. Läs [den här sidan](../building-journeys/about-action-activities.md).

>[!NOTE]
>
>Konfigurationen av anpassade åtgärder utförs alltid av en **teknisk användare**.

I listan över **åtgärder** kan du trycka på c för att skapa en ny resa, åtgärd, datakälla eller händelse. Mer information om genvägar i [!DNL Journey Orchestration] finns i [det här avsnittet](../about/user-interface.md#section_ksq_zr1_ffb).

Klicka på **[!UICONTROL Actions]** på de övre menyerna för att se åtgärdslistan eller konfigurera en ny åtgärd. Listan med åtgärder visas. Mer information om gränssnittet finns på [den här sidan](../about/user-interface.md).

![](../assets/custom1.png)

Om du har Adobe Campaign Standard måste du konfigurera den redan skapade åtgärden för att skicka e-postmeddelanden, push-meddelanden och SMS med funktionen Transaktionsmeddelanden i Adobe Campaign Standard. Se [den här sidan](../action/working-with-adobe-campaign.md).

Om du har Adobe Campaign v7 eller v8 blir en integrering tillgänglig på begäran. Se [den här sidan](../action/acc-action.md).

Om du använder ett tredjepartssystem för att skicka meddelanden såsom Epsilon, Facebook, Adobe.io, Firebase osv. måste du lägga till och konfigurera en anpassad åtgärd. Se [den här sidan](../action/about-custom-action-configuration.md).

