---
title: Tidszonshantering
description: Läs mer om hantering av tidszoner
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '252'
ht-degree: 0%

---



# Tidszonshantering {#timezone_management}

Du kan definiera en tidszon i [egenskaperna](../building-journeys/changing-properties.md) för din resa.

Du öppnar Egenskaper genom att klicka på pennikonen i skärmens övre högra hörn.

Den här tidszonen kommer att användas för varje aktivitet i resan som innehåller ett tidselement som:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Du kan välja en tidszon eller välja att använda den tidszon som är definierad i användarprofilen.

## Definiera en fast tidszon {#fixed-timezone}

Tidszonen kan också korrigeras. Rensa den fördefinierade tidszonen och välj en i listrutan. Om du använder en fast tidszon är den densamma för alla personer som deltar i resan.

I **[!UICONTROL Properties]** väljer du en tidszon.

![](../assets/journey73.png)

## Använda profiler för att definiera resetidszonen {#timezone-from-profiles}

Om resans inträde har ett namnutrymme, vilket innebär att resan kan nå kundprofiltjänsten i realtid i Adobe Experience Platform, är tidszonen fördefinierad med den som anges i profilen för den person som passerar resan.

Om en tidszon definieras i Adobe Experience Platform-profilen kan den hämtas under resan.

Om den enskilda personens profil inte innehåller någon tidszon är den tidszon som hämtas den som definieras i tidszonsfältet.

Om du vill göra det **[!UICONTROL Properties]** går du till **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey72.png)

## Använda tidszoner i uttryck {#timezone-in-expressions}

Start- och slutdatum för en resa kan inte länkas till en viss tidszon. De kopplas automatiskt till instansens tidszon.
