---
product: adobe campaign
title: Operatorer
description: Läs om operatorer i avancerade uttryck
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: fd86b6ab-76cf-4b35-9e87-f441e914f20b
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '504'
ht-degree: 5%

---

# Operatorer {#concept_wd5_pj5_dgb}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home) för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


Det finns två typer av operatorer: unära operatorer och binära operatorer. Det finns unära operatorer till vänster och unära operatorer till höger.

```json
    // left-hand unary operators
    <operator> <operand> // operand is an expression
    not (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example@adobe.com")

    // right-hand unary operators
    <operand> <operator> // operand is an expression
    @{LobbyBeacon.endUserIDs._experience.emailid.id} is not null

    // binary operators
    <operand1> <operator> <operand2>
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example1@adobe.com") or
    (@{LobbyBeacon.endUserIDs._experience.emailid.id}=="example2@adobe.com")
```

## Viktiga anteckningar{#important-notes}

* När du använder en multiplikation (`*`) måste båda åtgärdsfälten ha samma typ, antingen heltal eller decimal. Exempel:
   * följande exempel är korrekt: `3.0 * 4.0`
   * `3 * 4.0` leder till ett fel

## Logisk {#logical}

### och

```json
<expression1> and <expression2>
```

Både &lt;expression1> och &lt;expression2> måste vara booleska. Resultatet är booleskt.

Exempel:

```json
3.14 > 2 and 3.15 < 1
```

### eller



```json
<expression1> or <expression2>
```

Både &lt;expression1> och &lt;expression2> måste vara booleska. Resultatet är booleskt.

Exempel:

```json
3.14 > 2 or 3.15 < 1
```

### not



```json
not <expression>
```

&lt;expression> måste vara booleskt. Resultatet är booleskt.

Exempel:

```json
not 3.15 < 1
```

## Jämförelse {#comparison}

### är null



```json
<expression> is null
```

Resultatet är booleskt.

Observera att null betyder att uttrycket inte har något utvärderat värde.

Exempel:

```json
@{BarBeacon.location} is null
```

### är inte null



```json
<expression> is not null
```

Resultatet är booleskt.

Observera att null betyder att uttrycket inte har något utvärderat värde.

Exempel:

```json
@ is not null
```

### har null



```json
<expression> has null
```

&lt;expression> måste vara en lista. Resultatet är booleskt.

Användbart för att identifiera att en lista innehåller minst ett null-värde.

Exempel:

```json
["foo", "bar", null] has null --  returns true.
```

```json
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```json
<expression1> == <expression2>
```

Både &lt;expression1> och &lt;expression2> måste ha samma datatyp. Resultatet är booleskt.

Exempel:

```json
3.14 == 42
```

```json
"foo" == "bar"
```

### !=



```json
<expression1> != <expression2>
```

Både &lt;expression1> och &lt;expression2> måste ha samma datatyp. Resultatet är booleskt.

Exempel:

```json
3.14 != 42
```

```json
"foo" != "bar"
```

### >



```json
<expression1> > <expression2>
```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

Exempel:

```json
3.14 > 42
```

### >=



```json
<expression1> >= <expression2>
```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

Exempel:

```json
42 >= 3.14
```

### &lt;



```json
<expression1> < <expression2>
```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

Exempel:

```json
42 < 3.14
```

### &lt;=



```json
<expression1> <= <expression2>
```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

Exempel:

```json
42 <= 3.14
```

## Aritmetisk {#arithmetic}

### +



```json
<expression1> + <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

Exempel:

```json
1 + 2 -- returns 3
```

### –



```json
<expression1> - <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

Exempel:

```json
2 - 1 -- returns 1
```

### /



```json
<expression1> / <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

&lt;expression2> får inte vara lika med 0 (returnerar 0).

Exempel:

```json
4 / 2 -- returns 2
```

### *



```json
<expression1> * <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

Exempel:

```json
3 * 4 -- returns 12
```

### %



```json
<expression1> % <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

Exempel:

```json
3 % 2 -- returns 1.
```

## Matematik {#math}

### är numerisk



```json
<expression> is numeric
```

Uttryckstypen är heltal eller decimal.

Exempel:

```json
@ is numeric
```

### är heltal



```json
<expression> is integer
```

Uttryckstypen är ett heltal.

Exempel:

```json
@ is integer
```

### är decimal



```json
<expression> is decimal
```

Uttryckstypen är decimal.

Exempel:

```json
@ is decimal
```

## Sträng {#string}

### +



```json
<string> + <expression>
```

```json
<expression> + <string>
```

Det sammanfogar två uttryck.

Ett uttryck måste vara en kedjad sträng.

Exempel:

```json
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```json
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```json
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Datum {#date}

### +



```json
<expression> + <duration>
```

Lägg till en varaktighet för ett dateTime, ett dateTimeOnly eller en varaktighet.

Exempel:

```json
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```json
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```json
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```json
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
