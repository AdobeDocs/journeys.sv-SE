---
product: adobe campaign
title: Journey Orchestration begränsningar
description: Läs mer om begränsningar i Journey Orchestration
feature: Journeys
role: User
level: Beginner
exl-id: fef039ae-c04d-4198-a082-4be27710255f
source-git-commit: 861c6bd8ce65793b6009e220d88f105c75ea3008
workflow-type: tm+mt
source-wordcount: '564'
ht-degree: 0%

---

# Begränsningar {#limitations}

Här är begränsningar för användning av Journey Orchestration.

## Allmänna skyddsräcken för resan {#journeys-guardrails-journeys}

* Antalet aktiviteter under en resa är begränsat till 50. Antalet aktiviteter visas i den övre vänstra delen av arbetsytan.
* Antalet **direktresor** i en organisation är begränsat till 100 per sandlåda. När den här gränsen har nåtts kan du inte längre publicera en ny resa.

## Allmänna åtgärdsbegränsningar

* Tre försök utförs systematiskt om ett fel uppstår. Du kan inte justera antalet försök enligt det mottagna felmeddelandet. 
* Den inbyggda **Reaction**-händelsen gör att du kan reagera på åtgärder som inte är i kartong (se den här [sidan](../building-journeys/reaction-events.md)). Om du vill reagera på ett meddelande som skickas via en anpassad åtgärd måste du konfigurera en dedikerad händelse. 

## Begränsningar för reseversioner {#journey-versions-limitations}

* En resa som börjar med en händelseaktivitet i v1 kan inte börja med något annat än en händelse i andra versioner. Du kan inte starta en resa med en **Segmentkvalificeringshändelse**.
* En resa som börjar med en **segmentkvalificeringsaktivitet** i v1 måste alltid börja med en **segmentkvalificering** i ytterligare versioner.
* Det segment och namnområde som valts i **Segmentkvalificering** (första noden) kan inte ändras i nya versioner.
* Regeln för återinträde måste vara densamma i alla reseversioner.

## Segmentkvalificering {#segment-qualification}

* Aktiviteten **Segmentkvalificering** kan inte användas tillsammans med Adobe Campaign Standard Transactional Messaging på grund av dataflödesbegränsningar. Se [Adobe Campaign Standard produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/campaign-standard.html). 
 
## Begränsningar för anpassade åtgärder

* Den anpassade åtgärds-URL:en stöder inte dynamiska parametrar. 
* Endast anropsmetoderna POST och PUT stöds. 
* Namnet på frågeparametern eller -rubriken får inte börja med &quot;.&quot; eller &quot;$&quot;. 
* IP-adresser tillåts inte. 
* Interna Adobe-adresser (.adobe.) tillåts inte.
 
## Adobe Campaign åtgärdsbegränsningar

* Adobe Campaign Standard Transactional Messaging har en skala på högst 50 000 meddelanden per timme över alla kanaler för en viss instans. Se [Adobe Campaign Standard produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/campaign-standard.html). 
 
## Begränsningar för händelser

* För systemgenererade händelser måste strömmande data som används för att initiera en kundresa konfigureras inifrån Journey Orchestration först för att få ett unikt orkestrerings-ID. Detta Orchestration-ID måste bifogas till strömningsnyttolasten som kommer till Adobe Experience Platform. Denna begränsning gäller inte regelbaserade händelser.
 
## Begränsningar för datakällor

* Externa datakällor kan utnyttjas inom en kundresa för att söka externa data i realtid. Dessa källor måste kunna användas via REST API, ha stöd för JSON och kunna hantera antalet begäranden.

## Resor som börjar samtidigt som en profil skapas {#journeys-limitation-profile-creation}

Det finns en fördröjning i skapandet/uppdateringen av API-baserade profiler i Adobe Experience Platform. Servicenivåmålet (SLT) i form av fördröjning är &lt; 1 min från intag till en enhetlig profil för 95:e percentilen begäranden, vid en volym på 20 000 förfrågningar per sekund (RPS).

Om en resa utlöses samtidigt för att skapa en profil och omedelbart kontrollerar/hämtar information från profiltjänsten kanske den inte fungerar som den ska.

Du kan välja mellan följande två lösningar:

* Lägg till en vänteaktivitet efter den första händelsen för att ge Adobe Experience Platform den tid det behöver för att utföra inmatningen till profiltjänsten.

* Konfigurera en resa som inte omedelbart utnyttjar profilen. Om resan till exempel är utformad för att bekräfta att ett konto har skapats, kan upplevelsehändelsen innehålla information som behövs för att skicka det första bekräftelsemeddelandet (förnamn, efternamn, e-postadress osv.).
