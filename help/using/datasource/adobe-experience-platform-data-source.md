---
title: 'Datakälla för Adobe Experience Platform '
description: 'Lär dig hur du konfigurerar datakällan för Adobe Experience Platform '
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
source-git-commit: 7e69b19f2b7099e5c015dd1052a58728cf143ffa

---


# Datakälla för Adobe Experience Platform {#concept_zrb_nqt_52b}

Experience Platform-datakällan definierar anslutningen till kundprofiltjänsten i realtid. Den här datakällan är inbyggd och förkonfigurerad. Den kan inte tas bort. Den här datakällan är utformad för att hämta och använda data från kundprofiltjänsten i realtid (kontrollera t.ex. om personen som gjorde en resa är kvinna). Ni kan använda profildata och Experience Events-data. Mer information om kundprofiltjänsten i realtid finns på den här [sidan](https://www.adobe.io/apis/cloudplatform/dataservices/profile-identity-segmentation/profile-identity-segmentation-services.html#!api-specification/markdown/narrative/technical_overview/unified_profile_architectural_overview/unified_profile_architectural_overview.md).

>[!NOTE]
>
>Du kan hämta de 1 000 senaste upplevelsehändelserna som skapades för mindre än ett år sedan.

För att tillåta anslutningen till kundprofiltjänsten i realtid måste vi använda en nyckel för att identifiera en person och ett namnutrymme som kontextualiserar nyckeln. Därför kan du bara använda den här datakällan om dina resor börjar med en händelse som innehåller en nyckel och ett namnutrymme. Se [](../building-journeys/journey.md).

Du kan redigera den förkonfigurerade fältgruppen med namnet &quot;ProfileFieldGroup&quot;, lägga till nya och ta bort de som inte används i utkast- eller direktresor. Se [](../datasource/field-groups.md).

Här är de viktigaste stegen för att lägga till fältgrupper i den inbyggda datakällan.

1. Välj den inbyggda Experience Platform-datakällan i listan över datakällor.

   Då öppnas konfigurationsfönstret för datakällan till höger på skärmen.

   ![](../assets/journey23.png)

1. Klicka **[!UICONTROL Add a New Field Group]**för att definiera en ny serie fält som ska hämtas. Se[](../datasource/field-groups.md).

   ![](../assets/journey24.png)

1. Välj ett schema i **[!UICONTROL Schema]**listrutan. I det här fältet visas profilscheman och Experience Events-scheman som är tillgängliga i plattformen. Scheman skapas inte i Resesamordning. Den utförs i dataplattformen.
1. Markera de fält som du vill använda.
1. Definiera cachens varaktighet.
1. Klicka på **[!UICONTROL Save]**.

När du placerar markören på namnet på en fältgrupp visas två ikoner till höger. De gör att du kan ta bort och duplicera fältgruppen. Observera att **[!UICONTROL Delete]**ikonen bara är tillgänglig om fältgruppen inte används i någon live- eller utkastresa (information visas i**[!UICONTROL Used in]** fältet).
