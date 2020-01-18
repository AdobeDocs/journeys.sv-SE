---
title: Om det enkla användningssättet
description: Läs mer om enkel användning
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
source-git-commit: 54b54a64ad2822eec96008ac4a2e16c208a4a3ab

---


# Om det enkla användningssättet{#concept_grh_vby_w2b}

## Syfte {#purpose}

Låt oss ta ett exempel på ett hotellvarumärke som heter Marlton. På sina hotell har de placerat beacon-enheter nära alla strategiska områden: lobby, golv, restaurang, gym, pool osv.

I det här fallet ska vi se hur du skickar ett personligt meddelande i realtid till en person som går bredvid en fyr som är placerad nära spaen.

Vi vill bara skicka ett meddelande om personen är en kvinna. Meddelandet måste tas emot inom några sekunder.

![](../assets/journeyuc1_16.png)

## Krav {#prerequisites}

Vi har utformat en e-postmall för transaktionsmeddelanden i Adobe Campaign Standard. Vi använder en transaktionsmall för händelsetjänster. Se den här [sidan](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard är konfigurerat för att skicka e-postmeddelanden.

Händelser skickas från kundens mobiltelefon när de upptäcks nära en fyr. Du måste utforma ett mobilprogram för att kunna skicka händelser från kundens mobiltelefon till Mobile SDK.