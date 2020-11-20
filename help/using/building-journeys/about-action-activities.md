---
product: adobe campaign
solution: Journey Orchestration
title: Om instruktionsaktiviteter
description: Läs mer om åtgärdsaktiviteter
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '173'
ht-degree: 28%

---


# Om instruktionsaktiviteter {#concept_hbj_hrt_52b}

På paletten, till vänster på skärmen, under **[!UICONTROL Events]** och **[!UICONTROL Orchestration]** hittar du **[!UICONTROL Actions]** kategorin.

![](../assets/journey58.png)

Dessa aktiviteter representerar olika tillgängliga kommunikationskanaler. Du kan kombinera dem för att skapa ett flerkanalsscenario.

Om du har Adobe Campaign Standard finns följande färdiga åtgärdsaktiviteter: **[!UICONTROL Email]**, **[!UICONTROL Push]** och **[!UICONTROL SMS]**. Se [den här sidan](../building-journeys/using-adobe-campaign-actions.md).

Om du har konfigurerat anpassade åtgärder visas de också här (se [den här sidan](../building-journeys/using-custom-actions.md)).

När du släpper en funktionsmakroaktivitet på arbetsytan kan du definiera en **[!UICONTROL Label]**. På så sätt kan du lägga till ett suffix till åtgärdsnamnet som ska visas under aktiviteten på arbetsytan. Detta är användbart om du använder samma åtgärd flera gånger under resan och vill identifiera dem enklare. Rapporterna blir också enklare att läsa. Du kan också lägga till ett valfritt **[!UICONTROL Description]**.

![](../assets/journey59bis.png)

När ett fel inträffar i en åtgärd eller ett villkor upphör en individs resa. Det enda sättet att få den att fortsätta är att markera rutan **[!UICONTROL Add an alternative path in case of a timeout or an error]**. Se [det här avsnittet](../building-journeys/using-the-journey-designer.md#paths).
