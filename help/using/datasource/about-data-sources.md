---
product: adobe campaign
solution: Journey Orchestration
title: Om datakällor
description: 'Läs om hur du konfigurerar en datakälla '
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: f73e357d8947997f7f5872efa6a5ef4f51bc63a9
workflow-type: tm+mt
source-wordcount: '348'
ht-degree: 81%

---


# Om datakällor {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id="jo_datasources"
>title="Om datakällor"
>abstract="Med datakällkonfigurationen kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor."

Med datakällans konfiguration kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i resorna, till exempel:

* [villkorsdefinitioner](../building-journeys/condition-activity.md)
* parameter- och personaliseringsdata i [åtgärder](../action/action.md)
* [anpassade väntedefinitioner](../building-journeys/wait-activity.md#custom)
* [definition av tidszoner](../building-journeys/timezone-management.md)

Den här konfigurationen krävs inte om dina resor endast utnyttjar lokala data som kommer från en händelses nyttolast. Om din resa till exempel består av en händelse som följs av en e-postaktivitet, som bara använder data från händelsen, behöver du inte konfigurera någon datakälla.

Det finns två typer av datakällor:

* Den förkonfigurerade datakällan i Adobe Experience Platform som definierar anslutningen till kundprofilen i realtid. Detta är en inbyggd datakälla. Läs [den här sidan](../datasource/adobe-experience-platform-data-source.md).
* De externa datakällor som du använder för att definiera en anslutning till externa system. Dessa är de du kan skapa. Läs [den här sidan](../datasource/external-data-sources.md).

För varje datakälla definierar du den information som ska hämtas med fältgrupper. Fältgrupper är uppsättningar med fält som kan hämtas från en datakälla. Läs [den här sidan](../datasource/field-groups.md).

Titta på den här [självstudievideon](https://docs.adobe.com/content/help/sv-SE/journey-orchestration-learn/tutorials/configure-data-sources.html) för att få mer information om hur du konfigurerar en datakälla i Adobe Experience Platform och en extern datakälla samt hur du hittar och använder data i en resa.

Här följer de huvudsakliga konfigurationsstegen för datakällor:

>[!NOTE]
>
>Datakällans konfiguration utförs alltid av en **teknisk användare**.

1. Klicka på fliken **[!UICONTROL Data Sources]** på den övre menyn.

   Listan med datakällor visas. Mer information om gränssnittet finns på [den här sidan](../about/user-interface.md).

   ![](../assets/journey18.png)

1. Sedan kan du antingen lägga till fältgrupper i den inbyggda datakällan (se [den här sidan](../datasource/adobe-experience-platform-data-source.md)) eller skapa en ny extern datakälla (se [den här sidan](../datasource/external-data-sources.md)) och associerade fältgrupper (se [den här sidan](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Klicka på **[!UICONTROL Save]**.

   Datakällan är nu konfigurerad och redo att användas i resorna.
