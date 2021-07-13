---
product: adobe campaign
solution: Journey Orchestration
title: Använda Adobe Campaign v7/v8-åtgärder
description: Läs om åtgärder i Adobe Campaign v7/v8
feature: Resor
role: User
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 13%

---

# Använda Adobe Campaign v7/v8 {#using_campaign_classic}

Det finns en integrering om du har Adobe Campaign v7 eller v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner.

Kopplingen mellan Journey Orchestration och instanser i Campaign är konfigurerad av Adobe vid etableringstidpunkten. Kontakta Adobe.

För att detta ska fungera måste du konfigurera en dedikerad åtgärd. Se det här [avsnittet](../action/acc-action.md).

Det finns ett användningsexempel från början till slut i det här [avsnittet](../usecase/campaign-classic-use-case.md).

1. Designa din resa och börja med ett evenemang. Se det här [avsnittet](../building-journeys/journey.md).
1. Välj en Campaign-åtgärd i **Åtgärd**-delen av paletten och lägg till den på din resa.
1. I **åtgärdsparametrarna** visas alla fält som förväntas i meddelandets nyttolast. Du måste mappa vart och ett av dessa fält till det fält som du vill använda, antingen från händelsen eller från datakällan. Detta liknar anpassade åtgärder. Se det här [avsnittet](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
