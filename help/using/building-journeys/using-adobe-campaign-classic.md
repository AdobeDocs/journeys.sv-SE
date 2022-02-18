---
product: adobe campaign
solution: Journey Orchestration
title: Använda Adobe Campaign v7/v8-åtgärder
description: Läs om åtgärder i Adobe Campaign v7/v8
feature: Journeys
role: User
level: Intermediate
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 12%

---

# Använda Adobe Campaign v7/v8 {#using_campaign_classic}

Det finns en integrering om du har Adobe Campaign v7 eller v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner.

Kopplingen mellan Journey Orchestration och instanser i Campaign är konfigurerad av Adobe vid etableringstidpunkten. Kontakta Adobe.

För att detta ska fungera måste du konfigurera en dedikerad åtgärd. Se detta [section](../action/acc-action.md).

Ett heltäckande exempel på användning presenteras i detta [section](../usecase/campaign-classic-use-case.md).

1. Designa din resa och börja med ett evenemang. Se det här [section](../building-journeys/journey.md).
1. I **Åtgärd** väljer du en Campaign-åtgärd och lägger till den på din resa.
1. I **Åtgärdsparametrar** visas alla fält som förväntas i meddelandets nyttolast. Du måste mappa vart och ett av dessa fält till det fält som du vill använda, antingen från händelsen eller från datakällan. Detta liknar anpassade åtgärder. Se detta [section](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)
