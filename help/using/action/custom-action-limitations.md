---
title: Begränsningar för anpassade åtgärder
description: Läs mer om anpassade åtgärdsbegränsningar
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 295112e2d18fd275a0fd2826aa8bd87a8ed12636
workflow-type: tm+mt
source-wordcount: '125'
ht-degree: 0%

---


# Begränsningar för anpassade åtgärder {#concept_lh2_df1_2gb}

Här är några begränsningar för användning av anpassade åtgärder:

* Ingen volymbuffring/utjämning skickas.
* Två försök görs systematiskt om ett fel uppstår. Du kan inte justera antalet försök enligt det mottagna felmeddelandet.
* Den inbyggda **[!UICONTROL Reaction]** händelsen gör att du kan reagera på åtgärder som inte är installerade (se [](../building-journeys/event-activities.md)). Om du vill reagera på ett meddelande som skickas via en anpassad åtgärd måste du konfigurera en dedikerad händelse.
* Den anpassade åtgärds-URL:en stöder inte dynamiska parametrar.
* Endast anropsmetoderna POST och PUT stöds.
* Namnet på frågeparametern eller huvudet får inte börja med &quot;.&quot; eller &quot;$&quot;.
* IP-adresser tillåts inte.
* Interna Adobe-adresser (.adobe.) tillåts inte.
