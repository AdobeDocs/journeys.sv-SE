---
product: adobe campaign
solution: Journey Orchestration
title: Skapa en händelse
description: Lär dig hur du skapar en händelse
feature: Journeys
role: Business Practitioner
level: Intermediate
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '547'
ht-degree: 53%

---


# Skapa en ny händelse {#section_tbk_5qt_pgb}

Här följer de viktigaste stegen för att konfigurera en ny händelse:

1. Klicka på fliken **[!UICONTROL Events]** på den övre menyn. Listan med händelser visas. Mer information om gränssnittet finns på [den här sidan](../about/user-interface.md).

   ![](../assets/journey5.png)

1. Klicka på **[!UICONTROL Add]** för att skapa en ny händelse. Konfigurationsfönstret för händelsen öppnas till höger på skärmen. Ange ett namn på händelsen. Du kan också lägga till en beskrivning.

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >Använd inte blanksteg eller specialtecken. Använd maximalt 30 tecken.

1. Välj händelsetypen som du vill använda i fältet **[!UICONTROL Event ID type]**.

   ![](../assets/journey6bis.png)

   * **Regelbaserade** händelser: den här händelsetypen genererar inget eventID. I fältet **Händelse-ID villkor** definierar du bara en regel som ska användas av systemet för att identifiera de relevanta händelser som utlöser dina resor. Den här regeln kan baseras på alla fält som är tillgängliga i händelsenyttolasten, till exempel profilens plats eller antalet objekt som läggs till i profilens kundvagn.

   * **Systemgenererade** undantag: den här typen kräver ett eventID. Detta eventID-fält genereras automatiskt när händelsen skapas och läggs till i nyttolastförhandsvisningen. Det system som skickar händelsen ska inte generera ett ID, det ska skicka det som finns i nyttolastförhandsvisningen. Se [det här avsnittet](../event/previewing-the-payload.md).
   >[!NOTE]
   >
   >Läs mer om händelsetyper i [det här avsnittet](../event/about-events.md).
1. Antalet resor som använder den här händelsen visas i fältet **[!UICONTROL Used in]**. Du kan klicka på ikonen **[!UICONTROL View journeys]** för att visa en lista över resor som använder den här händelsen.
1. Definiera fälten för schemat och nyttolasten. Här väljer du den händelseinformation (kallas vanligtvis nyttolast) som [!DNL Journey Orchestration] förväntas ta emot. Du kan sedan använda den här informationen i din resa. Läs [den här sidan](../event/defining-the-payload-fields.md).
   >[!NOTE]
   >
   >När du väljer typen **[!UICONTROL System Generated]** är endast scheman som har typen eventID tillgängliga. När du väljer typen **[!UICONTROL Rule Based]** är alla Experience Event-scheman tillgängliga.

1. För regelbaserade händelser klickar du i fältet **[!UICONTROL Event ID condition]**. Använd den enkla uttrycksredigeraren för att definiera villkoret som ska användas av systemet för att identifiera de händelser som utlöser din resa.
   ![](../assets/alpha-event6.png)

   I vårt exempel skrev vi ett villkor baserat på profilens stad. Det innebär att när systemet tar emot en händelse som matchar det här villkoret (**[!UICONTROL City]**-fält och **[!UICONTROL Paris]**-värde) skickas den till Journey Orchestration.

1. Lägg till en namnrymd. Det här steget är valfritt men rekommenderas eftersom du kan lägga till en namnrymd vilket innebär att du kan utnyttja information som lagras i realtidskundprofilen. Denna definierar vilken typ av nyckel händelsen har. Läs [den här sidan](../event/selecting-the-namespace.md).
1. Definiera nyckeln. Välj ett fält från dina fält med nyttolaster eller definiera en formel som identifierar den person som är associerad med händelsen. Den här nyckeln konfigureras automatiskt (men kan fortfarande redigeras) om du väljer en namnrymd. [!DNL Journey Orchestration] väljer den nyckel som ska motsvara namnrymden (om du till exempel väljer en e-postnamnrymd väljs e-postnyckeln). Läs [den här sidan](../event/defining-the-event-key.md).
1. För systemgenererade händelser kan du lägga till ett villkor. Det här steget är valfritt. Med detta kan systemet endast bearbeta händelser som uppfyller villkoret. Villkoret kan endast baseras på information som finns i händelsen. Läs [den här sidan](../event/adding-a-condition.md).
1. Klicka på **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   Händelsen är nu konfigurerad och klar att injiceras i en resa. Ytterligare konfigurationssteg krävs för att ta emot händelser. Läs [den här sidan](../event/additional-steps-to-send-events-to-journey-orchestration.md).
