---
product: adobe campaign
title: Konfigurera datakällan
description: Lär dig hur du konfigurerar datakällan för ett enkelt användningsfall för resan
feature: Resor
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '139'
ht-degree: 7%

---

# Konfigurera datakällan{#concept_ax3_bcy_w2b}

I vårt fall vill vi använda personaliseringsdata för våra meddelanden. Vi måste också kontrollera att personen är en kvinna. Den här informationen lagras i kundprofildatabasen i realtid. Den **tekniska användaren** måste kontrollera att dessa fält är definierade i den inbyggda Adobe Experience Platform-datakällan.

Mer information om konfiguration av datakälla finns på [den här sidan](../datasource/about-data-sources.md).

1. Välj **[!UICONTROL Admin]** i menyrutan. Klicka på **[!UICONTROL Manage]** i **[!UICONTROL Data sources]**-avsnittet.
1. Välj den inbyggda Adobe Experience Platform-datakällan.

   ![](../assets/journey23.png)

1. Kontrollera att följande fält är markerade i fältgrupperna:

   * _person > namn > firstName_
   * _person > namn > efternamn_
   * _person > kön_
   * _personalEmail > address_

1. Klicka på **[!UICONTROL Save]**.

Datakällan är nu konfigurerad och klar att användas under din resa.
