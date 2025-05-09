---
product: adobe campaign
title: Om Journey Orchestration
description: Läs mer om Journey Orchestration
feature: Journeys
role: User
level: Beginner
exl-id: 430bac3a-06da-45a8-af90-1dcd1504d532
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '426'
ht-degree: 100%

---

# Om [!DNL Journey Orchestration]{#concept_nd3_mqt_52b}


>[!CAUTION]
>
>**Letar du efter Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


Bygg en orkestrering i realtid med hjälp av kontextuella data lagrade i händelser eller datakällor.

[!DNL Journey Orchestration] är en programtjänst som är integrerad i Adobe Experience Platform.

[!DNL Journey Orchestration] möjliggör orkestrering i realtid som bygger på kontextuella data från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part. Du kan konfigurera en anpassad åtgärd om du använder ett tredjepartssystem för att skicka meddelanden. Om du har Adobe Campaign Standard kan du skicka e-postmeddelanden, push-meddelanden och SMS med funktionen [Transaktionsmeddelanden](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=sv) i Adobe Campaign Standard.

På fliken Händelsekonfiguration kan en **teknisk användare** konfigurera händelser som förväntas under resorna. Data för inkommande händelser normaliseras enligt Adobes upplevelsedatamodell (XDM). Händelser kommer från API för strömningsinmatning för autentiserade och ej autentiserade händelser (till exempel händelser i Adobe Mobile SDK).

På fliken för konfiguration av datakälla kan en **teknisk användare** konfigurera:

* De olika fält som ses från Adobe Experience Platform i resedesignern för villkorsbyggnad och personalisering.
* De ytterligare anpassade datakällor som du kan använda i resedesignern. Anpassade datakällor är anslutningar mellan [!DNL Journey Orchestration] och tredjepartssystem eller -tjänster via API. Du kan ansluta ett tredjepartssystem, till exempel ett lojalitetssystem. Tredjepartstjänster kan till exempel vara ett väder-API.

Med resedesignern kan en **företagsanvändare** enkelt dra och släppa en starthändelse, lägga till villkor och specificera vilken åtgärd som ska utföras.

Du kan sedan skapa villkor baserade på:

* tid
* data som kommer från händelsens nyttolast
* information från datakällor: datakälla i en realtidskundprofil eller anpassade datakällor

Du kan använda det delade villkoret för att skicka personer, som befinner sig i resan, i olika riktningar.

Med åtgärdsaktiviteter kan du sedan skicka ett meddelande via ett tredjepartssystem. Med Adobe Campaign Standard kan du skicka personaliserade SMS-meddelanden, push-meddelanden eller e-postmeddelanden i realtid.

Eftersom [!DNL Journey Orchestration] använder sig av flera olika steg kan du skapa avancerade scenarier. Efter en första händelse och åtgärd kan du till exempel dra till andra händelser. Sedan kan du lägga till en andra åtgärd, placera en vänteaktivitet, lägga till ett delat villkor för att skicka personer på två olika vägar och sedan skicka olika meddelanden.

>[!NOTE]
>
>Dokumentationen uppdateras ofta för att återspegla de senaste ändringarna i produkten. Vissa skärmbilder kan dock skilja sig något från produktens gränssnitt.
