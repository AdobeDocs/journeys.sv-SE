---
product: adobe campaign
solution: Journey Orchestration
title: Konfigurera datakällorna
description: Lär dig hur du konfigurerar datakällan för resan med avancerad användning
feature: Resor
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '463'
ht-degree: 14%

---


# Konfigurera datakällorna {#concept_vml_hdy_w2b}

I vårt fall vill vi använda personaliseringsdata för våra meddelanden. Vi måste också kontrollera om personen är en lojalitetsmedlem och inte har kontaktats under de senaste 24 timmarna. Den här informationen lagras i kundprofildatabasen i realtid. Den **tekniska användaren** måste konfigurera Adobe Experience Platform-datakällan för att hämta fälten.

Mer information om konfiguration av datakälla finns på [den här sidan](../datasource/about-data-sources.md).

1. Klicka på fliken **[!UICONTROL Data Sources]** på den översta menyn och välj den inbyggda Adobe Experience Platform-datakällan.

   ![](../assets/journey23.png)

1. Kontrollera att följande fält är markerade i de förkonfigurerade gruppfälten:

   * _person > namn > firstName_
   * _person > namn > efternamn_
   * _personalEmail > address_

1. Klicka på **[!UICONTROL Add a New Field Group]**, välj ett **[!UICONTROL Profiles]**-schema och lägg till fältet **Lojalitetsmedlem** för villkoret. Fältet **Förmånsmedlem** är ett anpassat fält och har lagts till i XDM: &quot;_customer > marlton > loyaltyMember&quot;

   ![](../assets/journeyuc2_6.png)

1. Klicka på **[!UICONTROL Add a New Field Group]**, välj ett **[!UICONTROL ExperienceEvent]**-schema och välj de fält som behövs för villkoret för antalet meddelanden som skickas under en given period: _tidsstämpel_ för datumet och _directMarketing > skickar > värde_ för antalet skickade meddelanden.

   ![](../assets/journeyuc2_7.png)

1. Klicka på **[!UICONTROL Save]**.

Vi måste också kontrollera om personen har en bokning i hotellbokningen. Den tekniska användaren **måste konfigurera en andra datakälla för att hämta det här fältet.**

1. Klicka på **[!UICONTROL Add]** i listan över datakällor för att lägga till en ny extern datakälla för att definiera anslutningen till ditt bokningssystem.

   ![](../assets/journeyuc2_9.png)

1. Ange ett namn för datakällan och URL:en för den externa tjänsten, till exempel: _https://marlton.com/reservation_

   >[!CAUTION]
   >
   >Vi rekommenderar starkt att HTTPS används av säkerhetsskäl.

1. Konfigurera autentiseringen beroende på den externa tjänstens konfiguration: **[!UICONTROL No authentication]**, **[!UICONTROL Basic]**, **[!UICONTROL Custom]** eller **[!UICONTROL API key]**. I vårt exempel väljer vi&quot;Grundläggande&quot; som typ och anger användarnamn och lösenord för API-anropet.

   ![](../assets/journeyuc2_10.png)

1. Klicka på **[!UICONTROL Add a New Field Group]** för att definiera informationen som ska hämtas och API-parametrarna. Det finns till exempel bara en parameter (id), så vi måste skapa en fältgrupp med följande information:

   * **[!UICONTROL Method]**: välj metoden POST eller GET. I vårt fall väljer vi metoden GET.
   * **[!UICONTROL Cache duration]**: detta varierar beroende på hur ofta API-anrop görs. I vårt fall uppdateras reservationssystemet var 10:e minut.
   * **[!UICONTROL Response Payload]**: klicka inuti  **[!UICONTROL Payload]** fältet och klistra in ett exempel på nyttolasten. Kontrollera att fälttyperna är korrekta. Varje gång API:et anropas hämtas alla fält som ingår i exemplets nyttolast. I vårt exempel innehåller nyttolasten bara reservationsstatusen:

   ```
   {
       "reservation" : true
   }
   ```

   * **[!UICONTROL Dynamic Values]**: Ange parametern som motsvarar nyckeln som används för att identifiera varje kund,&quot;id&quot; i vårt exempel. Värdet för den här parametern definieras i resan.

   ![](../assets/journeyuc2_11.png)

1. Klicka på **[!UICONTROL Save]**.

   Datakällorna är nu konfigurerade och klara att användas under din resa.
