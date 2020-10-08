---
title: Villkorlig instruktion (if, then, else)
description: Läs om villkorlig instruktion
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
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

```
if  (<expression1>)
then
   (<expression2>)
else
   (<expression3>)
```

`<expression1>` måste returnera ett **booleskt värde**.

`<expression2>` och måste `<expression3>` ha samma typ eller kompatibla typer. De signaturer och returtyper som stöds är:

```
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
listDecimal,listDecimal : listDecimal
listInteger,listInteger : listInteger
listString,listString : listString
```

**Användning**

Med den villkorliga instruktionen kan du optimera arbetsflödet för resan genom att minska antalet villkorsaktiviteter. I samma åtgärdsaktivitet kan du till exempel ange två alternativ för en fältdefinition genom att bara använda ett villkorsuttryck.

Exempel för en åtgärdsaktivitet (för ett fält som förväntar en sträng som ett resultat av den villkorliga instruktionen):

```
if (startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iPad') or startWithIgnoreCase(@{eventiOSPushPermissionAllowed.device.model}, 'iOS'))
then
   ('apns')
else
   ('fcm')
```
