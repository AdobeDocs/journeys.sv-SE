---
product: adobe campaign
title: Hoppa från en resa till en annan
description: Hoppa från en resa till en annan
feature: Resor
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '337'
ht-degree: 5%

---

# Uppdatera profil {#update-profile}

Med åtgärdsaktiviteten **[!UICONTROL Update profile]** kan du uppdatera en befintlig Adobe Experience Platform-profil med information som kommer från händelsen, en datakälla eller med ett specifikt värde.

## Viktiga anteckningar

* Åtgärden **Uppdatera profil** kan bara användas i resor som börjar med en händelse som har ett namnutrymme.
* Åtgärden uppdaterar bara befintliga fält, inga nya profilfält skapas.
* Du kan inte använda åtgärden **Uppdatera profil** för att generera upplevelsehändelser, till exempel ett köp.
* Precis som med andra åtgärder kan du definiera en alternativ sökväg om fel eller timeout inträffar, och du kan inte placera två åtgärder parallellt.
* Uppdateringsbegäran som skickas till Platform kommer snabbt men inte omedelbart/inom en sekund. Det tar normalt några sekunder men ibland mer utan garanti. Om en åtgärd till exempel använder&quot;fält 1&quot; som har uppdaterats av en åtgärd av typen Uppdatera profil som har placerats precis tidigare, bör du därför inte förvänta dig att&quot;fält 1&quot; kommer att uppdateras i åtgärden.
* I testläge simuleras inte profiluppdateringen. Uppdateringen utförs på testprofilen.

## Använda profiluppdateringen

1. Designa din resa genom att börja med ett evenemang. Se det här [avsnittet](../building-journeys/journey.md).

1. I avsnittet **Åtgärd** på paletten släpper du aktiviteten **Uppdatera profil** på arbetsytan.

   ![](../assets/profileupdate0.png)

1. Välj ett schema i listan.

1. Klicka på **Fält** för att markera fältet som du vill uppdatera. Endast ett fält kan markeras.

   ![](../assets/profileupdate2.png)

1. Välj en datauppsättning i listan.

   >[!NOTE]
   >
   >Åtgärden **Uppdatera profil** uppdaterar profildata i realtid, men uppdaterar inte datauppsättningar. Val av datauppsättning krävs eftersom profilen är en post som är relaterad till en datauppsättning.

1. Klicka på fältet **Värde** för att definiera värdet som du vill använda:

   * Med den enkla uttrycksredigeraren kan du välja ett fält från en datakälla eller från den inkommande händelsen.

      ![](../assets/profileupdate4.png)

   * Om du vill definiera ett specifikt värde eller använda avancerade funktioner klickar du på **Avancerat läge**.

      ![](../assets/profileupdate3.png)

**Uppdateringsprofilen** är nu konfigurerad.

![](../assets/profileupdate1.png)
