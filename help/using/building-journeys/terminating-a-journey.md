---
product: adobe campaign
solution: Journey Orchestration
title: Avsluta en resa
description: Lär dig hur du avslutar en resa
feature: Resor
role: Yrkesverksam
level: Mellanliggande
translation-type: tm+mt
source-git-commit: 7755822065eb0bcc44f78e0e36c53ce73ac60ada
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 4%

---


# Avsluta en resa

Med alternativen **[!UICONTROL Stop]** och **[!UICONTROL Close to new entrances]** kan du avsluta **direktresor**. När en resa stängs innebär det **att nya kunder inte kan ta sig in på resan** och att de kunder som redan har tagit sig in på resan kan uppleva den till slutet. Det här är det mest rekommenderade sättet att få ett slut på en resa eftersom den erbjuder den bästa upplevelsen för kunderna. Att stoppa en resa innebär att alla som redan har tagit sig in på en resa stoppas i processen. Resan är i stort sett avstängd.

>[!NOTE]
>
>Observera att du inte kan återuppta en stängd eller stoppad resa.
>
>Begreppet slutresa beskrivs i detta [avsnitt](../building-journeys/journey.md#ending_a_journey).

## Stänga en resa

Du kan stänga en resa manuellt för att säkerställa att kunder som redan har gått in på resan kan slutföra sin resa, men nya användare inte kan ta sig in på resan.

När en resa stängs får den statusen **[!UICONTROL Closed (no entrance)]**. Efter den globala standardtidsgränsen på 30 dagar växlar resan till statusen **Slutförd**. Se det här [avsnittet](../building-journeys/changing-properties.md#entrance).

En stängd reseversion kan inte startas om eller tas bort. Du kan skapa en ny version av den eller duplicera den. Endast slutförda resor kan tas bort.

Du kan stänga en resa genom att klicka på **[!UICONTROL Close to new entrances]** medan du hovrar över en resa i listan över resor.

![](../assets/do-not-localize/journey-finish-quick-action.png)

Du kan även:

1. Klicka på den resa du vill stänga i **[!UICONTROL Home]**.
1. Klicka på nedpilen i det övre högra hörnet.

   ![](../assets/finish_drop_down_list.png)

1. Klicka på **[!UICONTROL Close to new entrances]**. En dialogruta visas.
1. Bekräfta genom att klicka på **[!UICONTROL Close to new entrances]**.

## Stoppa en resa

Du kan stoppa en resa när en kris inträffar och all behandling måste avslutas omedelbart under en resa.

Det går inte att starta om en stoppad reseversion.

När den stoppas får en resa statusen **[!UICONTROL Stopped]**.

Du kan stoppa en resa (till exempel om en marknadsförare upptäcker att resan riktar sig mot fel målgrupp eller en anpassad åtgärd som ska leverera meddelanden inte fungerar korrekt..) genom att klicka på **[!UICONTROL Stop]** medan du hovrar över en resa i listan över resor.

![](../assets/do-not-localize/journey-stop-quick-action.png)

Du kan även:

1. Klicka på den resa du vill stoppa i **[!UICONTROL Home]**.
1. Klicka på nedpilen i det övre högra hörnet.

![](../assets/finish_drop_down_list.png)

1. Klicka på **[!UICONTROL Stop]**. En dialogruta visas.
1. Bekräfta genom att klicka på **[!UICONTROL Stop]**.
