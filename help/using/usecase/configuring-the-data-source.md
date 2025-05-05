---
product: adobe campaign
title: Konfigurera datakällan
description: Lär dig hur du konfigurerar datakällan för ett enkelt användningsfall för resan
feature: Journeys
role: User
level: Intermediate
exl-id: 87f63d7d-b7d9-4243-a5ce-8948939f3d93
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '183'
ht-degree: 4%

---

# Konfigurera datakällan{#concept_ax3_bcy_w2b}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


I vårt fall vill vi använda personaliseringsdata för våra meddelanden. Vi måste också kontrollera att personen är en kvinna. Den här informationen lagras i kundprofildatabasen i realtid. Den **tekniska användaren** måste kontrollera att dessa fält har definierats i den inbyggda Adobe Experience Platform-datakällan.

Mer information om konfiguration av datakälla finns på [den här sidan](../datasource/about-data-sources.md).

1. Välj **[!UICONTROL Admin]** i menyrutan. Klicka på **[!UICONTROL Manage]** i avsnittet **[!UICONTROL Data sources]**.
1. Välj den inbyggda Adobe Experience Platform-datakällan.

   ![](../assets/journey23.png)

1. Kontrollera att följande fält är markerade i fältgrupperna:

   * _person > namn > firstName_
   * _person > namn > efternamn_
   * _person > kön_
   * _personalEmail > address_

1. Klicka på **[!UICONTROL Save]**.

Datakällan är nu konfigurerad och klar att användas under din resa.
