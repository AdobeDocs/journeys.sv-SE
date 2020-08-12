---
title: Om den avancerade uttrycksredigeraren
description: Läs mer om hur du skapar avancerade uttryck
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
source-git-commit: 1ccf020a882c1d6d9bd00f2e9f5d6b2aee6f7829
workflow-type: tm+mt
source-wordcount: '499'
ht-degree: 100%

---


# Om den avancerade uttrycksredigeraren {#concept_uyj_trt_52b}

Med den avancerade uttrycksredigeraren kan du skapa avancerade uttryck på olika skärmar i gränssnittet. Ett exempel är när du definierar ett villkor för en datakälla.
Den är också tillgänglig varje gång du behöver definiera åtgärdsparametrar som kräver specifika dataändringar. Du kan utnyttja data från händelser eller ytterligare information som hämtats från datakällan. I en resa är den lista med händelsefält som visas sammanhangsberoende och varierar beroende på vilka händelser som läggs till i resan.

Den avancerade uttrycksredigeraren har en uppsättning inbyggda funktioner och operatorer som du använder för att manipulera värden och definiera ett uttryck som passar dina behov. Med den avancerade uttrycksredigeraren kan du även definiera värden för den externa datakällans parameter samt ändra kartläggningsfält och samlingar, till exempel upplevelsehändelser.

![](../assets/journey65.png)

_Gränssnittet för den avancerade uttrycksredigeraren_

Den avancerade uttrycksredigeraren kan användas till att:

* skapa [avancerade villkor](../building-journeys/condition-activity.md#about_condition) för datakällor och händelseinformation
* definiera anpassade [vänteaktiviteter](../building-journeys/wait-activity.md#custom)
* definiera kartläggning av åtgärdsparametrar

När det är möjligt kan du växla mellan de två lägena med hjälp av knappen **[!UICONTROL Advanced mode]**/**[!UICONTROL Simple mode]** . Det enkla läget beskrivs [här](../building-journeys/condition-activity.md#about_condition).

>[!NOTE]
>
>Villkor kan definieras i den enkla eller avancerade uttrycksredigeraren. De returnerar alltid en boolesk typ.
>
>Åtgärdsparametrar kan definieras genom fältval eller via den avancerade uttrycksredigeraren. De returnerar en viss datatyp enligt sina uttryck.

## Komma åt den avancerade uttrycksredigeraren {#section_fdz_4nj_cjb}

Du kan komma åt den avancerade uttrycksredigeraren på olika sätt.

* När du skapar ett villkor för datakällan kan du klicka på **[!UICONTROL Advanced mode]** för att komma åt den avancerade redigeraren.

   ![](../assets/journeyuc2_33.png)

* När du skapar en anpassad timer visas den avancerade redigeraren direkt.
* Klicka på **[!UICONTROL Advanced mode]** när du kartlägger en åtgärdsparameter.

## Lära känna gränssnittet{#section_otq_tnj_cjb}

Med den här skärmen kan du ange ett uttryck manuellt.

![](../assets/journey70.png)

Till vänster på skärmen visas tillgängliga fält och funktioner:

* **[!UICONTROL Events]**: välj ett av fälten som har tagits emot från den inkommande händelsen. Listan med händelsefält som visas är sammanhangsberoende och varierar beroende på vilka händelser som läggs till i resan.
* **[!UICONTROL Data Sources]**: välj i listan bland tillgängliga fält från datakällornas fältgrupper.
* **[!UICONTROL Functions]**: välj i listan bland inbyggda funktioner som du använder för att utföra komplex filtrering. Funktionerna är organiserade per kategori.

![](../assets/journey65.png)

En mekanism för automatisk komplettering visar sammanhangsberoende förslag.

![](../assets/journey68.png)

En mekanism för syntaxvalidering kontrollerar kodens integritet. Fel visas överst på redigeraren.

![](../assets/journey69.png)

**Behovet av parametrar när du skapar villkor med den avancerade uttrycksredigeraren**

Om du väljer ett fält från en extern datakälla som kräver att en parameter anropas (se [](../datasource/external-data-sources.md). I en väderrelaterad datakälla används till exempel parametern &quot;city&quot; ofta. Därför måste du välja var du vill hämta den här parametern &quot;city&quot;. Funktioner kan även tillämpas på parametrar om man vill utföra formateringsändringar eller sammansättningar.

![](../assets/journeyuc2_19.png)

För mer komplicerade användningsfall kan du definiera parametrarnas värden med nyckelordet &quot;params&quot; för att inkludera dem från datakällan i huvuduttrycket. Läs [den här sidan](../expression/field-references.md).
