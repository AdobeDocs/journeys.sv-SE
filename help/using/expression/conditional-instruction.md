---
product: adobe campaign
title: Villkorlig instruktion (if, then, else)
description: Läs om villkorlig instruktion
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 48fb4944-5b78-4ccd-9b9b-ffe0719e7c21
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---

# Villkorlig instruktion (if, then, else) {#section_cdz_lsk_w3b}

Den villkorliga instruktionen (if, then, else) stöds i den avancerade redigeraren. Det gör det möjligt att definiera mer komplexa uttryck. Den består av följande element:

* **[!UICONTROL if]**: villkoret som ska utvärderas först.
* **[!UICONTROL then]**: uttrycket som ska utvärderas om resultatet av villkorsutvärderingen är sant.
* **[!UICONTROL else]**: uttrycket som ska utvärderas om resultatet av villkorsutvärderingen är false.

>[!NOTE]
>
>Parenteser krävs runt alla uttryck.

```json
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` måste returnera **boolesk**.

`<expression2>` och `<expression3>` måste ha samma typ eller kompatibla typer. De signaturer och returtyper som stöds är:

```json
boolean,boolean : boolean
dateTime,dateTime : dateTime
dateTimeOnly,dateTimeOnly : dateTimeOnly
decimal,integer : decimal
integer,decimal : integer
integer,decimal : decimal
duration,duration : duration
string,string : string
listBoolean,listBoolean : listBoolean
listDateTime,listDateTime : listDateTime
listDateTimeOnly,listDateTimeOnly : listDateTimeOnly
listDateOnly,listDateOnly : listDateOnly
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Användning**

Med den villkorliga instruktionen kan du optimera arbetsflödet för resan genom att minska antalet villkorsaktiviteter. I samma åtgärdsaktivitet kan du till exempel ange två alternativ för en fältdefinition med bara ett villkorsuttryck.

Exempel för en åtgärdsaktivitet (för ett fält som förväntar en sträng som ett resultat av den villkorliga instruktionen):

```json
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
