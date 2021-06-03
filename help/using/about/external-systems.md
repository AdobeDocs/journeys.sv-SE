---
product: adobe campaign
solution: Journey Orchestration
title: Integrera med externa system
description: Lär dig de bästa sätten att integrera externa system
feature: Resor
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: 5d2e82c10dd22b5b4bac15a78a2f6f592aedd371
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 1%

---

# Integrera med externa system {#external-systems}

På den här sidan presenteras de olika skyddsmekanismer som Journey Orchestration tillhandahåller när ett externt system integreras, samt bästa praxis: hur du optimerar skyddet för ditt externa system med API:t för appning, hur du konfigurerar timeout för resan och hur nya försök fungerar.

I Journey Orchestration kan du konfigurera anslutningar till externa system via anpassade datakällor och anpassade åtgärder. På så sätt kan du t.ex. berika dina resor med data från ett externt bokningssystem eller skicka meddelanden med ett tredjepartssystem som Epsilon eller Facebook.

När du integrerar ett externt system kan du stöta på flera problem, systemet kan vara långsamt, det kan sluta svara eller så kanske det inte kan hantera en stor volym. Journey Orchestration erbjuder flera skyddsräcken för att skydda systemet från överbelastning.

Alla externa system har olika prestanda. Du måste anpassa konfigurationen efter dina användningsfall.

När Journey Orchestration gör ett anrop till ett externt API körs de tekniska garantierna enligt följande:

1. Takregler tillämpas: om den maximala hastigheten uppnås, tas återstående anrop bort.

2. Timeout och försök igen: Om begränsningsregeln är uppfylld försöker Journey Orchestration genomföra anropet tills tidsgränsen är slut.

## Takning{#capping}

Det inbyggda Capping API:t erbjuder ett tekniskt skyddsräcke som hjälper till att skydda ditt externa system. Innan du gör det måste du utvärdera kapaciteten för det externa API:t. Om Journey Orchestration t.ex. skickar 1 000 samtal per sekund och systemet bara har stöd för 100 samtal per sekund, måste du definiera en spärrregel så att systemet inte blir mättat.

Takregler definieras på sandlådenivå för en specifik slutpunkt (URL:en anropas). Vid körning verifierar Journey Orchestration om det finns en definierad begränsningsregel och tillämpar den definierade hastigheten under anropen till den slutpunkten. Om antalet anrop överstiger den definierade hastigheten, ignoreras de återstående samtalen och räknas som fel i rapporteringen.

En begränsningsregel är specifik för en slutpunkt men global för alla resor i en sandlåda. Detta innebär att takplatser delas mellan alla resor i en sandlåda.

Anta till exempel att du har definierat en begränsning på 100 anrop per sekund för det externa systemet. Ditt system anropas av en anpassad åtgärd på tio olika resor. Om en resa tar emot 200 samtal per sekund används de 100 tillgängliga kortplatserna och de 100 återstående kortplatserna tas bort. Eftersom den högsta nivån har överskridits kommer de övriga nio resorna inte att ha några platser kvar. Denna granularitet hjälper till att skydda det externa systemet från överbelastning och krascher.

Mer information om API:t för capping och hur du konfigurerar regler för capping finns på [den här sidan](../api/capping.md).

## Timeout och försök igen{#timeout}

Om begränsningsregeln är uppfylld tillämpas timeoutregeln.

Under varje resa kan du definiera en tidsgräns. Detta gör att du kan ange en maximal varaktighet när du anropar ett externt system. Tidsgränsen har konfigurerats i egenskaperna för en resa. Se [den här sidan](../building-journeys/changing-properties.md#timeout_and_error).

Den här tidsgränsen är global för alla externa anrop (externa API-anrop i anpassade åtgärder och anpassade datakällor). Som standard är den inställd på 5 sekunder.

Under den angivna tidsgränsen försöker Journey Orchestration anropa det externa systemet. Efter det första anropet kan högst tre försök utföras tills tidsgränsen för timeout har nåtts. Antalet försök kan inte ändras.

Varje nytt försök använder en kortplats. Om du har ett tak på 100 samtal per sekund och vart och ett av dina samtal kräver två försök, kommer hastigheten att sänkas till 30 samtal per sekund (varje samtal använder 3 platser: första samtalet och två försök).

Tidsgränsvärdet beror på användningsfallet. Om du snabbt vill skicka ditt meddelande, till exempel när klienten kommer till butiken, vill du inte ange en lång tidsgräns. Ju längre tidsgränsen är, desto fler objekt placeras i kö. Detta kan i hög grad påverka prestandan. Om Journey Orchestration utför 1 000 anrop per sekund kan systemet snabbt överbelastas om 5 eller 15 sekunder data sparas.

Låt oss ta ett exempel i 5 sekunder.

* Det första anropet varar mindre än 5 sekunder: anropet lyckades, inga nya försök utförs.
* Det första samtalet varar längre än 5 sekunder: samtalet avbryts och inget nytt försök görs. Den räknas som ett timeout-fel vid rapportering.
* Det första anropet misslyckas efter 2 sekunder (det externa systemet returnerar ett fel): 3 sekunder kvar för återförsök, om det finns lediga platser.
   * Om ett av de tre försöken lyckas före slutet av de fem sekunderna utförs anropet och det finns inget fel.
   * Om tidsgränsen nås under återförsöken avbryts anropet och räknas som ett timeout-fel i rapporteringen.

## Frågor och svar{#faq}

**Hur konfigurerar jag en capping-regel? Finns det en standardregel för capping?**

Som standard finns det ingen begränsning. Takregler definieras på sandlådenivå för en specifik slutpunkt (den URL som anropas) med API:t för begränsning. Se [det här avsnittet](../about/external-systems.md#capping) och [den här sidan](../api/capping.md).

**Hur många försök utförs? Kan jag ändra antalet återförsök eller definiera en minimal vänteperiod mellan återförsök?**

För ett visst anrop kan högst tre försök utföras efter det första anropet, tills tidsgränsen för anropet har nåtts. Antalet försök och tiden mellan varje nytt försök kan inte ändras. Se [det här avsnittet](../about/external-systems.md#timeout).

**Var kan jag konfigurera tidsgränsen? Finns det ett maxvärde?**

Under varje resa kan du definiera en tidsgräns. Tidsgränsen har konfigurerats i egenskaperna för en resa. Tidsgränsen måste vara mellan 1 och 30 sekunder. Se [det här avsnittet](../about/external-systems.md#timeout) och [den här sidan](../building-journeys/changing-properties.md#timeout_and_error).