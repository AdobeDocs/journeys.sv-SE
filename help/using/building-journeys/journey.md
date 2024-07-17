---
product: adobe campaign
title: Om resebyggnad
description: Som affärsanvändare kan du lära dig att kombinera händelser, samordning och åtgärder för att skapa en resa.
feature: Journeys
role: User
level: Intermediate
exl-id: 540b5142-9323-4cc1-9b5a-3fa20a5945bf
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '558'
ht-degree: 8%

---

# Skapa en resa {#concept_gq5_sqt_52b}

Det här steget utförs av **affärsanvändaren**. Här skapar du dina resor. Kombinera de olika händelserna, samordningen och åtgärderna för att skapa flerstegsscenarier för olika kanaler.

Med resegränssnittet kan du enkelt dra och släppa aktiviteter från paletten till arbetsytan. Du kan också dubbelklicka på en aktivitet för att lägga till den på arbetsytan i nästa steg som är tillgängligt. Varje aktivitet har en särskild roll och plats i processen. Aktiviteterna är sekventierade. När en aktivitet är klar fortsätter flödet och bearbetar nästa aktivitet och så vidare.

Endast ett namnutrymme tillåts per resa. När du släpper den första händelsen blir händelser med olika namnutrymmen nedtonade. Om den första händelsen inte har något namnutrymme tonas alla händelser med ett namnutrymme ut. Se [den här sidan](../event/selecting-the-namespace.md). Dessutom är Adobe Experience Platform fältgrupper nedtonade om resan innehåller händelser utan namnutrymme. Och slutligen, om du använder flera händelser under samma resa, måste de använda samma namnutrymme.

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

## Avsluta en resa {#ending_a_journey}

En resa kan ta slut för en individ på grund av två orsaker:

* Personen kommer till den sista aktiviteten i en bana. Den senaste aktiviteten kan vara en slutaktivitet eller en annan aktivitet. Det finns ingen skyldighet att avsluta ett tågläge med en slutaktivitet. Läs [den här sidan](../building-journeys/end-activity.md).
* Personen kommer till en villkorsaktivitet (eller en vänteaktivitet med ett villkor) och matchar inte något av villkoren.

Personen kan sedan återinträda i resan om återinträde tillåts. Läs [den här sidan](../building-journeys/changing-properties.md).

En resa kan avslutas på grund av följande orsaker:

* Resan stängs manuellt med knappen **[!UICONTROL Close to new entrances]**.
* Slutdatumet för resan har nåtts.

När en resa stängs (av någon av anledningarna ovan) får den statusen **[!UICONTROL Closed]**. Resan kommer att sluta låta nya individer komma in på resan. Personer som redan är på resan kommer att slutföra resan normalt. Efter den globala standardtidsgränsen på 30 dagar växlar resan till statusen **Slutförd**. Se [avsnittet](../building-journeys/changing-properties.md#entrance).

Om ni behöver stoppa alla enskilda personers framsteg på resan kan ni stoppa den. Om du stoppar resan kommer alla personer på resan att tidsgränsen för timeout.

Mer information om hur du stänger eller stoppar en resa manuellt finns i det här [avsnittet](../building-journeys/terminating-a-journey.md).
