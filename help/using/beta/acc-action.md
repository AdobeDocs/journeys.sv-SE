---
product: adobe campaign
solution: Journey Orchestration
title: Om integrering med Campaign Classic
description: Läs om integrationen mellan Campaign Classic
hide: true
hidefromtoc: true
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 0%

---


# Integrera med Adobe Campaign Classic {#integrating-with-adobe-campaign-classic}

Tack vare den här integreringen kan du skicka e-post, push-meddelanden och SMS med Adobe Campaign Classic Transactional Messaging-funktioner.

Anslutningen mellan Journey Orchestration och Campaign Classic är konfigurerad av Adobe vid etableringstidpunkten.

>[!CAUTION]
>
> Den här integreringen lanseras som en privat betaversion. Det är inte tillgängligt för alla Journey Orchestration-kunder.

## Viktiga anteckningar

* Det finns ingen begränsning för meddelanden. Vi har som gräns antalet meddelanden som kan skickas till 50 000/timme baserat på vårt nuvarande Campaign Classic SLA. Av denna anledning bör endast färdvägskorrigering användas i enstaka fall (enskilda händelser, inte segment).

* Du måste konfigurera en åtgärd på arbetsytan per mall som du vill använda.

* Vi rekommenderar att du använder en dedikerad Message Center-instans som är värd för den här integreringen för att undvika att påverka andra Campaign Classic-åtgärder som du har påbörjat. Marknadsföringsservern kan vara värd eller lokal. Den version som krävs är 21.1 Release Candidate.

* Det finns ingen validering av att nyttolasten eller Campaign Classic-meddelandet är korrekt.

* Du kan inte använda en Campaign Classic-åtgärd med en segmentkvalificering.

## Förhandskrav

I Campaign Classic måste du skapa och publicera ett transaktionsmeddelande och tillhörande händelse. Läs [Adobe Campaign Classic-dokumentationen](https://experienceleague.adobe.com/docs/campaign-classic/using/transactional-messaging/introduction/about-transactional-messaging.html#transactional-messaging).

Kontakta Adobe för att få den JSON-nyttolast som motsvarar varje meddelande. Du klistrar sedan in den här nyttolasten när du konfigurerar åtgärden i Journey Orchestration (se nedan).

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

## Konfigurera åtgärden

I Journey Orchestration måste du konfigurera en åtgärd per transaktionsmeddelande. Följ de här stegen:

1. Skapa en ny åtgärd. Se det här [avsnittet](../action/action.md).
1. Ange ett namn och en beskrivning.
1. I fältet **Åtgärdstyp** väljer du **Adobe Campaign Classic**.
1. Klicka i fältet **Nyttolast** och klistra in ett exempel på JSON-nyttolasten som motsvarar Campaign Classic-meddelandet. Kontakta Adobe för att få denna nyttolast.
1. Justera de olika fälten. Vissa fält, som kanalparametrar och anpassningsfält (ctx), måste definieras som variabler.
1. Klicka på **Spara**.

![](../assets/accintegration1.png)

För varje konfigurerad åtgärd finns en åtgärdsaktivitet tillgänglig på paletten Resursdesigner.

## Lägga till ett meddelande i en resa

1. Designa din resa och börja med ett evenemang. Se det här [avsnittet](../building-journeys/journey.md).
1. I **Åtgärd**-delen av paletten väljer du en Campaign Classic-åtgärd och lägger till den på din resa.
1. I **åtgärdsparametrarna** visas alla fält som förväntas i meddelandets nyttolast. Du måste mappa vart och ett av dessa fält till det fält som du vill använda, antingen från händelsen eller från datakällan. Detta liknar anpassade åtgärder. Se det här [avsnittet](../building-journeys/using-custom-actions.md).

![](../assets/accintegration2.png)

