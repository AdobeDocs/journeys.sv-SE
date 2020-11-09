---
title: Om händelser
description: Läs om hur du konfigurerar en händelse
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '727'
ht-degree: 98%

---


# Om händelser {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Om händelser"
>abstract="En händelse är länkad till en person. Den är relaterad till en persons beteende (till exempel om en person köpt en produkt, besökt en butik eller lämnat en webbplats) eller något som händer relaterat till en person (en person som till exempel har nått 10 000 lojalitetspoäng). Detta är vad [!DNL Journey Orchestration] läser av i resor för att orkestrera bästa åtgärder."

En händelse är länkad till en person. Den är relaterad till en persons beteende (till exempel om en person köpt en produkt, besökt en butik eller lämnat en webbplats) eller något som händer relaterat till en person (en person som till exempel har nått 10 000 lojalitetspoäng). Detta är vad [!DNL Journey Orchestration] läser av i resor för att orkestrera bästa åtgärder.

Den här konfigurationen är **obligatorisk** eftersom [!DNL Journey Orchestration] är designad för att läsa av händelser och alltid utförs av en **teknisk användare**.

Med händelsekonfigurationen kan du definiera vilken information som [!DNL Journey Orchestration] ska tas emot som händelser. Du kan använda flera händelser (i olika steg på en resa) och flera resor kan använda samma händelse.

Om du redigerar en händelse som används i ett utkast eller en resa i realtid kan du bara ändra namn eller beskrivning eller lägga till fält för nyttolast. Vi begränsar strikt utgåvan av utkast eller resor i realtid för att undvika att resor avbryts.

## Allmän princip {#section_r1f_xqt_pgb}

Händelser är POST API-anrop. Händelser skickas till Adobe Experience Platform via API:er för strömningsinmatning. URL-destinationen för händelser som skickas via API:er för transaktionsmeddelanden kallas för ett &quot;inlet&quot;. Händelsers nyttolast följer XDM-formateringen.

Nyttolasten innehåller information som krävs för att API:er för strömningsinmatning ska fungera (i rubriken) och den information som krävs för att [!DNL Journey Orchestration] ska kunna fungera (händelse-ID och en del av nyttolastens brödtext). Den innehåller även information som ska användas på resor (i brödtexten, till exempel värdet på en övergiven kundvagn). Det finns två lägen för strömningsinmatning – autentiserad och ej autentiserad. Se [den här länken](https://docs.adobe.com/content/help/sv-SE/experience-platform/xdm/api/getting-started.html) för mer information om API:er för strömningsinmatning.

Efter att ha anlänt via API:er för strömningsinmatning flödar händelserna till en intern tjänst som kallas pipeline och sedan i Adobe Experience Platform. Om händelseschemat har tjänstflaggan realtidskundprofil aktiverad och ett datauppsättnings-ID som även har flaggan realtidskundprofil flödar det in i tjänsten realtidskundprofil.

En pipeline filtrerar händelser som har en nyttolast som innehåller händelse-ID:n i [!DNL Journey Orchestration] (se processen för att skapa händelser nedan) som tillhandahålls av [!DNL Journey Orchestration] och finns i händelsens nyttolast. [!DNL Journey Orchestration] läser av dessa händelser och motsvarande resa aktiveras.

## Skapa en ny händelse {#section_tbk_5qt_pgb}

Här följer de viktigaste stegen för att konfigurera en ny händelse:

1. Klicka på fliken **[!UICONTROL Events]** på den övre menyn. Listan med händelser visas. Mer information om gränssnittet finns på [den här sidan](../about/user-interface.md) .

   ![](../assets/journey5.png)

1. Klicka på **[!UICONTROL Add]** för att skapa en ny händelse. Konfigurationsfönstret för händelsen öppnas till höger på skärmen.

   ![](../assets/journey6.png)

1. Ange ett namn på händelsen.

   >[!NOTE]
   >
   >Använd inte blanksteg eller specialtecken. Använd maximalt 30 tecken.

1. Lägg till en beskrivning för händelsen. Det här steget är valfritt.
1. Definiera fälten för schemat och nyttolasten. Här väljer du den händelseinformation (kallas vanligtvis nyttolast) som [!DNL Journey Orchestration] förväntas ta emot. Du kan sedan använda den här informationen i din resa. Läs [den här sidan](../event/defining-the-payload-fields.md).
1. Antalet resor som använder den här händelsen visas i fältet **[!UICONTROL Used in]**. Du kan klicka på ikonen **[!UICONTROL View journeys]** för att visa en lista över resor som använder den här händelsen.
1. Lägg till en namnrymd. Det här steget är valfritt men rekommenderas eftersom du kan lägga till en namnrymd vilket innebär att du kan utnyttja information som lagras i realtidskundprofilen. Denna definierar vilken typ av nyckel händelsen har. Läs [den här sidan](../event/selecting-the-namespace.md).
1. Definiera nyckeln. Välj ett fält från dina fält med nyttolaster eller definiera en formel som identifierar den person som är associerad med händelsen. Den här nyckeln konfigureras automatiskt (men kan fortfarande redigeras) om du väljer en namnrymd. [!DNL Journey Orchestration] väljer den nyckel som ska motsvara namnrymden (om du till exempel väljer en e-postnamnrymd väljs e-postnyckeln). Läs [den här sidan](../event/defining-the-event-key.md).
1. Lägga till ett villkor. Det här steget är valfritt. Med detta kan systemet endast bearbeta händelser som uppfyller villkoret. Villkoret kan endast baseras på information som finns i händelsen. Läs [den här sidan](../event/adding-a-condition.md).
1. Klicka på **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   Händelsen är nu konfigurerad och klar att injiceras i en resa. Ytterligare konfigurationssteg krävs för att ta emot händelser. Läs [den här sidan](../event/additional-steps-to-send-events-to-journey-orchestration.md).
