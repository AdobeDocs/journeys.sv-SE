---
product: adobe campaign
solution: Journey Orchestration
title: Om det enkla användningsfallet
description: Läs mer om enkel användning
feature: Resor
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '179'
ht-degree: 11%

---


# Om det enkla användningsfallet{#concept_grh_vby_w2b}

## Syfte {#purpose}

Låt oss ta ett exempel på ett hotellvarumärke som heter Marlton. På sina hotell har de placerat beacon-enheter nära alla strategiska områden: lobby, golv, restaurang, gym, pool osv.

I det här fallet ska vi se hur du skickar ett personligt meddelande i realtid till en person som går bredvid en fyr som är placerad nära spaen.

Vi vill bara skicka ett meddelande om personen är en kvinna. Meddelandet måste tas emot inom några sekunder.

![](../assets/journeyuc1_16.png)

## Krav {#prerequisites}

Vi har utformat en e-postmall för transaktionsmeddelanden i Adobe Campaign Standard. Vi använder en transaktionsmall för händelsetjänster. Se den här [sidan](https://docs.adobe.com/content/help/sv-SE/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard har konfigurerats för att skicka e-post.

Händelser skickas från kundens mobiltelefon när de upptäcks nära en fyr. Du måste utforma ett mobilprogram för att kunna skicka händelser från kundens mobiltelefon till Mobile SDK.