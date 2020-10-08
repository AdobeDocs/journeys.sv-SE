---
title: Översikt över att dela steg i resan
description: Översikt över att dela steg i resan
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 7%

---


# Översikt över att dela steg i resan{#sharing-overview}

[!DNL Journey Orchestration] skickar automatiskt data om reseprestanda till Adobe Experience Platform så att de kan kombineras med andra data i analyssyfte.

Du har till exempel konfigurerat en resa som skickar flera e-postmeddelanden. Med den här funktionen kan ni kombinera [!DNL Journey Orchestration] data med händelsedata längre fram i kedjan, som hur många konverteringar som har gjorts, hur mycket engagemang som har gjorts på webbplatsen eller hur många transaktioner som har gjorts i butiken. Reseinformationen kan kombineras med data om Adobe Experience Platform, antingen från andra digitala resurser eller från offlineanläggningar, för att ge en mer heltäckande bild av resultatet.

[!DNL Journey Orchestration] skapar automatiskt nödvändiga scheman och strömmar till datauppsättningar till Adobe Experience Platform för varje steg en individ tar på en resa. En steghändelse motsvarar en person som flyttar från en nod till en annan under en resa. Exempel: i en resa som innehåller en händelse, ett villkor och en åtgärd skickas tre steghändelser till Adobe Experience Platform.

Listan över XDM-fält som skickas är omfattande. Vissa innehåller systemgenererade koder och andra har användarvänliga namn som kan läsas. Exempel är etiketten för reseaktiviteten eller stegstatusen: hur många gånger en åtgärd orsakade timeout eller fel.

>[!CAUTION]
>
>Datauppsättningar kan inte aktiveras för realtidsprofiltjänst. Kontrollera att **[!UICONTROL Profile]** växlingsknappen är avstängd

Journeys skickar data när de förekommer, på ett strömmande sätt. Du kan söka efter dessa data med hjälp av frågetjänsten. Du kan ansluta till Customer Journey Analytics eller andra BI-verktyg för att visa data som hör till dessa steg.

Följande scheman skapas:

* Profilhändelseschema för resesegment för [!DNL Journey Orchestration] - Upplev händelser för steg som tagits i en resa tillsammans med en identitetskarta som ska användas för att mappa till en enskild resespart.
* Händelseschema för resesegment för [!DNL Journey Orchestration] - Händelse för resesteg som är knuten till en resemetadata.
* Reseschema med resefält för [!DNL Journey Orchestration] - Resemetadata för att beskriva resor.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Följande datauppsättningar har skickats:

* Profilhändelseschema för resesteg för [!DNL Journey Orchestration]
* Resestegshändelser
* Resor

![](../assets/sharing3.png)

Listorna med XDM-fält som skickas till Adobe Experience Platform finns här:

* [journeySteps, händelser, vanliga fält](../building-journeys/sharing-common-fields.md)
* [journeyStep, händelser, körningsfält för åtgärder](../building-journeys/sharing-execution-fields.md)
* [journeyStep, händelser, datafält för hämtning](../building-journeys/sharing-fetch-fields.md)
* [journeyStep, händelser, identitetsfält](../building-journeys/sharing-identity-fields.md)
* [Resefält](../building-journeys/sharing-journey-fields.md)

Titta på den här [självstudievideon](https://docs.adobe.com/content/help/en/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html)om du vill ha mer information om hur du rapporterar steghändelser till Adobe Experience Platform.
