---
product: adobe campaign
solution: Journey Orchestration
title: Hantera tidszoner
description: Läs mer om hantering av tidszoner
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '261'
ht-degree: 2%

---



# Hantera tidszoner {#timezone_management}

Du kan definiera en tidszon i [egenskaperna](../building-journeys/changing-properties.md) för din resa.

Du öppnar Egenskaper genom att klicka på pennikonen i skärmens övre högra hörn.

Den här tidszonen kommer att användas för varje aktivitet i resan som innehåller ett tidselement som:

* [Tidsvillkor](../building-journeys/condition-activity.md#time_condition)
* [Datumvillkor](../building-journeys/condition-activity.md#date_condition)
* [Anpassad väntetid](../building-journeys/wait-activity.md#custom)
* [Vänta fast](../building-journeys/wait-activity.md#fixed_date)

Du kan välja en tidszon eller välja att använda den tidszon som är definierad i användarprofilen.

## Definiera en fast tidszon {#fixed-timezone}

Tidszonen kan också korrigeras. Rensa den fördefinierade tidszonen och välj en i listrutan. Om du använder en fast tidszon är den densamma för alla personer som deltar i resan.

Om du vill göra det väljer du en tidszon i **[!UICONTROL Properties]**.

![](../assets/journey73.png)

## Använda profiler för att definiera resetidszonen {#timezone-from-profiles}

Om resans inträde har ett namnutrymme, vilket innebär att resan kan nå kundprofiltjänsten i realtid i Adobe Experience Platform, är tidszonen fördefinierad med den som anges i profilen för den person som passerar resan.

Om en tidszon definieras i Adobe Experience Platform-profilen kan den hämtas under resan.

Om den enskilda personens profil inte innehåller någon tidszon är den tidszon som hämtas den som definieras i tidszonsfältet.

Om du vill göra det i **[!UICONTROL Properties]** markerar du **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey72.png)

## Använda tidszoner i uttryck {#timezone-in-expressions}

Start- och slutdatum för en resa kan inte länkas till en viss tidszon. De kopplas automatiskt till instansens tidszon.
