---
product: adobe campaign
solution: Journey Orchestration
title: Om det avancerade användningsfallet
description: Läs mer om resan - avancerad fallstudie
feature: Resor
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '422'
ht-degree: 4%

---


# Om det avancerade användningsfallet{#concept_vzy_ncy_w2b}

## Syfte {#purpose}

Låt oss ta ett exempel på ett hotellvarumärke som heter Marlton. På sina hotell har de placerat beacon-enheter nära alla strategiska områden: lobby, golv, restaurang, gym, pool osv.

>[!NOTE]
>
>I det här fallet använder vi Adobe Campaign Standard för att skicka meddelanden.

I det här fallet kommer vi att se hur vi kan skicka personaliserade meddelanden i realtid till kunder när de är nära en viss beacon.

Först och främst vill vi skicka ett meddelande så snart en person kommer in på ett Marlton-hotell. Vi vill bara skicka ett meddelande om personen inte har fått något meddelande från oss inom de senaste 24 timmarna.

Sedan kontrollerar vi två villkor:

* Om den här personen inte är lojalitetsmedlem skickar vi ett e-postmeddelande till honom/henne där han kan gå med i erbjudandet om lojalitetsmedlemskap.
* Om den här personen redan är en lojalitetsmedlem kontrollerar vi om han har en rumsreservation:
   * Om han inte gör det skickar vi ett push-meddelande till honom med rumssatser.
   * Om han gör det skickar vi ett välkomstmeddelande. Och om han kommer in på restaurangen inom 6 timmar skickar vi ett push-meddelande med rabatt på en måltid till honom.

![](../assets/journeyuc2_29.png)

I det här fallet måste vi skapa två händelser (se [den här sidan](../usecase/configuring-the-events.md)):

* Den lobby-beacon-händelse som kommer att skjutas upp till systemet när en kund kommer in på hotellet.
* Restauranghändelsen som kommer att skjutas upp när en kund kommer in på restaurangen.

Vi måste konfigurera en anslutning till två datakällor (se [den här sidan](../usecase/configuring-the-data-sources.md)):

* Den inbyggda Adobe Experience Platform-datakällan för att hämta information om våra två villkor (lojalitetsmedlemskap och senaste kontaktdatum) samt information om meddelandepersonalisering.
* Hotellbokssystemet för att hämta information om bokningsstatus.

## Krav {#prerequisites}

Vi har utformat tre mallar för transaktionsmeddelanden från Adobe Campaign Standard. Vi använder mallar för händelsetransaktioner. Se den här [sidan](https://docs.adobe.com/content/help/sv-SE/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

Adobe Campaign Standard är konfigurerat att skicka e-post och push-meddelanden.

Experience Cloud ID används som nyckel för att identifiera kunden i hotellbokningssystemet.

Händelser skickas från kundens mobiltelefon när de upptäcks nära en fyr. Du måste utforma ett mobilprogram för att kunna skicka händelser från kundens mobiltelefon till Mobile SDK.

Fältet Lojalitetsmedlem är ett anpassat fält och har lagts till i XDM för vårt specifika organisations-ID.
