---
product: adobe campaign
solution: Journey Orchestration
title: 'Om ExperienceEvent-scheman för Journey Orchestration-händelser '
description: 'Läs om ExperienceEvent-scheman för Journey Orchestration-händelser '
feature: Resor
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '328'
ht-degree: 0%

---



# Om ExperienceEvent-scheman för [!DNL Journey Orchestration]-händelser

[!DNL Journey Orchestration] -händelser är XDM Experience Events som skickas till Adobe Experience Platform via Streaming Ingmit.

Därför är en viktig förutsättning för att du ska kunna konfigurera händelser för [!DNL Journey Orchestration] att du känner till Adobe Experience Platform Experience Data Model (eller XDM) och hur du skapar XDM Experience Event-scheman samt hur du direktuppspelar XDM-formaterade data till Adobe Experience Platform.

## Schemakrav för [!DNL Journey Orchestration]-händelser

Det första steget i att konfigurera en händelse för [!DNL Journey Orchestration] är att se till att du har ett definierat XDM-schema för att representera händelsen och en datauppsättning som skapats för att registrera instanser av händelsen på Adobe Experience Platform. Det är inte helt nödvändigt att ha en datauppsättning för dina händelser, men om du skickar händelserna till en viss datauppsättning kan du behålla användarens händelsehistorik för framtida referens och analyser, så det är alltid en bra idé. Om du inte redan har ett lämpligt schema och datamängd för händelsen kan båda dessa åtgärder utföras i Adobe Experience Platform webbgränssnitt.

![](../assets/schema1.png)

Alla XDM-scheman som används för [!DNL Journey Orchestration]-händelser ska uppfylla följande krav:

* Schemat måste vara av klassen XDM ExperienceEvent.

   ![](../assets/schema2.png)

* För systemgenererade händelser måste schemat innehålla Orchestration-händelseID-mixin. [!DNL Journey Orchestration] använder det här fältet för att identifiera händelser som används under resor.

   ![](../assets/schema3.png)

* Deklarera ett identitetsfält för att identifiera föremålet för händelsen. Om ingen identitet anges kan en identitetskarta användas. Detta rekommenderas inte.

   ![](../assets/schema4.png)

* Om du vill att dessa data ska vara tillgängliga för sökning senare i en resa markerar du schemat och datauppsättningen för profil.

   ![](../assets/schema5.png)

   ![](../assets/schema6.png)

* Du kan inkludera datafält för att samla in andra kontextdata som du vill inkludera med händelsen, till exempel information om användaren, enheten som händelsen genererades från, plats eller andra meningsfulla omständigheter som rör händelsen.

   ![](../assets/schema7.png)

   ![](../assets/schema8.png)