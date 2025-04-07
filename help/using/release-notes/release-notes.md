---
product: adobe campaign
title: Versionsinformation
description: Läs om versionsinformation
feature: Journeys
role: User
level: Beginner
exl-id: b923f7e3-997b-483b-b6ac-eef62fc81a84
source-git-commit: 53e4d6af0e3d5fa2f3870802dc67c6200fec3ce8
workflow-type: tm+mt
source-wordcount: '4462'
ht-degree: 35%

---

# Versionsinformation {#release-notes}

>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} om du vill ha Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._

På den här sidan visas alla nya funktioner och förbättringar för Journey Orchestration. Information om Experience Platform-funktioner finns i följande [versionsinformation](https://experienceleague.adobe.com/docs/experience-platform/release-notes/latest.html).

Länkarna är direkta till [Adobe Journey Optimizer-dokumentationen](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} för funktioner som släppts efter 2022.

## Version från mars 2024 {#mar-rn-2024}

### Förbättringar {#mar-2024-improvements}

Nya mellanliggande statusvärden har lagts till i reseutvecklingscykeln:

* **Publicering**-status mellan **Utkast**-status och **Live**-status
* **Stoppar**-status mellan **Live**-status och **Stoppad**-status
* **Aktiverar testläge** eller **Inaktiverar testläge** mellan statusen **Utkast** och statusen **Utkast (test)**

När en resa befinner sig i ett mellanliggande tillstånd är den skrivskyddad. [Läs mer](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs#filter){target="_blank"}

## Version från februari 2024 {#feb-rn-2024}

### Förbättringar {#feb-2024-improvements}

* **Filtrera dina resor** - Nu kan du använda **anpassade datum för att filtrera lagret för resor**, utöver de befintliga fördefinierade datumfiltren. På så sätt kan du förfina listan genom att visa resor som skapats eller publicerats på ett visst datum, inom en viss månad, under ett helt år eller inom angivna tidsintervall. [Läs mer](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html#filter){target="_blank"}
* **Anpassade åtgärder** - Nu kan du uppdatera rubriken **content-type**. Den nya **innehållstypen** ska referera till JSON-innehåll. [Läs mer](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/about-custom-action-configuration.html#url-configuration){target="_blank"}
* **Configuration** - Attributet identityMap i stepEvents är nu förifyllt. Den primära identiteten definieras som &quot;primär = true&quot;. [Läs mer](https://experienceleague.adobe.com/docs/journey-optimizer/using/reporting/reports/sharing-field-list.html){target="_blank"}
* **Användargränssnitt** - Det översta fältet på skärmar har organiserats om för en förbättrad upplevelse. Bland de olika uppdateringarna kan du lägga märke till att pennikonen som gör att du kan komma åt färgegenskaperna nu visas till vänster om det övre fältet, bredvid resans namn. [Läs mer](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html#change-properties){target="_blank"}

## Version från januari 2024 {#jan-rn-2024}

### Förbättringar {#jan-2024-improvements}

* **Varaktighet för reaktionshändelser** - Den maximala varaktighet som du kan definiera i **reaktionshändelser** är nu 29 dagar i stället för 30. [Läs mer](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/about-journey-building/reaction-events.html){target="_blank"}
* **Fältgrupper** - Den här versionen åtgärdar ett fel som gjorde att fältgrupper inte kunde sparas i vissa fall.
* Stöd för `<listObject>` har ändrats i flera funktioner.

## Version från augusti 2023 {#aug-rn-2023}

### Förbättringar {#aug-2023-improvements}

* Nu kan du utnyttja API-anropssvar i anpassade åtgärder och samordna din resa baserat på dessa svar. Den här funktionen är för närvarande tillgänglig som en privat beta. Se Journey Optimizer [dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/action-response.html){target="_blank"}.

## Version från april 2023 {#apr-rn-2023}

### Förbättringar {#april-2023-improvements}

* Konfigurationsrutans layout, som visas i åtgärder, datakällor, händelser och resor, har förbättrats.
* Nu kan du definiera statiska eller dynamiska frågeparametrar i dina anpassade åtgärder. Se Journey Optimizer [dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/action-journeys/about-custom-action-configuration.html#url-configuration){target="_blank"}.
* Nya garantimöjligheter för att hantera upplevelsetillväxt som Journeys levererar:
   * Vi rekommenderar att du begränsar antalet noder till 50 eller färre för att hålla dina resor upprätt, lättlästa, QA och felsökning. Antalet aktiviteter visas i den övre vänstra delen av arbetsytan. Se Journey Optimizer [dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html#journeys-guardrails-journeys){target="_blank"}
   * När du utvecklar och startar resor kommer vi att meddela dig när du närmar dig milstolpen på 100 resor i realtid. Om dina planer kräver mer än 100 resor i taget kan du skapa en supportanmälan efter att du har fått meddelandet så hjälper vi dig. Se Journey Optimizer [dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html#journeys-guardrails-journeys){target="_blank"}

## Version från mars 2023 {#mar-2023}

### Förbättringar {#mar-2023-improvements}

* Med det nya **Begränsnings-API:t** kan du ange en gräns för hur många händelser som skickas per sekund, vilket förhindrar överväldigande trafiktoppar på externa system eller API. När den angivna gränsen nås ställs alla efterföljande API-anrop i kö och behandlas så snart som möjligt, i den ordning som de togs emot. Observera att den här funktionen bara har stöd för en begränsad konfiguration i alla sandlådor. [Läs mer](../api/throttling.md)
* Resans arbetsyta har förbättrats för en enklare och förbättrad användarupplevelse. I slutet av varje bana på arbetsytan har platshållarna tagits bort. Nu kan du enkelt lägga till dina aktiviteter genom att dra dem i slutet av en bana.
* På arbetsytan för resan ställs etiketten för taggen **End** inte längre in automatiskt med den föregående aktivitetens namn. Användarna kan lägga till en anpassad etikett manuellt vid behov.
* Standardtidsgränsen och fellängden för resans egenskaper har ändrats från 5 till 30 sekunder. Se Journey Optimizer [dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/configuration/configure-journeys/external-systems/external-systems.html#timeout){target="_blank"}.
* Ett skyddsutkast har lagts till i testläget för att endast lyssna på händelser som skickas via gränssnittet. Händelser som skickas via ett externt verktyg beaktas inte. Se Journey Optimizer [dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/testing-the-journey.html){target="_blank"}.

## Version från februari 2023 {#feb-2023}

### Förbättringar {#feb-2023-improvements}

* Fältet **Vänteperiod** för återinträde har lagts till i reseegenskaperna. I det här fältet kan du definiera väntetiden innan du tillåter en profil att gå in på resan igen med en enda resa (med början från en händelse eller en segmentkvalificering). Detta förhindrar att resor utlöses felaktigt flera gånger för samma händelse. Som standard är fältet inställt på 5 minuter. Se Journey Optimizer [dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html#entrance){target="_blank"}.
* Förbättringar har gjorts för **resans start- och slutdatum**. Om du inte har angett något startdatum läggs det nu till automatiskt vid publiceringstidpunkten. Detta gör att profiler kan avslutas automatiskt när datumet nås. Se Journey Optimizer [dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/create-journey/journey-gs.html#dates){target="_blank"}.

## Version från januari 2023 {#jan-2023-release}

### Förbättringar {#jan-2023-improvements}

* När du lägger till en **segmentkvalificering** i en resa är namnutrymmet nu som standard förifyllt med det senast använda namnutrymmet. Se Journey Optimizer [dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/about-journey-building/segment-qualification-events.html#about-segment-qualification){target="_blank"}.
* I arbetsytan på resan finns en ny knapp i verktygsfältet som gör att du kan hämta en skärmbild av din resa.

## September 2022-utgåvan{#sept-2022-release}

### Nya funktioner{#sept-2022-features}


<table>
<thead>
<tr>
<th><strong>Datastyrning och sekretess</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med styrningsramverket DULE (Data Usage Labeling and Enforcement) kan Journey Orchestration nu utnyttja Adobe Experience Platform styrningsprinciper för att förhindra att känsliga fält exporteras till tredjepartssystem via anpassade åtgärder. Om systemet identifierar ett begränsat fält i de anpassade åtgärdsparametrarna visas ett fel som hindrar dig från att publicera resan.</p>
<p>Användningen av etiketter och tvångsåtgärder för användning av data (DULE) är för närvarande begränsad till utvalda kunder och kommer att distribueras till alla miljöer i en framtida version.</p>
<p>Mer information finns i Journey Optimizer <a href="https://experienceleague.adobe.com/docs/journey-optimizer/using/privacy/action-privacy.html">dokumentation</a>.
</td>
</tr>
</tbody>
</table>

### Förbättringar{#sept-2022-improvements}

* Ett nytt skyddsräcke har lagts till för enhetsresor (med början vid en händelse eller en segmentkvalificering) för att förhindra att resor utlöses felaktigt flera gånger för samma händelse. Återinträde av profiler blockeras nu tillfälligt som standard i 5 minuter. Se Journey Optimizer [dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html#events-g){target="_blank"}.

### Andra ändringar{#sept-2022-other}

* För att förbättra prestanda kan inte längre Experience-fältgrupper användas i resor som börjar med en segmentkvalificeringsaktivitet. Denna ändring gäller endast för nya resor. Befintliga beteenden behåller det aktuella beteendet. Se Journey Optimizer [dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/get-started/guardrails.html#expression-editor){target="_blank"}.

### Förbättringar

* **Slutar en resa** - I arbetsytan har aktiviteten **Slut** tagits bort från paletten. Sluttaggar läggs nu till som standard i slutet av varje bana och kan inte tas bort. Denna förbättring gör det möjligt att bättre rapportera var en kund lämnade resan, utan att någon åtgärd krävs från kundens sida. Se Journey Optimizer [dokumentation](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/end-journey.html){target="_blank"}.

* Alternativet **Tidszon för profil** är nu avmarkerat som standard i resans egenskaper. [Läs mer](https://experienceleague.adobe.com/docs/journey-optimizer/using/orchestrate-journeys/manage-journey/timezone-management.html#timezone-from-profiles){target="_blank"}.

## Version från maj 2022 {#may-2022-release}

### Förbättringar

* **Uttrycksredigeraren** - Funktionen [limit](../functions/functionlimit.md) har lagts till så att du kan begränsa antalet objekt i en lista. Med funktionen [sort](../functions/functionsort.md) kan du nu sortera ett listobjekt. Stöd för listObject har också lagts till i funktionerna [disctinct](../functions/functiondistinct.md) och [distinktWithNull](../functions/functiondistinctwithnull.md) .

## Version från mars 2022 {#feb-2022-release}

### Förbättringar

* För att undvika att det finns onödiga fält i det enhetliga profilschemat är händelseschemat för resan som standard inte längre aktiverat för profiler. Om det behövs kan du aktivera det. [Läs mer](../building-journeys/sharing-overview.md)
* Nya steghändelser för exportjobb skickas nu av Journey Optimizer till Adobe Experience Platform. Exempel på frågor har lagts till i dokumentationen. [Läs mer](../building-journeys/query-examples.md)

## Version från februari 2022 {#february-2022-release}

### Förbättringar

* För att optimera prestanda och förhindra föråldrad resursanvändning kommer alla resor i testläge som inte har utlösts på en vecka nu att återgå till statusen Utkast. [Läs mer](../building-journeys/testing-the-journey.md#important_notes)

## Version från januari 2022 {#january-2022-release}

### Förbättringar

* Journey Orchestration steghändelser kan nu länkas till andra datauppsättningar i [Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html){target="_blank"}. Fältet **profileID**, i det inbyggda händelseschemat för kundsteg, har nu definierats som ett identitetsfält. [Läs mer](../building-journeys/sharing-overview.md#integration-cja)
* Begränsningsregeln för Adobe Campaign Standard-åtgärder har ändrats till 4 000 anrop/5 minuter. [Läs mer](../action/working-with-adobe-campaign.md)

## Oktober 2021-versionen {#october-2021-release}

### Förbättringar

* **Uttrycksredigeraren** - Som kraftfull användare kan du nu använda funktioner för att arbeta med kartor. [Läs mer](../expression/field-references.md)
* **Hjälpmedel** - Hjälpmedelsförbättringar har implementerats. Journey Orchestration är nu helt kompatibelt när det gäller tillgänglighet.
* **Samlingar** - Nu stöds arrayer med objekt som innehåller underobjekt. [Läs mer](../usecase/collections.md)
* **Övervakning** - steghändelser för direktresor och testläge har förbättrats. [Nya fält](../building-journeys/sharing-field-list.md#serviceevents) har lagts till i samband med profilexportjobb. För en bättre användarupplevelse är steghändelsefält nu ordnade i olika kategorier i schemat för guidade händelser för resan för Journey Orchestration. Alla föregående steg-händelsefält är fortfarande tillgängliga i kategorin [stepEvents](../building-journeys/sharing-legacy-fields.md).

## September 2021-utgåvan {#september-2021-release}

<table>
<thead>
<tr>
<th><strong>Skicka listor med data dynamiskt med anpassade åtgärder</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Nu kan du skicka samlingar eller en lista med data i dina anpassade åtgärdsparametrar som fylls i dynamiskt vid körning. Det finns två sorters samlingar: enkla samlingar och objektsamlingar. Tidigare skapade anpassade åtgärder fortsätter att fungera. </p>
<p>Mer information om samlingar finns i <a href="../usecase/collections.md">detaljerad dokumentation</a>. </p>
<p>Funktionerna för att filtrera och överlappa har lagts till i listan med funktioner som är tillgängliga i den avancerade uttrycksredigeraren. Det ger fler möjligheter att filtrera och jämföra samlingar.</p>
<p>Läs dokumentationen om funktionerna <a href="../functions/functionfilter.md">filter</a> och <a href="../functions/functionintersect.md">överlappa</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

* Systemgenererade scheman och datauppsättningar som har skapats under etablering av steghändelser är nu skrivskyddade, vilket skyddar mot oavsiktliga ändringar av viktiga scheman. [Läs mer](../building-journeys/sharing-overview.md)
* Etikettera **Wait**-aktiviteten med en etikett som visas på arbetsytan. Etiketten används också i loggar för rapportering och testläge för att tydligt identifiera vad du gör. [Läs mer](../building-journeys/using-the-journey-designer.md)
* Hitta dina händelser och åtgärder snabbare genom att filtrera elementen i kategorierna **Händelser** och **Åtgärd** med hjälp av sökning. Orchestration-aktiviteter är inte längre filtrerade. [Läs mer](../building-journeys/using-the-journey-designer.md)
* När du definierar ett händelse-ID-villkor i en regelbaserad operator är operatorn &quot;contains&quot; nu tillgänglig för strängtyper av fält. [Läs mer](../event/about-creating.md)

## Version från augusti 2021 {#august-2021-release}

### Förbättringar

**Resor**

* **Dynamiska rubriker** - Nu kan du skicka dynamiska data i HTTP-rubrikparametrar. De här parametrarna kan användas av de integreringssystem som tar emot resans åtgärd via HTTP-anrop, till exempel tidsstämpel eller spårnings-ID. [Läs mer](../action/url-configuration.md)
* **Dynamiska URL-sökvägar** - Nu kan du ställa in dynamiska URL-sökvägar för anpassade åtgärder. [Läs mer](../action/url-configuration.md)

## Version från juli 2021 {#july-2021-release}

<table>
<thead>
<tr>
<th><strong>Utnyttja schemarelationer</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Med Adobe Experience Platform kan du definiera relationer mellan scheman för att kunna använda en datauppsättning som en uppslagstabell för en annan. Journey Orchestration kan nu utnyttja data från ett länkat schema.</p>
<p>Dessa fält är tillgängliga i en enhetlig händelsekonfiguration, resevillkor och anpassad åtgärdspersonalisering.
<p>Mer information finns i den <a href="../event/experience-event-schema.md#leverage_schema_relationships">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

* Fältet **Cachevaraktighet** har tagits bort från konfigurationspanelen för datakällan. [Läs mer](../datasource/about-data-sources.md)

## Version från juni 2021 {#june-2021-release}

<table>
<thead>
<tr>
<th><strong> Integrering med Adobe Campaign Classic</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Integrationen med Adobe Campaign Classic är nu GA. Det gör att du kan skicka e-post, push-meddelanden och SMS med hjälp av funktionerna för transaktionsmeddelanden i Adobe Campaign v7 eller v8.</p>
<p>Anslutningen mellan Journey Orchestration- och Campaign-instanserna konfigureras av Adobe vid etableringstidpunkten.</p>
<p>Mer information finns i den <a href="../action/acc-action.md">detaljerade dokumentationen</a>.</p>
</td>
</tr>
</tbody>
</table>

### Förbättringar

* För externa datakällor definieras nu en begränsningsregel på 15 anrop per sekund automatiskt. [Läs mer](../about/external-systems.md#capping)
* De enkla och avancerade uttrycksredigerarna har nu stöd för XDM-datumformatet.
* Ett nytt filter har lagts till på skärmen med reselistan. Du kan nu filtrera efter resetyp: **[!UICONTROL Unitary event]** eller **[!UICONTROL Segment qualification]**. [Läs mer](../about/user-interface.md#section_lgm_hpz_pgb)
* För direktresor visas nu publiceringsdatumet och namnet på den användare som publicerade resan på skärmen för reseegenskaper. Den här informationen är också tillgänglig när du kopierar resans tekniska information. [Läs mer](../building-journeys/changing-properties.md#section_lgm_hpz_pgb)

## Version från april 2021 {#april-2021-release}

### Förbättringar

* I skärmen **Händelsekonfiguration** i testläget visas nu en listruta för fält som förväntar sig en uppräkning. Välj bara ett av de tillgängliga värdena. Detta undviker fel när händelsen utlöses om ett felaktigt värde definieras. [Läs mer](../building-journeys/testing-the-journey.md#firing_events)

## Version från mars 2021 {#march-2021-release}

### Förbättringar

* En ny status har lagts till på resor. När en resa avslutas eller stängs manuellt, ändras dess status från **Stängd** till **Avslutad** 30 dagar efter att den stängdes. På så sätt kan ni enklare identifiera inaktiva resor samtidigt som ni ser till att alla personer fortfarande är närvarande har tid att slutföra resan. [Läs mer](../building-journeys/journey.md#ending_a_journey)
* I de högra aktivitetspanelerna för utkastresor är skrivskyddade fält nu dolda som standard. Den här förenklingen hjälper dig att konfigurera dina aktiviteter enklare. Om du vill visa dem klickar du på ikonen **Visa skrivskyddade fält** som finns i det övre vänstra hörnet i aktivitetskonfigurationsrutan. [Läs mer](../building-journeys/using-the-journey-designer.md#configuration_pane)
* I testläge har namnet på fältet **Nyckel** som används för att definiera testprofilens ID ändrats till **Profilidentifierare** på skärmen **Händelsekonfiguration** för en bättre användarupplevelse. [Läs mer](../building-journeys/testing-the-journey.md).
* För reaktionshändelser kan tidsgränsen nu bara anges mellan 40 sekunder och 30 dagar. När du testar en resa som använder en reaktionshändelse är standardvärdet **[!UICONTROL Wait time]** och minimivärdet nu 40 sekunder. [Läs mer](../building-journeys/reaction-events.md).

## Version från februari 2021 {#february-2021-release}

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
* I den vänstra delen av den avancerade uttrycksredigeraren grupperas funktioner nu om under ett **Funktioner** i slutet av listan.

## Version från januari 2021 {#january-2021-release}

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
<p>Mer information finns i videon <a href="../building-journeys/jump.md">Detaljerad dokumentation</a> och <a href="https://experienceleague.adobe.com/docs/journey-orchestration-learn/tutorials/building-a-journey/jumping-to-another-journey.html">självstudiekurs</a>.</p>
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

Aktiviteten **Segmentkvalificering** kan inte längre användas i en resa som innehåller Campaign Standard meddelandeaktiviteter. Den här begränsningen skyddar integriteten för Adobe Campaign Standard-instanser. Användningen av Segmentkvalificering kan faktiskt leda till dagliga toppar av meddelanden som skulle överbelasta Campaign Standard Transactional Messaging. [Läs mer](../about/limitations.md#segment-qualification)

## Oktober 2020-versionen {#october-release}

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

### Alpha-uppdateringar{#september-alpha-update}

<table>
<thead>
<tr>
<th><strong>Förbättrad läsningssegmentaktivitet</strong><br/></th>
</tr>
</thead>
<tbody>
<tr>
<td>
<p>Följande förbättringar har gjorts i aktiviteten <strong>Lässegment</strong>:
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

## Version från augusti 2020 {#august-release}

### GA-uppdateringar{#august-ga-update}

Nyttolasten för segments kvalificeringshändelser innehåller nu följande sammanhangsinformation som du kan använda i villkor och åtgärder: beteendet (ingång, utgång), tidsstämpeln för kvalificeringen och segment-ID. [Läs mer](../building-journeys/segment-qualification-events.md)

### Alpha-uppdateringar{#august-alpha-update}

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
<li><p>Konfigurationen av transportschemaläggaren har tagits bort från aktivitetens egenskaper. Den är nu tillgänglig direkt från resans egenskaper i ett dedikerat avsnitt som visas om aktiviteten Läsa segment har placerats på arbetsytan. </p>
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

## Alpha-version - juli 2020 {#alpha-release---july-2020}

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
<p>Med aktiviteten för utlösare av segment kan du placera alla personer, som tillhör ett segment i Adobe Experience Platform, i en resa. Ingången till en resa kan genomföras antingen en gång eller regelbundet. 
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


## Q2-utgåvan - juni 2020 {#q2-release---june-2020}

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
<li><p>Adobe Experience Platform-segment kan nu skapas och redigeras utan att lämna Journey Orchestration-gränssnittet, tack vare den nya fliken <strong>Segment</strong> . <a href="../segment/about-segments.md">Läs mer</a></p>
<img src="../assets/rn-segment1.png"/>
</li>
<li><p>I den enkla uttrycksredigeraren visas nu Adobe Experience Platform-segment direkt i navigeringsträdet för att göra det möjligt att enkelt konfigurera villkor som"tillhör den här personen segment A?". <a href="../segment/using-a-segment.md">Läs mer</a></p>
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

## Q1-utgåvan - mars 2020 {#q1-release---march-2020}

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

## GA-release - december 2019 {#ga-release---december-2019}

Journey Orchestration är nu GA.

Bygg en orkestrering i realtid med hjälp av kontextuella data lagrade i händelser eller datakällor.

Journey Orchestration möjliggör orkestrering i realtid som bygger på kontextuella data från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part. I flöden med flera steg, som kallas för resor, fastställer programmet vilka som är bästa åtgärder för konsumenten utifrån hans/hennes profil och beteende. Detta omfattar både den optimala tidpunkten och typen av åtgärd. Sådana åtgärder kan vara att skicka ett push-meddelande till konsumenten via funktionen transaktionsmeddelanden i Adobe Campaign Standard (kräver Adobe Campaign Standard) eller ett meddelande från en tredje part. Dessa beslut fattas utifrån regler och Sensei-poäng.

[Läs mer](../action/working-with-adobe-campaign.md) om Journey Orchestration

Ytterligare resurser:

* [Självstudiekurser](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)
