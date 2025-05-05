---
product: adobe campaign
title: Om det avancerade användningsfallet
description: Lean more on the journey advanced use-case
feature: Journeys
role: User
level: Intermediate
exl-id: 43435aee-572d-4db2-88d5-6124ce074285
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '456'
ht-degree: 2%

---

# Om det avancerade användningsfallet{#concept_vzy_ncy_w2b}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home) för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


## Syfte {#purpose}

Låt oss ta ett exempel på ett hotellvarumärke som heter Marlton. På sina hotell har de placerat ut beacon-enheter nära alla strategiska områden: lobby, golv, restaurang, gymmet, pool osv.

>[!NOTE]
>
>I det här fallet använder vi Adobe Campaign Standard för att skicka meddelanden.

I det här fallet kommer vi att se hur vi kan skicka personaliserade meddelanden i realtid till kunder när de är nära en viss beacon.

First of all, we want to send a message as soon as a person enters a Marlton hotel. We want to send a message only if the person has not received any communication from us within the last 24 hours.

We then check two conditions:

* If this person is not a loyalty member, we send them an email to join the loyalty membership offer.
* Om den här personen redan är en lojalitetsmedlem kontrollerar vi om han har en rumsreservation:
   * Om han inte gör det skickar vi ett push-meddelande till dem med rumstariffer.
   * Om han gör det skickar vi ett välkomstmeddelande till dem. Och om han kommer in på restaurangen inom 6 timmar skickar vi ett push-meddelande med rabatt på en måltid till dem.

![](../assets/journeyuc2_29.png)

I det här fallet måste vi skapa två händelser (se [den här sidan](../usecase/configuring-the-events.md)):

* Den lobby-beacon-händelse som kommer att skjutas upp till systemet när en kund kommer in på hotellet.
* Restauranghändelsen som kommer att skjutas upp när en kund kommer in på restaurangen.

Vi måste konfigurera en anslutning till två datakällor (se [den här sidan](../usecase/configuring-the-data-sources.md)):

* The build-in Adobe Experience Platform data source, to retrieve the information for our two conditions (loyalty membership and last contact date) as well as the message personalization information.
* The hotel reservation system, to retrieve the reservation status information.

## Krav {#prerequisites}

Vi har utformat tre mallar för transaktionsmeddelanden från Adobe Campaign Standard. Vi använder mallar för händelsetransaktioner. Se den här [sidan](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=sv).

Adobe Campaign Standard är konfigurerat för att skicka e-post och push-meddelanden.

Experience Cloud-id:t används som nyckel för att identifiera kunden i hotellbokningssystemet.

Händelser skickas från kundens mobiltelefon när de upptäcks nära en fyr. Du måste utforma ett mobilprogram för att kunna skicka händelser från kundens mobiltelefon till Mobile SDK.

Fältet Lojalitetsmedlem är ett anpassat fält och har lagts till i XDM för vårt specifika organisations-ID.
