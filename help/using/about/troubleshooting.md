---
title: Felsökning
description: Läs mer om felsökning
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: e579936cfe5eb43caf72627004f98a5746c7abb1

---


# Felsökning{#concept_nlv_bcv_2fb}

I det här avsnittet hittar du hur du felsöker resor innan du testar eller publicerar. Alla kontroller som anges nedan kan utföras när resan är i testläge eller när resan är live. Rekommendationen är att göra alla kontroller nedan i testläge och sedan gå vidare till publiceringen. Se [](../building-journeys/testing-the-journey.md).

## Söker efter fel före testning{#section_h3q_kqk_fhb}

Kontrollera att alla aktiviteter är korrekt konfigurerade innan du testar och publicerar din resa. Du kan inte utföra tester eller publikationer om fel fortfarande upptäcks av systemet.

Fel visas med en varningssymbol på aktiviteterna på arbetsytan. Placera markören på utropstecknet för att visa felmeddelandet. Om du klickar på aktiviteten visas raden med en varning. Om ett obligatoriskt fält till exempel är tomt visas ett fel.

![](../assets/journey63.png)

Om två aktiviteter inte är kopplade visas en varning på arbetsytan.

![](../assets/canvas-disconnected.png)

Bredvid **[!UICONTROL Test]** växlingsknappen och **[!UICONTROL Publish]** knappen kan ett varningstecken visas. Den här varningssignalen visar fel som upptäckts av systemet och förhindrar aktivering av testläget eller publicering av resan. Vanligtvis är fel som upptäcks av systemet länkade till fel som visas i aktiviteterna, men ibland är de länkade till andra problem. I det här fallet kan du visa dem och försöka identifiera problemet med hjälp av felbeskrivningen. Om du inte kan identifiera problemet kan du kopiera informationen och skicka den till administratören eller till supporten. Observera att fel som blockerar testet och fel som blockerar publikationen är liknande.

Systemet upptäcker två typer av problem: fel och varningar. Fel vid blockpublicering och testaktivering. Varningar indikerar potentiella problem som inte blockerar testaktivering eller publicering. Du får en beskrivning av problemet och ett ID för felloggen av typen ERR_XXX_XXX. Detta hjälper teknisk support att identifiera problemet.

Det går att visa två olika färger på tecknet bredvid **[!UICONTROL Test]** växlingsknappen och **[!UICONTROL Publish]** knappen. Tecknet visas i rött vid fel. Den visas med orange om det finns varningsmeddelanden.

![](../assets/journey75.png)

Fel och varningar som är globala för resan visas först i listan. Fel och varningar som rör specifika aktiviteter listas efter, efter aktivitetsordning eller utseende under resan från vänster till höger. Knappen **[!UICONTROL Copy details]** kopierar teknisk information om den resa som supportteamet kan använda för att felsöka.

## Kontrollera att händelser skickas korrekt{#section_rqz_11t_dgb}

Startpunkten för en resa är alltid en händelse. Du kan utföra tester med verktyg som Postman.

Du kan kontrollera om API-anropet som du skickar via dessa verktyg skickas korrekt eller inte. Om du får tillbaka ett fel betyder det att ditt samtal har ett problem. Kontrollera nyttolasten igen, rubriken (och särskilt organisations-ID) och mål-URL:en. Du kan fråga administratören vilken URL som ska användas.

Händelser skickas inte direkt från källan till resesamordning. Journey Orchestration bygger på Experience Platforms API:er för direktuppspelning. Om det gäller händelserelaterade problem kan du därför gå till den här [sidan](https://docs.adobe.com/content/help/en/experience-platform/ingestion/streaming/troubleshooting.html) för felsökning av API:er för direktuppspelning.

## Kontrollerar om någon kommer in på resan{#section_x4v_zzs_dgb}

Resesamordning rapporterar människors inträde på en resa i realtid.

Om du lyckas skicka evenemanget men inte ser något inträde på resan betyder det att något går fel mellan det skickade evenemanget och det mottagande evenemanget under resan.

Här är några saker som administratören bör kontrollera:

* Är du säker på att resan där du förväntar dig att den inkommande händelsen ska vara i testläge eller live?
* Sparade du händelsen innan du kopierade nyttolasten från nyttolastförhandsvisningen?
* Innehåller händelsens nyttolast ett händelse-ID?
* Slog du rätt URL?
* Följde du nyttolaststrukturen för API:erna för direktuppspelning av inmatning med hjälp av förhandsgranskningen av nyttolaststrukturen i händelsekonfigurationsfönstret? Se [](../event/previewing-the-payload.md).
* Använde du rätt nyckel/värde-par i huvudet på din händelse?

   ```
   X-gw-ims-org-id - your ORGID
   Content-type - application/json
   ```

## Kontrollera hur människor navigerar genom resan{#section_l5y_yzs_dgb}

Rapportering om resesamordning mäter enskilda personers framsteg inom en resa. Det är enkelt att identifiera var och varför en person stoppades.

Här är några saker att kontrollera:

* Är det på grund av ett tillstånd som utesluter personen? Villkoret är till exempel&quot;kön = man&quot; och personen är en kvinna. Den här kontrollen kan utföras av en affärsanvändare om villkoret inte är för komplext.
* Orsaken är att ett anrop till en datakälla inte svarar? När resan är i testläge kan denna information visas i testlägesloggar. När resan är live kan en administratör testa direktanrop till datakällan och kontrollera svaret som tas emot. En administratör kan även duplicera resan och testa den.

## Kontrollera att meddelanden har skickats{#section_qb1_yzs_dgb}

Om enskilda personer flödar rätt väg på resan men inte får meddelanden som de ska ta emot, kan du kontrollera om:

* Transactional Messaging har tagit korrekt hänsyn till begäran om att skicka meddelandet. En företagsanvändare kan komma åt det transaktionsmeddelande som ska skickas och kontrollera om tidpunkten för den senaste körningen motsvarar körningstiden för din resa. Han kan även kontrollera de senaste API-anropen/händelserna som tagits emot av transaktionsmeddelanden.
* Meddelandet har skickats via transaktionsmeddelanden. I de sändande loggarna för transaktionsmeddelandet kan du se status för varje körning. Du kan se om det är grönt, rött och vad det var frågan om. En företagsanvändare kan komma åt den här skärmen och skicka loggarna till en administratör för ytterligare undersökningar.

Om ett meddelande skickas via en anpassad åtgärd är det enda som kan kontrolleras under resan att anropet till den anpassade åtgärdens system leder till ett fel eller inte. Om anropet till det externa system som är kopplat till den anpassade åtgärden inte leder till ett fel, men inte leder till att ett meddelande skickas, bör vissa undersökningar utföras på den externa datorns sida.

