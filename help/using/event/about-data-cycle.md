---
product: adobe campaign
title: Händelsedatacecykel
description: Läs mer om händelsedatecykel
feature: Resor
role: User
level: Intermediate
exl-id: b362589a-32b0-4dbd-8ceb-a371e1e048ac
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 76%

---

# Datacykel {#section_r1f_xqt_pgb}

Händelser är POST API-anrop. Händelser skickas till Adobe Experience Platform via API:er för strömningsinmatning. URL-destinationen för händelser som skickas via API:er för transaktionsmeddelanden kallas för ett &quot;inlet&quot;. Händelsers nyttolast följer XDM-formateringen.

Nyttolasten innehåller information som krävs för att API:er för strömningsinmatning ska fungera (i rubriken) och den information som krävs för att [!DNL Journey Orchestration] ska kunna fungera (händelse-ID och en del av nyttolastens brödtext). Den innehåller även information som ska användas på resor (i brödtexten, till exempel värdet på en övergiven kundvagn). Det finns två lägen för strömningsinmatning – autentiserad och ej autentiserad. Se [den här länken](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html) för mer information om API:er för strömningsinmatning.

Efter att ha anlänt via API:er för strömningsinmatning flödar händelserna till en intern tjänst som kallas pipeline och sedan i Adobe Experience Platform. Om händelseschemat har tjänstflaggan realtidskundprofil aktiverad och ett datauppsättnings-ID som även har flaggan realtidskundprofil flödar det in i tjänsten realtidskundprofil.

För systemgenererade händelser filtrerar pipelinen händelser som har en nyttolast som innehåller [!DNL Journey Orchestration] händelse-ID:n (se processen för att skapa händelsen nedan) som tillhandahålls av [!DNL Journey Orchestration] och som ingår i händelsens nyttolast. För regelbaserade händelser identifierar systemet händelsen med eventID-villkoret. [!DNL Journey Orchestration] läser av dessa händelser och motsvarande resa aktiveras.
