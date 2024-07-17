---
product: adobe campaign
title: Hantering av tidszoner
description: Läs mer om hantering av tidszoner
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 77fcc4ba02a855d4d584627625a08abb4af0da2f
workflow-type: tm+mt
source-wordcount: '276'
ht-degree: 2%

---

# Hantering av tidszoner {#timezone_management}

Du kan definiera en tidszon i [egenskaperna](../building-journeys/changing-properties.md) för din resa.

Du öppnar Egenskaper genom att klicka på pennikonen i skärmens övre högra hörn.

Den här tidszonen kommer att användas för varje aktivitet i resan som innehåller ett tidselement som:

* [Tidsvillkor](../building-journeys/condition-activity.md#time_condition)
* [Datumvillkor](../building-journeys/condition-activity.md#date_condition)
* [Anpassad väntetid](../building-journeys/wait-activity.md#custom)

Du kan välja en tidszon eller välja att använda den tidszon som är definierad i användarprofilen.

>[!NOTE]
>
>Profilens tidszon fungerar med fältet **timeZone** som finns i fältgruppen **Inställningsinformation**.

## Definiera en fast tidszon {#fixed-timezone}

Tidszonen kan också korrigeras. Rensa den fördefinierade tidszonen och välj en i listrutan. Om du använder en fast tidszon är den densamma för alla personer som deltar i resan.

Om du vill göra det i **[!UICONTROL Properties]** väljer du en tidszon.

![](../assets/journey72.png)

## Använda profiler för att definiera resetidszonen {#timezone-from-profiles}

Om resans inträde-händelse har ett namnutrymme, vilket innebär att resan kan nå kundprofiltjänsten i realtid i Adobe Experience Platform, kanske du vill använda den tidszon som har definierats på profilnivån. Om du vill göra det går du till **Egenskaper** och markerar **Använd profiltidszon i väntetider och villkor**. Det här alternativet är inte markerat som standard.

Om en tidszon har definierats för en profil hämtas den och används av resan. Om så inte är fallet används tidszonen som definieras i tidszonsfältet.

![](../assets/journey73.png)

## Använda tidszoner i uttryck {#timezone-in-expressions}

Start- och slutdatum för en resa kan inte länkas till en viss tidszon. De kopplas automatiskt till instansens tidszon.
