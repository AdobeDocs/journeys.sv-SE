---
product: adobe campaign
title: Om Adobe Experience Platform-segment
description: Lär dig konfigurera ett Adobe Experience Platform-segment
feature: Journeys
role: User
level: Intermediate
exl-id: 94e1e3e3-9a46-41ca-bec1-f41287925372
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 0%

---

# Om Adobe Experience Platform-segment {#about-segments}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


Om du använder [Adobe Experience Platform segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/home.html?lang=sv-SE) för att skapa dina segment kan du utnyttja dem i [!DNL Journey Orchestration]. Tack vare en dedikerad eventaktivitet kan du få individer att komma in på eller gå framåt i en resa baserat på Adobe Experience Platform segmentingångar och utgångar. På så sätt kan du även skapa komplexa villkor i dina resor med den enkla eller avancerade uttrycksredigeraren.

Säg att du har ett &quot;silverkundssegment&quot;. Med den här aktiviteten kan ni få alla nya silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem. Du kan också enkelt skapa villkor baserat på det här segmentet.

Här är möjligheterna som [!DNL Journey Orchestration] erbjuder dig med segment:

* Gå till listan över Adobe Experience Platform-segment. Se [Skapa ett segment](../segment/creating-a-segment.md).
* Skapa segment direkt i [!DNL Journey Orchestration] på samma sätt som du skapar dem med segmenteringstjänsten. Se [Skapa ett segment](../segment/creating-a-segment.md).
* Utnyttja segmenten i kundresan med den enkla eller avancerade uttrycksredigeraren. Se [Använda segment i villkor](../segment/using-a-segment.md).
* Lägg till en **[!UICONTROL Segment qualification]**-händelse på resan för att lyssna på ingångar och utträden för profiler i Adobe Experience Platform-segment. Se [Händelseaktiviteter](../building-journeys/segment-qualification-events.md).

## Utvärderingsmetod i Journey Orchestration {#evaluation-method-in-journey-orchestration}

I Journey Orchestration genereras målgrupper från segmentdefinitioner med någon av dessa utvärderingsmetoder:

* Direktuppspelningssegmentering - målgruppslistan för segmentet hålls uppdaterad i realtid medan nya data flödar in i systemet.
* Gruppsegmentering - målgruppslistan för segmentet uppdateras varje timme baserat på data som erhållits under den senaste timmen.

Fastställandet mellan gruppsegmentering och direktuppspelningssegmentering görs av systemet för varje segmentdefinition, baserat på komplexiteten och kostnaden för att utvärdera segmentregeln.

Du kan visa utvärderingsmetoden för varje segment i kolumnen **[!UICONTROL Evaluation method]** i segmentlistan.

När du har definierat ett segment första gången läggs profiler till i målgruppen när de kvalificerar sig.

Det kan ta upp till 24 timmar att fylla målgruppen med tidigare data. När målgruppen har fyllts i på nytt hålls målgruppen kontinuerligt uppdaterad och alltid redo för målinriktning.