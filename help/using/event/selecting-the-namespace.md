---
title: Markera namnutrymmet
description: Lär dig hur du väljer namnutrymmet
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
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# Markera namnutrymmet {#concept_ckb_3qt_52b}

Med namnutrymmet kan du definiera vilken typ av nyckel som används för att identifiera den person som är associerad med händelsen. Dess konfiguration är valfri. Det krävs om du under dina resor vill hämta ytterligare information från kundprofilen [i](https://docs.adobe.com/content/help/en/experience-platform/profile/home.html)realtid. Namnutrymmesdefinitionen behövs inte om du bara använder data från ett tredjepartssystem via en anpassad datakälla.

Du kan antingen använda en av de fördefinierade eller skapa en ny med hjälp av tjänsten Identity Namespace. Se den här [sidan](https://docs.adobe.com/content/help/en/experience-platform/identity/home.html).

Om du väljer ett schema som har en primär identitet fylls **[!UICONTROL Key]** - och **[!UICONTROL Namespace]** -fälten i förväg i. Om ingen identitet har definierats väljer vi _identityMap > id_ som primärnyckel. Sedan måste du markera ett namnutrymme och nyckeln fylls i automatiskt (nedanför **[!UICONTROL Namespace]** fältet) med _identityMap > id_.

När du markerar fält taggas primära identitetsfält.

![](../assets/primary-identity.png)


Välj ett namnutrymme i listrutan.

![](../assets/journey17.png)

Endast ett namnutrymme tillåts per resa. Om du använder flera händelser under samma resa måste de använda samma namnutrymme. Se [](../building-journeys/journey.md).
