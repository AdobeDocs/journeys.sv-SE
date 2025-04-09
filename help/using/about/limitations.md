---
product: adobe campaign
title: Journey Orchestration begränsningar
description: Läs mer om Journey Orchestration begränsningar
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '609'
ht-degree: 0%

---

# Begränsningar {#limitations}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._



Här är begränsningar för användning av Journey Orchestration.

## Allmänna vägräcken {#journeys-guardrails-journeys}

* Antalet aktiviteter i en resa är begränsat till 50. Antalet aktiviteter visas i den övre vänstra delen av researbetsytan.
* **Antalet liveresor** i en organisation är begränsat till 100 per sandbox. När den här gränsen har nåtts kan du inte längre publicera en ny resa.

## Begränsningar för allmänna åtgärder

* Tre återförsök utförs systematiskt i händelse av ett fel. Du kan inte justera antalet återförsök enligt det mottagna felmeddelandet. 
* Med den inbyggda **reaktionshändelsen** kan du reagera på färdiga åtgärder (se den här [sidan](../building-journeys/reaction-events.md)). Om du vill reagera på ett meddelande som skickas via en anpassad åtgärd måste du konfigurera en dedikerad händelse.

## Begränsningar för reseversioner {#journey-versions-limitations}

* En resa som börjar med en händelseaktivitet i v1 kan inte börja med något annat än en händelse i framtida versioner. Du kan inte starta en resa med en **segmentkvalificeringshändelse** .
* En resa som börjar med en **segmentkvalificeringsaktivitet** i v1 måste alltid börja med en **segmentkvalificering** i ytterligare versioner.
* Det segment och namnområde som valts i **Segmentkvalificering** (första noden) kan inte ändras i nya versioner.
* Regeln för återinträde måste vara densamma i alla reseversioner.

## Segmentkvalificering {#segment-qualification}

* Aktiviteten **Segmentkvalificering** kan inte användas tillsammans med Adobe Campaign Standard Transactional Messaging på grund av dataflödesbegränsningar. Se [Adobe Campaign Standard produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/campaign-standard.html). 
 
## Begränsningar för anpassade åtgärder

* Den anpassade åtgärds-URL:en stöder inte dynamiska parametrar. 
* Det finns bara stöd för anropsmetoderna POST och PUT. 
* Namnet på frågeparametern eller -rubriken får inte börja med &quot;.&quot; eller &quot;$&quot;. 
* IP-adresser är inte tillåtna. 
* Interna Adobe-adresser (.adobe.) är inte tillåtna.
 
## Begränsningar för Adobe Campaign-åtgärder

* Adobe Campaign Standard Transactional Messaging har en skala på högst 50 000 meddelanden per timme över alla kanaler för en viss instans. Se [Adobe Campaign Standard produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/campaign-standard.html). 
 
## Begränsningar för händelser

* För systemgenererade händelser måste strömmande data som används för att initiera en kundens färd konfigureras i Journey Orchestration först för att få ett unikt orkestrerings-ID.Det här orkestrerings-ID:t måste läggas till i den direktuppspelningsnyttolast som kommer till Adobe Experience Platform. Den här begränsningen gäller inte för regelbaserade händelser.
 
## Begränsningar för datakällor

* Externa datakällor kan utnyttjas i en kundresa för att söka efter externa data i realtid. Dessa källor måste kunna användas via REST API, ha stöd för JSON och kunna hantera antalet begäranden.

## Resor som börjar samtidigt som en profil skapas {#journeys-limitation-profile-creation}

Det finns en fördröjning i skapandet/uppdateringen av API-baserade profiler i Adobe Experience Platform. Servicenivåmålet (SLT) i form av fördröjning är &lt; 1 min från intag till en enhetlig profil för 95:e percentilen begäranden, vid en volym på 20 000 förfrågningar per sekund (RPS).

Om en resa utlöses samtidigt för att skapa en profil och omedelbart kontrollerar/hämtar information från profiltjänsten kanske den inte fungerar som den ska.

Du kan välja mellan följande två lösningar:

* Lägg till en vänteaktivitet efter den första händelsen för att ge Adobe Experience Platform den tid det behöver för att utföra inmatningen till profiltjänsten.

* Skapa en resa som inte omedelbart utnyttjar profilen. Om färden till exempel är utformad för att bekräfta att ett konto har skapats kan upplevelsehändelsen innehålla information som behövs för att skicka det första bekräftelsemeddelandet (förnamn, efternamn, e-postadress osv.).
