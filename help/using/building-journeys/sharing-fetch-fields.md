---
product: adobe campaign
title: datafält för hämtning för händelsen journeyStep
description: datafält för hämtning för händelsen journeyStep
feature: Journeys
role: User
level: Intermediate
exl-id: 4df471ae-c6b7-452e-8e44-a108d0da276f
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 4%

---

# datafält för hämtning för händelsen journeyStep {#sharing-fetch-fields}

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
* error

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

Felkoden som tillhandahålls av systemet [!DNL Journey Orchestration] frågar. Det kan till exempel vara en 404, 500 osv.

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
