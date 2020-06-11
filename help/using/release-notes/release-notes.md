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
source-git-commit: 556dbe88d2717a387e5f0ce8795c9fa02a45ac6f
workflow-type: tm+mt
source-wordcount: '1098'
ht-degree: 0%

---


# Versionsinformation {#release-notes}

På den här sidan visas alla nya funktioner och förbättringar för resesamordning.
Du kan även läsa [Dokumentationsuppdateringar](../release-notes/documentation-updates.md).

## Q2-utgåvan - juni 2020 {#q2-release---june-2020}

<table>
<thead>
<tr>
<th><strong>Förbättringar av integrationen med Adobe Experience Platform</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Följande plattformsintegreringsförbättringar har gjorts:</p>
<ul>
<li><p>Med en ny aktivitet kan man lyssna på Platform-segmentets ingångar/utgångar för att få människor att komma in på eller gå framåt under en resa. <a href="../building-journeys/event-activities.md#segment-qualification">Läs mer</a></p>
<img src="../assets/rn-segment7.png"/>
</li>
<li><p>Tack vare den nya fliken <strong>Segment</strong> kan du nu skapa och redigera plattformssegment utan att lämna gränssnittet för guidad redigering.<a href="../segment/about-segments.md">Läs mer</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>I den enkla uttrycksredigeraren visas nu plattformssegment direkt i navigeringsträdet så att du enkelt kan konfigurera villkor som"tillhör den här personen segment A?".<a href="../segment/using-a-segment.md">Läs mer</a></p>
<img src="../assets/rn-segment4.png"/>
</li>
<li><p>Resesamordning skickas nu automatiskt de steg som utförs under resor till Adobe Data Platform. Detta inkluderar potentiella fel som påträffats. Den här informationen kan användas för att utföra rapportering och felsökning genom att köra frågor om steg-händelser för en viss resa eller för alla resor. <a href="../building-journeys/sharing-overview.md">Läs mer</a></p>
<img src="../assets/rn-journeystepevent.png"/>
</li>
</li>
<li><p>Resesamordning kan nu kopplas till sandlådor för produktionsplattform och icke-produktionsplattform. Observera att sandlådor är en betafunktion. Effektiv tillgänglighet: 30 juni 2020. <a href="../about/access-management.md#sandboxes">Läs mer</a></p>
</li>
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
<li><p>Nu kan du kopiera inklistringsaktiviteter från en resa till en annan, och välja 1 eller N reseaktiviteter. <a href="../building-journeys/using-the-journey-designer.md#copy-paste">Läs mer</a></p>
<img src="../assets/rn-copy-paste1.png"/>
</li>
<li><p>När du har startat en händelse för att få en testprofil att ta sig in på en resa kan du nu se hur den fortskrider under resan tack vare ett färgat visuellt flöde. Om det uppstår fel under resan visas även information om fel. <a href="../building-journeys/testing-the-journey.md#firing_events">Läs mer</a></p>
<img src="../assets/rn-journeytest6.png"/>
</li>
<li>Det <strong>färdiga</strong> resetillståndet har bytt namn till <strong>Stängd (ingen entré)</strong> för att bättre återspegla vad det här läget innebär.</li>
</ul>
</td>
</tr>
</tbody>
</table>

**Andra förbättringar**

För att undvika att skicka för många API-anrop till tredjepartssystem introducerar vi ett nytt offentligt API för att konfigurera &quot;appningsregler&quot;. Begränsningsregler tillåter definition av ett maximalt antal anrop till en API-slutpunkt per millisekunder. [Läs mer](../api/capping.md)

Åtkomstkontroll ger nu större detaljrikedom i hanteringen av användaråtkomst. Effektiv tillgänglighet: 30 juni 2020. [Läs mer](../about/access-management.md#create-product-profile)

Resesamordning är nu tillgängligt i APAC (Australiens datacenter). Effektiv tillgänglighet: 30 juni 2020

Gränssnittet för guidad redigering är tillgängligt på japanska.

## Q1-utgåvan - mars 2020 {#q1-release---march-2020}

**Vad är nytt?**

<table>
<thead>
<tr>
<th><strong>Förbättringar av testläge</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Följande förbättringar har gjorts i testläget:</p>
<ul>
<li>När en resa använder flera händelser kan du nu utlösa var och en av dem individuellt från en nedrullningsbar lista på skärmen för <strong>händelsekonfiguration</strong> i testläget. <a href="../building-journeys/testing-the-journey.md#firing_events">Läs mer</a></p></li>
<li><p>När en eller flera <strong>Wait</strong> -aktiviteter används i en resa kan du nu definiera den tid som varje aktivitet ska vara i testläge. Standardtiden är 10 sekunder. Du kan ändra detta med parametern <strong>Väntetid i test</strong> i det nedre vänstra hörnet. <a href="../building-journeys/testing-the-journey.md">Läs mer</a></p><img src="../assets/rn-test.png"/>
</li>
<li>I <strong>testloggarna</strong>visas felkoden och felsvaret om ett fel uppstår när ett system från tredje part anropas (datakälla eller åtgärd). <a href="../building-journeys/testing-the-journey.md#viewing_logs">Läs mer</a>
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
<p>Tidszonshanteringen är nu centraliserad i panelen för reseegenskaper. Två parametrar har lagts till i resans egenskaper:</p>
<img src="../assets/rn-timezone.png"/>
<ul>
<li>I listrutan <strong>Tidszon</strong> kan du välja en viss tidszon. Som standard används webbläsarens tidszon. </li>
<li>I kryssrutan Tidszon för <strong>profil</strong> kan du använda tidszonen Experience Platform-profil för den person som går in på resan, om den är tillgänglig. Annars används den tidszon som definieras i listrutan. Den här funktionen är inte kompatibel med resor som använder händelser som inte har något namnutrymme.</li>
</ul>
<p>Mer information finns i avsnitten <a href="../building-journeys/changing-properties.md#timezone">Ändra egenskaper</a> och <a href="../building-journeys/timezone-management.md">Tidszonshantering</a> .</p>
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
<p>Färdpaletten <strong>till vänster</strong>har förbättrats:</p>
<ul>
<li>Med en ny ikon bredvid <strong>sökfältet</strong> kan du dölja eller visa otillgängliga element på paletten, till exempel händelser som använder ett annat namnutrymme än de som används under din resa. Som standard är otillgängliga objekt dolda.</li>
<li>När du använder <strong>sökfältet</strong> visas nu antalet resultat för varje aktivitetskategori på arbetsytan.</li>
<li>Navigeringen mellan de olika aktivitetskategorierna har förbättrats.</li>
</ul>
<p>I resedesignern kan du nu kontrollera att du har tillgång till den senaste versionen av resan. Den här informationen visas bredvid versionsnumret.</p>
<p>När två aktiviteter inte är kopplade till <strong>arbetsytan</strong>på resan visas ett varningsmeddelande.</p>
<img src="../assets/rn-canvas.png"/>
<p>Mer information finns i den <a href="../building-journeys/using-the-journey-designer.md">detaljerade dokumentationen</a>.</p>
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
<p>Det finns nu sammanhangsbaserad hjälp för de olika listskärmarna för resesamordning (resor, händelser, åtgärder och datakällor). På så sätt kan du visa en kort beskrivning av den aktuella funktionen och få tillgång till relaterade artiklar och videoklipp.</p>
<p>Om du vill visa sammanhangsberoende hjälp klickar du på <img src="../assets/icon-context.png"/> ikonen i skärmens övre högra hörn. </p>
<img src="../assets/rn-context.png"/>
</td>
</tr>
</tbody>
</table>

**Andra förbättringar**

* Förutom i USA finns nu även Journeys Orchestration i **EMEA**. Ansökan och dokumentationen finns på franska och tyska.

* Experience League är nu integrerat i produkten. Detta förenklar åtkomsten till relaterat innehåll och hjälper er att få ut mesta möjliga av Experience Cloud. Direktåtkomst till dokumentationen för resesamordning finns längst ned på fliken Hjälp. Klicka dessutom på Hjälp > Feedback för att rapportera problem eller dela med dig av dina idéer till Adobe.

* Kortkommandot **C** , som gör att du kan skapa ett nytt objekt, är nu tillgängligt på alla listskärmar: resor, datakällor, åtgärder och händelser. [Läs mer](../about/user-interface.md#section_ksq_zr1_ffb)

* Du kan nu **ta bort** avbrutna resor. Rapporter som är kopplade till dessa raderade resor är inte tillgängliga.

* När du bläddrar bland **dataplattfält** (XDM-format) visas visningsnamnet förutom fältnamnet. Den här informationen hämtas från schemadefinitionen i Experience Data Model. Om det är tillgängligt visas det alternativa visningsnamnet. Den här användarvänliga beskrivningen, som är särskilt användbar för eVar-fält, gör det enklare att identifiera fälten. [Läs mer](../about/user-interface.md#friendly-names-display)

## GA-release - december 2019 {#ga-release---december-2019}

Journey Orchestration är nu GA.

Bygg realtidssamordning med hjälp av kontextuella data lagrade i händelser eller datakällor.

Journey Orchestration möjliggör realtidssamordning som bygger på kontextuella data från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part. I flerstegsflöden som kallas resor bestämmer programmet vilka av de bästa åtgärder som är specifika för konsumenten utifrån deras profil och beteende. Detta omfattar både den optimala tidpunkten och typen av åtgärd, till exempel att skicka ett push-meddelande till konsumenten via transaktionsmeddelandefunktionerna i Adobe Campaign Standard (kräver Adobe Campaign Standard) eller ett meddelande om ett tredjepartssystem. Dessa beslut fattas utifrån regler och Sensei-poäng.

[Läs mer](../action/working-with-adobe-campaign.md) om Journey Orchestration.

Ytterligare resurser:

* [Självstudiekurser](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)
