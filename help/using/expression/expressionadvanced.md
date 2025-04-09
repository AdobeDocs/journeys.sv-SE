---
product: adobe campaign
title: Om den avancerade uttrycksredigeraren
description: Läs mer om hur du skapar avancerade uttryck
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: f6f0004d-8a33-4671-9c16-e56edfe2a45e
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '595'
ht-degree: 71%

---

# Om den avancerade uttrycksredigeraren {#concept_uyj_trt_52b}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


Använd den avancerade uttrycksredigeraren för att skapa avancerade uttryck på olika skärmar i gränssnittet. Du kan till exempel skapa uttryck när du konfigurerar och använder resor och när du definierar ett datakällsvillkor.
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

## Åtkomst till den avancerade uttrycksredigeraren {#section_fdz_4nj_cjb}

Du kan komma åt den avancerade uttrycksredigeraren på olika sätt.

* När du skapar ett villkor för datakällan kan du klicka på **[!UICONTROL Advanced mode]** för att komma åt den avancerade redigeraren.

  ![](../assets/journeyuc2_33.png)

* När du skapar en anpassad timer visas den avancerade redigeraren direkt.
* Klicka på **[!UICONTROL Advanced mode]** när du kartlägger en åtgärdsparameter.

## Lära känna gränssnittet{#section_otq_tnj_cjb}

Med den här skärmen kan du ange ett uttryck manuellt.

![](../assets/journey70.png)

Till vänster på skärmen visas tillgängliga fält och funktioner:

* **[!UICONTROL Events]**: välj ett av fälten som har tagits emot från den inkommande händelsen. Den visade listan med händelsefält är sammanhangsberoende och varierar beroende på vilka händelser som läggs till under resan. [Läs mer](../event/about-events.md)
* **[!UICONTROL Segments]**: Om du har släppt en **[!UICONTROL Segment qualification]**-händelse väljer du det segment som du vill använda i uttrycket. [Läs mer](../segment/using-a-segment.md)
* **[!UICONTROL Data Sources]**: välj i listan över fält som är tillgängliga från fältgrupperna i datakällorna. [Läs mer](../datasource/about-data-sources.md)
* **[!UICONTROL Journey properties]**: I det här avsnittet grupperas de tekniska fält som är relaterade till resan för en viss profil om. [Läs mer](../expression/journey-properties.md)
* **[!UICONTROL Functions]**: välj i listan bland inbyggda funktioner som du använder för att utföra komplex filtrering. Funktionerna är ordnade efter kategorier. [Läs mer](../expression/functions.md)

![](../assets/journey65.png)

En mekanism för automatisk komplettering visar sammanhangsberoende förslag.

![](../assets/journey68.png)

En mekanism för syntaxvalidering kontrollerar kodens integritet. Fel visas överst på redigeraren.

![](../assets/journey69.png)

**Behovet av parametrar när du skapar villkor med den avancerade uttrycksredigeraren**

Om du väljer ett fält från en extern datakälla som kräver att en parameter anropas (se [den här sidan](../datasource/external-data-sources.md)). I en väderrelaterad datakälla används till exempel parametern &quot;city&quot; ofta. Därför måste du välja var du vill hämta den här parametern &quot;city&quot;. Funktioner kan även tillämpas på parametrar om man vill utföra formateringsändringar eller sammansättningar.

![](../assets/journeyuc2_19.png)

För mer komplicerade användningsfall kan du definiera parametrarnas värden med nyckelordet &quot;params&quot; för att inkludera dem från datakällan i huvuduttrycket. Läs [den här sidan](../expression/field-references.md).
