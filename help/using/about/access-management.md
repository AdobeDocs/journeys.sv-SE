---
title: Åtkomsthantering
description: Läs mer om åtkomsthantering
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: fed6fd8d8ee497ec47727f7297dc72f319fabe27

---


# Åtkomsthantering{#concept_rfj_wpt_52b}

## Om åtkomsthantering {#about-access-management}

Produktprofiler tilldelas till en uppsättning användare som delar samma rättigheter inom organisationen.

På Admin Console kan du tilldela användarna en av följande färdiga produktprofiler:

* **[!UICONTROL Limited Access User]**: användare med skrivskyddad åtkomst till resor och rapporter. Den här produktprofilen innehåller följande rättigheter:
   * Läsa resor
   * Läs rapporter

* **[!UICONTROL Administrators]**: användare med tillgång till administrationsmenyerna med möjlighet att hantera resor, evenemang och rapporter. Den här produktprofilen innehåller följande rättigheter:
   * Hantera och genomför resor
   * Hantera händelser, datakällor och åtgärder
   * Hantera rapporter
   >[!NOTE]
   >
   >**[!UICONTROL Administrators]**är den enda produktprofil som gör det möjligt att skapa, publicera och publicera transaktionsmeddelanden (eller meddelandemallar) i Adobe Campaign Standard. Den här produktprofilen behövs om du använder Adobe Campaign Standard för att skicka meddelanden under dina resor.

* **[!UICONTROL Standard User]**: användare med grundläggande åtkomst, t.ex. resehantering. Den här produktprofilen innehåller följande rättigheter:
   * Hantera och genomför resor
   * Hantera rapporter

Här finns [](../assets/do-not-localize/acs_rights_journeys.pdf) kompatibiliteten mellan rättigheter och Journey Orchestrations olika funktioner.

## Tilldela en produktprofil {#assigning-product-profile}

Produktprofiler hanteras i Admin Console. Mer information finns i dokumentationen [till](https://helpx.adobe.com/enterprise/managing/user-guide.html)Admin Console.

Så här tilldelar du en produktprofil för en användare så att han/hon kan komma åt en guidad resa:

1. Välj i Admin Console **[!UICONTROL Journey orchestration]**.

   ![](../assets/user_management.png)

1. Välj den produktprofil som den nya användaren ska länkas till.

   ![](../assets/user_management_2.png)

1. Klicka **[!UICONTROL Add user]**.

   Du kan också lägga till din nya användare i en användargrupp för att finjustera den delade behörighetsgruppen. Mer information finns på den här [sidan](https://helpx.adobe.com/enterprise/using/user-groups.html).

   ![](../assets/user_management_3.png)

1. Skriv den nya användarens e-postadress och klicka sedan på **[!UICONTROL Save]**.

   ![](../assets/user_management_4.png)

Användaren bör sedan få ett e-postmeddelande som dirigeras om till din instans av resesamordning.