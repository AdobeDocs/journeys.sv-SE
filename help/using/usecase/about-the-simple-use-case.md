---
product: adobe campaign
title: Om det enkla användningsfallet
description: Läs mer om enkel användning
feature: Resor
role: Business Practitioner
level: Intermediate
exl-id: 11858c7a-fdb3-43a4-af28-0d5c23fa2468
source-git-commit: e7c3dde02837d31c5eb7d170cae7f142ce376175
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 7%

---

# Om det enkla användningsfallet{#concept_grh_vby_w2b}

## Syfte {#purpose}

Låt oss ta ett exempel på ett hotellvarumärke som heter Marlton. På sina hotell har de placerat beacon-enheter nära alla strategiska områden: lobby, golv, restaurang, gym, pool osv.

I det här fallet ska vi se hur du skickar ett personligt meddelande i realtid till en person som går bredvid en fyr som är placerad nära spaen.

Vi vill bara skicka ett meddelande om personen är en kvinna. Meddelandet måste tas emot inom några sekunder.

![](../assets/journeyuc1_16.png)

## Krav {#prerequisites}

Vi har utformat en e-postmall för transaktionsmeddelanden i Adobe Campaign Standard. Vi använder en transaktionsmall för händelsetjänster. Se den här [sidan]().

Adobe Campaign Standard har konfigurerats för att skicka e-post.

Händelser skickas från kundens mobiltelefon när de upptäcks nära en fyr. Du måste utforma ett mobilprogram för att kunna skicka händelser från kundens mobiltelefon till Mobile SDK.
