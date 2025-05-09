---
product: adobe campaign
solution: Journey Orchestration
title: Integrera med externa system
description: Lär dig de bästa sätten att integrera externa system
feature: Journeys
role: User
level: Beginner
exl-id: e39218bd-fa6e-443f-9843-92b7a07070fa
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1084'
ht-degree: 5%

---

# Integrering med externa system {#external-systems}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._



På den här sidan visas de olika säkerhetsutkast som Journey Orchestration ger när ett externt system integreras, liksom de bästa sätten: hur man optimerar skyddet för det externa systemet med API:t för appning, hur man konfigurerar tidsgränsen för resan och hur försök fungerar igen.

Med Journey Orchestration kan du konfigurera anslutningar till externa system via anpassade datakällor och anpassade åtgärder. På så sätt kan du till exempel berika dina resor med data från ett externt bokningssystem eller skicka meddelanden med ett tredjepartssystem som Epsilon eller Facebook.

När du integrerar ett externt system kan du stöta på flera problem, systemet kan vara långsamt, det kan sluta svara eller så kanske det inte kan hantera en stor volym. Journey Orchestration erbjuder flera skyddsräcken för att skydda datorn mot överbelastning.

Alla externa system har olika prestanda. Du måste anpassa konfigurationen efter dina användningsfall.

När Journey Orchestration gör ett anrop till ett externt API körs de tekniska garantierna enligt följande:

1. Begränsningsregler tillämpas: om den högsta nivån uppnås ignoreras återstående anrop.

2. Timeout och försök igen: om begränsningsregeln är uppfylld försöker Journey Orchestration genomföra anropet tills tidsgränsen har nåtts.

## Takning{#capping}

Det inbyggda Capping API:t erbjuder ett tekniskt skyddsräcke som hjälper till att skydda ditt externa system.

För externa datakällor är det maximala antalet anrop per sekund satt till 15. Om antalet anrop överstiger 15 per sekund ignoreras de återstående samtalen. Du kan öka den här gränsen för privata externa datakällor. Kontakta Adobe om du vill inkludera slutpunkten i tillåtelselista. Detta är inte möjligt för offentliga externa datakällor.

För anpassade åtgärder måste du utvärdera kapaciteten för det externa API:t. Om Journey Optimizer t.ex. skickar 1 000 samtal per sekund och systemet bara har stöd för 100 samtal per sekund, måste du definiera en spärrregel så att systemet inte blir mättat.

Takregler definieras på sandlådenivå för en specifik slutpunkt (URL:en anropas). Vid körning verifierar Journey Orchestration om det finns en definierad begränsningsregel och tillämpar den definierade hastigheten vid anrop till den slutpunkten. Om antalet anrop överstiger den definierade hastigheten, ignoreras de återstående samtalen och räknas som fel i rapporteringen.

En begränsningsregel är specifik för en slutpunkt men global för alla resor i en sandlåda. Detta innebär att takplatser delas mellan alla resor i en sandlåda.

Anta till exempel att du har definierat en begränsning på 100 anrop per sekund för det externa systemet. Ditt system anropas av en anpassad åtgärd på tio olika resor. Om en resa tar emot 200 samtal per sekund används de 100 tillgängliga kortplatserna och de 100 återstående kortplatserna tas bort. Eftersom den högsta nivån har överskridits har de övriga nio resorna inte några fack kvar. Denna precision hjälper till att skydda det externa systemet från överbelastning och krascher.

Mer information om API:t för capping och hur du konfigurerar regler för capping finns på [den här sidan](../api/capping.md).

## Timeout och försök igen{#timeout}

Om begränsningsregeln är uppfylld tillämpas timeoutregeln.

Under varje resa kan du definiera en tidsgräns. Detta gör att du kan ange en maximal varaktighet när du anropar ett externt system. Tidsgränsen har konfigurerats i egenskaperna för en resa. Se [den här sidan](../building-journeys/changing-properties.md#timeout_and_error).

Den här tidsgränsen är global för alla externa anrop (externa API-anrop i anpassade åtgärder och anpassade datakällor). Som standard är den inställd på 5 sekunder.

Under den angivna tidsgränsen försöker Journey Orchestration anropa det externa systemet. Efter det första anropet kan högst tre försök utföras tills tidsgränsen för timeout har nåtts. Antalet försök kan inte ändras.

Varje nytt försök använder en kortplats. Om du har ett tak på 100 samtal per sekund och vart och ett av dina samtal kräver två försök, kommer hastigheten att sänkas till 30 samtal per sekund (varje samtal använder 3 platser: det första samtalet och två försök).

Tidsgränsvärdet beror på användningsfallet. Om du snabbt vill skicka ditt meddelande, till exempel när klienten kommer in i butiken, vill du inte ange en lång tidsgräns. Ju längre tidsgränsen är, desto fler objekt placeras i kö. Detta kan påverka prestandan avsevärt. Om Journey Orchestration utför 1 000 anrop per sekund, kan det vara bra att lagra 5 eller 15 sekunder med data.

Låt oss ta ett exempel i 5 sekunder.

* Det första anropet varar mindre än 5 sekunder: anropet lyckades, inget nytt försök utförs.
* Det första samtalet varar längre än 5 sekunder: samtalet avbryts och det görs inget nytt försök. Den räknas som ett timeout-fel vid rapportering.
* Det första anropet misslyckas efter 2 sekunder (det externa systemet returnerar ett fel): 3 sekunder återstår för nya försök, om det finns lediga fack.
   * Om ett av de tre försöken lyckas före slutet av de fem sekunderna utförs anropet och det finns inget fel.
   * Om tidsgränsen nås under återförsöken avbryts anropet och räknas som ett timeout-fel i rapporteringen.

## Vanliga frågor och svar{#faq}

**Hur konfigurerar jag en begränsning? Finns det en standardregel för begränsning?**

Som standard finns det ingen begränsning. Takregler definieras på sandlådenivå för en specifik slutpunkt (den URL som anropas) med API:t för begränsning. Se [det här avsnittet](../about/external-systems.md#capping) och [sidan](../api/capping.md).

**Hur många försök utförs? Kan jag ändra antalet återförsök eller definiera en minsta vänteperiod mellan återförsök?**

För ett visst anrop kan högst tre försök utföras efter det första anropet, tills tidsgränsen för anropet har nåtts. Antalet försök och tiden mellan varje nytt försök kan inte ändras. Se [det här avsnittet](../about/external-systems.md#timeout).

**Var kan jag konfigurera timeout? Finns det ett maxvärde?**

Under varje resa kan du definiera en tidsgräns. Tidsgränsen har konfigurerats i egenskaperna för en resa. Tidsgränsen måste vara mellan 1 och 30 sekunder. Se [det här avsnittet](../about/external-systems.md#timeout) och [sidan](../building-journeys/changing-properties.md#timeout_and_error).
