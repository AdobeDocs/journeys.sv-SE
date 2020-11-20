---
product: adobe campaign
solution: Journey Orchestration
title: Välja namnrymden
description: Lär dig hur du väljer namnutrymmet
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '204'
ht-degree: 12%

---


# Välja namnrymden {#concept_ckb_3qt_52b}

Med namnutrymmet kan du definiera vilken typ av nyckel som används för att identifiera den person som är associerad med händelsen. Dess konfiguration är valfri. Det krävs om du under dina resor vill hämta ytterligare information från kundprofilen [i](https://docs.adobe.com/content/help/sv-SE/experience-platform/profile/home.html)realtid. Namnutrymmesdefinitionen behövs inte om du bara använder data från ett tredjepartssystem via en anpassad datakälla.

Du kan antingen använda en av de fördefinierade eller skapa en ny med hjälp av tjänsten Identity Namespace. Refer to this [page](https://docs.adobe.com/content/help/sv-SE/experience-platform/identity/home.html).

Om du väljer ett schema som har en primär identitet fylls **[!UICONTROL Key]** - och **[!UICONTROL Namespace]** -fälten i förväg i. Om ingen identitet har definierats väljer vi _identityMap > id_ som primärnyckel. Sedan måste du markera ett namnutrymme och nyckeln fylls i automatiskt (nedanför **[!UICONTROL Namespace]** fältet) med _identityMap > id_.

När du markerar fält taggas primära identitetsfält.

![](../assets/primary-identity.png)


Välj ett namnutrymme i listrutan.

![](../assets/journey17.png)

Endast ett namnutrymme tillåts per resa. Om du använder flera händelser under samma resa måste de använda samma namnutrymme. Läs [den här sidan](../building-journeys/journey.md).
