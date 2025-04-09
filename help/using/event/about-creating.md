---
product: adobe campaign
title: Skapa en händelse
description: Lär dig hur du skapar en händelse
feature: Journeys
role: User
level: Intermediate
exl-id: 2ae8854a-c3e7-469d-9f89-25b54bc3e894
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '590'
ht-degree: 47%

---

# Skapa en ny händelse {#section_tbk_5qt_pgb}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


Här följer de viktigaste stegen för att konfigurera en ny händelse:

1. Klicka på fliken **[!UICONTROL Events]** på den övre menyn. Listan med händelser visas. Mer information om gränssnittet finns på [den här sidan](../about/user-interface.md).

   ![](../assets/journey5.png)

1. Klicka på **[!UICONTROL Add]** för att skapa en ny händelse. Händelsekonfigurationsfönstret öppnas till höger på skärmen. Ange ett namn för händelsen. Du kan också lägga till en beskrivning.

   ![](../assets/journey6.png)

   >[!NOTE]
   >
   >Använd inte blanksteg eller specialtecken. Använd maximalt 30 tecken.

1. I fältet **[!UICONTROL Event ID type]** väljer du den händelsetyp som du vill använda.

   ![](../assets/journey6bis.png)

   * **Regelbaserade** händelser: Den här händelsetypen genererar inget eventID. I fältet **Händelse-ID villkor** definierar du bara en regel som ska användas av systemet för att identifiera de relevanta händelser som utlöser dina resor. Den här regeln kan baseras på alla fält som är tillgängliga i händelsenyttolasten, till exempel profilens plats eller antalet objekt som läggs till i profilens kundvagn.

   * **Systemgenererade** händelser: den här typen kräver ett eventID. Detta eventID-fält genereras automatiskt när händelsen skapas och läggs till i nyttolastförhandsvisningen. Det system som skickar händelsen ska inte generera ett ID, det ska skicka det som finns i nyttolastförhandsvisningen. Se [det här avsnittet](../event/previewing-the-payload.md).

   >[!NOTE]
   >
   >Läs mer om händelsetyper i [det här avsnittet](../event/about-events.md).
1. Antalet resor som använder den här händelsen visas i fältet **[!UICONTROL Used in]**. Du kan klicka på ikonen **[!UICONTROL View journeys]** för att visa en lista över resor som använder den här händelsen.
1. Definiera fälten för schemat och nyttolasten. Här väljer du den händelseinformation (kallas vanligtvis nyttolast) som [!DNL Journey Orchestration] förväntas ta emot. Du kan sedan använda den här informationen i din resa. Läs [den här sidan](../event/defining-the-payload-fields.md).
   >[!NOTE]
   >
   >När du väljer typen **[!UICONTROL System Generated]** är endast scheman med typen eventID tillgängliga. När du väljer typen **[!UICONTROL Rule Based]** är alla Experience Event-scheman tillgängliga.

1. För regelbaserade händelser klickar du i fältet **[!UICONTROL Event ID condition]**. Använd den enkla uttrycksredigeraren för att definiera villkoret som ska användas av systemet för att identifiera de händelser som utlöser din resa.
   ![](../assets/alpha-event6.png)

   I vårt exempel skrev vi ett villkor baserat på profilens stad. Det innebär att när systemet tar emot en händelse som matchar det här villkoret (**[!UICONTROL City]** fält och **[!UICONTROL Paris]** värde) skickas den till Journey Orchestration.

   >[!NOTE]
   >
   >Den avancerade uttrycksredigeraren är inte tillgänglig när **[!UICONTROL Event ID condition]** definieras. I den enkla uttrycksredigeraren är inte alla operatorer tillgängliga, de är beroende av datatypen. För en strängtyp av fält kan du till exempel använda &quot;contains&quot; eller &quot;equal to&quot;.

1. Lägg till en namnrymd. Det här steget är valfritt men rekommenderas eftersom du kan lägga till en namnrymd vilket innebär att du kan utnyttja information som lagras i realtidskundprofilen. Denna definierar vilken typ av nyckel händelsen har. Läs [den här sidan](../event/selecting-the-namespace.md).
1. Definiera nyckeln. Välj ett fält från dina fält med nyttolaster eller definiera en formel som identifierar den person som är associerad med händelsen. Den här nyckeln konfigureras automatiskt (men kan fortfarande redigeras) om du väljer en namnrymd. [!DNL Journey Orchestration] väljer den nyckel som ska motsvara namnrymden (om du till exempel väljer en e-postnamnrymd väljs e-postnyckeln). Läs [den här sidan](../event/defining-the-event-key.md).
1. Klicka på **[!UICONTROL Save]**.

   ![](../assets/journey7.png)

   Händelsen är nu konfigurerad och klar att injiceras i en resa. Ytterligare konfigurationssteg krävs för att ta emot händelser. Läs [den här sidan](../event/additional-steps-to-send-events-to-journey-orchestration.md).
