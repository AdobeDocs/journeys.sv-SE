---
title: Evenemangsaktiviteter
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
source-git-commit: 957e72de7feccb33684523e26b2bdccb2074e4ca
workflow-type: tm+mt
source-wordcount: '969'
ht-degree: 0%

---


# Evenemangsaktiviteter {#concept_rws_1rt_52b}

De händelser som konfigureras av den tekniska användaren (se [](../event/about-events.md) alla visas i den första kategorin på paletten, till vänster på skärmen.

![](../assets/journey43.png)

Starta alltid din resa genom att dra och släppa en händelseaktivitet. Du kan också dubbelklicka på den.

![](../assets/journey44.png)

När du klickar på händelseaktiviteten på arbetsytan visas aktivitetskonfigurationsrutan. Som standard, när du använder samma händelse flera gånger, läggs ett stegvis värde till i händelsenamnet på arbetsytan. Du kan dessutom använda **[!UICONTROL Label]** fältet för att lägga till ett suffix till händelsenamnet som ska visas under din aktivitet på arbetsytan. Detta är användbart när du vill identifiera händelser på arbetsytan, särskilt om du använder samma händelse flera gånger. Felsökningen blir också enklare om fel uppstår, vilket gör det lättare att läsa rapporterna.

![](../assets/journey33.png)

## Allmänna händelser {#section_ofg_jss_dgb}

För den här händelsetypen kan du bara lägga till en etikett och en beskrivning. Resten av konfigurationen kan inte redigeras. Den utfördes av den tekniska användaren. Se [](../event/about-events.md).

## Reaktionshändelser {#section_dhx_gss_dgb}

En av de olika händelseaktiviteterna som finns på paletten är den inbyggda **reaktionshändelsen** . Med den här aktiviteten kan du reagera på spårningsdata för ett meddelande som skickas med e-post, SMS eller push-aktiviteter inom samma resa. Den här informationen kommer från transaktionsmeddelanden i Adobe Campaign Standard. Vi samlar in den här informationen i realtid när den delas med dataplattformen. För push-meddelanden kan du reagera på klickade, skickade eller misslyckade meddelanden. För SMS-meddelanden kan du reagera på skickade eller misslyckade meddelanden. För e-postmeddelanden kan du reagera på klickade, skickade, öppnade eller misslyckade meddelanden.

Du kan också använda den här funktionen för att utföra en åtgärd när det inte finns någon reaktion på dina meddelanden. Det gör du genom att skapa en andra sökväg parallellt med reaktionsaktiviteten och lägga till en vänteaktivitet. Om ingen reaktion inträffar under den period som anges i vänteaktiviteten väljs den andra banan. Du kan välja att skicka t.ex. ett uppföljningsmeddelande.

Observera att du bara kan använda en reaktionsaktivitet på arbetsytan om det finns en tidigare e-post-, push- eller SMS-aktivitet.

Se [](../building-journeys/about-action-activities.md).

![](../assets/journey45.png)

Här följer de olika stegen för att konfigurera reaktionshändelser:

1. Lägg till en **[!UICONTROL Label]** reaktion i reaktionen. Det här steget är valfritt.
1. Välj den åtgärd som du vill reagera på i listrutan. Du kan välja vilken åtgärdsaktivitet som helst som placerats i banans tidigare steg.
1. Beroende på vilken åtgärd du har valt (ett e-postmeddelande, SMS eller ett push-meddelande) väljer du vad du vill reagera på.
1. Du kan definiera ett villkor som ett valfritt steg. Efter en e-poståtgärd kan du till exempel bestämma dig för att skapa två banor, en med en reaktionshändelse som spårar endast klickningar för VIP-kunder och en med en reaktionshändelse som spårar klickningar som utförs av kvinnor.

>[!NOTE]
>
>Reaktionshändelser kan inte spåra e-post, SMS eller push-åtgärder som utförs under en annan resa.
>
>Reaktionshändelser spårar klick på länkar av typen &quot;spårade&quot; (se den här [sidan](https://docs.adobe.com/content/help/en/campaign-standard/using/designing-content/links.html#about-tracked-urls)). Ta inte hänsyn till länkar för att ta bort prenumerationer och spegla sidor.

>[!CAUTION]
>
>E-postklienter som Gmail tillåter bildblockering. E-postmeddelanden som öppnas spåras med en bild på 0 pixlar som ingår i e-postmeddelandet. Om bilder blockeras kommer e-postöppningar inte att beaktas.

## Segmentkvalificeringshändelser {#segment-qualification}

Med den här aktiviteten kan din resa lyssna på ingångar och utgångar för profiler i plattformssegment för att få individer att komma in på eller gå framåt under en resa. Mer information om hur du skapar segment finns i det här [avsnittet](../segment/about-segments.md).

Säg att du har ett &quot;silverkundssegment&quot;. Med den här aktiviteten kan ni få alla nya silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem.

Den här typen av händelse kan placeras som det första steget eller senare under resan.

Om segmentet direktuppspelas med alternativet High Frequency Audiences i Platform avlyssnas ingångs- och utgångar i realtid. Om segmentet inte direktuppspelas beaktas ingångar och utgångar vid segmentberäkningstillfället.

1. Ge liv åt kategorin **Händelser** och släpp en **segmentkvalificeringsaktivitet** på arbetsytan.

   ![](../assets/segment5.png)

1. Lägg till en **etikett** till aktiviteten. Det här steget är valfritt.

1. Klicka i fältet **Segment** och markera de segment som du vill använda.

   ![](../assets/segment6.png)

1. I fältet **Beteende** väljer du om du vill lyssna på segmentingångar, utgångar eller både och.

1. Välj ett namnutrymme. Detta behövs bara om händelsen placeras som det första steget i resan.

   ![](../assets/segment7.png)

Nyttolasten innehåller följande kontextinformation som du kan använda i villkor och åtgärder:

* beteendet (entré, exit)
* tidsstämpel för kvalificeringen
* segment-ID

## Avancerad användning: parallella händelser{#section_vxv_h25_pgb}

**Hur kan du lyssna på en händelse endast under en viss tid?**

En händelseaktivitet som placeras på resan lyssnar på händelser i oändlighet. Om du bara vill lyssna på en händelse under en viss tid måste du lägga till en vänteaktivitet parallellt med händelsens sökväg. Resan lyssnar sedan på händelsen under den tid som anges i vänteaktiviteten. Om en händelse tas emot under den perioden kommer personen att flöda in i händelsens sökväg. Annars kommer kunden att flyta in i väntetiden.

Du har t.ex. skickat en välkommen första push till en kund och vill bara skicka en push för måltidsrabatt om kunden kommer in på restaurangen inom 6 timmar. För att göra detta skapar du en andra väg (parallellt med restaurangeventet) med en 6-timmars vänteaktivitet. Om restauranghändelsen tas emot mindre än 6 timmar efter välkomstpushen skickas push-aktiviteten för måltidsrabatt. Om ingen restauranghändelse tas emot inom de närmaste 6 timmarna flödar personen genom väntebanan.

![](../assets/journeyuc2_31.png)
