---
product: adobe campaign
solution: Journey Orchestration
title: Definiera händelsenyckeln
description: Lär dig hur du definierar händelsenyckeln
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '399'
ht-degree: 5%

---


# Definiera händelsenyckeln {#concept_ond_hqt_52b}

Nyckeln är fältet eller kombinationen av fält som är en del av händelsenyttolastdata och som gör att systemet kan identifiera den person som är associerad med händelsen. Nyckeln kan till exempel vara Experience Cloud-ID, ett CRM-ID eller en e-postadress.

Om du planerar att utnyttja data som lagras i kundprofildatabasen i realtid måste du som händelsenyckel välja information som du definierat som en profils identitet i [kundprofiltjänsten](https://docs.adobe.com/content/help/sv-SE/experience-platform/profile/home.html)i realtid.

Det gör att systemet kan utföra avstämningen mellan händelsen och personens profil. Om du väljer ett schema som har en primär identitet fylls **[!UICONTROL Key]** - och **[!UICONTROL Namespace]** -fälten i förväg i. Om ingen identitet har definierats väljer vi _identityMap > id_ som primärnyckel. Sedan måste du markera ett namnutrymme och nyckeln fylls i automatiskt (nedanför **[!UICONTROL Namespace]** fältet) med _identityMap > id_.

När du markerar fält taggas primära identitetsfält.

![](../assets/primary-identity.png)

Om du behöver använda en annan nyckel, till exempel ett CRM-ID eller en e-postadress, måste du lägga till den manuellt:

1. Klicka inuti **[!UICONTROL Key]** fältet eller på pennikonen.

   ![](../assets/journey16.png)

1. Välj det fält som valts som nyckel i listan över nyttolastfält. Du kan också växla till den avancerade uttrycksredigeraren för att skapa mer komplexa nycklar (till exempel en sammanfogning av två fält med händelser). Se nedan i detta avsnitt.

   ![](../assets/journey20.png)

När händelsen tas emot, kommer nyckelns värde att göra det möjligt för systemet att identifiera den person som är associerad med händelsen. Nyckeln är kopplad till ett namnutrymme (se [den här sidan](../event/selecting-the-namespace.md)) och kan användas för att utföra frågor på Adobe Experience Platform. Läs [den här sidan](../building-journeys/about-orchestration-activities.md).
Nyckeln används också för att kontrollera att en person befinner sig på en resa. En person kan faktiskt inte befinna sig på två olika platser på samma resa. Därför tillåter systemet inte att samma nyckel, till exempel nyckeln CRMID=3224, finns på olika platser under samma resa.

Du har även tillgång till de avancerade uttrycksfunktionerna (**[!UICONTROL Advanced mode]**) om du vill utföra ytterligare ändringar. Dessa funktioner gör att du kan ändra de värden som används för att utföra specifika frågor, till exempel ändra format, utföra fältsammanfogningar, med hänsyn enbart till en del av ett fält (till exempel de 10 första tecknen). Läs [den här sidan](../expression/expressionadvanced.md).
