---
title: Användargränssnittet
description: Läs mer i användargränssnittet
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: 891216a489b79fe4b168ecdb6120f5d9f3e107d0

---


# Användargränssnitt{#concept_rcq_lqt_52b}


>[!CONTEXTUALHELP]
>id=&quot;jo_home&quot;
>title=&quot;About Journey list&quot;
>abstract=&quot;Med reselistan kan du se alla dina resor på en gång, se deras status och utföra grundläggande åtgärder. Du kan duplicera, stoppa eller ta bort dina resor. Beroende på resan kanske vissa åtgärder inte är tillgängliga. Du kan till exempel inte stoppa eller ta bort en resa som är slutförd. Du kan också använda sökfältet för att söka efter en resa.&quot;
>additional-url=&quot;https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4&quot; text=&quot;Titta på filmen&quot;

>[!NOTE]
>
>För att få ut så mycket som möjligt av Journey Orchestration rekommenderar vi att du använder Chrome som webbläsare.
>
>Dokumentationen uppdateras ofta för att återspegla de senaste ändringarna i produkten. Vissa skärmbilder kan dock skilja sig något från produktens gränssnitt.

## Identifiera gränssnittet{#section_jsq_zr1_ffb}

Klicka på ikonen i det övre högra hörnet om du vill öppna gränssnittet för **[!UICONTROL App Selector]** en guidad resa. Klicka sedan **[!UICONTROL Journey Orchestration]** till höger under Experience Platform.

![](../assets/journey1.png)

Du kan även få åtkomst till Journey Orchestration från Experience Cloud-startsidan i **[!UICONTROL Quick access]** avsnittet.

![](../assets/journey1bis.png)

De översta menyerna gör att du kan navigera bland de olika funktionerna i Journey Orchestration: **[!UICONTROL Home]**(resorna),**[!UICONTROL Data Sources]**, **[!UICONTROL Events]**, **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Klicka på ![](../assets/icon-context.png) ikonen i skärmens övre högra hörn för att visa sammanhangsberoende hjälp. Den är tillgänglig på olika skärmar i listan över resan (resor, händelser, åtgärder och datakällor). På så sätt kan du visa en kort beskrivning av den aktuella funktionen och få tillgång till relaterade artiklar och videoklipp.

![](../assets/journey2bis.png)

## Söka och filtrera{#section_lgm_hpz_pgb}

I listorna **[!UICONTROL Home]**,**[!UICONTROL Data Sources]****[!UICONTROL Events]** och **[!UICONTROL Actions]** kan du söka efter ett objekt med hjälp av ett sökfält.

Du **[!UICONTROL Filters]** kommer åt dem genom att klicka på filterikonen högst upp till vänster i listan. Med filtermenyn kan du filtrera de visade elementen enligt olika villkor. Du kan välja att endast visa element av en viss typ eller status, de element du har skapat eller de element som har ändrats under de senaste 30 dagarna.

I listorna **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]** , använder du filtren **** Skapa för att filtrera på skapandedatum och användare. Du kan t.ex. välja att bara visa händelser som du har skapat de senaste 30 dagarna.

I reselistan (under **[!UICONTROL Home]**) kan du, utöver **[!UICONTROL Creation filters]** själva, även filtrera de visade resorna efter status och version (**[!UICONTROL Status and version filters]**). Du kan också välja att endast visa resor som använder en viss händelse, fältgrupp eller åtgärd (**[!UICONTROL Activity filters]** och **[!UICONTROL Data filters]**). **[!UICONTROL Publication filters]** Du kan välja ett publiceringsdatum eller en viss användare. Du kan till exempel välja att endast visa de senaste versionerna av direktresor som publicerades i går. Se [](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>Observera att kolumner som visas kan anpassas med hjälp av konfigurationsknappen högst upp till höger i listorna. Personalisering sparas för varje användare.

Med kolumnerna **[!UICONTROL Last update]** och **[!UICONTROL Last update by]** kan du visa när den senaste uppdateringen av dina resor har gjorts och vilken användare som använde den.

![](../assets/journey74.png)

I händelse-, datakälla- och åtgärdskonfigurationsrutor visas antalet resor som använder just den händelsen, fältgruppen eller åtgärden i **[!UICONTROL Used in]** fältet. Du kan klicka på **[!UICONTROL View journeys]** knappen för att visa en lista över motsvarande resor.

![](../assets/journey3bis.png)

I de olika listorna kan du utföra grundläggande åtgärder för varje element. Du kan till exempel duplicera eller ta bort ett objekt.

![](../assets/journey4.png)

## Bläddra bland fälten för dataplattformen {#friendly-names-display}

När du definierar [händelsenyttolast](../event/defining-the-payload-fields.md), [fältgruppnyttolast](../datasource/field-groups.md) och väljer fält i [uttrycksredigeraren](../expression/expressionadvanced.md)visas visningsnamnet förutom fältnamnet. Den här informationen hämtas från schemadefinitionen i Experience Data Model.

Om beskrivningar som &quot;xdm:alternateDisplayInfo&quot; anges när du ställer in scheman, kommer de användarvänliga namnen att ersätta visningsnamnen. Det är särskilt användbart när du arbetar med&quot;eVars&quot; och generiska fält. Du kan konfigurera egna namnbeskrivningar via ett API-anrop. Mer information finns i Utvecklarhandbok [för](https://www.adobe.io/apis/experienceplatform/home/xdm/xdmservices.html#!api-specification/markdown/narrative/technical_overview/schema_registry/schema_registry_developer_guide.md)schemaregister.

![](../assets/xdm-from-descriptors.png)

Om det finns ett eget namn visas fältet som `<friendly-name>(<name>)`. Om det inte finns något eget namn visas till exempel visningsnamnet `<display-name>(<name>)`. Om ingen av dem är definierad visas bara fältets tekniska namn `<name>`.

>[!NOTE]
>
>Eget namn hämtas inte när du väljer fält från en förening av scheman.

## Använda olika kortkommandon{#section_ksq_zr1_ffb}

Här är de olika kortkommandona som är tillgängliga i gränssnittet för Journey Orchestration.

_I förteckningen över resor, åtgärder, datakällor eller händelser:_

* Tryck på **c** för att skapa en ny resa, åtgärd, datakälla eller händelse.

_När du konfigurerar en aktivitet under en resa:_

Arbetsytan sparas automatiskt. Längst upp till vänster på arbetsytan visas sparstatus.

* Tryck på **Esc** för att stänga konfigurationsrutan och ignorera ändringarna. Det här är motsvarigheten till **[!UICONTROL Cancel]** knappen.
* Tryck **[!UICONTROL Enter]** eller klicka utanför rutan för att stänga konfigurationsrutan. Ändringarna sparas. Det här är motsvarigheten till **[!UICONTROL Ok]** knappen.
* Om du trycker på **[!UICONTROL Delete]** eller **backstegstangenten** kan du sedan trycka på **[!UICONTROL Enter]** för att bekräfta borttagningen.

_I popup-fönster:_

* Tryck på **Esc** för att stänga den (motsvarar knappen **Avbryt** ).
* Tryck på **[!UICONTROL Enter]** för att spara eller bekräfta (motsvarar knappen **[!UICONTROL Ok]** eller **[!UICONTROL Save]** ).

_I händelse-, datakälla- eller åtgärdskonfigurationsrutan:_

* Tryck på **Esc** för att stänga konfigurationsfönstret utan att spara.
* Tryck på **[!UICONTROL Enter]** för att spara ändringarna och stänga konfigurationsfönstret.
* Tryck på **tabbtangenten** för att hoppa mellan de olika fälten som ska konfigureras.

_I den enkla uttrycksredigeraren_

* Dubbelklicka på ett fält till vänster för att lägga till en fråga (motsvarande dra och släpp).

_När du bläddrar bland XDM-fält:_

* Om du markerar en nod markeras alla fält i noden.

_I alla textområden:_

* Markera texten med **Ctrl+Kommando+A** . I nyttolastförhandsvisningen väljs nyttolasten.

_På en skärm med ett sökfält:_

* Markera sökfältet med **Ctrl+** +Kommando+F.

_På resans arbetsyta:_

* Använd tangentkombinationen **Ctrl/Cmd + A** för att markera alla aktiviteter.
* När en eller flera aktiviteter är markerade trycker du på **[!UICONTROL Delete]** eller **backsteg** för att ta bort dem. Sedan kan du trycka på **[!UICONTROL Enter]** för att bekräfta i bekräftelsefönstret.
* Dubbelklicka på en aktivitet från den vänstra paletten för att lägga till den på den första tillgängliga positionen (uppifrån och ned).
