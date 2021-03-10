---
product: adobe campaign
solution: Journey Orchestration
title: Operatorer
description: Lär dig mer om operatorer i avancerade uttryck
feature: Resor
role: Datatekniker
level: Erfaren
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '439'
ht-degree: 6%

---



# Operatorer {#concept_wd5_pj5_dgb}

Det finns två typer av operatorer: unära operatorer och binära operatorer. Det finns unära operatorer till vänster och unära operatorer till höger.

```
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

Här är en lista över operatorer som stöds:

## Logisk {#logical}

### och

```
<expression1> and <expression2>
```

Både &lt;expression1> och &lt;expression2> måste vara booleska. Resultatet är booleskt.

Exempel:

```
3.14 > 2 and 3.15 < 1
```

### eller



```
<expression1> or <expression2>
```

Både &lt;expression1> och &lt;expression2> måste vara booleska. Resultatet är booleskt.

Exempel:

```
3.14 > 2 or 3.15 < 1
```

### not



```
not <expression>
```

&lt;expression> måste vara booleskt. Resultatet är booleskt.

Exempel:

```
not 3.15 < 1
```

## Jämförelse {#comparison}

### är null



```
<expression> is null
```

Resultatet är booleskt.

Observera att null betyder att uttrycket inte har något utvärderat värde.

Exempel:

```
@{BarBeacon.location} is null
```

### är inte null



```
<expression> is not null
```

Resultatet är booleskt.

Observera att null betyder att uttrycket inte har något utvärderat värde.

Exempel:

```
@ is not null
```

### har null



```
<expression> has null
```

&lt;expression> måste vara en lista. Resultatet är booleskt.

Användbart för att identifiera att en lista innehåller minst ett null-värde.

Exempel:

```
["foo", "bar", null] has null --  returns true.
```

```
["foo", "bar", ""] has null -- returns false because "" is not considered as null.
```

### ==



```
<expression1> == <expression2>
```

Både &lt;expression1> och &lt;expression2> måste ha samma datatyp. Resultatet är booleskt.

Exempel:

```
3.14 == 42
```

```
"foo" == "bar"
```

### !=



```
<expression1> != <expression2>
```

Både &lt;expression1> och &lt;expression2> måste ha samma datatyp. Resultatet är booleskt.

Exempel:

```
3.14 != 42
```

```
"foo" != "bar"
```

### >



```
<expression1> > <expression2>
```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

Exempel:

```
3.14 > 42
```

### >=



```
<expression1> >= <expression2>
```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

Exempel:

```
42 >= 3.14
```

### &lt;>



```
<expression1> < <expression2>
```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

Exempel:

```
42 < 3.14
```

### &lt;>



```
<expression1> <= <expression2>
```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

Exempel:

```
42 <= 3.14
```

## Aritmetisk {#arithmetic}

### +



```
<expression1> + <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

Exempel:

```
1 + 2 -- returns 3
```

### -



```
<expression1> - <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

Exempel:

```
2 - 1 -- returns 1
```

### /



```
<expression1> / <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

&lt;expression2> får inte vara lika med 0 (returnerar 0).

Exempel:

```
4 / 2 -- returns 2
```

### *



```
<expression1> * <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

Exempel:

```
3 * 4 -- returns 12
```

### %



```
<expression1> % <expression2>
```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

Exempel:

```
3 % 2 -- returns 1.
```

## Matematik {#math}

### är numerisk



```
<expression> is numeric
```

Uttryckstypen är heltal eller decimal.

Exempel:

```
@ is numeric
```

### är heltal



```
<expression> is integer
```

Uttryckstypen är ett heltal.

Exempel:

```
@ is integer
```

### är decimal



```
<expression> is decimal
```

Uttryckstypen är decimal.

Exempel:

```
@ is decimal
```

## Sträng {#string}

### +



```
<string> + <expression>
```

```
<expression> + <string>
```

Det sammanfogar två uttryck.

Ett uttryck måste vara en kedjad sträng.

Exempel:

```
"the current time is " + (now()) -- returns "the current time is 2019-09-23T09:30:06.693Z"
```

```
(now()) + " is the current time" -- returns "2019-09-23T09:30:06.693Z is the current time"
```

```
"a" + "b" + "c" + 1234 -- returns "abc1234".
```

## Datum {#date}

### +



```
<expression + <duration>
```

Lägg till en varaktighet för ett dateTime, ett dateTimeOnly eller en varaktighet.

Exempel:

```
toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M") -- returns 2011-12-03T15:30:30Z
```

```
toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M") -- returns 2011-12-03T15:30:30
```

```
now() + toDuration("PT1H") -- returns a dateTime (with UTC time zone) one hour later from current time
```

```
toDuration("PT1H") + toDuration("PT1H") -- returns  PT2H
```
