---
product: adobe campaign
title: Reseversioner
description: Läs om olika versioner av resan
feature: Journeys
role: User
level: Intermediate
exl-id: 554d1f60-5d46-4e75-afcb-8209b127c4cd
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '288'
ht-degree: 1%

---

# Reseversioner{#concept_ldc_k55_zgb}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


I reselistan visas alla reseversioner med versionsnumret. Se [den här sidan](../building-journeys/using-the-journey-designer.md). När du söker efter en resa visas de senaste versionerna högst upp i listan första gången programmet öppnas. Sedan kan du definiera den sortering som du vill ha så att programmet behåller den som en användarinställning. Färdens version visas också överst i reseupplagans gränssnitt, ovanför arbetsytan.

![](../assets/journeyversions1.png)

Om du behöver ändra till en direktresa måste du skapa en ny version av din resa.

>[!NOTE]
>
>Mer information om begränsningar för reseversioner finns på [den här sidan](../about/limitations.md#journey-versions-limitations)

1. Öppna den senaste versionen av din liveresa, klicka på **[!UICONTROL Create a new version]** och bekräfta.

   ![](../assets/journeyversions2.png)

   >[!NOTE]
   >
   >Du kan bara skapa en ny version av den senaste versionen av en resa.

1. Gör ändringarna, klicka på **[!UICONTROL Publish]** och bekräfta.

   ![](../assets/journeyversions3.png)

Från det att resan har publicerats kommer individerna att börja flöda in i den senaste versionen av resan. Personer som redan har gått in i en tidigare version stannar kvar tills de är klara med resan. Om de senare återgår till samma resa, kommer de att gå till den senaste versionen.

Reseversioner kan stoppas individuellt. Alla versioner av resor har samma namn.

>[!NOTE]
>
>När du publicerar en ny version av en resa avslutas den tidigare versionen automatiskt och ändras till statusen **Stängd** . Ingen entré på resan kommer att ske. Även om du stoppar den senaste versionen förblir den tidigare versionen stängd.
