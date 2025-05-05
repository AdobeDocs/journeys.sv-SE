---
product: adobe campaign
title: Reaktionshändelser
description: Läs mer om reaktionshändelser
feature: Journeys
role: User
level: Intermediate
exl-id: 2f2a2905-1521-48d9-b593-9b31238282a5
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---

# Reaktionshändelser {#section_dhx_gss_dgb}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._



En av de olika händelseaktiviteterna som finns på paletten finns i den inbyggda **[!UICONTROL Reactions]**-händelsen. Med den här aktiviteten kan du reagera på spårningsdata för ett meddelande som skickas med e-post, SMS eller push-aktiviteter inom samma resa. Informationen kommer från transaktionsmeddelanden i Adobe Campaign Standard. Vi sparar denna information i realtid när den delas med Adobe Experience Platform. För push-meddelanden kan du reagera på klickade, skickade eller misslyckade meddelanden. För SMS-meddelanden kan du reagera på skickade eller misslyckade meddelanden. För e-postmeddelanden kan du reagera på klickade, skickade, öppnade eller misslyckade meddelanden.

Du kan också använda den här funktionen för att utföra en åtgärd när det inte finns någon reaktion på dina meddelanden. Det gör du genom att skapa en andra sökväg parallellt med reaktionsaktiviteten och lägga till en vänteaktivitet. Om ingen reaktion inträffar under den period som anges i vänteaktiviteten väljs den andra banan. Du kan välja att skicka t.ex. ett uppföljningsmeddelande.

Observera att du bara kan använda en reaktionsaktivitet på arbetsytan om det finns en tidigare e-post-, push- eller SMS-aktivitet.

Se [Om åtgärdsaktiviteter](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Här följer de olika stegen för att konfigurera reaktionshändelser:

1. Lägg till en **[!UICONTROL Label]** i svaret. Det här steget är valfritt.
1. Välj den åtgärd som du vill reagera på i listrutan. Du kan välja vilken åtgärdsaktivitet som helst som placerats i banans tidigare steg.
1. Beroende på vilken åtgärd du har valt (ett e-postmeddelande, SMS eller ett push-meddelande) väljer du vad du vill reagera på.
1. Du kan definiera en timeout för en händelse (mellan 40 sekunder och 30 dagar) och en timeout-sökväg. Detta kommer att skapa en andra väg för individer som inte reagerade inom den definierade tidsperioden. När du testar en resa som använder en reaktionshändelse är standardvärdet **[!UICONTROL Wait time]** och minimivärdet 40 sekunder. Se [det här avsnittet](../building-journeys/testing-the-journey.md).

>[!NOTE]
>
>Reaktionshändelser fungerar med Adobe Campaign Standard, oavsett om de distribueras på AWS- eller Azure-servrar.
>
>Reaktionshändelser kan inte spåra e-post, SMS eller push-åtgärder som utförs under en annan resa.
>
>Reaktionshändelser spårar klick på länkar av typen &quot;spårade&quot; (se den här [sidan](https://experienceleague.adobe.com/docs/campaign-standard/using/designing-content/links.html?lang=sv-SE#about-tracked-urls)). Ta inte hänsyn till länkar för att ta bort prenumerationer och spegla sidor.

>[!IMPORTANT]
>
>E-postklienter som Gmail tillåter bildblockering. E-postmeddelanden som öppnas spåras med en bild på 0 pixlar som ingår i e-postmeddelandet. Om bilder blockeras kommer e-postöppningar inte att beaktas.
