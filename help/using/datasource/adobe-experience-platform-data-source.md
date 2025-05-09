---
product: adobe campaign
title: Datakällan i Adobe Experience Platform
description: Lär dig hur du konfigurerar Adobe Experience Platform datakälla
feature: Journeys
role: User
level: Intermediate
exl-id: 847fa819-2b92-49e5-8a5e-4f3f0acd5e35
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 8%

---

# Datakällan i Adobe Experience Platform {#concept_zrb_nqt_52b}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


Adobe Experience Platform datakälla definierar anslutningen till kundprofiltjänsten i realtid. Den här datakällan är inbyggd och förkonfigurerad. Den kan inte tas bort. Den här datakällan är utformad för att hämta och använda data från kundprofiltjänsten i realtid (kontrollera t.ex. om personen som gjorde en resa är kvinna). Ni kan använda profildata och Experience Events-data. Mer information om kundprofiltjänsten i realtid finns på [sidan](https://experienceleague.adobe.com/docs/experience-platform/profile/home.html?lang=sv).

>[!NOTE]
>
>Du kan hämta de 1 000 senaste upplevelsehändelserna som skapades för mindre än ett år sedan.

För att tillåta anslutningen till kundprofiltjänsten i realtid måste vi använda en nyckel för att identifiera en person och ett namnutrymme som kontextualiserar nyckeln. Därför kan du bara använda den här datakällan om dina resor börjar med en händelse som innehåller en nyckel och ett namnutrymme. Läs [den här sidan](../building-journeys/journey.md).

Du kan redigera den förkonfigurerade fältgruppen med namnet &quot;ProfileFieldGroup&quot;, lägga till nya och ta bort de som inte används i utkast- eller direktresor. Läs [den här sidan](../datasource/field-groups.md).

Här är de viktigaste stegen för att lägga till fältgrupper i den inbyggda datakällan.

1. Välj den inbyggda Adobe Experience Platform-datakällan i listan över datakällor.

   Detta öppnar konfigurationsfönstret för datakällan till höger på skärmen.

   ![](../assets/journey23.png)

1. Klicka på **[!UICONTROL Add a New Field Group]** för att definiera en ny serie med fält som ska hämtas. Läs [den här sidan](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Välj ett schema i listrutan **[!UICONTROL Schema]**. I det här fältet visas profilscheman och Experience Events-scheman som är tillgängliga i Adobe Experience Platform. Schemat skapas inte i [!DNL Journey Orchestration]. Det är gjort i Adobe Experience Platform.
1. Markera de fält som du vill använda.
1. Klicka på **[!UICONTROL Save]**.

När du placerar markören på namnet på en fältgrupp visas två ikoner till höger. De gör att du kan ta bort och duplicera fältgruppen. Observera att ikonen **[!UICONTROL Delete]** bara är tillgänglig om fältgruppen inte används i någon direktresa eller utkastresa (information visas i fältet **[!UICONTROL Used in]**).
