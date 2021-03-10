---
product: adobe campaign
solution: Journey Orchestration
title: Åtkomsthantering
description: Läs mer om åtkomsthantering
feature: Resor
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '855'
ht-degree: 98%

---


# Åtkomsthantering{#concept_rfj_wpt_52b}

## Om åtkomsthantering {#about-access-management}

Med [!DNL Journey Orchestration] kan du tilldela en uppsättning behörigheter till dina användare för att definiera vilken del av gränssnittet de ska kunna komma åt.

De kan hanteras av administratörer som har åtkomst till Admin Console. Se den här [dokumentationen](https://helpx.adobe.com/se/enterprise/managing/user-guide.html) för mer information om Admin Console.

För att få åtkomst till [!DNL Journey Orchestration] måste användaren vara:

* En del av en **[!UICONTROL product profile]** i [!DNL Journey Orchestration] som är kopplad till [!DNL Journey Orchestration]-behörigheter.
* En del av en **[!UICONTROL product profile]** i [!DNL Adobe Experience Platform]. Det finns inget obligatoriskt tillstånd att inneha. Användaren ska ha **[!UICONTROL profile management]**-behörighet för att skapa och redigera plattformssegment från gränssnittet i [!DNL Journey Orchestration]. Se denna [sida](https://docs.adobe.com/content/help/sv-SE/experience-platform/access-control/home.html#adobe-admin-console) för mer information om detta.

I Admin Console kan du tilldela användarna en av följande färdiga produktprofiler:

* **[!UICONTROL Limited Access User]**: användare med skrivskyddad åtkomst till resor och rapporter. Den här produktprofilen innehåller följande behörigheter:
   * Läsa resor
   * Läsa rapporter

* **[!UICONTROL Administrators]**: användare med tillgång till administrationsmenyerna med möjlighet att hantera resor, händelser och rapporter. Den här produktprofilen innehåller följande behörigheter:
   * Hantera resor
   * Publicera resor
   * Hantera händelser, datakällor och åtgärder
   * Hantera rapporter

   >[!NOTE]
   >
   >**[!UICONTROL Administrators]** är den enda produktprofil som har åtkomst till att skapa, redigera och publicera transaktionsmeddelanden (eller meddelandemallar) i Adobe Campaign Standard. Den här produktprofilen behövs om du använder Adobe Campaign Standard för att skicka meddelanden i dina resor.

* **[!UICONTROL Standard User]**: användare med grundläggande åtkomst, till exempel resehantering. Den här produktprofilen innehåller följande behörigheter:
   * Hantera resor
   * Publicera resor
   * Hantera rapporter
   * Läs händelser, datakällor och åtgärder

Du kan också skapa egna produktprofiler om de färdiga profilerna inte räcker för att hantera användarna.
Användare måste alltid vara länkade till en produktprofil för att du ska kunna tilldela dem specifika inbyggda behörigheter såsom:

* **[!UICONTROL Read journeys]**
* **[!UICONTROL Read reports]**
* **[!UICONTROL Manage events, data sources and actions]**
* **[!UICONTROL Read events, data sources and actions]**
* **[!UICONTROL Manage journeys]**
* **[!UICONTROL Publish journeys]**
* **[!UICONTROL Manage reports]**

Du hittar kompatibiliteten mellan behörigheter och de olika funktionerna i [!DNL Journey Orchestration] nedan.

![](../assets/do-not-localize/journey_permission.png)

## Skapa en produktprofil {#create-product-profile}

Med [!DNL Journey Orchestration] kan du skapa anpassade produktprofiler och tilldela en uppsättning behörigheter och sandlådor till dina användare. Med produktprofiler kan du auktorisera eller neka åtkomst till vissa funktioner eller objekt i gränssnittet.

Se [dokumentationen om Adobe Experience Platform](https://docs.adobe.com/content/help/sv-SE/experience-platform/sandbox/ui/user-guide.html) för mer information om hur du skapar och hanterar sandlådor.

Så här skapar du en produktprofil och tilldelar en uppsättning behörigheter och sandlådor:

1. Välj **[!UICONTROL Journey Orchestration]** i Admin Console. Klicka på **[!UICONTROL New Profile]** på fliken **[!UICONTROL Product profile]**.

   ![](../assets/do-not-localize/user_management_5.png)

1. Lägg till ett **[!UICONTROL Profile Name]** och en **[!UICONTROL Description]** för din nya produktprofil. Avmarkera **[!UICONTROL Same as Profile Name]** och ange ett **[!UICONTROL Display name]** om du vill att din profils **[!UICONTROL Display name]** ska vara annorlunda.

1. I kategorin **[!UICONTROL User Notifications]** väljer du om användare ska meddelas via e-post när de läggs till i eller tas bort från den här produktprofilen.

1. Klicka på **[!UICONTROL Done]** när du är klar. Den nya produktprofilen har skapats.

   ![](../assets/do-not-localize/user_management_1.png)

1. Välj den nya produktprofilen för att börja hantera behörigheter. Lägg till användare i produktprofilen på fliken **[!UICONTROL Users]**. Se denna [sida](../about/access-management.md#assigning-product-profile) för mer information om detta.

1. Utför samma steg som beskrivs ovan för att lägga till **[!UICONTROL Admin]** i din produktprofil.

1. På fliken **[!UICONTROL Permissions]** väljer du en av de två kategorierna **[!UICONTROL Sandbox]** eller **[!UICONTROL Authoring]** för att öppna sidan **[!UICONTROL Edit Permissions]** och lägga till eller ta bort behörigheter för produktprofilen.

   ![](../assets/do-not-localize/user_management_7.png)

1. I behörighetskategorin **[!UICONTROL Sandboxes]** kan du välja vilka sandlådor som ska tilldelas produktprofilen. Klicka på plusikonen (+) i **[!UICONTROL Available Permissions Items]** för att tilldela sandlådor till profilen. Se det här [avsnittet](../about/access-management.md#sandboxes) för mer information om sandlådor.

   ![](../assets/do-not-localize/user_management_8.png)

1. Klicka vid behov på X-ikonen under **[!UICONTROL Included Permission Items]** bredvid respektive behörighet till din produktprofil.

   ![](../assets/do-not-localize/user_management_9.png)

1. Gå till behörighetskategorin **[!UICONTROL Authoring]** och utför samma steg som ovan för att lägga till behörigheter i din produktprofil.
   <br>Se det här [avsnittet](../about/access-management.md#about-access-management) för mer information om behörigheter och kompatibilitet mellan behörigheter och olika funktionaliteter i [!DNL Journey Orchestration].

   ![](../assets/do-not-localize/user_management_10.png)

1. Klicka på **[!UICONTROL Save]** när du är klar.

Din produktprofil har nu skapats och konfigurerats. Användare som är länkade till den här profilen kan nu ansluta till [!DNL Journey Orchestration].

## Tilldela en produktprofil {#assigning-product-profile}

Produktprofiler tilldelas till en uppsättning användare som delar samma behörigheter inom organisationen.
I det här avsnittet finns en lista med alla färdiga produkt profiler med respektive tilldelade behörigheter.

Så här tilldelar du en produktprofil så att en användare får åtkomst till [!DNL Journey Orchestration]:

1. Välj **[!UICONTROL Journey Orchestration]** i Admin Console.

   ![](../assets/do-not-localize/user_management.png)

1. Välj den produktprofil som den nya användaren ska länkas till.

   ![](../assets/do-not-localize/user_management_2.png)

1. Klicka på **[!UICONTROL Add user]**.

   Du kan också lägga till den nya användaren i en användargrupp för att finjustera den delade uppsättningen behörigheter. Se denna [sida](https://helpx.adobe.com/se/enterprise/using/user-groups.html) för mer information om detta.

   ![](../assets/do-not-localize/user_management_3.png)

1. Ange den nya användarens e-postadress och klicka sedan på **[!UICONTROL Save]**.

   ![](../assets/do-not-localize/user_management_4.png)

Användaren får sedan ett e-postmeddelande som omdirigerar denne till din instans i [!DNL Journey Orchestration].

## Använda sandlådor {#sandboxes}

Med [!DNL Journey Orchestration] kan du partitionera instansen i separerade virtuella miljöer som kallas för sandlådor.
Sandlådor tilldelas via produktprofiler i Admin Console. Se det här [avsnittet](../about/access-management.md#create-product-profile) för mer information om hur du tilldelar sandlådor.

[!DNL Journey Orchestration] speglar sandlådorna i Adobe Experience Platform som har skapats för en viss organisation.
Sandlådorna i Adobe Experience Platform kan skapas eller återställas från din instans i Adobe Experience Platform. Se [användarhandboken om sandlådor](https://docs.adobe.com/content/help/en/experience-platform/sandbox/ui/user-guide.html) för detaljerade anvisningar.

Du hittar kontrollen för att välja sandlåda längst upp till vänster på skärmen. Klicka på den för närvarande aktiva sandlådan i väljaren för att växla från en sandlåda till en annan och välj sedan en annan sandlåda på rullgardinsmenyn.
