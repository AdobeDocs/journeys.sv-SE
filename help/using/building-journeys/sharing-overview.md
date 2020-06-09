---
title: Översikt över delning av resesteg
description: Översikt över delning av resesteg
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
source-git-commit: a6a98eca551bf5fc46ebd3a6d0d11486e3fbe06b
workflow-type: tm+mt
source-wordcount: '442'
ht-degree: 0%

---


# Översikt över delning av resesteg{#sharing-overview}

Joursamordning skickar automatiskt data om reseprestanda till Adobe Experience Platform så att den kan kombineras med andra data för analysändamål.

Du har till exempel konfigurerat en resa som skickar flera e-postmeddelanden. Med den här funktionen kan ni kombinera data från resesamordning med händelsedata längre fram i kedjan, som hur många konverteringar som har gjorts, hur mycket engagemang som har förekommit på webbplatsen eller hur många transaktioner som har gjorts i butiken. Reseinformationen kan kombineras med data på plattformen, antingen från andra digitala resurser eller från offlineanläggningar, för att ge en mer heltäckande bild av resultatet.

Resesamordning skapar automatiskt nödvändiga scheman och strömmar in i datauppsättningar till plattformen för varje steg en individ tar på en resa. En steghändelse motsvarar en person som flyttar från en nod till en annan under en resa. Exempel: i en resa som innehåller en händelse, ett villkor och en åtgärd skickas tre steghändelser till plattformen.

Listan över XDM-fält som skickas är omfattande. Vissa innehåller systemgenererade koder och andra har användarvänliga namn som kan läsas. Exempel är etiketten för reseaktiviteten eller stegstatusen: hur många gånger en åtgärd orsakade timeout eller fel.

>[!CAUTION]
>
>Datamängder är som standard inte aktiverade för realtidsprofiltjänst. Om du vill ha en datauppsättning i en profiltjänst måste du aktivera den (växla **profil** ). Tänk på att ett stort antal händelser kommer att ta upp lagringsutrymme i din kvot. Fortsätt noggrant innan du aktiverar en datauppsättning för profiler
>
>![](../assets/sharing4.png)

>[!]
>
>Resor kan också skicka om händelsen Resestegsprofil ska skickas till plattformen eller inte.  Journeys har en teknikväxel för att avgöra detta.
>
>![](../assets/techtoggle.png)

Journeys skickar data när de förekommer, på ett strömmande sätt. Du kan söka efter dessa data med hjälp av frågetjänsten. Du kan ansluta till kundreseanalys eller andra BI-verktyg för att visa data som hör till dessa steg.

Följande scheman skapas:

* Profilhändelseschema för resestege för resesamordning - Upplev händelser för steg som tagits på en resa tillsammans med en identitetskarta som ska användas för mappning till en enskild resedeltagare.
* Resestegshändelseschema för resesamordning - Resestegshändelse som är knuten till en resemetadata.
* Reseschema med resefält för resesamordning - Resemetadata för att beskriva resor.

![](../assets/sharing1.png)

![](../assets/sharing2.png)

Följande datauppsättningar har skickats:

* Schema för resesegmentprofilhändelse för resesorkestrering
* Resestegshändelser
* Resor

![](../assets/sharing3.png)

Listorna med XDM-fält som skickas till plattformen finns här:

* [resaSteg-händelser, vanliga fält](../building-journeys/sharing-common-fields.md)
* [roadStep-händelser, körningsfält för åtgärd](../building-journeys/sharing-execution-fields.md)
* [progressStep-händelsedatafält för hämtning](../building-journeys/sharing-fetch-fields.md)
* [travelStep, händelseidentitetsfält](../building-journeys/sharing-identity-fields.md)
* [resefält](../building-journeys/sharing-journey-fields.md)

