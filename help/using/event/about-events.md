---
product: adobe campaign
title: Om händelser
description: Läs mer om evenemang
feature: Resor
role: Business Practitioner
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: ht
source-wordcount: '354'
ht-degree: 100%

---

# Allmän princip {#concept_gfj_fqt_52b}

>[!CONTEXTUALHELP]
>id="jo_events"
>title="Om händelser"
>abstract="En händelse är länkad till en person. Det rör en persons beteende eller något som händer i samband med en person. Detta är vad [!DNL Journey Orchestration] läser av i resor för att orkestrera bästa åtgärder."

En händelse är länkad till en person. Den är relaterad till en persons beteende (till exempel om en person köpt en produkt, besökt en butik eller lämnat en webbplats) eller något som händer relaterat till en person (en person som till exempel har nått 10 000 lojalitetspoäng). Detta är vad [!DNL Journey Orchestration] läser av i resor för att orkestrera bästa åtgärder.

Den här konfigurationen är **obligatorisk** eftersom [!DNL Journey Orchestration] är designad för att läsa av händelser och alltid utförs av en **teknisk användare**.

Med händelsekonfigurationen kan du definiera vilken information som [!DNL Journey Orchestration] ska tas emot som händelser. Du kan använda flera händelser (i olika steg på en resa) och flera resor kan använda samma händelse.

Om du redigerar en händelse som används i ett utkast eller en resa i realtid kan du bara ändra namn eller beskrivning eller lägga till fält för nyttolast. Vi begränsar strikt utgåvan av utkast eller resor i realtid för att undvika att resor avbryts.

Du kan definiera två typer av händelser:

* **Regelbaserade** händelser: Den här händelsetypen genererar inget eventID. Med den enkla uttrycksredigeraren definierar du helt enkelt en regel som ska användas av systemet för att identifiera de relevanta händelserna som utlöser dina resor. Den här regeln kan baseras på alla fält som är tillgängliga i händelsenyttolasten, till exempel profilens plats eller antalet objekt som läggs till i profilens kundvagn.

   >[!CAUTION]
   >
   >En begränsningsregel definieras för regelbaserade händelser. Det begränsar antalet kvalificerade händelser som en resa kan behandla till 5 000 per sekund för en viss organisation (ORG). Det motsvarar SLA:er i Journey Orchestration. Läs den här [sidan](https://helpx.adobe.com/se/legal/product-descriptions/journey-orchestration.html).

* **Systemgenererade** händelser: Dessa händelser kräver ett eventID. Det här eventID-fältet genereras automatiskt när händelsen skapas. Systemet som skickar händelsen ska inte generera ett ID utan det ska skicka det som finns i nyttolastförhandsvisningen.

Mer information om hur du skapar en händelse finns på den här [sidan](../event/about-creating.md).
