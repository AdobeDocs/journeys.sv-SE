---
product: adobe campaign
title: Om integrering med Campaign Classic
description: Läs om integrationen mellan Campaign Classic
feature: Resor
role: Business Practitioner
level: Intermediate
exl-id: 4b321b63-c624-4c2a-ae92-f9a2a95688d4
source-git-commit: 1712529984af02d0a3f678418db1e819370056d6
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 0%

---

# Arbeta med Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Tack vare den här integreringen kan du skicka e-post, push-meddelanden och SMS med Adobe Campaign Classic Transactional Messaging-funktioner.

Anslutningen mellan Journey Orchestration och Campaign Classic är konfigurerad av Adobe vid etableringstidpunkten.

Det finns ett användningsexempel från början till slut i det här [avsnittet](../usecase/campaign-classic-use-case.md).

För varje konfigurerad åtgärd finns en åtgärdsaktivitet tillgänglig på paletten Resursdesigner. Se det här [avsnittet](../building-journeys/using-adobe-campaign-classic.md).

## Viktiga anteckningar

* Det finns ingen begränsning för meddelanden. Vi har som gräns antalet meddelanden som kan skickas till 50 000/timme baserat på vårt nuvarande Campaign Classic SLA. Av denna anledning bör endast färdvägskorrigering användas i enstaka fall (enskilda händelser, inte segment).

* Du måste konfigurera en åtgärd på arbetsytan per mall som du vill använda. Du måste konfigurera en åtgärd i Journey Orchestration för varje mall som du vill använda från Adobe Campaign Classic.

* Vi rekommenderar att du använder en dedikerad Message Center-instans som är värd för den här integreringen för att undvika att påverka andra Campaign Classic-åtgärder som du har påbörjat. Marknadsföringsservern kan vara värd eller lokal. Den version som krävs är 21.1 Release Candidate eller senare.

* Det finns ingen validering av att nyttolasten eller Campaign Classic-meddelandet är korrekt.

* Du kan inte använda en Campaign Classic-åtgärd med en segmentkvalificeringshändelse.

## Förhandskrav

I Campaign Classic måste du skapa och publicera ett transaktionsmeddelande och tillhörande händelse. Läs [Adobe Campaign Classic-dokumentationen](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Du kan skapa din JSON-nyttolast som motsvarar varje meddelande enligt mönstret nedan. Du klistrar sedan in den här nyttolasten när du konfigurerar åtgärden i Journey Orchestration (se nedan)

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

* **kanal**: den kanal som är definierad för din transaktionsmall för Campaign Classic
* **eventType**: Campaign Classic-händelsens interna namn
* **ctx**: variabeln baserat på den personalisering du har i ditt meddelande.

## Konfigurera åtgärden

I Journey Orchestration måste du konfigurera en åtgärd per transaktionsmeddelande. Följ de här stegen:

1. Skapa en ny åtgärd. Se det här [avsnittet](../action/action.md).
1. Ange ett namn och en beskrivning.
1. I fältet **Åtgärdstyp** väljer du **Adobe Campaign Classic**.
1. Klicka i fältet **Nyttolast** och klistra in ett exempel på JSON-nyttolasten som motsvarar Campaign Classic-meddelandet. Kontakta Adobe för att få denna nyttolast.
1. Justera de olika fälten så att de blir statiska eller variabla beroende på om du vill mappa dem på arbetsytan på resan. Vissa fält, till exempel kanalparametrar för e-postadresser och anpassningsfält (ctx), kan behöva definieras som variabler för mappning i samband med resan.
1. Klicka på **Spara**.

![](../assets/accintegration1.png)


