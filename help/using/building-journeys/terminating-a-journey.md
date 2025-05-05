---
product: adobe campaign
title: Avsluta en resa
description: Lär dig hur du avslutar en resa
feature: Journeys
role: User
level: Intermediate
exl-id: 2d1b9d6b-0a53-436c-b251-ce77cb931aaa
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '401'
ht-degree: 4%

---

# Avsluta en resa


>[!CAUTION]
>
>**Letar du efter Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för dokumentation om Journey Optimizer.
>
>
>_Den här dokumentationen refererar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


Med **[!UICONTROL Stop]** alternativen och **[!UICONTROL Close to new entrances]** kan du avsluta **liveresor** . Att stänga en resa innebär **att ankomsten av nya kunder på resan blockeras** och att de kunder som redan har påbörjat resan kan uppleva den till slutet. Detta är det mest rekommenderade sättet att sätta stopp för en resa eftersom det ger den bästa upplevelsen för kunderna. Att stoppa en resa innebär att människor som redan har påbörjat en resa alla stoppas i sin framfart. Resan är i princip avstängd.

>[!NOTE]
>
>Observera att du inte kan återuppta en stängd eller stoppad resa.
>
>Begreppet resans slut beskrivs i det här [avsnittet](../building-journeys/journey.md#ending_a_journey).

## Avsluta en resa

Du kan stänga en färd manuellt för att säkerställa att kunder som redan har påbörjat färden kan slutföra sin färd, men att nya användare inte kan komma in i färden.

När den är stängd får en färd statusen **[!UICONTROL Closed (no entrance)]**. Efter den globala standardtidsgränsen på 30 dagar växlar färden till statusen **Slutförd** . Läs det här [avsnittet](../building-journeys/changing-properties.md#entrance).

En version av en stängd färd kan inte startas om eller tas bort. Du kan skapa en ny version av den eller duplicera den. Endast slutförda resor kan raderas.

Du kan stänga en resa genom att klicka medan **[!UICONTROL Close to new entrances]** du håller muspekaren över en resa i listan över resor.

![](../assets/do-not-localize/journey-finish-quick-action.png)

Du kan även:

1. I **[!UICONTROL Home]** klickar du på den färd som du vill avsluta.
1. Klicka på nedåtpilen uppe till höger.

   ![](../assets/finish_drop_down_list.png)

1. Klicka på **[!UICONTROL Close to new entrances]**. En dialogruta visas.
1. Klicka på **[!UICONTROL Close to new entrances]** för att bekräfta.

## Avbryta en resa

Du kan stoppa en resa när en nödsituation har inträffat och all behandling måste avslutas omedelbart under en resa.

Det går inte att starta om en version av en stoppad resa.

När en resa stoppas får den statusen **[!UICONTROL Stopped]**.

Du kan stoppa en färd (till exempel om en marknadsförare inser att färden riktar sig till fel målgrupp eller att en anpassad åtgärd som ska leverera meddelanden inte fungerar korrekt...) genom att klicka **[!UICONTROL Stop]** medan du håller muspekaren över en färd i listan över färder.

![](../assets/do-not-localize/journey-stop-quick-action.png)

Du kan även:

1. I **[!UICONTROL Home]** klickar du på den resa du vill stoppa.
1. Klicka på nedåtpilen uppe till höger.

![](../assets/finish_drop_down_list.png)

1. Klicka på **[!UICONTROL Stop]**. En dialogruta visas.
1. Klicka på **[!UICONTROL Stop]** för att bekräfta.
