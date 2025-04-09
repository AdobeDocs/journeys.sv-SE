---
product: adobe campaign
solution: Journey Orchestration
title: Använda Adobe Campaign v7/v8-åtgärder
description: Läs om åtgärder i Adobe Campaign v7/v8
feature: Journeys
role: User
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '209'
ht-degree: 2%

---

# Använda Adobe Campaign v7/v8 {#using_campaign_classic}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


Det finns en integrering om du har Adobe Campaign v7 eller v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner.

Anslutningen mellan Journey Orchestration- och Campaign-instanserna konfigureras av Adobe vid etableringstidpunkten. Kontakta Adobe.

För att detta ska fungera måste du konfigurera en dedikerad åtgärd. Se det här [avsnittet](../action/acc-action.md).

Ett slutanvändarfall visas i det här [avsnittet](../usecase/campaign-classic-use-case.md).

1. Designa din resa och börja med ett evenemang. Se [avsnittet](../building-journeys/journey.md).
1. Välj en Campaign-åtgärd i **Åtgärd**-delen av paletten och lägg till den på din resa.
1. I **åtgärdsparametrarna** visas alla fält som förväntas i meddelandenyttolasten. Du måste mappa vart och ett av dessa fält till det fält som du vill använda, antingen från händelsen eller från datakällan. Detta liknar anpassade åtgärder. Se det här [avsnittet](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
