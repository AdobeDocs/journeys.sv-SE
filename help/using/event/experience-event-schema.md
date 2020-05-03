---
title: 'Om ExperienceEvent-scheman för guidehändelser på resan '
description: 'Läs mer om ExperienceEvent-scheman för guidehändelser för resor '
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
source-git-commit: 9b8d4bebe024e90733cb1ae6d31b36fb6ce4b606

---



# Om ExperienceEvent-scheman för guidehändelser på resan

Journey Orchestration-händelser är XDM Experience Events som skickas till Adobe Experience Platform via Streaming Ingestion.

Därför är en viktig förutsättning för att skapa händelser för resesamordning att du känner till plattformens Experience Data Model (eller XDM) och hur du skapar XDM Experience Event-scheman, samt hur du strömmar XDM-formaterade data till plattformen.

## Schemakrav för guidade händelser

Det första steget i att konfigurera en händelse för en resvägssamordning är att se till att du har ett definierat XDM-schema som representerar händelsen och en datauppsättning som skapats för att registrera instanser av händelsen på plattformen. Det är inte helt nödvändigt att ha en datauppsättning för dina händelser, men om du skickar händelserna till en viss datauppsättning kan du behålla användarens händelsehistorik för framtida referens och analyser, så det är alltid en bra idé. Om du inte redan har ett lämpligt schema och datamängd för händelsen kan båda dessa åtgärder utföras i plattformens webbgränssnitt.

![](../assets/schema1.png)

Alla XDM-scheman som används för Journey Orchestration-händelser ska uppfylla följande krav:

* Schemat måste vara av klassen XDM ExperienceEvent.

![](../assets/schema2.png)

* Schemat måste innehålla Orchestration-händelseID-mixin. Journey Orchestration använder det här fältet för att identifiera händelser som används under resor.

![](../assets/schema3.png)

* Deklarera ett identitetsfält för att identifiera föremålet för händelsen. Om ingen identitet anges kan en identitetskarta användas. Detta rekommenderas inte.

![](../assets/schema4.png)

* Om du vill att dessa data ska vara tillgängliga för sökning senare i en resa markerar du schemat och datauppsättningen för profil.

![](../assets/schema5.png)

![](../assets/schema6.png)

* Du kan inkludera datafält för att samla in andra kontextdata som du vill inkludera med händelsen, till exempel information om användaren, enheten som händelsen genererades från, plats eller andra meningsfulla omständigheter som rör händelsen.

![](../assets/schema7.png)

![](../assets/schema8.png)