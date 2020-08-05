---
title: Regelbaserade händelser
description: Läs mer om regelbaserade händelser.
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
source-git-commit: a65a5db5b35291cbc2635f9ae67fd8c8c5284575
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 1%

---


# Regelbaserade händelser{#simplified-events}

Vi har förenklat hur ni konfigurerar Experience Events. Vi introducerar en ny metod som inte kräver att ett eventID används. När du konfigurerar en händelse i Journey Orchestration kan du nu definiera en regelbaserad händelse.

Den här nya händelsetypen genererar inget eventID. Med den enkla uttrycksredigeraren definierar du nu helt enkelt en regel som ska användas av systemet för att identifiera de relevanta händelser som utlöser dina resor. Den här regeln kan baseras på alla fält som är tillgängliga i händelsenyttolasten, till exempel profilens plats eller antalet objekt som läggs till i profilens kundvagn.

Den här nya metoden är för det mesta genomskinlig för användarna. Den enda ändringen är ett nytt fält på skärmen för händelsdefinition.

1. Klicka på **[!UICONTROL Admin]** ikonen i den vänstra menyn och klicka sedan på **[!UICONTROL Events]**. Listan med händelser visas.

   ![](../assets/alpha-event1.png)

1. Klicka **[!UICONTROL Add]** för att skapa en ny händelse. Händelsekonfigurationsfönstret öppnas till höger på skärmen.

   ![](../assets/alpha-event2.png)

1. Ange namnet på händelsen. Du kan också lägga till en beskrivning.

   ![](../assets/alpha-event3.png)

1. In the new **[!UICONTROL Event ID type]** field, select **[!UICONTROL Rule Based]**.

   ![](../assets/alpha-event4.png)

   >[!NOTE]
   >
   >Typen är den befintliga metoden som kräver ett eventID. **[!UICONTROL System Generated]** Se [det här avsnittet](../event/about-events.md).

1. Definiera **[!UICONTROL Schema]** och nyttolast **[!UICONTROL Fields]**. Se [det här avsnittet](../event/defining-the-payload-fields.md).

   ![](../assets/alpha-event5.png)

   >[!NOTE]
   >
   >När du väljer **[!UICONTROL System Generated type]** det här alternativet är endast scheman med typen eventID tillgängliga. När du väljer **[!UICONTROL Rule Based]** typ är alla Experience Event-scheman tillgängliga.

1. Klicka inuti **[!UICONTROL Event ID condition]** fältet. Använd den enkla uttrycksredigeraren för att definiera villkoret som ska användas av systemet för att identifiera de händelser som utlöser din resa.

   ![](../assets/alpha-event6.png)

   I vårt exempel skrev vi ett villkor baserat på profilens stad. Det innebär att när systemet tar emot en händelse som matchar det här villkoret (**[!UICONTROL City]** fält och **[!UICONTROL Paris]** värde) skickas den till Journey Orchestration.

1. Definiera **[!UICONTROL Namespace]** och **[!UICONTROL Key]**. Se [Markera namnutrymmet](../event/selecting-the-namespace.md) och [definiera händelsenyckeln](../event/defining-the-event-key.md).

   ![](../assets/alpha-event7.png)

De andra stegen för händelsekonfiguration och skapande av resa ändras inte.

Händelsen är nu konfigurerad och klar att släppas in på en resa som vilken händelse som helst. Varje gång en händelse som matchar regeln skickas till systemet, skickas den till Journey Orchestration för att utlösa dina resor.

