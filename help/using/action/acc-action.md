---
product: adobe campaign
title: Om integrering med Campaign v7/v8
description: Läs om integrationen mellan Campaign v7 och v8
feature: Journeys
role: User
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '482'
ht-degree: 1%

---

# Arbeta med Adobe Campaign v7/v8 {#integrating-with-adobe-campaign-classic}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


Den här integreringen är tillgänglig för Adobe Campaign Classic v7 från och med version 21.1 och Adobe Campaign v8. Det gör att du kan skicka e-post, push-meddelanden och SMS med Adobe Campaign Transactional Messaging-funktioner.

Anslutningen mellan Journey Orchestration- och Campaign-instanserna konfigureras av Adobe vid etableringstidpunkten.

Ett slutanvändarfall visas i det här [avsnittet](../usecase/campaign-classic-use-case.md).

För varje konfigurerad åtgärd finns en åtgärdsaktivitet tillgänglig på paletten Resursdesigner. Se det här [avsnittet](../building-journeys/using-adobe-campaign-classic.md).

## Viktiga anteckningar

* Det finns ingen begränsning för meddelanden. Vi har som gräns antalet meddelanden som kan skickas till 50 000/timme baserat på vår nuvarande Campaign SLA. Av denna anledning bör endast färdvägskorrigering användas i enstaka fall (enskilda händelser, inte segment).

* Du måste konfigurera en åtgärd på arbetsytan per mall som du vill använda. Du måste konfigurera en åtgärd i Journey Orchestration för varje mall som du vill använda från Adobe Campaign.

* Vi rekommenderar att du använder en dedikerad Message Center-instans som är värd för den här integreringen för att undvika att påverka andra Campaign-åtgärder som du har påbörjat. Marknadsföringsservern kan vara värd eller lokal. Den version som krävs är 21.1 Release Candidate eller senare.

* Det finns ingen validering av att nyttolasten eller kampanjmeddelandet är korrekt.

* Du kan inte använda en Campaign-åtgärd med en segmentkvalificeringshändelse.

## Förhandskrav

I Campaign måste du skapa och publicera ett transaktionsmeddelande och tillhörande händelse. Mer information finns i [Adobe Campaign-dokumentationen](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Du kan skapa din JSON-nyttolast som motsvarar varje meddelande enligt mönstret nedan. Du klistrar sedan in nyttolasten när du konfigurerar åtgärden i Journey Orchestration (se nedan)

Här är ett exempel:

```
{
    "channel": "email",
    "eventType": "welcome",
    "email": "example@adobe.com",
    "ctx": {
        "firstName": "John"
    }
}
```

* **kanal**: kanalen som är definierad för din transaktionsmall för Campaign
* **eventType**: det interna namnet på Campaign-händelsen
* **ctx**: variabel baserad på den personalisering du har i meddelandet.

## Konfigurera åtgärden

I Journey Orchestration måste du konfigurera en åtgärd per transaktionsmeddelande. Följ de här stegen:

1. Skapa en ny åtgärd. Se det här [avsnittet](../action/action.md).
1. Ange namn och beskrivning.
1. I fältet **Åtgärdstyp** väljer du **Adobe Campaign Classic**.
1. Klicka i fältet **Nyttolast** och klistra in ett exempel på JSON-nyttolasten som motsvarar Campaign-meddelandet. Kontakta Adobe för att få denna nyttolast.
1. Justera de olika fälten så att de blir statiska eller variabla beroende på om du vill mappa dem på arbetsytan på resan. Vissa fält, till exempel kanalparametrar för e-postadresser och anpassningsfält (ctx), kan behöva definieras som variabler för mappning i samband med resan.
1. Klicka på **Spara**.

![](../assets/accintegration1.png)


