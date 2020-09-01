---
title: Versionsinformation
description: Läs om versionsinformation
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
source-git-commit: 619f05137bfad573a5de23ceda5448180dad2d6a
workflow-type: tm+mt
source-wordcount: '1527'
ht-degree: 63%

---


# Versionsinformation {#release-notes}

På den här sidan listas alla nya funktioner och förbättringar i Journey Orchestration.
Du kan även läsa [dokumentationsuppdateringarna](../release-notes/documentation-updates.md).

## Augustiversionen 2020 {#august-release}

### GA-uppdateringar{#august-ga-update}

Nyttolasten för seg kvalificeringshändelser innehåller nu följande kontextinformation som du kan använda i villkor och åtgärder: Beteendet (entré, exit), tidsstämpeln för kvalificeringen och segment-id:t. [Läs mer](../building-journeys/segment-qualification-events.md)

### Uppdateringar om alfa{#august-alpha-update}

Se det här [avsnittet](../alpha/alpha-overview.md)om du vill veta mer om alfavärdet.

<table>
<thead>
<tr>
<th><strong>Aktivitet för utlösare av segment</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Följande förbättringar har gjorts i aktiviteten Utlösare för segment:
</p>
<ul>
<li><p>Aktivitetens namn har ändrats till"Läsa segment". </p>
</li>
<li><p>Konfigurationen av transportschemaläggaren har tagits bort från aktivitetens egenskaper. Den är nu tillgänglig direkt från reseegenskaperna i ett dedikerat avsnitt som visas om en Läs segment-aktivitet har släppts på arbetsytan. </p>
</li>
<li><p>Nu kan du testa resan med en enhetlig profil och följa förloppet i resan med hjälp av det visuella flödet.</p>
</li>
</ul>
<p>Mer information finns i den <a href="../alpha/alpha-segment-trigger.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Regelbaserade händelser</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Följande förbättringar har gjorts i regelbaserade händelser:
</p>
<ul>
<li><p>Nu kan ni utnyttja alla Adobe Analytics beteendehändelsedata som ni redan samlar in och strömmar till plattformen för att utlösa resor och automatisera kundernas upplevelser. <a href="../alpha/alpha-events.md#analytics-data">Läs mer</a></p>
</li>
<li><p>När du utlöser en regelbaserad händelse i testläge kan du nu direkt visa händelse-ID-villkoret. Dessutom har ett verktygstips lagts till bredvid varje fält som är en del av regelutvärderingen. <a href="../alpha/alpha-events.md#configuring-rule-based">Läs mer</a></p>
</li>
<li><p>Den regelbaserade skärmen för händelsedefinition har omorganiserats för att ge en bättre upplevelse. <a href="../alpha/alpha-events.md#test-rule-based">Läs mer</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Alpha Release - juli 2020 {#alpha-release---july-2020}

Alpha-programmet har funktioner som för närvarande är testade bland ett begränsat antal kunder. På så sätt kan vi förbättra vår produkt baserat på den feedback vi fått. De här funktionerna är inte tillgängliga för alla Journey Orchestration-kunder.

Dessa funktioner beskrivs i ett dedikerat [avsnitt](../alpha/alpha-overview.md).

<table>
<thead>
<tr>
<th><strong>Förbättrat användargränssnitt</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Navigeringen på Journey Orchestration-menyer har förbättrats så att gränssnittet med Adobe Experience Platform blir konsekvent:
</p>
<ul>
<li><p>Menyer har flyttats från den övre till den vänstra sidan av gränssnittet. </p>
</li>
<li><p>Gruppering av administratörsfunktioner i en enda kontrollpanel.</p>
</li>
</ul>
<p>Mer information finns i den <a href="../alpha/alpha-interface.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Aktivitet för utlösare av segment</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med aktiviteten Segmentutlösare kan du göra så att alla personer som tillhör ett Adobe Experience Platform-segment går in på en resa. Ingången till en resa kan genomföras antingen en gång eller regelbundet. <a href="../alpha/alpha-segment-trigger.md">Läs mer</a>
</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Regelbaserade händelser</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Vi har förenklat hur ni konfigurerar Experience Events. Vi introducerar en ny metod som inte kräver att ett eventID används. När du konfigurerar en händelse i Journey Orchestration kan du nu definiera en regelbaserad händelse. <a href="../alpha/alpha-events.md">Läs mer</a>
</p>
</td>
</tr>
</tbody>
</table>


## Utgåvan kvartal 2 – juni 2020 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Förbättrad integrering med Adobe Experience Platform</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Följande Adobe Experience Platform-integreringsförbättringar har gjorts:</p>
<ul>
<li><p>Med en ny aktivitet kan man lyssna på Adobe Experience Platform segmentingångar/utgångar så att man kan ta sig in på eller gå vidare på en resa. <a href="../building-journeys/segment-qualification-events.md">Läs mer</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>Adobe Experience Platform segments can now be created and edited without leaving the Journey Orchestration interface, thanks to a new <strong>Segments</strong> tab.<a href="../segment/about-segments.md">Läs mer</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>I den enkla uttrycksredigeraren visas nu Adobe Experience Platform-segment direkt i navigeringsträdet för att göra det möjligt att enkelt konfigurera villkor som"tillhör den här personen segment A?".<a href="../segment/using-a-segment.md">Läs mer</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Journey Orchestration övergår nu automatiskt de steg som utförs på resorna till Adobe Experience Platform. Detta inkluderar potentiella fel som påträffas. Den här informationen kan användas när man vill utföra rapportering och felsökning genom att köra frågor om steg i resehändelser för en viss resa eller för alla resor. <a href="../building-journeys/sharing-overview.md">Läs mer</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>Journey Orchestration kan nu anslutas till Adobe Experience Platform-sandlådor för produktion och icke-produktion. Observera att sandlådor är en betafunktion. <a href="../about/access-management.md#sandboxes">Läs mer</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Förbättringar av resedesignern och testläget</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Följande förbättringar har gjorts för resedesignern och testläget:</p>
<ul>
<li><p>Du kan nu kopiera inklistringsaktiviteter från en resa till en annan och välja 1 eller N reseaktiviteter. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">Läs mer</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>När du har startat en händelse för att en testprofil ska komma in i en resa kan du nu se hur den fortskrider i resan tack vare ett färglagt visuellt flöde. Om det uppstår fel i resan visas även information om felen. <a href="../building-journeys/testing-the-journey.md#firing_events">Läs mer</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>Det <strong>slutförda</strong> resetillståndet har bytt namn till <strong>Stängd (ingen entré)</strong> för att bättre återspegla vad det här läget innebär.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**Andra förbättringar**

För att undvika att för många API-anrop skickas till tredjepartssystem introducerar vi ett nytt offentligt API för att konfigurera &quot;begränsningsregler&quot;. Med begränsningsregler tillåts definitionen av ett maximalt antal anrop till en API-slutpunkt per millisekunder. [Läs mer](../api/capping.md)

Med åtkomstkontroll tillåts nu större detaljrikedom i åtkomsthantering av användare. Effektiv tillgänglighet: 30 juni 2020. [Läs mer](../about/access-management.md#create-product-profile)

Journey Orchestration är nu tillgängligt i APAC (Australiens datacenter). Effektiv tillgänglighet: 30 juni 2020

Gränssnittet i Journey Orchestration finns tillgängligt på japanska.

## Utgåvan kvartal 1 – mars 2020 {#q1-release---march-2020}

**Nyheter?**

<table>
<thead>
<tr>
<th><strong>Förbättringar av testläget</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Följande förbättringar har gjorts i testläget:</p>
<ul>
<li>När en resa använder flera händelser kan du nu utlösa dem individuellt från en rullgardinsmeny på skärmen för <strong>händelsekonfiguration</strong> i testläget. <a href="../building-journeys/testing-the-journey.md#firing_events">Läs mer</a></p></li>
<li><p>När en eller flera <strong>Vänta</strong>-aktiviteter används i en resa kan du nu definiera den tid som varje aktivitet ska vara i testläge. Den förinställda tiden är tio sekunder. Du kan ändra detta med parametern <strong>Väntetid i test</strong> i det nedre vänstra hörnet. <a href="../building-journeys/testing-the-journey.md">Läs mer</a></p><img src="../assets/rn-test.png"/>
</li>
<li>I <strong>testloggarna</strong> visas nu felkoden och felsvaret om ett fel uppstår när ett system från tredje part anropas (datakälla eller åtgärd). <a href="../building-journeys/testing-the-journey.md#viewing_logs">Läs mer</a>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Centraliserad hantering av tidszoner</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>Hantering av tidszoner är nu centraliserad i panelen för reseegenskaper. Två parametrar har lagts till i resans egenskaper:</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>På rullgardinsmenyn <strong>Tidszon</strong> kan du välja en specifik tidszon. Som standard används webbläsarens tidszon. </li>
<li>The <strong>Profile Timezone</strong> checkbox allows you to use the Adobe Experience Platform Profile timezone of the person entering the journey, if available. Annars används den tidszon som definieras på rullgardinsmenyn. Den här funktionen är inte kompatibel med resor som använder händelser som saknar namnrymd.</li>
</ul>
<p>Se avsnitten <a href="../building-journeys/changing-properties.md#timezone">Ändra egenskaper</a> och <a href="../building-journeys/timezone-management.md">Hantera tidszoner</a> för mer information.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Förbättringar av resedesignern</strong><br/></th>
</tr>
</thead>
<tbody>
<tr> 
<td>
<p>Resans <strong>palett</strong> till vänster om resedesignern har förbättrats:</p>
<ul>
<li>Med en ny ikon bredvid <strong>sökfältet</strong> kan du dölja eller visa otillgängliga element på paletten såsom händelser som använder en annan namnrymd än de som används i din resa. Som standard är otillgängliga objekt dolda.</li>
<li>När du använder <strong>sökfältet</strong> visas nu antalet resultat för varje aktivitetskategori på arbetsytan.</li>
<li>Navigeringen mellan de olika aktivitetskategorierna har förbättrats.</li>
</ul>
<p>I resedesignern kan du nu kontrollera att du har tillgång till den senaste versionen av resan. Den här informationen visas bredvid versionsnumret.</p>
<p>När två aktiviteter inte är kopplade till resans <strong>arbetsyta</strong> visas ett varningsmeddelande.</p>
<img src="../assets/rn-canvas.png"/>
<p>Se den <a href="../building-journeys/using-the-journey-designer.md">detaljerade dokumentationen</a> för mer information.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Sammanhangsberoende hjälp</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu finns det sammanhangsberoende hjälp för olika listskärmar i Journey Orchestration (resor, händelser, åtgärder och datakällor). Hjälpen innehåller en kort beskrivning av den aktuella funktionen och du får tillgång till relaterade artiklar och videor.</p>
<p>Klicka på ikonen <img src="../assets/icon-context.png"/> i skärmens övre högra hörn för att visa sammanhangsberoende hjälp. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Andra förbättringar**

* In addition to US, Journey Orchestration is now available in **EMEA**. Ansökan och dokumentationen finns tillgänglig på franska och tyska.

* Experience League är nu integrerad i produkten. Detta förenklar åtkomsten till relaterat innehåll och hjälper dig att få ut mesta möjliga av Experience Cloud. Direktåtkomst till dokumentationen om Journey Orchestration finns tillgänglig längst ned på hjälpfliken. Du kan dessutom klicka på Hjälp > Feedback för att rapportera problem eller dela med dig av dina idéer till Adobe.

* Tangentbordsgenvägen **C**, som du använder för att skapa en ny post, är nu tillgängligt på alla listskärmar såsom resor, datakällor, åtgärder och händelser. [Läs mer](../about/user-interface.md#section_ksq_zr1_ffb)

* Du kan nu **radera** avbrutna resor. Rapporter som är kopplade till dessa raderade resor är inte tillgängliga.

* When browsing through **Adobe Experience Platform fields** (XDM format), you will now see the display name in addition to the field name. Den här informationen hämtas från schemadefinitionen i upplevelsedatamodellen. Det alternativa visningsnamnet visas när det är tillgängligt. Med den här användarvänliga beskrivningen, som är särskilt användbar för eVar-fält, blir det enklare att identifiera fälten. [Läs mer](../about/user-interface.md#friendly-names-display)

## GA-utgåva – december 2019 {#ga-release---december-2019}

Journey Orchestration är nu GA.

Bygg en orkestrering i realtid med hjälp av kontextuella data lagrade i händelser eller datakällor.

Journey Orchestration möjliggör orkestrering i realtid som bygger på kontextuella data från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part. I flöden med flera steg, som kallas för resor, fastställer programmet vilka som är bästa åtgärder för konsumenten utifrån hans/hennes profil och beteende. Detta omfattar både den optimala tidpunkten och typen av åtgärd. Sådana åtgärder kan vara att skicka ett push-meddelande till konsumenten via funktionen transaktionsmeddelanden i Adobe Campaign Standard (kräver Adobe Campaign Standard) eller ett meddelande från en tredje part. Dessa beslut fattas utifrån regler och Sensei-poäng.

[Läs mer](../action/working-with-adobe-campaign.md) om Journey Orchestration

Ytterligare resurser:

* [Självstudiekurser](https://docs.adobe.com/content/help/sv-SE/journey-orchestration-learn/tutorials/understanding-journey-orchestration.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)
