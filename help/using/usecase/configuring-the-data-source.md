---
product: adobe campaign
solution: Journey Orchestration
title: Konfigurera datakällan
description: Lär dig hur du konfigurerar datakällan för ett enkelt användningsfall för resan
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 6%

---


# Konfigurera datakällan{#concept_ax3_bcy_w2b}

I vårt fall vill vi använda personaliseringsdata för våra meddelanden. Vi måste också kontrollera att personen är en kvinna. Den här informationen lagras i kundprofildatabasen i realtid. Den **tekniska användaren** måste kontrollera att dessa fält är definierade i den inbyggda Adobe Experience Platform-datakällan.

Mer information om konfiguration av datakälla finns på [den här sidan](../datasource/about-data-sources.md).

1. Klicka på fliken på den övre menyn och välj den inbyggda Adobe Experience Platform-datakällan **[!UICONTROL Data Sources]** .

   ![](../assets/journey23.png)

1. Kontrollera att följande fält är markerade i fältgrupperna:

   * _person > namn > firstName_
   * _person > namn > efternamn_
   * _person > kön_
   * _personalEmail > address_

1. Klicka på **[!UICONTROL Save]**.

Datakällan är nu konfigurerad och klar att användas under din resa.
