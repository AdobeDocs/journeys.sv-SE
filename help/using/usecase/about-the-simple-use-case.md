---
product: adobe campaign
title: Om det enkla användningsfallet
description: Läs mer om enkel användning under resan
feature: Journeys
role: User
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '211'
ht-degree: 5%

---

# Om det enkla användningsfallet{#concept_grh_vby_w2b}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


## Syfte {#purpose}

Låt oss ta ett exempel på ett hotellvarumärke som heter Marlton. På sina hotell har de placerat ut beacon-enheter nära alla strategiska områden: lobby, golv, restaurang, gymmet, pool osv.

I det här fallet ska vi se hur du skickar ett personligt meddelande i realtid till en person som går bredvid en fyr som är placerad nära spaen.

Vi vill bara skicka ett meddelande om personen är en kvinna. Meddelandet måste tas emot inom några sekunder.

![](../assets/journeyuc1_16.png)

## Krav {#prerequisites}

Vi har utformat en e-postmall för transaktionsmeddelanden i Adobe Campaign Standard. Vi använder en transaktionsmall för händelsetjänster. Se den här [sidan](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=sv).

Adobe Campaign Standard har konfigurerats för att skicka e-post.

Händelser skickas från kundens mobiltelefon när de upptäcks nära en fyr. Du måste utforma ett mobilprogram för att kunna skicka händelser från kundens mobiltelefon till Mobile SDK.
