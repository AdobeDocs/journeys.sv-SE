---
product: adobe campaign
solution: Journey Orchestration
title: Versionsinformation
description: Läs om versionsinformation
feature: Resor
role: Business Practitioner
level: Beginner
exl-id: b923f7e3-997b-483b-b6ac-eef62fc81a84
translation-type: tm+mt
source-git-commit: ae1179e0f9d4b1b3f2b004e4eadfd172637596ce
workflow-type: tm+mt
source-wordcount: '2481'
ht-degree: 63%

---

# Versionsinformation {#release-notes}

På den här sidan listas alla nya funktioner och förbättringar i Journey Orchestration.
Du kan även läsa de senaste [dokumentationsuppdateringarna](../release-notes/documentation-updates.md).

## Version {#april-2021-release} från april 2021

### Förbättringar

* I skärmen **Händelsekonfiguration** i testläget visas nu en listruta för fält som förväntar sig en uppräkning. Välj bara ett av de tillgängliga värdena. Detta undviker fel när händelsen utlöses om ett felaktigt värde definieras. [Läs mer](../building-journeys/testing-the-journey.md#firing_events)

## Mars 2021-utgåvan {#march-2021-release}

### Förbättringar

* En ny status har lagts till på resor. När en resa avslutas eller stängs manuellt växlar dess status från **Closed** till **Finished** 30 dagar efter att den stängdes. På så sätt kan ni enklare identifiera inaktiva resor samtidigt som ni ser till att alla personer fortfarande är närvarande har tid att slutföra resan. [Läs mer](../building-journeys/journey.md#ending_a_journey)
* I de högra aktivitetspanelerna för utkastresor är skrivskyddade fält nu dolda som standard. Den här förenklingen hjälper dig att konfigurera dina aktiviteter enklare. Om du vill visa dem klickar du på ikonen **Visa skrivskyddade fält** som finns i det övre vänstra hörnet i aktivitetskonfigurationsrutan. [Läs mer](../building-journeys/using-the-journey-designer.md#configuration_pane)
* I testläge har fältet **Nyckel** som används för att definiera testprofilens ID ändrats till **Profilidentifierare** på skärmen **Händelsekonfiguration** för en bättre användarupplevelse. [Läs mer](../building-journeys/testing-the-journey.md).
* För reaktionshändelser kan tidsgränsen nu bara anges mellan 40 sekunder och 30 dagar. När du testar en resa som använder en reaktionshändelse är standardläget **[!UICONTROL Wait time]** och minimivärdet 40 sekunder. [Läs mer](../building-journeys/reaction-events.md).

## Februari 2021-utgåvan {#february-2021-release}

<table>
<thead>
<tr>
<th><strong>Uppdatera profilaktivitet</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med den här nya åtgärdsaktiviteten kan du uppdatera en befintlig Adobe Experience Platform-profil med information som kommer från händelsen, en datakälla eller med ett specifikt värde.</p>
<p>Mer information finns i den <a href="../building-journeys/update-profiles.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Andra förbättringar

* När du konfigurerar en händelse är nu endast fält som är obligatoriska för XDM-valideringen förmarkerade som standard. Dessa fält kan inte avmarkeras.
* Ett nytt filter har lagts till på paletten Resa. Det gör att du bara kan visa de fem senaste händelserna och åtgärderna, förutom de som är färdiga. Detta är specifikt för varje användare. Som standard visas alla objekt. [Läs mer](../building-journeys/using-the-journey-designer.md#palette)
* När du påbörjar en ny resa döljs nu element som inte kan släppas på arbetsytan som det första steget. Detta gäller alla åtgärder, villkorsaktiviteten, väntetiden och reaktionen.
* I den vänstra delen av den avancerade uttrycksredigeraren grupperas funktioner nu om under ett **Funktioner**-avsnitt i slutet av listan.

## Utgåvan från januari 2021 {#january-2021-release}

När du väljer ett schema i händelsekonfigurationen markeras endast fält som är obligatoriska för att händelsen ska kunna tas emot av Journey Orchestration. [Läs mer](../event/defining-the-payload-fields.md)

Attribut för reseegenskaper är nu tillgängliga i den enkla uttrycksredigeraren. [Läs mer](../expression/journey-properties.md)

Två nya attribut för resans egenskaper har lagts till (sandboxName och organizationId). [Läs mer](../expression/journey-properties.md)

För att följa Adobe Campaign Standard SLA-avtal definieras nu en begränsning på 13 anrop per sekund automatiskt för Adobe Campaign Standard-åtgärder så snart Adobe Campaign Standard-integreringen är klar. [Läs mer](../action/working-with-adobe-campaign.md)

Tidsgränsen för händelsen anges nu tydligare på tidsgränsen. [Läs mer](../building-journeys/event-activities.md#listening-to-events-during-a-specific-time)

Funktionerna [getListItem](../functions/functiongetlistitem.md) och [split](../functions/functionsplit.md) har lagts till i listan med funktioner som är tillgängliga i den avancerade uttrycksredigeraren. Detta ger fler möjligheter att använda strängberäkning.

## November 2020-utgåvan {#november-release}

<table>
<thead>
<tr>
<th><strong>Hoppa från en resa till en annan</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>En ny åtgärdsaktivitet gör att ni kan skjuta individer från en resa till en annan. Med aktiviteten <strong>Hoppa</strong> kan du:
</p>
<ul>
<li>förenkla utformningen av mycket komplexa resor genom att dela upp dem i flera. </li>
<li>bygga resor baserat på gemensamma och återanvändbara resemönster</li>
</ul>
<p>Mer information finns i <a href="../building-journeys/jump.md">den detaljerade dokumentationen</a> och <a href="https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html">självstudievideon</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Använda reseegenskaper i uttrycksredigeraren</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>I den avancerade uttrycksredigeraren har vi lagt till en ny kategori i listan med fält och funktioner. Det här är den information som hämtats av systemet från direktresor, till exempel rese-ID:t eller de specifika fel som påträffats. Då får ni fler möjligheter när ni bygger era resor. Du kan till exempel meddela tredjepartssystem om ett villkor eller en åtgärd innehåller fel.
</p>
<p>Mer information finns i den <a href="../expression/journey-properties.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr>
<th><strong>Regelbaserade händelser (beta)</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Det finns nu en ny metod för att enklare konfigurera händelser, utan att använda ett eventID: regelbaserade händelser utvärderar om händelsen ska utlösas enligt ett villkor. Du kan fortfarande använda den befintliga metoden, som nu kallas"systemgenererad". Den här funktionen, som har testats bland ett begränsat antal kunder genom Alpha-programmet, är nu tillgänglig i Beta för alla kunder.
</p>
</td>
</tr>
</tbody>
</table>

### Andra förbättringar

Begränsningar har lagts till när nya versioner av en resa skapas. Dessa begränsningar förhindrar alltför stora förändringar i kundresan för att bibehålla en viss enhetlighet mellan versionerna. [Läs mer](../about/limitations.md#journey-versions-limitations)

Det går inte längre att använda aktiviteten **Segmentkvalificering** i en resa som innehåller meddelandeaktiviteter för Campaign Standarder. Den här begränsningen skyddar integriteten för Adobe Campaign Standard-instanser. Användningen av Segmentkvalificering kan faktiskt leda till dagliga toppar av meddelanden som skulle överbelasta Campaign Standarden Transactional Messaging. [Läs mer](../about/limitations.md#segment-qualification)

## Oktober 2020-utgåvan {#october-release}

<table>
<thead>
<tr>
<th><strong>Tidsgräns för händelse</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Du kan nu konfigurera en timeout för en händelse för att få en resa att lyssna på en händelse endast under en viss tid. Du behöver inte längre lägga till en Vänta-aktivitet parallellt med händelsens sökväg för att uppnå detta.
</p>
<p>Mer information finns i den <a href="../building-journeys/event-activities.md#listening-to-events-during-a-specific-time">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Andra förbättringar

* När du publicerar en ny version av en resa avslutas den tidigare versionen automatiskt och ändras till statusen Stängd. [Läs mer](../building-journeys/journey-versions.md)

## September 2020-utgåvan {#september-release}

### GA-uppdateringar{#september-ga-update}

<table>
<thead>
<tr>
<th><strong>Förbättringar av villkorsaktivitet</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>När du lägger till villkor till din resa kan du nu definiera en etikett. Om du använder flera villkor under en resa kan du lättare identifiera dem.
</p>
<p>Mer information finns i den <a href="../building-journeys/condition-activity.md#about_condition">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Alfa-uppdateringar{#september-alpha-update}

<table>
<thead>
<tr>
<th><strong>Förbättrad läsningssegmentaktivitet</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Följande förbättringar har gjorts i aktiviteten <strong>Läs segment</strong>:
</p>
<ul>
<li><p>Segmentbaserade resor visar nu, ovanför arbetsytan, en påminnelse om resans schematyp. Du kan klicka på den här påminnelsen för att komma åt schemakonfigurationsmenyn.</p>
</li>
<li><p>Detaljrikedomen i testlägesloggarna har förbättrats för att visa segmentets exportförloppsstatus.</p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Versionen från augusti 2020 {#august-release}

### GA-uppdateringar{#august-ga-update}

Nyttolasten för segments kvalificeringshändelser innehåller nu följande sammanhangsinformation som du kan använda i villkor och åtgärder: beteendet (ingång, utgång), tidsstämpeln för kvalificeringen och segment-ID. [Läs mer](../building-journeys/segment-qualification-events.md)

### Alfa-uppdateringar{#august-alpha-update}

<table>
<thead>
<tr>
<th><strong>Aktivitet för utlösare av segment</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Följande förbättringar har gjorts i aktiviteten för utlösare av segment:
</p>
<ul>
<li><p>Aktivitetens namn har ändrats till ”Läsa segment”. </p>
</li>
<li><p>Konfigurationen av resans schemaläggare har tagits bort från aktivitetens egenskaper. Den är nu tillgänglig direkt från resans egenskaper i ett dedikerat avsnitt som visas om aktiviteten Läsa segment har placerats på arbetsytan. </p>
</li>
<li><p>Du kan nu testa resan med en enhetlig profil och följa förloppet i den med hjälp av det visuella flödet.</p>
</li>
</ul>
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
<li><p>Du kan nu utnyttja alla händelsedata från beteenden i Adobe Analytics som du redan samlar in och strömmar till plattformen för att utlösa resor och automatisera kundernas upplevelser. <a href="../event/about-analytics.md">Läs mer</a></p>
</li>
<li><p>När du utlöser en regelbaserad händelse i testläget kan du nu direkt se villkorets händelse-ID. Dessutom har ett verktygstips lagts till bredvid varje fält som en del av regelutvärderingen. <a href="../building-journeys/testing-the-journey.md#test-rule-based">Läs mer</a></p>
</li>
<li><p>Den regelbaserade skärmen för händelsedefinition har omorganiserats för att leverera en bättre upplevelse. <a href="../event/about-creating.md">Läs mer</a></p>
</li>
</ul>
</td>
</tr>
</tbody>
</table>

## Alfaaversion – juli 2020 {#alpha-release---july-2020}

Programmets alfaversion har funktioner som för närvarande testas bland ett begränsat antal kunder. På så sätt kan vi förbättra vår produkt baserat på den feedback vi får. De här funktionerna är inte tillgängliga för alla kunder som använder Journey Orchestration.

<table>
<thead>
<tr>
<th><strong>Förbättrat användargränssnitt</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Navigeringen bland menyerna i Journey Orchestration har förbättrats så att gränssnittet med Adobe Experience Platform blir konsekvent:
</p>
<ul>
<li><p>Menyer har flyttats från den övre delen till den vänstra sidan av gränssnittet. </p>
</li>
<li><p>Gruppering av administratörsfunktioner i en enda kontrollpanel.</p>
</li>
</ul>
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
<p>Med aktiviteten för utlösare av segment kan du placera alla personer, som tillhör ett segment i Adobe Experience Platform, i en resa. Inträde i en resa kan genomföras antingen en gång eller regelbundet. 
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
<p>Vi har förenklat hur du konfigurerar upplevelsehändelser. Vi introducerar en ny metod som inte kräver att ett händelse-ID används. När du konfigurerar en händelse i Journey Orchestration kan du nu definiera en regelbaserad händelse. <a href="../event/about-events.md">Läs mer</a>
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
<p>Följande förbättringar gällande integreringen i Adobe Experience Platform har gjorts:</p>
<ul>
<li><p>En ny aktivitet tillåter avläsning av ett segments ingångar/utgångar i Adobe Experience Platform för att få människor att komma in i eller gå framåt i en resa. <a href="../building-journeys/segment-qualification-events.md">Läs mer</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>Segment i Adobe Experience Platform kan nu skapas och redigeras utan att man lämnar gränssnittet i Journey Orchestration tack vare en ny flik för <strong>segment</strong> . <a href="../segment/about-segments.md">Läs mer</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>I den enkla uttrycksredigeraren visas nu segment i Adobe Experience Platform direkt i navigeringsträdet så att man enkelt kan konfigurera villkor såsom ”tillhör den här personen segment A?”. <a href="../segment/using-a-segment.md">Läs mer</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Journey Orchestration skickar nu automatiskt de steg som har körts i resorna till Adobe Experience Platform. Detta inkluderar potentiella fel som påträffas. Den här informationen kan användas när man vill utföra rapportering och felsökning genom att köra frågor om steg i resehändelser för en viss resa eller för alla resor. <a href="../building-journeys/sharing-overview.md">Läs mer</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
<li><p>Journey Orchestration kan nu anslutas till sandlådor i Adobe Experience Platform för produktion och icke-produktion. Observera att sandlådor är en betafunktion. <a href="../about/access-management.md#sandboxes">Läs mer</a></p>
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
<li>I kryssrutan <strong>Tidszonsprofil</strong> kan du använda tidszonen från profilen i Adobe Experience Platform (om den är tillgänglig) för den person som påbörjar resan. Annars används den tidszon som definieras på rullgardinsmenyn. Den här funktionen är inte kompatibel med resor som använder händelser som saknar namnrymd.</li>
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

* Förutom i USA finns nu även Journey Orchestration tillgänglig i **EMEA**. Ansökan och dokumentationen finns tillgänglig på franska och tyska.

* Experience League är nu integrerad i produkten. Detta förenklar åtkomsten till relaterat innehåll och hjälper dig att få ut mesta möjliga av Experience Cloud. Direktåtkomst till dokumentationen om Journey Orchestration finns tillgänglig längst ned på hjälpfliken. Du kan dessutom klicka på Hjälp > Feedback för att rapportera problem eller dela med dig av dina idéer till Adobe.

* Tangentbordsgenvägen **C**, som du använder för att skapa en ny post, är nu tillgängligt på alla listskärmar såsom resor, datakällor, åtgärder och händelser. [Läs mer](../about/user-interface.md#section_ksq_zr1_ffb)

* Du kan nu **radera** avbrutna resor. Rapporter som är kopplade till dessa raderade resor är inte tillgängliga.

* När du bläddrar bland **datafälten i Adobe Experience Platform** (XDM-format) visas nu även visningsnamnet tillsammans med fältnamnet. Den här informationen hämtas från schemadefinitionen i upplevelsedatamodellen. Det alternativa visningsnamnet visas när det är tillgängligt. Med den här användarvänliga beskrivningen, som är särskilt användbar för eVar-fält, blir det enklare att identifiera fälten. [Läs mer](../about/user-interface.md#friendly-names-display)

## GA-utgåva – december 2019 {#ga-release---december-2019}

Journey Orchestration är nu GA.

Bygg en orkestrering i realtid med hjälp av kontextuella data lagrade i händelser eller datakällor.

Journey Orchestration möjliggör orkestrering i realtid som bygger på kontextuella data från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part. I flöden med flera steg, som kallas för resor, fastställer programmet vilka som är bästa åtgärder för konsumenten utifrån hans/hennes profil och beteende. Detta omfattar både den optimala tidpunkten och typen av åtgärd. Sådana åtgärder kan vara att skicka ett push-meddelande till konsumenten via funktionen transaktionsmeddelanden i Adobe Campaign Standard (kräver Adobe Campaign Standard) eller ett meddelande från en tredje part. Dessa beslut fattas utifrån regler och Sensei-poäng.

[Läs mer](../action/working-with-adobe-campaign.md) om Journey Orchestration

Ytterligare resurser:

* [Självstudiekurser](https://docs.adobe.com/content/help/sv-SE/journey-orchestration-learn/tutorials/understanding-journey-orchestration.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)
