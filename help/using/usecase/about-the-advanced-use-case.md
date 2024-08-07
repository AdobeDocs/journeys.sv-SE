---
product: adobe campaign
title: Om det avancerade användningsfallet
description: Läs mer om resan - avancerad fallstudie
feature: Journeys
role: User
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 579e5a0dbdc11369248c2683c399b090130a7262
workflow-type: tm+mt
source-wordcount: '411'
ht-degree: 2%

---

# Om det avancerade användningsfallet{#concept_vzy_ncy_w2b}

## Syfte {#purpose}

Låt oss ta ett exempel på ett hotellvarumärke som heter Marlton. På sina hotell har de placerat ut beacon-enheter nära alla strategiska områden: lobby, golv, restaurang, gymmet, pool osv.

>[!NOTE]
>
>I det här fallet använder vi Adobe Campaign Standard för att skicka meddelanden.

I det här fallet kommer vi att se hur vi kan skicka personaliserade meddelanden i realtid till kunder när de är nära en viss beacon.

Först och främst vill vi skicka ett meddelande så snart en person kommer in på ett Marlton-hotell. Vi vill bara skicka ett meddelande om personen inte har fått något meddelande från oss inom det senaste dygnet.

Sedan kontrollerar vi två villkor:

* Om den här personen inte är en lojalitetsmedlem skickar vi ett e-postmeddelande till dem där de kan gå med i erbjudandet om lojalitetsmedlemskap.
* Om den här personen redan är en lojalitetsmedlem kontrollerar vi om han har en rumsreservation:
   * Om han inte gör det skickar vi ett push-meddelande till dem med rumstariffer.
   * Om han gör det skickar vi ett välkomstmeddelande till dem. Och om han kommer in på restaurangen inom 6 timmar skickar vi ett push-meddelande med rabatt på en måltid till dem.

![](../assets/journeyuc2_29.png)

I det här fallet måste vi skapa två händelser (se [den här sidan](../usecase/configuring-the-events.md)):

* Den lobby-beacon-händelse som kommer att skjutas upp till systemet när en kund kommer in på hotellet.
* Restauranghändelsen som kommer att skjutas upp när en kund kommer in på restaurangen.

Vi måste konfigurera en anslutning till två datakällor (se [den här sidan](../usecase/configuring-the-data-sources.md)):

* Den inbyggda Adobe Experience Platform-datakällan för att hämta information om våra två villkor (lojalitetsmedlemskap och senaste kontaktdatum) samt information om meddelandepersonalisering.
* Hotellbokssystemet för att hämta information om bokningsstatus.

## Krav {#prerequisites}

Vi har utformat tre mallar för transaktionsmeddelanden från Adobe Campaign Standard. Vi använder mallar för händelsetransaktioner. Se den här [sidan](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=sv).

Adobe Campaign Standard är konfigurerat för att skicka e-post och push-meddelanden.

Experience Cloud-ID används som nyckel för att identifiera kunden i hotellbokningssystemet.

Händelser skickas från kundens mobiltelefon när de upptäcks nära en fyr. Du måste utforma ett mobilprogram för att kunna skicka händelser från kundens mobiltelefon till Mobile SDK.

Fältet Lojalitetsmedlem är ett anpassat fält och har lagts till i XDM för vårt specifika organisations-ID.
