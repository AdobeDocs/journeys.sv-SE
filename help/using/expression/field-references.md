---
product: adobe campaign
title: Fältreferenser
description: Läs mer om fältreferenser i avancerade uttryck
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 2f317306-9afd-4e9a-88b8-fc66102e1046
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '607'
ht-degree: 2%

---

# Fältreferenser {#concept_fkj_ll5_dgb}


>[!CAUTION]
>
>**Letar du efter Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


En fältreferens kan bifogas till en händelse eller en fältgrupp. Den enda meningsfulla informationen är fältets namn och sökväg.

Om du använder specialtecken i ett fält måste du använda dubbla citattecken eller enkla citattecken. Här är de fall där citattecken behövs:

* Fältet börjar med numeriska tecken
* Fältet börjar med tecknet &quot;-&quot;
* fältet innehåller något annat än: _a-z___, _A-Z___, _0-9___, _ , - __

Till exempel om ditt fält är _3h_: _#{OpenWeather.weatherData.rain.&#39;3h&#39;} > 0_

```json
// event field
@{<event name>.<XDM path to the field>}
@{LobbyBeacon.endUserIDs._experience.emailid.id}

// field group
#{<data source name>.<field group name>.<path to the field>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address}
```

I uttrycket refereras händelsefält till&quot;@&quot; och datakällfält refereras till med &quot;#&quot;.

En syntaxfärg används för att visuellt skilja händelsefält (grönt) från fältgrupper (blått).

## Standardvärden för fältreferenser {#default-value}

Ett standardvärde kan associeras med ett fältnamn. Syntaxen är följande:

```json
// event field
@{<event name>.<XDM path to the field>, defaultValue: <default value expression>}
@{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue: "example@adobe.com"}
// field group
#{<data source name>.<field group name>.<path to the field>, defaultValue: <default value expression>}
#{ExperiencePlatform.ProfileFieldGroup.profile.personalEmail.address, defaultValue: "example@adobe.com"}
```

>[!NOTE]
>
>Fälttypen och standardvärdet måste vara desamma. Till exempel @{LobbyBeacon.endUserIDs._experience.emailid.id, defaultValue : 2} kommer att vara ogiltigt eftersom standardvärdet är ett heltal medan det förväntade värdet ska vara en sträng.

Exempel:

```json
// for an event 'OrderEvent' having the following payload:
{
    "orderId": "12345"
}
 
expression example:
- @{OrderEvent.orderId}                                    -> "12345"
- @{OrderEvent.producdId, defaultValue : "not specified" } -> "not specified" // default value, productId is not a field present in the payload
- @{OrderEvent.productId}                                  -> null
 
 
// for an entity 'Profile' on datasource 'ACP' having fields person/lastName, with fetched data such as:
{
    "person": {
        "lastName":"Snow"
    },
    "emails": [
        { "email":"john.snow@winterfell.westeros" },
        { "email":"snow@thewall.westeros" }
    ]
}
 
expression examples:
- #{ACP.Profile.person.lastName}                 -> "Snow"
- #{ACP.Profile.emails.at(1).email}              -> "snow@thewall.westeros"
- #{ACP.Profile.person.age, defaultValue : -1}   -> -1 // default value, age is not a field present in the payload
- #{ACP.Profile.person.age}                      -> null
```

Du kan lägga till vilken typ av uttryck som helst som standardvärde. Den enda begränsningen är att uttrycket måste returnera den förväntade datatypen. När du använder en funktion måste du kapsla in funktionen med ().

```
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.any.time, defaultValue : (now())} 
== date("2022-02-10T00:00:00Z")
```

## Referens till ett fält i samlingar

De element som definieras i samlingar refereras med de specifika funktionerna `all`, `first` och `last`. För mer information om detta hittar du i [det här avsnittet](../expression/collection-management-functions.md).

Exempel:

```json
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all()
```

## Referens till ett fält som definieras i en karta

### Funktionen `entry`

För att kunna hämta ett element i en karta använder vi inmatningsfunktionen med en given nyckel. Det används till exempel när du definierar nyckeln för en händelse enligt det valda namnutrymmet. Se Välja namnutrymme. Mer information finns på [den här sidan](../event/selecting-the-namespace.md).

```json
@{MyEvent.identityMap.entry('Email').first().id}
```

I det här uttrycket får vi posten för nyckeln &quot;Email&quot; i fältet &quot;IdentityMap&quot; för en händelse. Posten &quot;E-post&quot; är en samling som vi tar &quot;id&quot; i det första elementet med hjälp av &quot;first()&quot;. Mer information finns på [den här sidan](../expression/collection-management-functions.md).

### `firstEntryKey` funktion

Om du vill hämta den första startnyckeln för en karta använder du funktionen `firstEntryKey`.

I det här exemplet visas hur du hämtar den första e-postadressen för prenumeranterna i en viss lista:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-email').subscribers.firstEntryKey()}
```

I det här exemplet heter prenumerationslistan `daily-email`. E-postadresser definieras som nycklar i `subscribers` kartan, som är länkad till prenumerationslistkartan.

### `keys` funktion

Om du vill hämta till alla nycklar på en karta använder du `keys` funktionen.

Det här exemplet visar hur du hämtar alla e-postadresser som är associerade med prenumeranterna i en viss lista för en viss profil:

```json
#{ExperiencePlatform.Subscriptions.profile.consents.marketing.email.subscriptions.entry('daily-mail').subscribers.keys()
```

## Parametervärden för en datakälla (dynamiska värden för datakälla)

Om du väljer ett fält från en extern datakälla som kräver att en parameter anropas visas en ny flik till höger där du kan ange den här parametern. Läs [den här sidan](../expression/expressionadvanced.md).

Om du vill ta med parametrarna för datakällan i huvuduttrycket kan du definiera deras värden med nyckelordet _params_ för mer komplexa användningsområden. En parameter kan vara vilket giltigt uttryck som helst, även från en annan datakälla som även innehåller en annan parameter.

>[!NOTE]
>
>När du definierar parametervärdena i uttrycket försvinner fliken till höger.

Använd följande syntax:

```json
#{<datasource>.<field group>.fieldName, params: {<params-1-name>: <params-1-value>, <params-2-name>: <params-2-value>}}
```

* **`<params-1-name>`**: exakt namn på den första parametern från datakällan.
* **`<params-1-value>`**: värdet för den första parametern. Det kan vara vilket giltigt uttryck som helst.

Exempel:

```json
#{Weather.main.temperature, params: {localisation: @{Profile.address.localisation}}}
#{Weather.main.temperature, params: {localisation: #{GPSLocalisation.main.coordinates, params: {city: @{Profile.address.city}}}}}
```
