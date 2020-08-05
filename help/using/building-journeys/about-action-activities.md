---
title: Om funktionsmakron
description: Läs mer om åtgärdsaktiviteter
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
source-git-commit: a65a5db5b35291cbc2635f9ae67fd8c8c5284575
workflow-type: tm+mt
source-wordcount: '166'
ht-degree: 4%

---


# Om funktionsmakron {#concept_hbj_hrt_52b}

På paletten, till vänster på skärmen, under **[!UICONTROL Events]** och **[!UICONTROL Orchestration]** hittar du **[!UICONTROL Actions]** kategorin.

![](../assets/journey58.png)

Dessa aktiviteter representerar olika tillgängliga kommunikationskanaler. Du kan kombinera dem för att skapa ett flerkanalsscenario.

Om du har Adobe Campaign Standard finns följande färdiga åtgärdsaktiviteter: **[!UICONTROL Email]**, **[!UICONTROL Push]** och **[!UICONTROL SMS]**. Se [](../building-journeys/using-adobe-campaign-actions.md).

Om du har konfigurerat anpassade åtgärder visas de också här (se [](../building-journeys/using-custom-actions.md)).

När du släpper en funktionsmakroaktivitet på arbetsytan kan du definiera en **[!UICONTROL Label]**. På så sätt kan du lägga till ett suffix till åtgärdsnamnet som ska visas under aktiviteten på arbetsytan. Detta är användbart om du använder samma åtgärd flera gånger under resan och vill identifiera dem enklare. Rapporterna blir också enklare att läsa. Du kan också lägga till ett valfritt **[!UICONTROL Description]**.

![](../assets/journey59bis.png)

När ett fel inträffar i en åtgärd eller ett villkor upphör kundens resa. Det enda sättet att få det att fortsätta är att markera rutan **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Se [](../building-journeys/using-the-journey-designer.md#paths).
