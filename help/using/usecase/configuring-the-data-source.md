---
title: Konfigurera datakällan
description: Lär dig hur du konfigurerar datakällan för ett enkelt användningsfall för resan
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
source-wordcount: '135'
ht-degree: 0%

---


# Konfigurera datakällan{#concept_ax3_bcy_w2b}

I vårt fall vill vi använda personaliseringsdata för våra meddelanden. Vi måste också kontrollera att personen är en kvinna. Den här informationen lagras i kundprofildatabasen i realtid. Den **tekniska användaren** måste kontrollera att dessa fält är definierade i den inbyggda Adobe Experience Platform-datakällan.

Mer information om konfiguration av datakälla finns i [](../datasource/about-data-sources.md).

1. Klicka på fliken på den översta menyn och välj den inbyggda Adobe Experience Platform-datakällan. **[!UICONTROL Data Sources]**

   ![](../assets/journey23.png)

1. Kontrollera att följande fält är markerade i fältgrupperna:

   * _person > namn > firstName_
   * _person > namn > efternamn_
   * _person > kön_
   * _personalEmail > address_

1. Klicka på **[!UICONTROL Save]**.

Datakällan är nu konfigurerad och klar att användas under din resa.
