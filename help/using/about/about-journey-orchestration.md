---
title: Om resesamordning
description: Läs mer om resesamordning
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 1e7765352ec91be50b51633927ab038d3492b71a
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---


# Om [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}

Bygg realtidssamordning med hjälp av kontextuella data lagrade i händelser eller datakällor.

[!DNL Journey Orchestration] är en programtjänst som är integrerad med Experience Platform.

![](../assets/journeydiagram.png)

[!DNL Journey Orchestration] möjliggör realtidssamordning som bygger på kontextuella data från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part. Du kan konfigurera en anpassad åtgärd om du använder ett tredjepartssystem för att skicka meddelanden. Om ni har Adobe Campaign Standard kan ni skicka e-post, push-meddelanden och SMS med hjälp av Adobe Campaign Standard [Transactional Messaging-funktionerna](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

På fliken Händelsekonfiguration konfigurerar en **teknisk användare** händelser som förväntas under resorna. Data för inkommande händelser normaliseras enligt Adobe Experience Data Model (XDM). Händelser kommer från API:er för direktuppspelning av inmatning för autentiserade och oautentiserade händelser (som Adobe Mobile SDK-händelser).

På fliken för konfiguration av datakälla konfigurerar en **teknisk användare** :

* De olika fält som visas i Adobe Experience Platform i kunddesignern för villkorsskapande och personalisering.
* De ytterligare anpassade datakällor som ni använder i kundresedesignern. Anpassade datakällor är anslutningar mellan [!DNL Journey Orchestration] och tredjepartssystem eller -tjänster via API. Du kan ansluta ett tredjepartssystem, till exempel ett lojalitetssystem. Tredjepartstjänster kan till exempel vara ett väder-API.

Med resedesignern kan en **affärsanvändare** enkelt dra och släppa ett tävlingsbidrag, lägga till villkor och specificera vilken åtgärd som ska utföras.

Sedan skapar du villkor baserade på:

* tid
* data som kommer från händelsenyttolasten
* information från datakällor: Datakälla för kundprofil i realtid eller anpassade datakällor

Du kan använda det delade villkoret för att skicka personer på resan till olika riktningar.

Med åtgärdsaktiviteter kan du sedan skicka ett meddelande via ett tredjepartssystem. Om du har Adobe Campaign Standard kan du skicka personaliserade SMS-meddelanden, push-meddelanden eller e-postmeddelanden i realtid.

I likhet med [!DNL Journey Orchestration] flerstegsläge kan du skapa avancerade scenarier. Efter en första händelse och åtgärd kan du till exempel dra andra händelser. Sedan kan du lägga till en andra åtgärd, placera en vänteaktivitet för att vänta en stund, lägga till ett delat villkor för att skicka personer till två olika sökvägar och sedan skicka olika meddelanden.

>[!NOTE]
>
>Dokumentationen uppdateras ofta för att återspegla de senaste ändringarna i produkten. Vissa skärmbilder kan dock skilja sig något från produktens gränssnitt.
