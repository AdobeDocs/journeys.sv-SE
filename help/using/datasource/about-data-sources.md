---
title: Om datakällor
description: 'Lär dig konfigurera en datakälla '
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
source-git-commit: 690f8c1732c7d54c234e9ba633a2cf014492f423

---


# Om datakällor {#concept_s1s_dqt_52b}

>[!CONTEXTUALHELP]
>id=&quot;jo_datasources&quot;
>title=&quot;Om datakällor&quot;
>abstract=&quot;Datakällans konfiguration utförs alltid av en teknisk användare. Med datakällkonfigurationen kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor, till exempel: villkorsdefinition, parameter- och personaliseringsdata i funktionsmakron, anpassad väntedefinition, anpassad tidszonsdefinition.&quot;

Med datakällkonfigurationen kan du definiera en anslutning till ett system för att hämta ytterligare information som ska användas i dina resor, till exempel:

* [villkorsdefinition](../building-journeys/condition-activity.md)
* parameter- och personaliseringsdata i [funktionsmakron](../action/action.md)
* [egen väntedefinition](../building-journeys/wait-activity.md#custom)
* [anpassad tidszonsdefinition](../building-journeys/timezone-management.md)

Den här konfigurationen krävs inte om dina resor endast utnyttjar lokala data som kommer från en händelsenyttolast. Om din resa till exempel består av en händelse som följs av en e-postaktivitet som bara använder data från händelsen behöver du inte konfigurera någon datakälla.

Det finns två typer av datakällor:

* Den förkonfigurerade Experience Platform-datakälla som definierar anslutningen till kundprofiltjänsten i realtid. Detta är en inbyggd datakälla. Se [](../datasource/adobe-experience-platform-data-source.md).
* De externa datakällor som gör att du kan definiera en anslutning till externa system. Det här är de du kan skapa. Se [](../datasource/external-data-sources.md).

För varje datakälla definierar du den information som ska hämtas med fältgrupper. Fältgrupper är uppsättningar med fält som kan hämtas från en datakälla. Se [](../datasource/field-groups.md).

Titta på den här [videon](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/configure-data-sources.html)om du vill ha mer information om hur du konfigurerar en Experience Platform-datakälla och en extern datakälla samt hur du hittar och använder data under en resa.

Här följer de huvudsakliga konfigurationsstegen för datakällor:

>[!NOTE]
>
>Datakällans konfiguration utförs alltid av en **teknisk användare**.

1. Klicka på **[!UICONTROL Data Sources]** fliken i den övre menyn.

   Listan med datakällor visas. Mer information om gränssnittet finns [](../about/user-interface.md) i.

   ![](../assets/journey18.png)

1. Sedan kan du antingen lägga till fältgrupper i den inbyggda datakällan (se [](../datasource/adobe-experience-platform-data-source.md)) eller skapa en ny extern datakälla (se [](../datasource/external-data-sources.md)) och associerade fältgrupper (se [](../datasource/field-groups.md)).

   ![](../assets/journey23.png)

1. Klicka **[!UICONTROL Save]**.

   Datakällan är nu konfigurerad och klar att användas på dina resor.
