---
title: Om händelseaktiviteter
description: Läs mer om aktiviteter
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
source-git-commit: 71b5b1ecd20056d0103ae1a8b83a31478449e844
workflow-type: tm+mt
source-wordcount: '333'
ht-degree: 0%

---


# Om händelseaktiviteter {#concept_rws_1rt_52b}

De händelser som konfigureras av den tekniska användaren (se [](../event/about-events.md)) visas alla i den första kategorin på paletten, till vänster på skärmen.

![](../assets/journey43.png)

Starta alltid din resa genom att dra och släppa en händelseaktivitet. Du kan också dubbelklicka på den.

![](../assets/journey44.png)

När du klickar på händelseaktiviteten på arbetsytan visas aktivitetskonfigurationsrutan. Som standard, när du använder samma händelse flera gånger, läggs ett stegvis värde till i händelsenamnet på arbetsytan. Du kan dessutom använda **[!UICONTROL Label]** fältet för att lägga till ett suffix till händelsenamnet som ska visas under din aktivitet på arbetsytan. Detta är användbart när du vill identifiera händelser på arbetsytan, särskilt om du använder samma händelse flera gånger. Felsökningen blir också enklare om fel uppstår, vilket gör det lättare att läsa rapporterna.

![](../assets/journey33.png)

## Avancerad användning: parallella händelser{#section_vxv_h25_pgb}

**Hur kan du lyssna på en händelse endast under en viss tid?**

En händelseaktivitet som placeras på resan lyssnar på händelser i oändlighet. Om du bara vill lyssna på en händelse under en viss tid måste du lägga till en vänteaktivitet parallellt med händelsens sökväg. Resan lyssnar sedan på händelsen under den tid som anges i vänteaktiviteten. Om en händelse tas emot under den perioden kommer personen att flöda in i händelsens sökväg. Annars kommer kunden att flyta in i väntetiden.

Du har t.ex. skickat en välkommen första push till en kund och vill bara skicka en push för måltidsrabatt om kunden kommer in på restaurangen inom 6 timmar. För att göra detta skapar du en andra väg (parallellt med restaurangeventet) med en 6-timmars vänteaktivitet. Om restauranghändelsen tas emot mindre än 6 timmar efter välkomstpushen skickas push-aktiviteten för måltidsrabatt. Om ingen restauranghändelse tas emot inom de närmaste 6 timmarna flödar personen genom väntebanan.

![](../assets/journeyuc2_31.png)
