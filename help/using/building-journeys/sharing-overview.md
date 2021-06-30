---
product: adobe campaign
title: Översikt över att dela steg i resan
description: Översikt över att dela steg i resan
feature: Resor
role: Business Practitioner
level: Intermediate
exl-id: 95ca5fdb-38b7-47a0-b1a9-b1b26bf8e5f5
source-git-commit: 78c758c75825c0f85788190c4526fa5c743c6673
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 7%

---

# Översikt över att dela steg i resan{#sharing-overview}

[!DNL Journey Orchestration] skickar automatiskt data om reseprestanda till Adobe Experience Platform så att de kan kombineras med andra data i analyssyfte.

>[!NOTE]
>
>Den här funktionen aktiveras som standard för alla instanser för steg i kundresan. Vid portoplanssteg aktiveras aktiveringen på begäran. Scheman och datauppsättningarna som skapades under etableringen för den här funktionen får inte ändras.

Du har till exempel konfigurerat en resa som skickar flera e-postmeddelanden. Med den här funktionen kan du kombinera [!DNL Journey Orchestration]-data med händelsedata längre fram i kedjan, som hur många konverteringar som har gjorts, hur mycket engagemang som har gjorts på webbplatsen eller hur många transaktioner som har gjorts i butiken. Reseinformationen kan kombineras med data om Adobe Experience Platform, antingen från andra digitala resurser eller från offlineanläggningar, för att ge en mer heltäckande bild av resultatet.

[!DNL Journey Orchestration] skapar automatiskt nödvändiga scheman och strömmar till datauppsättningar till Adobe Experience Platform för varje steg en individ tar på en resa. En steghändelse motsvarar en person som flyttar från en nod till en annan under en resa. Exempel: i en resa som innehåller en händelse, ett villkor och en åtgärd skickas tre steghändelser till Adobe Experience Platform.

Listan över XDM-fält som skickas är omfattande. Vissa innehåller systemgenererade koder och andra har användarvänliga namn som kan läsas. Exempel är etiketten för reseaktiviteten eller stegstatusen: hur många gånger en åtgärd orsakade timeout eller fel.

>[!CAUTION]
>
>Datauppsättningar kan inte aktiveras för realtidsprofiltjänst. Kontrollera att växlingsknappen **[!UICONTROL Profile]** är inaktiverad.

Journeys skickar data när de förekommer, på ett strömmande sätt. Du kan söka efter dessa data med hjälp av frågetjänsten. Du kan ansluta till Customer Journey Analytics eller andra BI-verktyg för att visa data som hör till dessa steg.

Följande scheman skapas:

* Händelseschema för resesegmentprofil för [!DNL Journey Orchestration] - Upplev händelser för steg som tagits på en resa tillsammans med en identitetskarta som ska användas för mappning till en enskild resespart.
* Resestegshändelseschema för [!DNL Journey Orchestration] - Resestegshändelse som är knuten till en resemetadata.
* Reseschema med resefält för [!DNL Journey Orchestration] - Resemetadata för att beskriva resor.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Följande datauppsättningar har skickats:

* Profilhändelseschema för resestegsprofil för [!DNL Journey Orchestration]
* Resestegshändelser
* Resor

![](../assets/sharing3.png)

Listorna med XDM-fält som skickas till Adobe Experience Platform finns här:

* [vanliga fält för händelsen journeySteps](../building-journeys/sharing-common-fields.md)
* [fält för händelseexekvering för händelsen journeyStep](../building-journeys/sharing-execution-fields.md)
* [datafält för hämtning för händelsen journeyStep](../building-journeys/sharing-fetch-fields.md)
* [identitetsfält för händelsen journeyStep](../building-journeys/sharing-identity-fields.md)
* [resefält](../building-journeys/sharing-journey-fields.md)

Titta på den här [självstudievideon](https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/reporting-step-events-to-adobe-experience-platform.html) om du vill ha mer information om steghändelser som rapporteras till Adobe Experience Platform.
