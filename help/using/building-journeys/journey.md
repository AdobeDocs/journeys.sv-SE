---
product: adobe campaign
solution: Journey Orchestration
title: Om att bygga en resa
description: Som affärsanvändare kan du lära dig att kombinera händelser, samordning och åtgärder för att skapa en resa.
feature: Resor
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 11%

---


# Skapa en resa {#concept_gq5_sqt_52b}

Det här steget utförs av **företagsanvändaren**. Här skapar du dina resor. Kombinera de olika händelserna, orkestreringen och åtgärderna för att skapa scenarier i flera steg över olika kanaler.

Med resegränssnittet kan du enkelt dra och släppa aktiviteter från paletten till arbetsytan. Du kan också dubbelklicka på en aktivitet för att lägga till den på arbetsytan i nästa steg som är tillgängligt. Varje aktivitet har en särskild roll och plats i processen. Aktiviteterna är sekventierade. När en aktivitet är klar fortsätter flödet och bearbetar nästa aktivitet och så vidare.

Endast ett namnutrymme tillåts per resa. När du släpper den första händelsen blir händelser med olika namnutrymmen nedtonade. Om den första händelsen inte har något namnutrymme tonas alla händelser med ett namnutrymme ut. Läs [den här sidan](../event/selecting-the-namespace.md). Dessutom är Adobe Experience Platform fältgrupper nedtonade om resan innehåller händelser utan namnutrymme. Och slutligen, om du använder flera händelser under samma resa, måste de använda samma namnutrymme.

När du påbörjar en ny resa döljs element som inte kan släppas på arbetsytan som det första steget. Detta gäller alla åtgärder, villkorsaktiviteten, väntetiden och reaktionen.

## Snabbstart {#creating_journey}

Här är de viktigaste stegen för att skapa och publicera en resa.

1. Klicka på fliken **[!UICONTROL Home]** på den övre menyn.

   Listan över resor visas. Mer information om gränssnittet finns på [den här sidan](../building-journeys/using-the-journey-designer.md).

   ![](../assets/journey30.png)

1. Klicka på **[!UICONTROL Create]** för att skapa en ny resa.

   ![](../assets/journey31.png)

1. Redigera resans egenskaper i konfigurationsrutan som visas till höger. Läs [den här sidan](../building-journeys/changing-properties.md).

   ![](../assets/journey32.png)

1. Börja med att dra och släppa en händelseaktivitet från paletten på arbetsytan. Du kan också dubbelklicka på en aktivitet för att lägga till den på arbetsytan.

   ![](../assets/journey33.png)

1. Dra och släpp dina andra aktiviteter och konfigurera dem. Se sidorna [Händelseaktiviteter](../building-journeys/event-activities.md), [Om orkestreringsaktiviteter](../building-journeys/about-orchestration-activities.md) och [Om åtgärdsaktiviteter](../building-journeys/about-action-activities.md).

   ![](../assets/journey34.png)

1. Din resa sparas automatiskt. Testa din resa och publicera den. Se [testa resan](../building-journeys/testing-the-journey.md) och [Publicera resan](../building-journeys/publishing-the-journey.md).

   ![](../assets/journey36.png)

## Avslutar en resa {#ending_a_journey}

Det finns två sätt att avsluta en resa:

* Personen kommer till den sista aktiviteten i en bana. Den senaste aktiviteten kan vara en slutaktivitet eller en annan aktivitet. Det finns ingen skyldighet att avsluta ett tågläge med en slutaktivitet. Läs [den här sidan](../building-journeys/end-activity.md).
* Personen kommer till en villkorsaktivitet (eller en vänteaktivitet med ett villkor) och matchar inte något av villkoren.

Personen kan sedan återinträda i resan om återinträde tillåts. Läs [den här sidan](../building-journeys/changing-properties.md).
