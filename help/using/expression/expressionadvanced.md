---
title: Om den avancerade uttrycksredigeraren
description: Lär dig hur du skapar avancerade uttryck
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
ht-degree: 0%

---


# Om den avancerade uttrycksredigeraren {#concept_uyj_trt_52b}

Med den avancerade uttrycksredigeraren kan du skapa avancerade uttryck på olika skärmar i gränssnittet, till exempel när du definierar ett villkor för en datakälla.
Det är också tillgängligt varje gång du behöver definiera åtgärdsparametrar som kräver specifika dataändringar. Du kan utnyttja data från händelser eller ytterligare information som hämtats från datakällan. Under en resa är den visade listan med händelsefält sammanhangsberoende och varierar beroende på vilka händelser som läggs till under resan.

Den avancerade uttrycksredigeraren har en uppsättning inbyggda funktioner och operatorer som du kan använda för att ändra värden och definiera ett uttryck som passar just dina behov. Med den avancerade uttrycksredigeraren kan du också definiera värden för den externa datakällparametern, ändra mappningsfält och samlingar, till exempel upplevelsehändelser.

![](../assets/journey65.png)

_Det avancerade gränssnittet för uttrycksredigeraren_

Den avancerade uttrycksredigeraren kan användas för att:

* skapa [avancerade villkor](../building-journeys/condition-activity.md#about_condition) för datakällor och händelseinformation
* definiera anpassade [vänteaktiviteter](../building-journeys/wait-activity.md#custom)
* definiera åtgärdsparametermappning

När det är möjligt kan du växla mellan de två lägena med hjälp av **[!UICONTROL Advanced mode]** / **[!UICONTROL Simple mode]** . Det enkla läget beskrivs [här](../building-journeys/condition-activity.md#about_condition).

>[!NOTE]
>
>Villkoren kan definieras i den enkla eller avancerade uttrycksredigeraren. De returnerar alltid en boolesk typ.
>
>Åtgärdsparametrar kan definieras genom att välja fält eller via den avancerade uttrycksredigeraren. De returnerar en viss datatyp enligt deras uttryck.

## Åtkomst till den avancerade uttrycksredigeraren {#section_fdz_4nj_cjb}

Du kan komma åt den avancerade uttrycksredigeraren på olika sätt:

* När du skapar ett datakällvillkor kan du komma åt den avancerade redigeraren genom att klicka på **[!UICONTROL Advanced mode]**.

   ![](../assets/journeyuc2_33.png)

* När du skapar en anpassad timer visas den avancerade redigeraren direkt.
* När du mappar åtgärdsparameter klickar du på **[!UICONTROL Advanced mode]**.

## Upptäcka gränssnittet{#section_otq_tnj_cjb}

På den här skärmen kan du skriva ditt uttryck manuellt.

![](../assets/journey70.png)

Till vänster på skärmen visas tillgängliga fält och funktioner:

* **[!UICONTROL Events]**: välj ett av fälten som tagits emot från den inkommande händelsen. Den visade listan med händelsefält är sammanhangsberoende och varierar beroende på vilka händelser som läggs till under resan.
* **[!UICONTROL Data Sources]**: Välj i listan över fält som är tillgängliga från fältgrupperna i datakällorna.
* **[!UICONTROL Functions]**: välj i en lista över inbyggda funktioner som gör att du kan utföra komplex filtrering. Funktionerna är ordnade efter kategorier.

![](../assets/journey65.png)

En mekanism för automatisk komplettering visar sammanhangsberoende förslag.

![](../assets/journey68.png)

En syntaxvalideringsmekanism kontrollerar kodens integritet. Fel visas ovanpå redigeraren.

![](../assets/journey69.png)

**Behovet av parametrar när du skapar villkor med den avancerade uttrycksredigeraren**

Om du väljer ett fält från en extern datakälla som kräver att en parameter anropas (se [](../datasource/external-data-sources.md). I en väderrelaterad datakälla kommer till exempel parametern&quot;city&quot; att användas ofta. Därför måste du välja var du vill få den här parametern city. Funktioner kan också användas för parametrar för att utföra formatändringar eller sammanfogningar.

![](../assets/journeyuc2_19.png)

Om du vill ta med parametrarna för datakällan i huvuduttrycket kan du definiera deras värden med nyckelordet &quot;params&quot; för mer komplicerade användningsområden. Se [den här sidan](../expression/field-references.md).
