---
product: adobe campaign
solution: Journey Orchestration
title: Operatorer
description: Lär dig mer om operatorer i avancerade uttryck
translation-type: tm+mt
source-git-commit: 20498e89eb9c95dd19a11e42150a0bbf67024f67
workflow-type: tm+mt
source-wordcount: '531'
ht-degree: 5%

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

## Logisk  {#logical}

### och

**Litteralt uttryck**

```<expression1> and <expression2>```

Både &lt;expression1> och &lt;expression2> måste vara booleska. Resultatet är booleskt.

**Exempel**

```3.14 > 2 and 3.15 < 1```

### eller

**Litteralt uttryck**

```<expression1> or <expression2>```

Både &lt;expression1> och &lt;expression2> måste vara booleska. Resultatet är booleskt.

**Exempel**

```3.14 > 2 or 3.15 < 1```

### not

**Litteralt uttryck**

```not <expression>```

&lt;expression> måste vara booleskt. Resultatet är booleskt.

**Exempel**

```not 3.15 < 1```

## Jämförelse {#comparison}

### är null

**Litteralt uttryck**

```<expression> is null```

Resultatet är booleskt.

Observera att null betyder att uttrycket inte har något utvärderat värde.

**Exempel**

```@{BarBeacon.location} is null```

### är inte null

**Litteralt uttryck**

```<expression> is not null```

Resultatet är booleskt.

Observera att null betyder att uttrycket inte har något utvärderat värde.

**Exempel**

```@ is not null```

### har null

**Litteralt uttryck**

```<expression> has null```

&lt;expression> måste vara en lista. Resultatet är booleskt.

Användbart för att identifiera att en lista innehåller minst ett null-värde.

**Exempel**

```["foo", "bar", null] has null``` returnerar true.

```["foo", "bar", ""] has null``` returnerar false eftersom &quot;&quot; inte betraktas som null.

### ==

**Litteralt uttryck**

```<expression1> == <expression2>```

Både &lt;expression1> och &lt;expression2> måste ha samma datatyp. Resultatet är booleskt.

**Exempel**

```3.14 == 42```

```"foo" == "bar"```

### !=

**Litteralt uttryck**

```<expression1> != <expression2>```

Både &lt;expression1> och &lt;expression2> måste ha samma datatyp. Resultatet är booleskt.

**Exempel**

```3.14 != 42```

```"foo" != "bar"```

### >

**Litteralt uttryck**

```<expression1> > <expression2>```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

**Exempel**

```3.14 > 42```

### >=

**Litteralt uttryck**

```<expression1> >= <expression2>```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

**Exempel**

```42 >= 3.14```

### &lt;

**Litteralt uttryck**

```<expression1> < <expression2>```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

**Exempel**

```42 < 3.14```

### &lt;=

**Litteralt uttryck**

```<expression1> <= <expression2>```

Datetime kan jämföras med Datetime.

Datetimeonly kan jämföras med Datetimeonly.

Både heltal och decimal kan jämföras med både heltal och decimal.

Alla andra kombinationer är förbjudna.

Resultatet är booleskt.

**Exempel**

```42 <= 3.14```

## Aritmetisk {#arithmetic}

### +

**Litteralt uttryck**

```<expression1> + <expression2>```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

**Exempel**

```1 + 2``` returnerar 3

### -

**Litteralt uttryck**

```<expression1> - <expression2>```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

**Exempel**

```2 - 1``` returnerar 1

### /

**Litteralt uttryck**

```<expression1> / <expression2>```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

&lt;expression2> får inte vara lika med 0 (returnerar 0).

**Exempel**

```4 / 2``` returnerar 2

### *

**Litteralt uttryck**

```<expression1> * <expression2>```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

**Exempel**

```3 * 4``` returnerar 12

### %

**Litteralt uttryck**

```<expression1> % <expression2>```

Båda uttrycken måste vara numeriska (heltal eller decimal).

Resultatet är också numeriskt.

**Exempel**

```3 % 2``` returnerar 1.

## Matematik {#math}

### är numerisk

**Litteralt uttryck**

```<expression> is numeric```

Uttryckstypen är heltal eller decimal.

**Exempel**

```@ is numeric```

### är heltal

**Litteralt uttryck**

```<expression> is integer```

Uttryckstypen är ett heltal.

**Exempel**

```@ is integer```

### är decimal

**Litteralt uttryck**

```<expression> is decimal```

Uttryckstypen är decimal.

**Exempel**

```@ is decimal```

## Sträng {#string}

### +

**Litteralt uttryck**

```<string> + <expression>```

```<expression> + <string>```

Det sammanfogar två uttryck.

Ett uttryck måste vara en kedjad sträng.

**Exempel**

```"the current time is " + (now())``` returnerar &quot;den aktuella tiden är 2019-09-23T09:30:06.693Z&quot;

```(now()) + " is the current time"``` returnerar &quot;2019-09-23T09:30:06.693Z är den aktuella tiden&quot;

```"a" + "b" + "c" + 1234``` returnerar &quot;abc1234&quot;.

## Datum {#date}

### +

**Litteralt uttryck**

```<expression + <duration>```

Lägg till en varaktighet för ett dateTime, ett dateTimeOnly eller en varaktighet.

**Exempel**

```toDateTime("2011-12-03T15:15:30Z") + toDuration("PT15M")``` returnerar 2011-12-03T15:30:30Z

```toDateTimeOnly("2011-12-03T15:15:30") + toDuration("PT15M")``` returnerar 2011-12-03T15:30:30

```now() + toDuration("PT1H")``` returnerar en dateTime (med UTC-tidszon) en timme senare från aktuell tid

```toDuration("PT1H") + toDuration("PT1H")``` returnerar PT2H
