---
product: adobe campaign
title: Utnyttja utmattningspoäng
description: Lär dig hur man utnyttjar trötthetspoäng på resor
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '249'
ht-degree: 9%

---


# Utnyttja rese-AI {#concept_dsh_1ry_wfb}

Det här användningsexemplet visar hur du kan utnyttja trötthetspoäng för att undvika att överdriva kundresan.

>[!NOTE]
>
>Funktionen för prediktiv trötthet är bara tillgänglig för kunder som använder [Adobe Experience Platform Data Connector](https://experienceleague.adobe.com/docs/campaign-standard/using/integrating-with-adobe-cloud/adobe-experience-platform/data-connector/aep-about-data-connector.html).

## Konfigurera händelsen {#section_ptb_ws1_ffb}

Följ stegen som beskrivs i [den här sidan](../event/about-events.md).

## Konfigurera datakällan {#section_o3n_4yy_wfb}

Utför följande steg för att välja utmattningspoängfält i den inbyggda datakällan:

1. I menyrutan väljer du **[!UICONTROL Admin]**. I **[!UICONTROL Data sources]** avsnitt, klicka **[!UICONTROL Manage]**.
1. Välj den inbyggda Adobe Experience Platform-datakällan.

   ![](../assets/journey23.png)

1. Kontrollera att fälten som krävs för ditt användningsfall är markerade.
1. Klicka **[!UICONTROL Add a New Field Group]** väljer du **[!UICONTROL Profiles]** modellera och lägga till **[!UICONTROL fatigueLevel]** och **[!UICONTROL fatigueScore]** fält (under _resaAI > emailScore > utmattning_).

   ![](../assets/journeyuc3_1.png)

1. Klicka på **[!UICONTROL Save]**.

## Bygga resan {#section_uzm_pyy_wfb}

Följ stegen som beskrivs i [den här sidan](../building-journeys/journey.md).

Vi använder **[!UICONTROL fatigueLevel]** fält. Du kan också använda **[!UICONTROL fatigueScore]** fält.

Utför följande steg för att utnyttja trötthetsnivån under din resa:

1. Lägg till en händelse och ett villkor under resan.

   ![](../assets/journeyuc2_14.png)

1. Välj typen **[!UICONTROL Data Source Condition]** och klicka i fältet **[!UICONTROL Expression]**. 

   ![](../assets/journeyuc3_2.png)

1. Använd den enkla uttrycksredigeraren för att leta efter **[!UICONTROL fatigueLevel]** fält (_ExperiencePlatformDataSource > JourneyAIScores > Profile > travelAI > emailScore > utmattning_), släpp det till höger och skapa följande villkor: &quot;fatigueLevel är lika med &quot;Low&quot;. Klicka på **[!UICONTROL Ok]**.

   ![](../assets/journeyuc3_3.png)

   Det avancerade uttrycket är:

   ```
   #{ExperiencePlatformDataSource.JourneyAIScores.Profile.journeyAI.emailScore.fatigue.fatigueLevel} == "low"
   ```

1. I villkoret skapar du två andra banor för medelhög och hög utmattningsnivå.

   ![](../assets/journeyuc3_4.png)

1. Nu kan du lägga till olika åtgärder för varje trötthetsnivå.

   ![](../assets/journeyuc3_5.png)
