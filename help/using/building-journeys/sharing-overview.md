---
product: adobe campaign
title: Översikt över att dela steg i resan
description: Översikt över att dela steg i resan
feature: Journeys
role: User
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: bb07c0edaae469962ee3bf678664b4a0a83572fe
workflow-type: tm+mt
source-wordcount: '506'
ht-degree: 4%

---

# Översikt över att dela steg i resan{#sharing-overview}

[!DNL Journey Orchestration] skickar automatiskt data om reseprestanda till Adobe Experience Platform så att de kan kombineras med andra data i analyssyfte.

>[!NOTE]
>
>Den här funktionen aktiveras som standard för alla instanser för steg i kundresan. Du kan inte ändra eller uppdatera scheman och datauppsättningar som har skapats under etablering för steghändelser. Dessa scheman och datauppsättningar är som standard skrivskyddade.

Du har till exempel konfigurerat en resa som skickar flera e-postmeddelanden. Med den här funktionen kan du kombinera [!DNL Journey Orchestration] data med händelsedata längre fram i kedjan, som hur många konverteringar som har gjorts, hur mycket engagemang som har gjorts på webbplatsen eller hur många transaktioner som har gjorts i butiken. Reseinformationen kan kombineras med data om Adobe Experience Platform, antingen från andra digitala resurser eller från offlineanläggningar, för att ge en mer heltäckande bild av resultatet.

[!DNL Journey Orchestration] skapar automatiskt nödvändiga scheman och strömmar till datauppsättningar till Adobe Experience Platform för varje steg en individ tar på sig under en resa. En steghändelse motsvarar en person som flyttar från en nod till en annan under en resa. Exempel: i en resa som innehåller en händelse, ett villkor och en åtgärd skickas tre steghändelser till Adobe Experience Platform.

Listan över XDM-fält som skickas är omfattande. Vissa innehåller systemgenererade koder och andra har användarvänliga namn som kan läsas. Exempel är etiketten för reseaktiviteten eller stegstatusen: hur många gånger en åtgärd orsakade timeout eller fel.

>[!CAUTION]
>
>Datauppsättningar kan inte aktiveras för realtidsprofiltjänst. Se till att **[!UICONTROL Profile]** växlingsknappen är inaktiverad.

Journeys skickar data när de förekommer, på ett strömmande sätt. Du kan söka efter dessa data med hjälp av frågetjänsten. Du kan ansluta till Customer Journey Analytics eller andra BI-verktyg för att visa data som hör till dessa steg.

Följande scheman skapas:

* Schema för resesegmenthändelse för [!DNL Journey Orchestration] - Resestegshändelse som är knuten till en resemetadata.
* Reseschema med resefält för [!DNL Journey Orchestration] - Resemetadata för att beskriva resor.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Följande datauppsättningar har skickats:

* Resestegshändelser
* Resor

![](../assets/sharing3.png)

Listorna med XDM-fält som skickas till Adobe Experience Platform finns här:

* [Lista över steghändelsefält](../building-journeys/sharing-field-list.md)
* [Äldre steghändelsefält](../building-journeys/sharing-legacy-fields.md)

Om du vill ha mer information om steghändelser som rapporterar till Adobe Experience Platform kan du titta på den här [video med självstudiekurser](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html).

## Integrering med kundreseanalys{#integration-cja}

Journey Orchestration-steghändelser kan länkas till andra datauppsättningar i [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html). Här är det allmänna arbetsflödet:

* Customer Journey Analytics inmatar datauppsättningen&quot;Journey Step Event&quot;.
* The **profileID** fältet i det associerade schemat för resesegmenthändelse för Journey Orchestration definieras som ett identitetsfält. I Customer Journey Analytics kan du sedan länka den här datauppsättningen till andra datauppsättningar som har samma värde som den personbaserade identifieraren.
* Om du vill använda den här datauppsättningen i Customer Journey Analytics, för analys av flerkanalsresor, se den här [dokumentation](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-usecases/cross-channel.html).
