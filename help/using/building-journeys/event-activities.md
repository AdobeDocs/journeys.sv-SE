---
product: adobe campaign
solution: Journey Orchestration
title: Om händelseaktiviteter
description: Läs mer om aktiviteter
feature: Resor
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '450'
ht-degree: 1%

---


# Om händelseaktiviteter {#concept_rws_1rt_52b}

De händelser som konfigureras av den tekniska användaren (se [den här sidan](../event/about-events.md)) visas alla i den första kategorin på paletten, till vänster på skärmen.

![](../assets/journey43.png)

Starta alltid din resa genom att dra och släppa en händelseaktivitet. Du kan också dubbelklicka på den.

![](../assets/journey44.png)

När du klickar på händelseaktiviteten på arbetsytan visas aktivitetskonfigurationsrutan. Som standard, när du använder samma händelse flera gånger, läggs ett stegvis värde till i händelsenamnet på arbetsytan. Du kan dessutom använda fältet **[!UICONTROL Label]** för att lägga till ett suffix till händelsenamnet som ska visas under din aktivitet på arbetsytan. Detta är användbart om du vill identifiera händelser på arbetsytan, särskilt om du använder samma händelse flera gånger. Felsökningen blir också enklare om fel uppstår, vilket gör det lättare att läsa rapporterna.

![](../assets/journey33.png)

## Lyssna på händelser under en viss tid

En händelseaktivitet som placeras på resan lyssnar på händelser i oändlighet. Om du bara vill lyssna på en händelse under en viss tid måste du konfigurera en timeout för händelsen.

Resan lyssnar sedan på händelsen under den tid som anges i tidsgränsen. Om en händelse tas emot under den perioden kommer personen att flöda in i händelsens sökväg. Annars kommer kunden antingen att flöda in i en tidsgräns eller avsluta sin resa.

Så här konfigurerar du en timeout för en händelse:

1. Aktivera alternativet **[!UICONTROL Enable the event timeout]** från händelseegenskaperna.

1. Ange hur lång tid resan ska vänta på händelsen.

1. Om du vill skicka personerna till en timeout-sökväg när ingen händelse tas emot inom den angivna tidsgränsen aktiverar du alternativet **[!UICONTROL Set the timeout path]**. Om det här alternativet inte är aktiverat avslutas kundresan för personen när tidsgränsen nås.

   ![](../assets/event-timeout.png)

I det här exemplet skickar resan en första välkomstknuff till en kund. Sedan skickas en reklamfilm för måltidsrabatt endast om kunden kommer in på restaurangen nästa dag. Därför har vi konfigurerat restaurangevenemanget med en 1-dagars timeout:

* Om restauranghändelsen tas emot mindre än 1 dygn efter välkomstsändningen skickas push-aktiviteten för måltidsrabatt.
* Om ingen restauranghändelse tas emot under nästa dag flödar personen genom timeoutvägen.

Observera att om du vill konfigurera en timeout för flera händelser som placerats efter en **[!UICONTROL Wait]**-aktivitet, måste du bara konfigurera timeout för en av dessa händelser.

Tidsgränsen gäller för alla händelser som placeras efter aktiviteten **[!UICONTROL Wait]**. Om ingen händelse tas emot efter den angivna tidsgränsen kommer individerna att flyta in i en enda tidsgräns eller avsluta sin resa.

![](../assets/event-timeout-group.png)
