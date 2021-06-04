---
product: adobe campaign
solution: Journey Orchestration
title: Använda åtgärder i Adobe Campaign
description: Läs om Adobe Campaign åtgärder
feature: Resor
role: Business Practitioner
level: Intermediate
exl-id: 4e59a256-d494-4407-a0a8-a2523eb1084e
source-git-commit: c17808a4cae7ebbd1129f6b28ad2ea945098f826
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 3%

---

# Använda Adobe Campaign Classic {#using_campaign_classic}

Om du har Adobe Campaign Classic kan du integrera programmet. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Classic Transactional Messaging-funktioner.

Anslutningen mellan Journey Orchestration och Campaign Classic är konfigurerad av Adobe vid etableringstidpunkten. Kontakta Adobe.

För att detta ska fungera måste du konfigurera en dedikerad åtgärd. Se det här [avsnittet](../action/acc-action.md).

Det finns ett användningsexempel från början till slut i det här [avsnittet](../usecase/campaign-classic-use-case.md).

1. Designa din resa och börja med ett evenemang. Se det här [avsnittet](../building-journeys/journey.md).
1. I **Åtgärd**-delen av paletten väljer du en Campaign Classic-åtgärd och lägger till den på din resa.
1. I **åtgärdsparametrarna** visas alla fält som förväntas i meddelandets nyttolast. Du måste mappa vart och ett av dessa fält till det fält som du vill använda, antingen från händelsen eller från datakällan. Detta liknar anpassade åtgärder. Se det här [avsnittet](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
