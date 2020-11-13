---
title: Journey Orchestration begränsningar
description: Läs mer om begränsningar i Journey Orchestration
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 59b726388ee1c2c4b51ada9e7e5f7ca4eb6554b3
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 2%

---


# Begränsningar {#limitations}

Här är begränsningar för användning av Journey Orchestration.

## Allmänna åtgärdsbegränsningar

* Det finns ingen sändande begränsning. 
* Två försök görs systematiskt om ett fel uppstår. Du kan inte justera antalet försök enligt det mottagna felmeddelandet. 
* Den inbyggda **reaktionshändelsen** gör att du kan reagera på åtgärder som inte är installerade (se den här [sidan](../building-journeys/reaction-events.md)). Om du vill reagera på ett meddelande som skickas via en anpassad åtgärd måste du konfigurera en dedikerad händelse. 
* Det finns ingen Adobe Campaign Classic-integration.
 
## Begränsningar för anpassade åtgärder

* Den anpassade åtgärds-URL:en stöder inte dynamiska parametrar. 
* Endast anropsmetoderna POST och PUT stöds. 
* Namnet på frågeparametern eller huvudet får inte börja med &quot;.&quot; eller &quot;$&quot;. 
* IP-adresser tillåts inte. 
* Interna Adobe-adresser (.adobe.) tillåts inte.
 

## Begränsningar för Adobe Campaign-åtgärder

* Adobe Campaign Standard Transactional Messaging har en skala på högst 50 000 meddelanden per timme över alla kanaler för en viss instans. Se [Adobe Campaign Standard produktbeskrivning](https://helpx.adobe.com/se/legal/product-descriptions/campaign-standard.html). 
* Aktiviteten för **segmentkvalificering** bör inte användas tillsammans med Adobe Campaign Standard Transactional Messaging på grund av dataflödesbegränsningar.
 
## Begränsningar för händelser

* Direktuppspelningsdata som används för att initiera en kundresa måste konfigureras inom Journey Orchestration först för att få ett unikt orkestrerings-ID. Detta Orchestration-ID måste bifogas till strömningsnyttolasten som kommer till Adobe Experience Platform.
 

## Begränsningar för datakällor:

* Externa datakällor kan utnyttjas inom en kundresa för att söka externa data i realtid. Dessa källor måste kunna användas via REST API, ha stöd för JSON och kunna hantera antalet begäranden.