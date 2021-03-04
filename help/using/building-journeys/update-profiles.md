---
product: adobe campaign
solution: Journey Orchestration
title: Hoppa från en resa till en annan
description: Hoppa från en resa till en annan
translation-type: tm+mt
source-git-commit: 27a65d8bac83e7a9343ad68306c06a0590a607e9
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 3%

---


# Uppdatera profil {#update-profile}

Med åtgärdsaktiviteten **[!UICONTROL Update profile]** kan du uppdatera en befintlig Adobe Experience Platform-profil med information som kommer från händelsen, en datakälla eller med ett specifikt värde.

## Viktiga anteckningar

* Åtgärden **Uppdatera profil** kan bara användas i resor som börjar med en händelse som har ett namnutrymme.
* I testläge simuleras inte profiluppdateringen. Uppdateringen utförs på testprofilen.
* Åtgärden uppdaterar bara befintliga fält, inga nya profilfält skapas.
* Du kan inte använda åtgärden **Uppdatera profil** för att generera upplevelsehändelser, till exempel ett köp.
* Precis som med andra åtgärder kan du definiera en alternativ sökväg om fel eller timeout inträffar, och du kan inte placera två åtgärder parallellt.
* Uppdateringsbegäran som skickas till Platform kommer snabbt men inte omedelbart/inom en sekund. Det tar normalt några sekunder men ibland mer utan garanti. Om en åtgärd till exempel använder&quot;fält 1&quot; som har uppdaterats av en åtgärd av typen Uppdatera profil som har placerats precis tidigare, bör du därför inte förvänta dig att&quot;fält 1&quot; kommer att uppdateras i åtgärden.
* Datakällor har en uppfattning om cache-varaktighet på fältgruppsnivå. Om du förväntar dig att under en resa återanvända ett profilfält som nyligen uppdaterats bör du vara noga med att definiera en mycket kort cachevaraktighet.

## Använda profiluppdateringen.

1. Designa din resa genom att börja med ett evenemang. Se det här [avsnittet](../building-journeys/journey.md).

1. I avsnittet **Åtgärd** på paletten släpper du aktiviteten **Uppdatera profil** på arbetsytan.

   ![](../assets/profileupdate0.png)

1. Välj ett schema i listan.

1. Klicka på **Fält** för att markera fältet som du vill uppdatera. Endast ett fält kan markeras.

   ![](../assets/profileupdate2.png)

1. Välj en datauppsättning i listan. Datamängdsvalet avgör var det nya värdet i profilfältet ska lagras.

1. Klicka på fältet **Värde** för att definiera värdet som du vill använda:

   * Med den enkla uttrycksredigeraren kan du välja ett fält från en datakälla eller från den inkommande händelsen.

      ![](../assets/profileupdate4.png)

   * Om du vill definiera ett specifikt värde eller använda avancerade funktioner klickar du på **Avancerat läge**.

      ![](../assets/profileupdate3.png)

**Uppdateringsprofilen** är nu konfigurerad.

![](../assets/profileupdate1.png)
