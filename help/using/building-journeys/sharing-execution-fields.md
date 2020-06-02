---
title: roadStep-händelser, körningsfält för åtgärd
description: roadStep-händelser, körningsfält för åtgärd
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
source-git-commit: 10402a774bda66629f30869102d5e6ceca267535
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 0%

---


# roadStep-händelser, körningsfält för åtgärd {#sharing-execution-fields}

Den här mixinen delas av travelStepEvent och travelStepProfileEvent.

Om steget har en åtgärd som ska bearbetas läggs dessa fält till i händelsens nyttolast.

## actionID

ID för åtgärden som körs.

Typ: string

## actionName

Åtgärdens namn. Om inget namn har angetts används stepName.

Typ: string

## actionType

Typ av åtgärd.

Typ: string

## actionParametriszed

Anger om åtgärden är parametriserad eller inte.

Typ: boolesk

## actionExecutionTime

Den tid (i millisekunder) som krävs för att köra en aktuell åtgärd.

Typ: long

## actionExecutionError

Typ av fel som inträffar när åtgärden anropas.

Typ: string

Värden:
* http
* capping
* timeout
* fel

## actionExecutionErrorCode

Kod för körningsfel för åtgärd. Visa om felet har en kod, t.ex. en HTTP-kod.

Typ: string

## actionExecutionOriginError

En timeout kan uppstå i två fall:

* vid första försöket utförs en åtgärd. I det här fallet är körningen inte slutförd, så det finns inget underliggande fel
* vid ett nytt försök: I det här fallet beskriver actionExecOrigError/actionExecOrigErrorCode det fel som uppstod vid försöket före det nya försöket.

Ett e-postmeddelande skickas till exempel och ett HTTP 500-fel returneras vid det första försöket. Ett nytt hämtningsförsök görs, men längden på två försök överskrider tidsgränsen. Sedan taggas körningen av åtgärden som timeout. Åtgärdsdelen ser ut så här:

```
    ...
    "actionId": "myActionId",
    "actionName": "My mail sending",
    "actionType": "acsRestAction",
    "actionParameterized": true,
    "actionExecError": "timedout",
    "actionExecOrigError": "http",
    "actionExecOrigErrorCode": "500"
```

Typ: string

## actionExecutionOriginCode

Felkod för actionExecOrigError.

Typ: string

## actionBusinessType

Anger typen av åtgärd.

Värden:

* inbyggd
* ACS-e-post
* ACS SMS
* ACS-push
* kund
* Epsilon
* ...

Typ: string

## deliveryJobID

Detta beskriver leveransjobb-ID för batchresan.

Typ: string

## batchDeliveryID

Detta beskriver leverans-ID för batchresan.

Typ: string

## fromSegmentTrigger

Detta beskriver om batchresan aktiveras från målgruppssegmentet.

Typ: boolesk

## actionSchedulerCount

Antal begäranden om schemaläggningsmeddelanden som skickats till schemaläggningstjänsten under stegbearbetningen.

Typ: long
