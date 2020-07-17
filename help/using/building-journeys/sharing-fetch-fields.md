---
title: progressStep-händelsedatafält för hämtning
description: progressStep-händelsedatafält för hämtning
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
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---


# progressStep-händelsedatafält för hämtning {#sharing-fetch-fields}

Den här mixinen delas av travelStepEvent och travelStepProfileEvent.

Under en stegvis bearbetning kan vi hämta N-data i fältgrupper.

## fetchTotalTime

Total tid i millisekunder som datahämtningen pågick under stegbearbetningen.

Typ: long

## fetchTypeInError

Definierar om den felaktiga hämtningen finns på Adobe Experience Platform eller i en anpassad datakälla.

Typ: string

Värden:
* aep
* anpassad

## fetchError

Typ av fel som inträffar när datahämtningen bearbetas.

Typ: string

Värden:
* http
* capping
* tidsgränsen
* fel

## fetchErrorCode

Kod för hämtningsfel. Visa om felet har en kod, t.ex. en HTTP-kod. Om actionExecError till exempel är http representerar koden 404 HTTP 404-felet.

Typ: string

## fetchOriginError

En timeout kan uppstå i två fall:

* vid första försöket utförs åtgärden. I det här fallet är körningen inte slutförd, så det finns inget underliggande fel
* vid ett nytt försök: I det här fallet beskriver actionExecOrigError/actionExecOrigErrorCode det fel som uppstod vid försöket före det nya försöket.

Data hämtas till exempel från Unified Profile Service och ett HTTP 500-fel returneras vid det första försöket. Ett nytt hämtningsförsök görs, men längden på två försök överskrider tidsgränsen. Sedan taggas körningen av åtgärden som timeout. Åtgärdsdelen ser ut så här:

```
    ...
    "fetchTypeInError": "aep",
    "fieldgroupIdInError": "MyProfileFieldgroup",
    "fetchError": "timedout",
    "fetchOrigError": "http",
    "fetchOrigErrorCode": "500"
```

Typ: string

## fetchOriginErrorCode

Felkoden som tillhandahålls av systemet [!DNL Journey Orchestration] efterfrågas. Det kan till exempel vara en 404, 500 osv.

Typ: string

## fetchCount

Hur många gånger data hämtas, oavsett källtyp.

Typ: long

## fetchPlatformTotalTime

Den totala tiden det tar att hämta data från Adobe Experience Platform i millisekunder. Anmärkning: denna tid beräknas från den tidpunkt då motorn skickar anrikningshändelsen till anrikningstjänsten och får svaret.

Typ: long

## fetchPlatformCount

Hur många gånger data hämtas från Adobe Experience Platform.

Typ: long

## fetchCustomTotalTime

Hur lång tid det tar att hämta anpassade data i millisekunder. Anmärkning: denna tid beräknas från den tidpunkt då motorn skickar anrikningshändelsen till anrikningstjänsten och får svaret

Typ: long

## fetchCustomCount

Hur många gånger som anpassade data hämtas från externa system.

Typ: long
