---
title: Använda resedesignern
description: Läs mer om hur du använder resedesignern
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
source-git-commit: e53ecd96bbb308fe109843de6f64cde4cba5e246

---


# Använda resedesignern {#concept_m1g_5qt_52b}

På hemmenyn för resan kan du visa **listan över resor**. Skapa en ny resa eller klicka på en befintlig för att öppna **resedesignerns gränssnitt**. Designern består av följande zoner: paletten, arbetsytan och aktivitetskonfigurationsrutan.

## Reselistan {#journey_list}

Med **reselistan** kan du visa alla dina resor på en gång, se deras status och utföra grundläggande åtgärder. Du kan duplicera, stoppa eller ta bort dina resor. Beroende på resan kanske vissa åtgärder inte är tillgängliga. Du kan till exempel inte ta bort eller starta om en resa som är slutförd. Du kan skapa en ny version av den eller duplicera den. Du kan också använda sökfältet för att söka efter en resa.

Du **[!UICONTROL Filters]** kommer åt dem genom att klicka på filterikonen högst upp till vänster i listan. Med filtermenyn kan du filtrera de visade resorna enligt olika villkor (status, de som du skapade, de som ändrades under de senaste 30 dagarna, endast de senaste versionerna osv.). Du kan också välja att endast visa resor som använder en viss händelse, fältgrupp eller åtgärd. Kolumner som visas i listan kan konfigureras. Alla filter och kolumner sparas per användare.

![](../assets/journey74.png)

Alla versioner av dina resor visas i listan med versionsnumret. Se [](../building-journeys/journey-versions.md).

![](../assets/journey37.png)

>[!NOTE]
>
>Om du vill öppna arbetsytan för en resa på en annan flik i webbläsaren håller du ned **Ctrl** eller **Kommando** och klickar på resan.

## Paletten {#palette}

Paletten **** finns till vänster på skärmen. Alla tillgängliga aktiviteter är sorterade i flera kategorier: **[!UICONTROL Events]**, **[!UICONTROL Orchestration]** och **[!UICONTROL Actions]**. Du kan expandera/komprimera de olika kategorierna genom att klicka på deras namn. Om du vill använda en aktivitet på din resa drar och släpper du den från paletten till arbetsytan. Du kan också dubbelklicka på en aktivitet på paletten för att lägga till den på arbetsytan i nästa steg. Du måste konfigurera varje aktivitet som läggs till från paletten innan du publicerar resan. Om du släpper en aktivitet på arbetsytan och inte slutför konfigurationen, stannar den kvar på arbetsytan, men en röd varning anger att konfigurationen inte har slutförts för den här aktiviteten.

>[!NOTE]
>
>Observera att det finns regler när en resa konfigureras. Otillåten konfiguration ignoreras. Du kan till exempel inte placera åtgärder parallellt, länka en aktivitet till ett tidigare steg för att skapa en slinga, starta en resa med något annat än en händelse, osv.

![](../assets/journey38.png)

Med ikonen **Visa inaktiverade objekt** i det övre vänstra hörnet kan du dölja eller visa otillgängliga element på paletten, till exempel händelser som använder ett annat namnutrymme än de som används under din resa. Som standard är otillgängliga objekt dolda. Om du väljer att visa dem visas de som nedtonade.

När du använder fältet **Sök** visas antalet resultat för varje aktivitetskategori på arbetsytan.

![](../assets/palette-filter.png)

## Arbetsytan {#canvas}

Arbetsytan **är** den centrala zonen i resedesignern. Det är i den här zonen som du kan släppa dina aktiviteter och konfigurera dem. Klicka på en aktivitet på arbetsytan för att konfigurera den. Aktivitetskonfigurationsrutan öppnas till höger. Du kan zooma in och ut genom att använda knapparna &quot;+&quot; och &quot;-&quot; högst upp till höger. På arbetsytan kan du lägga till ett steg efter dem, förutom **[!UICONTROL End]** aktiviteter (se [](../building-journeys/end-activity.md)).

![](../assets/journey39.png)

## Åtgärdskonfigurationsfönstret {#configuration_pane}

Aktivitetskonfigurationsrutan **** visas när du klickar på en aktivitet på paletten. Fyll i de obligatoriska fälten. Klicka på **[!UICONTROL Delete]** ikonen för att ta bort aktiviteten. Klicka på **[!UICONTROL Cancel]** för att avbryta ändringarna eller **[!UICONTROL Ok]** för att bekräfta. Om du vill ta bort aktiviteter kan du även markera en aktivitet (eller flera) och trycka på backstegstangenten. Om du trycker på Esc stängs aktivitetskonfigurationsrutan.

På arbetsytan representeras dina åtgärder och händelseaktiviteter av en ikon med namnet på händelsen eller åtgärden som visas under. I aktivitetskonfigurationsrutan kan du använda **[!UICONTROL Label]** fältet för att lägga till ett suffix till aktivitetsnamnet. Dessa etiketter hjälper dig att kontextualisera användningen av händelser och åtgärder, särskilt när du använder samma händelse eller åtgärd flera gånger under resan. Du kan också se etiketterna som du har lagt till i rapporten för resesamordning.

![](../assets/journey59bis.png)

## Åtgärder i det övre fältet {#top_actions}

Beroende på resans status kan du utföra olika åtgärder under resan med hjälp av knapparna i det övre högra hörnet: **[!UICONTROL Publish]**, **[!UICONTROL Duplicate]**, **[!UICONTROL Delete]**, **[!UICONTROL Journey properties]**, **[!UICONTROL Test]**.. De här knapparna visas när ingen aktivitet är markerad. Vissa knappar visas i sitt sammanhang. Loggknappen för testläget visas när testläget aktiveras (se [](../building-journeys/testing-the-journey.md)). Rapporteringsknappen visas när resan är live, stoppad eller slutförd.

![](../assets/journey41.png)

## Användning av banor på arbetsytan {#paths}

Flera aktiviteter (**[!UICONTROL Condition]**, **[!UICONTROL Action]** aktiviteter) gör att du kan definiera en reservåtgärd om ett fel eller en timeout inträffar. Markera kryssrutan i aktivitetskonfigurationsrutan: **[!UICONTROL Add an alternative path in case of a timeout or an error]**. En annan sökväg läggs till efter aktiviteten. Tidsgränsen definieras i resans egenskaper (se [](../building-journeys/changing-properties.md) av en administratörsanvändare). Om det t.ex. tar för lång tid att skicka ett e-postmeddelande eller om det är fel, kan du bestämma dig för att skicka ett SMS.

![](../assets/journey42.png)

Med olika aktiviteter (händelse, åtgärd, vänta) kan du lägga till flera sökvägar efter dem. Placera markören på aktiviteten och klicka på plustecknet (+). Endast händelse- och vänteaktiviteter kan anges parallellt. Om flera händelser anges parallellt är den valda sökvägen den första händelsen som inträffar.

När du lyssnar på en händelse rekommenderar vi att du inte väntar på händelsen i oändlighet. Det är inte obligatoriskt, bara en god praxis. Om du bara vill lyssna på en eller flera händelser under en viss tid, placerar du en eller flera händelser och en vänteaktivitet parallellt. Se [](../building-journeys/event-activities.md#section_vxv_h25_pgb).

Om du vill ta bort banan placerar du markören på den och klickar på **[!UICONTROL Delete arrow]** ikonen.

![](../assets/journey42ter.png)

När två aktiviteter inte är kopplade till arbetsytan visas en varning. Placera markören på varningsikonen för att visa felmeddelandet. Åtgärda problemet genom att flytta den frånkopplade aktiviteten och koppla den till föregående aktivitet.

![](../assets/canvas-disconnected.png)