---
product: adobe campaign
title: Hantering av tidszoner
description: Läs mer om hantering av tidszoner
feature: Journeys
role: User
level: Intermediate
exl-id: c0e67849-caa0-4045-94ed-38e483054e1d
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 2%

---

# Hantering av tidszoner {#timezone_management}

Du kan definiera en tidszon i dialogrutan [egenskaper](../building-journeys/changing-properties.md) av din resa.

Du öppnar Egenskaper genom att klicka på pennikonen i skärmens övre högra hörn.

Den här tidszonen kommer att användas för varje aktivitet i resan som innehåller ett tidselement som:

* [Tidsvillkor](../building-journeys/condition-activity.md#time_condition)
* [Datumvillkor](../building-journeys/condition-activity.md#date_condition)
* [Anpassad väntetid](../building-journeys/wait-activity.md#custom)
* [Vänta fast](../building-journeys/wait-activity.md#fixed_date)

Du kan välja en tidszon eller välja att använda den tidszon som är definierad i användarprofilen.

>[!NOTE]
>
>Tidszonen för profilen fungerar med **timeZone** fältet finns i **Inställningsinformation** fältgrupp.

## Definiera en fast tidszon {#fixed-timezone}

Tidszonen kan också korrigeras. Rensa den fördefinierade tidszonen och välj en i listrutan. Om du använder en fast tidszon är den densamma för alla personer som deltar i resan.

Gör så här: **[!UICONTROL Properties]** väljer du en tidszon.

![](../assets/journey72.png)

## Använda profiler för att definiera resetidszonen {#timezone-from-profiles}

Om resans inträde har ett namnutrymme, vilket innebär att resan kan nå kundprofiltjänsten i realtid i Adobe Experience Platform, är tidszonen fördefinierad med den som anges i profilen för den person som passerar resan.

Om en tidszon definieras i Adobe Experience Platform-profilen kan den hämtas under resan.

Om den enskilda personens profil inte innehåller någon tidszon är den tidszon som hämtas den som definieras i tidszonsfältet.

Gör så här: **[!UICONTROL Properties]**, kontrollera **[!UICONTROL Use Profile timezone in timers and conditions]**.

![](../assets/journey73.png)

## Använda tidszoner i uttryck {#timezone-in-expressions}

Start- och slutdatum för en resa kan inte länkas till en viss tidszon. De kopplas automatiskt till instansens tidszon.
