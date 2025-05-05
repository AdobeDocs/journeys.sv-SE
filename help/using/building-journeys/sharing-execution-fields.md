---
product: adobe campaign
title: fält för händelseexekvering för händelsen journeyStep
description: fält för händelseexekvering för händelsen journeyStep
feature: Journeys
role: User
level: Intermediate
exl-id: 9af66037-63d7-41a8-86d1-b03c655dfb82
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '367'
ht-degree: 4%

---

# fält för händelseexekvering för händelsen journeyStep {#sharing-execution-fields}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


Den här mixinen delas av travelStepEvent och travelStepProfileEvent.

Om steget har en åtgärd som ska bearbetas läggs dessa fält till i händelsens nyttolast.

## actionID

ID för åtgärden som körs.

Typ: sträng

## actionName

Åtgärdens namn. Om inget namn har angetts används stepName.

Typ: sträng

## actionType

Typ av åtgärd.

Typ: sträng

## actionParametriszed

Anger om åtgärden är parametriserad eller inte.

Typ: boolesk

## actionExecutionTime

Den tid (i millisekunder) som krävs för att köra en aktuell åtgärd.

Typ: lång

## actionExecutionError

Typ av fel som inträffar när åtgärden anropas.

Typ: sträng

Värden:
* http
* capping
* timeout
* fel

## actionExecutionErrorCode

Kod för körningsfel för åtgärd. Visa om felet har en kod, t.ex. en HTTP-kod.

Typ: sträng

## actionExecutionOriginError

En timeout kan uppstå i två fall:

* vid första försöket utförs en åtgärd. I det här fallet är körningen inte slutförd, så det finns inget underliggande fel
* vid ett nytt försök: i det här fallet beskriver actionExecOrigError/actionExecOrigErrorCode det fel som uppstod vid försöket före det nya försöket.

Ett e-postmeddelande skickas till exempel och ett HTTP 500-fel returneras vid det första försöket. Ett nytt hämtningsförsök görs, men längden på de två försöken överskrider tidsgränsen. Sedan taggas körningen av åtgärden som timeout. Åtgärdsdelen ser ut så här:

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

Typ: sträng

## actionExecutionOriginCode

Felkod för actionExecOrigError.

Typ: sträng

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

Typ: sträng

## deliveryJobID

Detta beskriver leveransjobb-ID för batchresan.

Typ: sträng

## batchDeliveryID

Detta beskriver leverans-ID för batchresan.

Typ: sträng

## fromSegmentTrigger

Detta beskriver om batchresan aktiveras från målgruppssegmentet.

Typ: boolesk

## actionSchedulerCount

Antal begäranden om schemaläggningsmeddelanden som skickats till schemaläggningstjänsten under stegbearbetningen.

Typ: lång
