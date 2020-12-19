---
product: adobe campaign
solution: Journey Orchestration
title: Reaktionshändelser
description: Läs mer om reaktionshändelser
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '407'
ht-degree: 1%

---


# Reaktionshändelser {#section_dhx_gss_dgb}

Bland de olika händelseaktiviteterna som finns på paletten finns den inbyggda **[!UICONTROL Reactions]**-händelsen. Med den här aktiviteten kan du reagera på spårningsdata för ett meddelande som skickas med e-post, SMS eller push-aktiviteter inom samma resa. Den här informationen kommer från transaktionsmeddelanden i Adobe Campaign Standard. Vi sparar denna information i realtid när den delas med Adobe Experience Platform. För push-meddelanden kan du reagera på klickade, skickade eller misslyckade meddelanden. För SMS-meddelanden kan du reagera på skickade eller misslyckade meddelanden. För e-postmeddelanden kan du reagera på klickade, skickade, öppnade eller misslyckade meddelanden.

Du kan också använda den här funktionen för att utföra en åtgärd när det inte finns någon reaktion på dina meddelanden. Det gör du genom att skapa en andra sökväg parallellt med reaktionsaktiviteten och lägga till en vänteaktivitet. Om ingen reaktion inträffar under den period som anges i vänteaktiviteten väljs den andra banan. Du kan välja att skicka t.ex. ett uppföljningsmeddelande.

Observera att du bara kan använda en reaktionsaktivitet på arbetsytan om det finns en tidigare e-post-, push- eller SMS-aktivitet.

Se [Om åtgärdsaktiviteter](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Här följer de olika stegen för att konfigurera reaktionshändelser:

1. Lägg till en **[!UICONTROL Label]** i reaktionen. Det här steget är valfritt.
1. Välj den åtgärd som du vill reagera på i listrutan. Du kan välja vilken åtgärdsaktivitet som helst som placerats i banans tidigare steg.
1. Beroende på vilken åtgärd du har valt (ett e-postmeddelande, SMS eller ett push-meddelande) väljer du vad du vill reagera på.
1. Du kan definiera ett villkor som ett valfritt steg. Efter en e-poståtgärd kan du till exempel bestämma att du ska skapa två banor, en med en reaktionshändelse som bara spårar klickningar för VIP och en med en reaktionshändelse som spårar klickningar som utförs av kvinnor.

>[!NOTE]
>
>Reaktionshändelser fungerar med Adobe Campaign Standard, oavsett om de distribueras på AWS- eller Azure-servrar.
>
>Reaktionshändelser kan inte spåra e-post, SMS eller push-åtgärder som utförs under en annan resa.
>
>Reaktionshändelser spårar klickningar på länkar av typen &quot;spårade&quot; (se den här [sidan](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Ta inte hänsyn till länkar för att ta bort prenumerationer och spegla sidor.

>[!IMPORTANT]
>
>E-postklienter som Gmail tillåter bildblockering. E-postmeddelanden som öppnas spåras med en bild på 0 pixlar som ingår i e-postmeddelandet. Om bilder blockeras kommer e-postöppningar inte att beaktas.
