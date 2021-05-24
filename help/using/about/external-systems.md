---
product: adobe campaign
solution: Journey Orchestration
title: Integrera med externa system
description: Lär dig de bästa sätten att integrera externa system
feature: Resor
role: Business Practitioner
level: Beginner
exl-id: 27859689-dc61-4f7a-b942-431cdf244455
source-git-commit: a25ff95e0b74d3a0693310179670c7fe7b0de51c
workflow-type: tm+mt
source-wordcount: '530'
ht-degree: 0%

---

# Integrera med externa system {#external-systems}

På den här sidan presenteras de olika skyddsmekanismer som Journey Orchestration tillhandahåller när ett externt system integreras, samt bästa praxis: hur du optimerar skyddet för ditt externa system med API:t för appning, hur du konfigurerar timeout för resan och hur nya försök fungerar.

I Journey Orchestration kan du konfigurera anslutningar till externa system via anpassade datakällor och anpassade åtgärder. På så sätt kan du till exempel berika dina resor med data från ett externt bokningssystem eller skicka meddelanden via ett tredjepartssystem som Epsilon eller Facebook.

När du integrerar ett externt system kan du stöta på flera problem, systemet kan vara långsamt, det kan sluta svara eller så kanske det inte kan hantera en stor volym. Journey Orchestration erbjuder flera skyddsräcken för att skydda systemet från överbelastning.

Alla externa system har olika prestanda. Du måste anpassa konfigurationen efter varje användningsfall.

När Journey Orchestration gör ett anrop till ett externt API körs de tekniska garantierna enligt följande:

1. Takning: appningsregler tillämpas
2. Timeout och försök igen:

## Takning

Det inbyggda Capping API:t erbjuder ett tekniskt skyddsräcke som skyddar ditt externa system. Innan du gör det måste du utvärdera kapaciteten för det externa API:t. Om Journey Orchestration t.ex. skickar 1 000 samtal per sekund och systemet bara har stöd för 100 samtal per sekund, måste du definiera en spärrregel så att systemet inte blir mättat.

Takregler definieras på sanddoxinivå för en specifik slutpunkt (URL anropas). Vid körning verifierar Journey Orchestration om det finns en definierad begränsningsregel och tillämpar den definierade hastigheten under anropen till den slutpunkten. Om antalet anrop överstiger den definierade hastigheten, ignoreras återstående anrop.

En begränsningsregel är specifik för en slutpunkt men global för alla resor i en sandlåda. Detta innebär att samtalsplatser delas mellan alla resor i en sandlåda. Låt oss till exempel säga att ditt externa system har en definierad begränsning på 100 samtal per sekund och att den anropas av en anpassad åtgärd på 10 olika resor. Om en resa tar emot 200 samtal per sekund är de 100 kortplatserna tillgängliga och de 100 återstående kortplatserna tas bort. Eftersom den högsta nivån redan har överskridits kommer de övriga nio resorna inte att ha något tillgängligt parti. Denna granularitet hjälper till att skydda det externa systemet från överbelastning och krascher.

Ett anrop som ignoreras på grund av begränsningar räknas som ett fel vid rapportering.

Mer information om hur du konfigurerar regler för capping finns på [den här sidan](../api/timezone-management.md).

## Timeout och försök igen

Se till att -> timeout definition, et qui definition le temps maximal qu&#39;on aloue a lappel au sys externe. Pendant ce temps là, on essaie de faire des appels. På fait un appel, si l&#39;appel dure moholtemps que le timeout ca marche, si plus long temps on voit ca comme une timeout error, et coté reporting compabilisé comme une erreur. si l&#39;appel echoue, (planter sur 500 ou autre), retry. 3 återförsök max, pas configurable. SI kan överskrida timeoutglobal (par example 2 essais, mais depasse le timeout), erreur de timeout. plsu de temps que necessary. Timeout durée max qu&#39;on alloue a appel et aux retry is erreurs.

