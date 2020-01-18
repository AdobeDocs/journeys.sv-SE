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
source-git-commit: f57cc43d8f2a223c04cc4ccccb3b3c3e0bcadfc1

---



# Tidszonshantering {#timezone_management}

Tidszonsdefinitionen är tillgänglig i följande aktiviteter:

* [](../building-journeys/condition-activity.md#time_condition)
* [](../building-journeys/condition-activity.md#date_condition)
* [](../building-journeys/wait-activity.md#custom)
* [](../building-journeys/wait-activity.md#fixed_date)

Om resans inmatningshändelse har ett namnutrymme, vilket innebär att resan kan nå kundprofiltjänsten i realtid för dataplattformen, är tidszonen fördefinierad med den som anges i profilen för den person som löper på resan. Om individens profil inte innehåller någon tidszon används instansens tidszon. Du kan kontakta administratören för att få information om instansens tidszon.

![](../assets/journey73.png)

Tidszonen kan också korrigeras. Rensa den fördefinierade tidszonen och välj en i listrutan. Om du använder en fast tidszon är den densamma för alla personer som deltar i resan.

![](../assets/journey72.png)

Slutligen kan tidszonen vara dynamisk för varje person som går in i steget. I det här fallet använder du uttrycksredigeraren för att välja var du vill att systemet ska hämta informationen (det kan vara från en händelse eller en datakälla). Se [](../expression/expressionadvanced.md).


Start- och slutdatum för en resa kan inte länkas till en viss tidszon. De kopplas automatiskt till instansens tidszon.
