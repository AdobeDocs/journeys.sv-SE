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
source-git-commit: 6274426ec04315149fb430b847498c0e20164bae

---


# Versionsinformation {#release-notes}

På den här sidan visas alla nya funktioner och förbättringar för resesamordning.
Du kan även läsa [Dokumentationsuppdateringar](../release-notes/documentation-updates.md).

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
<li>I listrutan <strong>Tidszon</strong> kan du välja en viss tidszon. Som standard används webbläsarens tidszon.</li>
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
<li>Med en ny ikon bredvid **Search**-fältet kan du dölja eller visa otillgängliga element på paletten, till exempel händelser som använder ett annat namnutrymme än de som används under resan. Som standard är otillgängliga objekt dolda.</li>
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

* När du bläddrar bland **dataplattfält** (XDM-format) visas visningsnamnet förutom fältnamnet. Den här informationen hämtas från schemadefinitionen i Experience Data Model. Om det är tillgängligt visas det alternativa visningsnamnet. Den här användarvänliga beskrivningen, som är särskilt användbar för eVar-fält, gör det enklare att identifiera fälten. [Läs mer](../event/defining-the-payload-fields.md)

## GA-release - december 2019 {#ga-release---december-2019}

Journey Orchestration är nu GA.

Bygg realtidssamordning med hjälp av kontextuella data lagrade i händelser eller datakällor.

Journey Orchestration möjliggör realtidssamordning som bygger på kontextuella data från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part. I flerstegsflöden som kallas resor bestämmer programmet vilka av de bästa åtgärder som är specifika för konsumenten utifrån deras profil och beteende. Detta omfattar både den optimala tidpunkten och typen av åtgärd, till exempel att skicka ett push-meddelande till konsumenten via transaktionsmeddelandefunktionerna i Adobe Campaign Standard (kräver Adobe Campaign Standard) eller ett meddelande om ett tredjepartssystem. Dessa beslut fattas utifrån regler och Sensei-poäng.

[Läs mer](../action/working-with-adobe-campaign.md) om Journey Orchestration.

Ytterligare resurser:

* [Självstudiekurser](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)