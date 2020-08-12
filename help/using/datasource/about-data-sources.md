---
title: Om datakällor
description: 'Läs om hur du konfigurerar en datakälla '
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 86%

---


# Om datakällor {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Om datakällor"
>abstract="Datakällans konfiguration utförs alltid av en teknisk användare. Med datakällans konfiguration kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i resorna. Dessa kan till exempel vara: villkorsdefinitioner, parameter- och personaliseringsdata i åtgärder, anpassade väntedefinitioner och definitionen av tidszoner."

Med datakällans konfiguration kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i resorna, till exempel:

* [villkorsdefinitioner](../building-journeys/condition-activity.md)
* parameter- och personaliseringsdata i [åtgärder](../action/action.md)
* [anpassade väntedefinitioner](../building-journeys/wait-activity.md#custom)
* [definition av tidszoner](../building-journeys/timezone-management.md)

Den här konfigurationen krävs inte om dina resor endast utnyttjar lokala data som kommer från en händelses nyttolast. Om din resa till exempel består av en händelse som följs av en e-postaktivitet, som bara använder data från händelsen, behöver du inte konfigurera någon datakälla.

Det finns två typer av datakällor:

* Den förkonfigurerade Adobe Experience Platform-datakälla som definierar anslutningen till kundprofiltjänsten i realtid. Detta är en inbyggd datakälla. Se [](../datasource/adobe-experience-platform-data-source.md).
* De externa datakällor som du använder för att definiera en anslutning till externa system. Dessa är de du kan skapa. Se [](../datasource/external-data-sources.md).

För varje datakälla definierar du den information som ska hämtas med fältgrupper. Fältgrupper är uppsättningar med fält som kan hämtas från en datakälla. Se [](../datasource/field-groups.md).

For more information on how to configure an Adobe Experience Platform Data Source and an external data source and how to find and use data in a journey, watch this [tutorial video](https://docs.adobe.com/content/help/sv-SE/journey-orchestration-learn/tutorials/configure-data-sources.html).

Här följer de huvudsakliga konfigurationsstegen för datakällor:

>[!NOTE]
>
>Datakällans konfiguration utförs alltid av en **teknisk användare**.

1. Klicka på fliken **[!UICONTROL Data Sources]** på den övre menyn.

   Listan med datakällor visas. Se [](../about/user-interface.md) för mer information om gränssnittet.

   ![](../assets/journey18.png)

1. Därefter kan du antingen lägga till fältgrupper i den inbyggda datakällan (se [](../datasource/adobe-experience-platform-data-source.md)) eller skapa en ny extern datakälla (se [](../datasource/external-data-sources.md)) och associerade fältgrupper (se [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Klicka på **[!UICONTROL Save]**.

   Datakällan är nu konfigurerad och redo att användas i resorna.
