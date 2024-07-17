---
product: adobe campaign
title: Uppdatera profil
description: Uppdatera profil
feature: Journeys
role: User
level: Intermediate
exl-id: eaf2c795-0920-4b9c-9f06-801e43c1844b
source-git-commit: 64f415f3a4120685b64a4b1dc15bf004e86b35d2
workflow-type: tm+mt
source-wordcount: '345'
ht-degree: 2%

---

# Uppdatera profil {#update-profile}

Åtgärdsaktiviteten **[!UICONTROL Update profile]** gör att du kan uppdatera en befintlig Adobe Experience Platform-profil med information som kommer från händelsen, en datakälla eller med ett specifikt värde.

## Viktiga anteckningar

* Åtgärden **Uppdatera profil** kan bara användas i resor som börjar med en händelse som har ett namnutrymme.
* Åtgärden uppdaterar bara befintliga fält, inga nya profilfält skapas.
* Du kan inte använda åtgärden **Uppdatera profil** för att generera upplevelsehändelser, till exempel ett köp.
* Precis som med andra åtgärder kan du definiera en alternativ sökväg om fel eller timeout inträffar, och du kan inte placera två åtgärder parallellt.
* Uppdateringsbegäran som skickas till Platform kommer snabbt men inte omedelbart/inom en sekund. Det tar normalt några sekunder men ibland mer utan garanti. Om en åtgärd till exempel använder&quot;fält 1&quot; som har uppdaterats av en åtgärd av typen Uppdatera profil som har placerats precis tidigare, bör du därför inte förvänta dig att&quot;fält 1&quot; kommer att uppdateras i åtgärden.
* I testläge simuleras inte profiluppdateringen. Uppdateringen utförs på testprofilen.
* Aktiviteten **Uppdatera profil** stöder inte XDM-fält som är definierade som en uppräkning.

## Använda profiluppdateringen

1. Designa din resa genom att börja med ett evenemang. Se [avsnittet](../building-journeys/journey.md).

1. Släpp aktiviteten **Uppdatera profil** på arbetsytan i avsnittet **Åtgärd** på paletten.

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

   * Om du vill definiera ett specifikt värde eller utnyttja avancerade funktioner klickar du på **Avancerat läge**.

     ![](../assets/profileupdate3.png)

**Uppdateringsprofilen** har nu konfigurerats.

![](../assets/profileupdate1.png)
