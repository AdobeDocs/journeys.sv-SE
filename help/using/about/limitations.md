---
product: adobe campaign
solution: Journey Orchestration
title: Journey Orchestration begränsningar
description: Läs mer om begränsningar i Journey Orchestration
translation-type: tm+mt
source-git-commit: 6ebedad2cb8e78b4dd953bc7a2993cebbeefabcc
workflow-type: tm+mt
source-wordcount: '361'
ht-degree: 3%

---


# Begränsningar {#limitations}

Här är begränsningar för användning av Journey Orchestration.

## Allmänna åtgärdsbegränsningar

* Det finns ingen sändande begränsning. 
* Två försök görs systematiskt om ett fel uppstår. Du kan inte justera antalet försök enligt det mottagna felmeddelandet. 
* Den inbyggda **Reaction**-händelsen gör att du kan reagera på åtgärder som inte finns i lådan (se den här [sidan](../building-journeys/reaction-events.md)). Om du vill reagera på ett meddelande som skickas via en anpassad åtgärd måste du konfigurera en dedikerad händelse. 
* Det finns ingen Adobe Campaign Classic-integration.

## Begränsningar för reseversioner {#journey-versions-limitations}

* en resa som börjar med en händelseaktivitet i v1 kan inte börja med något annat än en händelse i andra versioner. Det går inte att starta en resa med en **segmentkvalificeringshändelse**.
* en resa som börjar med en **segmentkvalificering**-aktivitet i v1 måste alltid börja med en **segmentkvalificering** i ytterligare versioner.
* Det segment och namnområde som valts i **Segmentkvalificering** (första noden) kan inte ändras i nya versioner.
* Regeln för återinträde måste vara densamma i alla reseversioner.

## Segmentkvalificering {#segment-qualification}

* Aktiviteten **Segmentkvalificering** kan inte användas tillsammans med Adobe Campaign Standard Transactional Messaging på grund av dataflödesbegränsningar. Se [Adobe Campaign Standard produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/campaign-standard.html). 
 

## Begränsningar för anpassade åtgärder

* Den anpassade åtgärds-URL:en stöder inte dynamiska parametrar. 
* Endast anropsmetoderna POST och PUT stöds. 
* Namnet på frågeparametern eller huvudet får inte börja med &quot;.&quot; eller &quot;$&quot;. 
* IP-adresser tillåts inte. 
* Interna Adobe-adresser (.adobe.) tillåts inte.
 

## Begränsningar för Adobe Campaign-åtgärder

* Adobe Campaign Standard Transactional Messaging har en skala på högst 50 000 meddelanden per timme över alla kanaler för en viss instans. Se [Adobe Campaign Standard produktbeskrivning](https://helpx.adobe.com/legal/product-descriptions/campaign-standard.html). 
 

## Begränsningar för händelser

* Direktuppspelningsdata som används för att initiera en kundresa måste konfigureras inom Journey Orchestration först för att få ett unikt orkestrerings-ID. Detta Orchestration-ID måste bifogas till strömningsnyttolasten som kommer till Adobe Experience Platform.
 

## Begränsningar för datakällor

* Externa datakällor kan utnyttjas inom en kundresa för att söka externa data i realtid. Dessa källor måste kunna användas via REST API, ha stöd för JSON och kunna hantera antalet begäranden.