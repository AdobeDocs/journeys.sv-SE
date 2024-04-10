---
product: adobe campaign
title: Användargränssnittet
description: Läs mer om användargränssnittet
feature: Journeys
role: User
level: Intermediate
exl-id: 0d0e74c7-6cb0-4068-a69a-3c01f8b3552d
source-git-commit: a5ec1c4c5608113bb17dfbdea0587f6bb342099a
workflow-type: tm+mt
source-wordcount: '959'
ht-degree: 59%

---

# Användargränssnitt{#concept_rcq_lqt_52b}

>[!NOTE]
>
>För att du ska få ut så mycket som möjligt av [!DNL Journey Orchestration] rekommenderar vi att du använder webbläsaren Chrome. Gränssnittet visas på det språk som definieras i IMS. Om ditt IMS-språk inte stöds av [!DNL Journey Orchestration] visas gränssnittet på engelska.
>
>Dokumentationen uppdateras ofta för att återspegla de senaste ändringarna i produkten. Vissa skärmbilder kan dock skilja sig något från produktens gränssnitt.

## Komma åt [!DNL Journey Orchestration]{#accessing_journey_orchestration}

Så här öppnar du [!DNL Journey Orchestration]I gränssnittet klickar du på **[!UICONTROL App Selector]** ikonen, längst upp till höger och klicka sedan på **[!UICONTROL Journey Orchestration]**.

![](../assets/journey1.png)

Du kan även komma åt [!DNL Journey Orchestration] från webbplatsen för Experience Cloud i avsnittet **[!UICONTROL Quick access]**.

![](../assets/journey1bis.png)

## Lära känna gränssnittet{#section_jsq_zr1_ffb}

>[!CONTEXTUALHELP]
>id="jo_home"
>title="Om reselistan"
>abstract="Med reselistan kan du visa alla dina resor på en gång, se deras status och utföra grundläggande åtgärder."
>additional-url="https://images-tv.adobe.com/mpcv3/38af62cb-9390-4bc0-a576-d336849adb97_1574809570.1920x1080at3000_h264.mp4" text="Se demovideon"

Med de översta menyerna kan du navigera bland de olika funktionerna i [!DNL Journey Orchestration]: **[!UICONTROL Home]** (resorna), **[!UICONTROL Data Sources]**, **[!UICONTROL Events]**, **[!UICONTROL Actions]**.

![](../assets/journey2.png)

Klicka på ![](../assets/icon-context.png)-ikonen på skärmens övre högra hörn för att visa sammanhangsberoende hjälp. Den finns för alla listskärmar i [!DNL Journey Orchestration] (resor, händelser, åtgärder och datakällor). Hjälpen innehåller en kort beskrivning av den aktuella funktionen och du får tillgång till relaterade artiklar och videor.

![](../assets/journey2bis.png)

## Söka och filtrera{#section_lgm_hpz_pgb}

I listorna **[!UICONTROL Home]**, **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]** kan du söka efter ett alternativ med hjälp av ett sökfält.

Du kommer åt **[!UICONTROL Filters]** genom att klicka på filterikonen högst upp till vänster i listan. Med filtermenyn kan du filtrera de element som visas enligt olika villkor. Du kan välja att endast visa element av en viss typ eller status, de som du har skapat eller de som har ändrats under de senaste 30 dagarna.

I listorna **[!UICONTROL Data Sources]**, **[!UICONTROL Events]** och **[!UICONTROL Actions]** kan du använda **[!UICONTROL Creation filters]** för att filtrera per datum för skapande och per användare. Du kan till exempel välja att bara visa händelser som du har skapat under de senaste 30 dagarna.

I reselistan (under **[!UICONTROL Home]**), utöver **[!UICONTROL Creation filters]** kan du även filtrera de visade resorna efter status, typ och version (**[!UICONTROL Status and version filters]**). Typen kan vara: **[!UICONTROL Unitary event]** eller **[!UICONTROL Segment qualification]**. Du kan även välja att endast visa resor som använder en viss händelse, fältgrupp eller åtgärd (**[!UICONTROL Activity filters]** och **[!UICONTROL Data filters]**). Med **[!UICONTROL Publication filters]** kan du välja ett publiceringsdatum eller en viss användare. Du kan till exempel välja att endast visa de senaste versionerna av resor i realtid som publicerades i går. Läs [den här sidan](../building-journeys/using-the-journey-designer.md).

>[!NOTE]
>
>Observera att kolumner som visas kan personaliseras med hjälp av konfigurationsknappen längst upp till höger i listorna. Personalisering sparas per användare.

Med kolumnerna **[!UICONTROL Last update]** och **[!UICONTROL Last update by]** kan du visa när den senaste uppdateringen av dina resor gjorts och vilken användare som använde den.

![](../assets/journey74.png)

I konfigurationsfönstren för händelser, datakällor och åtgärder visar fältet **[!UICONTROL Used in]** antalet resor som använder just den händelsen, fältgruppen eller åtgärden. Du kan klicka på knappen **[!UICONTROL View journeys]** för att visa en lista över motsvarande resor.

![](../assets/journey3bis.png)

I de olika listorna kan du utföra grundläggande åtgärder för varje element. Du kan till exempel skapa dubbletter eller radera en post.

![](../assets/journey4.png)

## Bläddra bland Adobe Experience Platform-fält {#friendly-names-display}

När du definierar [händelsers nyttolast](../event/defining-the-payload-fields.md), [fältgruppers nyttolast](../datasource/field-groups.md) och väljer fält i [uttrycksredigeraren](../expression/expressionadvanced.md) visas visningsnamnet förutom fältnamnet. Den här informationen hämtas från schemadefinitionen i upplevelsedatamodellen.

Om beskrivningar som &quot;xdm:alternateDisplayInfo&quot; anges när du ställer in scheman, ersätts visningsnamnen med de användarvänliga namnen. Detta är särskilt användbart när du arbetar med &quot;eVars&quot; och generiska fält. Du kan konfigurera användarvänliga namnbeskrivningar via ett API-anrop. Mer information finns i [utvecklarhandboken för schemaregister](https://experienceleague.adobe.com/docs/experience-platform/xdm/api/getting-started.html).

![](../assets/xdm-from-descriptors.png)

Om användarvänliga namn finns visas fältet som `<friendly-name>(<name>)`. Om det inte finns något användarvänligt namn visas till exempel visningsnamnet som `<display-name>(<name>)`. Om inget av dem är definierade visas bara fältets tekniska namn `<name>`.

>[!NOTE]
>
>Användarvänliga namn hämtas inte när du väljer fält från en sammanslutning av scheman.

## Tillgänglighet{#accessibility}

Tillgänglighetsfunktionerna i Adobe Journey Optimizer tillhandahålls av Adobe Experience Platform:

* Tangentbordstillgänglighet
* Färgkontrast
* Validering av obligatoriska fält

[Läs mer](https://experienceleague.adobe.com/docs/experience-platform/accessibility/features.html){target="_blank"} i Adobe Experience Platform-dokumentationen.

Du kan använda följande vanliga kortkommandon i Adobe Journey Optimizer:

| Åtgärd | Genväg |
| --- | --- |
| Växla mellan element, avsnitt och menygrupper i användargränssnittet | Tabb |
| Gå bakåt mellan element, avsnitt och menygrupper i användargränssnittet | Skift+Tabb |
| Flytta inom avsnitt för att ange fokus till enskilda element | Pil |
| Markera eller rensa ett element som är i fokus | Enter eller mellanslagstangenten |
| Avbryt en markering, komprimera en panel eller stänga en dialogruta | Esc |

[Läs mer](https://experienceleague.adobe.com/docs/experience-platform/accessibility/custom.html){target="_blank"} i Adobe Experience Platform-dokumentationen.

Du kan använda dessa kortkommandon i vissa delar av Journey Optimizer:

<table>
  <thead>
    <tr>
      <th>Gränssnittselement</th>
      <th>Åtgärd</th>
      <th>Genväg</th>
    </tr>
  </thead>
  <tr>
    <td>Förteckning över resor, åtgärder, datakällor eller händelser</td>
    <td>Skapa en resa, en åtgärd, en datakälla eller en händelse</td>
    <td>C</td>
  </tr>
  <tr>
    <td rowspan="3">Researbetsyta med utkaststatus</td>
    <td>Lägg till en aktivitet från den vänstra paletten vid den första tillgängliga positionen, uppifrån och ned</td>
    <td>Dubbelklicka på aktiviteten</td>
  </tr>
  <tr>
    <td>Välj alla aktiviteter</td>
    <td>Ctrl + A (Windows)<br/>Cmd + A (Mac)</td>
  </tr>
  <tr>
    <td>Ta bort de valda aktiviteterna</td>
    <td>Ta bort eller Backsteg, och bekräfta sedan borttagningen genom att ange</td>
  </tr>
  <tr>
  <td rowspan="3">

Konfigurationsruta för dessa element:

<ul>
  <li>Aktivitet under en resa</li>
  <li>Händelse</li>
  <li>Datakälla</li>
  <li>Åtgärd</li>
</ul>

</td>
    <td>Flytta till nästa fält som ska konfigureras</td>
    <td>Tabb</td>
  </tr>
  <tr>
    <td>Spara ändringar och stäng konfigurationsfönstret</td>
    <td>Retur</td>
  </tr>
  <tr>
    <td>Ignorera ändringar och stäng konfigurationsfönstret</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td rowspan="4">Resa i testläge</td>
    <td>Aktivera eller inaktivera testläget</td>
    <td>T</td>
  </tr>
  <tr>
    <td>Utlösa en händelse i en händelsebaserad resa</td>
    <td>E</td>
  </tr>
  <tr>
    <td>

Utlös en händelse i en segmentbaserad resa för vilken **[!UICONTROL Single profile at a time]** alternativ är aktiverat

</td>
    <td>P</td>
  </tr>
  <tr>
    <td>Visa testloggarna</td>
    <td>L</td>
  </tr>
<!-- //Ajouter ce raccourci quand il marchera (actuellement, le raccourci Ctrl/Cmd+F du navigateur a priorité sur celui de AJO).//
  <tr>
    <td>Page with a search bar</td>
    <td>Select the search bar</td>
    <td>Ctrl/Command + F</td>
  </tr>
-->
  <tr>
    <td>Textfält</td>
    <td>Markera all text i det markerade fältet</td>
    <td>Ctrl + A (Windows)<br/>Cmd + A (Mac)</td>
  </tr>
  <tr>
    <td rowspan="2">Popup-fönster</td>
    <td>Spara ändringarna eller bekräfta åtgärden</td>
    <td>Retur</td>
  </tr>
  <tr>
    <td>Stäng fönstret</td>
    <td>Esc</td>
  </tr>
  <tr>
    <td>Enkel uttrycksredigerare</td>
    <td>Markera och lägga till ett fält</td>
    <td>Dubbelklicka på ett fält</td>
  </tr>
  <tr>
    <td>Bläddra bland XDM-fält</td>
    <td>Markera alla fält i en nod</td>
    <td>Markera den överordnade noden</td>
  </tr>
  <tr>
    <td>Förhandsgranska nyttolast</td>
    <td>Välj nyttolast</td>
    <td>Ctrl + A (Windows)<br/>Cmd + A (Mac)</td>
  </tr>
</table>
