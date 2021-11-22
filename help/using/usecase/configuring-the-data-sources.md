---
product: adobe campaign
title: Konfigurera datakällorna
description: Lär dig hur du konfigurerar datakällan för resan med avancerad användning
feature: Journeys
role: User
level: Intermediate
exl-id: 2cfa4397-fe8f-44b3-b219-2fd5d3bdd156
source-git-commit: e1ee5a488e9eb6fd8d175a2ab8989c73289ea708
workflow-type: tm+mt
source-wordcount: '440'
ht-degree: 15%

---

# Konfigurera datakällorna {#concept_vml_hdy_w2b}

I vårt fall vill vi använda personaliseringsdata för våra meddelanden. Vi måste också kontrollera om personen är en lojalitetsmedlem och inte har kontaktats under de senaste 24 timmarna. Den här informationen lagras i kundprofildatabasen i realtid. The **teknisk användare** måste konfigurera Adobe Experience Platform datakälla för att hämta dessa fält.

Mer information om konfiguration av datakälla finns i [den här sidan](../datasource/about-data-sources.md).

1. I menyrutan väljer du **[!UICONTROL Admin]**. I **[!UICONTROL Data sources]** avsnitt, klicka **[!UICONTROL Manage]**.
1. Välj den inbyggda Adobe Experience Platform-datakällan.

   ![](../assets/journey23.png)

1. Kontrollera att följande fält är markerade i de förkonfigurerade gruppfälten:

   * _person > namn > firstName_
   * _person > namn > efternamn_
   * _personalEmail > address_

1. Klicka **[!UICONTROL Add a New Field Group]** väljer du en **[!UICONTROL Profiles]** schemat och lägg till **Förmånsmedlem** för vårt tillstånd. The **Förmånsmedlem** fältet är ett anpassat fält och har lagts till i XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Klicka **[!UICONTROL Add a New Field Group]** väljer du en **[!UICONTROL ExperienceEvent]** och välj de fält som krävs för vårt villkor för antalet meddelanden som skickas under en viss period: _tidsstämpel_ för datum och _directMarketing > sending > value_ för antalet skickade meddelanden.

   ![](../assets/journeyuc2_7.png)

1. Klicka på **[!UICONTROL Save]**.

Vi måste också kontrollera om personen har en bokning i hotellbokningen. The **teknisk användare** måste konfigurera en andra datakälla för att hämta det här fältet.

1. Klicka på i listan över datakällor **[!UICONTROL Add]** om du vill lägga till en ny extern datakälla för att definiera anslutningen till ditt bokningssystem.

   ![](../assets/journeyuc2_9.png)

1. Ange ett namn för datakällan och URL:en för den externa tjänsten, till exempel: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >Vi rekommenderar starkt att HTTPS används av säkerhetsskäl.

1. Konfigurera autentiseringen beroende på den externa tjänstens konfiguration: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** eller **[!UICONTROL API key]**. I vårt exempel väljer vi&quot;Grundläggande&quot; som typ och anger användarnamn och lösenord för API-anropet.

   ![](../assets/journeyuc2_10.png)

1. Klicka **[!UICONTROL Add a New Field Group]** för att definiera den information som ska hämtas och API-parametrarna. Det finns till exempel bara en parameter (id), så vi måste skapa en fältgrupp med följande information:

   * **[!UICONTROL Method]**: välj metoden POST eller GET. I vårt fall väljer vi metoden GET.
   * **[!UICONTROL Response Payload]**: klicka inuti **[!UICONTROL Payload]** och klistra in ett exempel på nyttolasten. Kontrollera att fälttyperna är korrekta. Varje gång API:et anropas hämtas alla fält som ingår i exemplets nyttolast. I vårt exempel innehåller nyttolasten bara reservationsstatusen:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: Ange parametern som motsvarar nyckeln som används för att identifiera varje kund,&quot;id&quot; i vårt exempel. Värdet för den här parametern definieras i resan.

   ![](../assets/journeyuc2_11.png)

1. Klicka på **[!UICONTROL Save]**.

   Datakällorna är nu konfigurerade och klara att användas under din resa.
