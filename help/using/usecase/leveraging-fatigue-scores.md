---
title: Utnyttja utmattningspoäng
description: Lär dig hur man utnyttjar trötthetspoäng på resor
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 9%

---


# Utnyttja rese-AI {#concept_dsh_1ry_wfb}

Det här användningsexemplet visar hur du kan utnyttja trötthetspoäng för att undvika att överdriva kundresan.

>[!NOTE]
>
>Funktionen för prediktiv trötthet är bara tillgänglig för kunder som använder [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

## Konfigurera händelsen {#section_ptb_ws1_ffb}

Följ stegen som beskrivs i [](../event/about-events.md).

## Konfigurera datakällan {#section_o3n_4yy_wfb}

Utför följande steg för att välja utmattningspoängfält i den inbyggda datakällan:

1. Klicka på fliken på den övre menyn och välj den inbyggda Adobe Experience Platform-datakällan **[!UICONTROL Data Sources]** .

   ![](../assets/journey23.png)

1. Kontrollera att fälten som krävs för ditt användningsfall är markerade.
1. Klicka **[!UICONTROL Add a New Field Group]** och markera **[!UICONTROL Profiles]** modellen och lägg till fälten **[!UICONTROL fatigueLevel]** och **[!UICONTROL fatigueScore]** (under _resanAI > emailScore > utmattning_).

   ![](../assets/journeyuc3_1.png)

1. Klicka på **[!UICONTROL Save]**.

## Bygga resan {#section_uzm_pyy_wfb}

Följ stegen som beskrivs i [](../building-journeys/journey.md)för att skapa, validera och publicera resan.

Vi utnyttjar **[!UICONTROL fatigueLevel]** fältet. Du kan också använda **[!UICONTROL fatigueScore]** fältet.

Utför följande steg för att utnyttja trötthetsnivån under din resa:

1. Lägg till en händelse och ett villkor under resan.

   ![](../assets/journeyuc2_14.png)

1. Välj typen **[!UICONTROL Data Source Condition]** och klicka i fältet **[!UICONTROL Expression]**. 

   ![](../assets/journeyuc3_2.png)

1. Använd den enkla uttrycksredigeraren och leta efter **[!UICONTROL fatigueLevel]** fältet (_ExperiencePlatformDataSource > JourneyAIScores > Profile > travelAI > emailScore > fatigue_), släpp det till höger och skapa följande villkor: &quot;fatigueLevel är lika med &quot;Low&quot;. Klicka på **[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   Det avancerade uttrycket är:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. I villkoret skapar du två andra banor för medelhög och hög utmattningsnivå.

   ![](../assets/journeyuc3_4.png)

1. Nu kan du lägga till olika åtgärder för varje trötthetsnivå.

   ![](../assets/journeyuc3_5.png)
