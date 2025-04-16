---
product: adobe campaign
title: Om händelser
description: Läs mer om evenemang
feature: Journeys
role: User
level: Intermediate
exl-id: 2115ab1d-1084-4429-8315-0357c8525c47
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: ht
source-wordcount: '446'
ht-degree: 100%

---

# Allmän princip {#concept_gfj_fqt_52b}


>[!CAUTION]
>
>**Letar du efter Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._



>[!CONTEXTUALHELP]
>id="jo_events"
>title="Om händelser"
>abstract="En händelse är länkad till en person. Det rör en persons beteende eller något som händer i samband med en person. Detta är vad [!DNL Journey Orchestration] läser av i resor för att orkestrera bästa åtgärder."

En händelse är länkad till en person. Relaterar till en persons beteende (till exempel en person som köpte en produkt, besökte en butik, lämnade en webbplats, osv.) eller något som händer kopplat till en person (till exempel en person nådde 10 000 lojalitetspoäng). Detta är vad [!DNL Journey Orchestration] läser av i resor för att orkestrera bästa åtgärder.

Den här konfigurationen är **obligatorisk** eftersom [!DNL Journey Orchestration] är designad för att läsa av händelser och alltid utförs av en **teknisk användare**.

Med händelsekonfigurationen kan du definiera vilken information som [!DNL Journey Orchestration] ska tas emot som händelser. Du kan använda flera händelser (i olika steg på en resa) och flera resor kan använda samma händelse.

Om du redigerar en händelse som används i ett utkast eller en resa i realtid kan du bara ändra namn eller beskrivning eller lägga till fält för nyttolast. Vi begränsar strikt utgåvan av utkast eller resor i realtid för att undvika att resor avbryts.

Du kan definiera två typer av händelser:

* **Regelbaserade** händelser: Den här händelsetypen genererar inget eventID. Med den enkla uttrycksredigeraren definierar du helt enkelt en regel som ska användas av systemet för att identifiera de relevanta händelserna som utlöser dina resor. Den här regeln kan baseras på alla fält som är tillgängliga i händelsenyttolasten, till exempel profilens plats eller antalet objekt som läggs till i profilens kundvagn.

  >[!CAUTION]
  >
  >En begränsningsregel definieras för regelbaserade händelser. Det begränsar antalet kvalificerade händelser som en resa kan behandla till 5 000 per sekund för en viss organisation (ORG). Det motsvarar SLA:er i Journey Orchestration. Läs den här [sidan](https://helpx.adobe.com/sv/legal/product-descriptions/journey-orchestration.html).

* **Systemgenererade** händelser: Dessa händelser kräver ett eventID. Det här eventID-fältet genereras automatiskt när händelsen skapas. Systemet som skickar händelsen ska inte generera ett ID utan det ska skicka det som finns i nyttolastförhandsvisningen.

Journey Orchestration kräver att händelser direktuppspelas eller grupperas i Adobe Experience Platform. Dessa data behöver inte nödvändigtvis gå till realtidsprofilen. Om du vill använda händelserna för segmentering eller sökning i en separat resa rekommenderar vi att du aktiverar datauppsättningen för profil.

Mer information om hur du skapar en händelse finns på den här [sidan](../event/about-creating.md).
