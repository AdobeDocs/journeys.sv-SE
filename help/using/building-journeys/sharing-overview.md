---
product: adobe campaign
title: Översikt över att dela steg i resan
description: Översikt över att dela steg i resan
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '518'
ht-degree: 3%

---

# Översikt över att dela steg i resan{#sharing-overview}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


[!DNL Journey Orchestration] skickar automatiskt reseprestandadata till Adobe Experience Platform så att de kan kombineras med andra data i analyssyfte.

>[!NOTE]
>
>Den här funktionen aktiveras som standard för alla instanser för steg i kundresan. Du kan inte ändra eller uppdatera scheman och datauppsättningar som har skapats under etablering för steghändelser. Dessa scheman och datauppsättningar är som standard skrivskyddade.

Du har till exempel konfigurerat en resa som skickar flera e-postmeddelanden. Med den här funktionen kan du kombinera [!DNL Journey Orchestration]-data med händelsedata längre fram i kedjan, som hur många konverteringar som har gjorts, hur mycket engagemang som har gjorts på webbplatsen eller hur många transaktioner som har gjorts i butiken. Reseinformationen kan kombineras med data om Adobe Experience Platform, antingen från andra digitala resurser eller från offlineanläggningar, för att ge en mer heltäckande bild av resultatet.

[!DNL Journey Orchestration] skapar automatiskt nödvändiga scheman och strömmar till datauppsättningar till Adobe Experience Platform för varje steg en individ tar på en resa. En steghändelse motsvarar en person som flyttar från en nod till en annan under en resa. Exempel: i en resa som innehåller en händelse, ett villkor och en åtgärd skickas tre steghändelser till Adobe Experience Platform.

Listan över XDM-fält som skickas är omfattande. Vissa innehåller systemgenererade koder och andra har användarvänliga namn som kan läsas. Exempel är etiketten för reseaktiviteten eller stegstatusen: hur många gånger en åtgärd orsakade fel eller orsakade timeout.

>[!CAUTION]
>
>Datauppsättningar kan inte aktiveras för realtidsprofiltjänst. Kontrollera att växlingsknappen **[!UICONTROL Profile]** är inaktiverad.

Journeys skickar data när de förekommer, på ett strömmande sätt. Du kan söka efter dessa data med hjälp av frågetjänsten. Du kan ansluta till Customer Journey Analytics eller andra BI-verktyg för att visa data som hör till dessa steg.

Följande scheman skapas:

* Resestegshändelseschema för [!DNL Journey Orchestration] - Resestegshändelse som är knuten till en resemetadata.
* Reseschema med resefält för [!DNL Journey Orchestration] - Resemetadata för att beskriva resor.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Följande datauppsättningar har skickats:

* Resestegshändelser
* Resor

![](../assets/sharing3.png)

Listorna med XDM-fält som skickas till Adobe Experience Platform finns här:

* [Lista över steghändelsefält](../building-journeys/sharing-field-list.md)
* [Händelsefält för äldre steg](../building-journeys/sharing-legacy-fields.md)


## Integrering med kundreseanalys{#integration-cja}

Journey Orchestration steghändelser kan länkas till andra datauppsättningar i [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html). Här är det allmänna arbetsflödet:

* Customer Journey Analytics infogar datauppsättningen&quot;Journey Step Event&quot;.
* Fältet **profileID** i det associerade schemat för resesegmenthändelse för Journey Orchestration definieras som ett identitetsfält. I Customer Journey Analytics kan du sedan länka den här datauppsättningen till andra datauppsättningar som har samma värde som den personbaserade identifieraren.
* Om du vill använda den här datauppsättningen i Customer Journey Analytics, för flerkanalsanalys, kan du läsa den här [dokumentationen](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html).
