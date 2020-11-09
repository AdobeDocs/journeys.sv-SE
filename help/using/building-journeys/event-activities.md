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
translation-type: tm+mt
source-git-commit: e353d593ab2710f50a88a3715378c86c2e37b4f6
workflow-type: tm+mt
source-wordcount: '446'
ht-degree: 1%

---


# Om händelseaktiviteter {#concept_rws_1rt_52b}

De händelser som konfigureras av den tekniska användaren (se [den här sidan](../event/about-events.md)) visas alla i den första kategorin på paletten, till vänster på skärmen.

![](../assets/journey43.png)

Starta alltid din resa genom att dra och släppa en händelseaktivitet. Du kan också dubbelklicka på den.

![](../assets/journey44.png)

När du klickar på händelseaktiviteten på arbetsytan visas aktivitetskonfigurationsrutan. Som standard, när du använder samma händelse flera gånger, läggs ett stegvis värde till i händelsenamnet på arbetsytan. Du kan dessutom använda **[!UICONTROL Label]** fältet för att lägga till ett suffix till händelsenamnet som ska visas under din aktivitet på arbetsytan. Detta är användbart om du vill identifiera händelser på arbetsytan, särskilt om du använder samma händelse flera gånger. Felsökningen blir också enklare om fel uppstår, vilket gör det lättare att läsa rapporterna.

![](../assets/journey33.png)

## Lyssna på händelser under en viss tid

En händelseaktivitet som placeras på resan lyssnar på händelser i oändlighet. Om du bara vill lyssna på en händelse under en viss tid måste du konfigurera en timeout för händelsen.

Resan lyssnar sedan på händelsen under den tid som anges i tidsgränsen. Om en händelse tas emot under den perioden kommer personen att flöda in i händelsens sökväg. Annars kommer kunden antingen att flöda in i en tidsgräns eller avsluta sin resa.

Så här konfigurerar du en timeout för en händelse:

1. Aktivera **[!UICONTROL Enable the event timeout]** alternativet från händelseegenskaperna.

1. Ange hur lång tid resan ska vänta på händelsen.

1. Om du vill skicka personerna till en timeout-sökväg när ingen händelse tas emot inom den angivna tidsgränsen aktiverar du **[!UICONTROL Set the timeout path]** alternativet. Om det här alternativet inte är aktiverat avslutas kundresan för personen när tidsgränsen nås.

   ![](../assets/event-timeout.png)

I det här exemplet skickar resan en första välkomstknuff till en kund. Sedan skickas en reklamfilm för måltidsrabatt endast om kunden kommer in på restaurangen nästa dag. Därför har vi konfigurerat restaurangevenemanget med en 1-dagars timeout:

* Om restauranghändelsen tas emot mindre än 1 dygn efter välkomstsändningen skickas push-aktiviteten för måltidsrabatt.
* Om ingen restauranghändelse tas emot under nästa dag flödar personen genom timeoutvägen.

Observera att om du vill konfigurera en timeout för flera händelser som placeras efter en **[!UICONTROL Wait]** aktivitet, måste du bara konfigurera timeout för en av dessa händelser.

Tidsgränsen gäller för alla händelser som placeras efter **[!UICONTROL Wait]** aktiviteten. Om ingen händelse tas emot efter den angivna tidsgränsen kommer individerna att flyta in i en enda tidsgräns eller avsluta sin resa.

![](../assets/event-timeout-group.png)
