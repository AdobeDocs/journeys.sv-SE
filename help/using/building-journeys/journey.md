---
title: Om resebyggnad
description: Lär dig hur du bygger en resa
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
source-git-commit: d5c013ed6031e8138a8e2c099fc28af82966d3ec

---



# Skapa en resa {#concept_gq5_sqt_52b}

Det här steget utförs av **affärsanvändaren**. Här skapar du dina resor. Kombinera de olika händelserna, samordningen och åtgärderna för att skapa flerstegsscenarier för olika kanaler.

Med resegränssnittet kan du enkelt dra och släppa aktiviteter från paletten till arbetsytan. Du kan också dubbelklicka på en aktivitet för att lägga till den på arbetsytan i nästa steg som är tillgängligt. Varje aktivitet har en särskild roll och plats i processen. Aktiviteterna är sekventierade. När en aktivitet är klar fortsätter flödet och bearbetar nästa aktivitet och så vidare.

Endast ett namnutrymme tillåts per resa. När du släpper den första händelsen blir händelser med olika namnutrymmen nedtonade. Om den första händelsen inte har något namnutrymme tonas alla händelser med ett namnutrymme ut. Se [](../event/selecting-the-namespace.md). Dessutom är fältgrupper i Experience Platform nedtonade om resan har händelser utan namnutrymme. Och slutligen, om du använder flera händelser under samma resa, måste de använda samma namnutrymme.

## Snabbstart {#creating_journey}

Här är de viktigaste stegen för att skapa och publicera en resa.

1. Klicka på **[!UICONTROL Home]** fliken i den övre menyn.

   Listan över resor visas. Mer information om gränssnittet finns [](../building-journeys/using-the-journey-designer.md) i.

   ![](../assets/journey30.png)

1. Klicka **[!UICONTROL Create]** för att skapa en ny resa.

   ![](../assets/journey31.png)

1. Redigera resans egenskaper i konfigurationsrutan som visas till höger. Se [](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Börja med att dra och släppa en händelseaktivitet från paletten på arbetsytan. Du kan också dubbelklicka på en aktivitet för att lägga till den på arbetsytan.

   ![](../assets/journey33.png)

1. Dra och släpp dina andra aktiviteter och konfigurera dem. Se [](../building-journeys/event-activities.md), [](../building-journeys/about-orchestration-activities.md) och [](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Din resa sparas automatiskt. Testa din resa och publicera den. Se [](../building-journeys/testing-the-journey.md) och [](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Avsluta en resa {#ending_a_journey}

Det finns två sätt att avsluta en resa:

* Personen kommer till den sista aktiviteten i en bana. Den senaste aktiviteten kan vara en slutaktivitet eller en annan aktivitet. Det finns ingen skyldighet att avsluta ett tågläge med en slutaktivitet. Se [](../building-journeys/end-activity.md).
* Personen kommer till en villkorsaktivitet (eller en vänteaktivitet med ett villkor) och matchar inte något av villkoren.

Personen kan sedan återinträda i resan om återinträde tillåts. Se [](../building-journeys/changing-properties.md).
