---
product: adobe campaign
solution: Journey Orchestration
title: Datatyper
description: Lär dig mer om datatyper i avancerade uttryck
translation-type: tm+mt
source-git-commit: f755f92d0479e2889dd7ed6dfa5e72d52c25634f
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 4%

---


# Datatyper {#concept_gp3_rj5_dgb}

Tekniskt sett innehåller en konstant alltid en datatyp. I det litterala uttrycket anger vi bara värdet. Datatypen kan härledas från värdet (t.ex. sträng, heltal, decimal). I särskilda fall, till exempel datum och tid, använder vi dedikerade funktioner för representationen.

Avsnitten nedan innehåller information om de olika datatypsuttrycken och hur de återges.

## Sträng {#string}

**Beskrivning**

Vanlig teckensekvens. Den har ingen specifik storlek förutom den som kommer från miljön, till exempel mängden tillgängligt minne.

JSON-format: Sträng

Serialiseringsformat: UTF-8

**Litteral representation**

```"<value>"```

```'<value>'```

**Exempel**

```"hello world"```

```'hello world'```

## heltal {#integer}

**Beskrivning**

Heltalsvärde från -2^63 till 2^63-1.

JSON-format: Nummer

**Litteral representation**

```<integer value>```

**Exempel**

```42```

## decimal {#decimal}

**Beskrivning**

Decimaltal. Det representerar ett flytande värde:

* det största positiva, ändliga värdet av typen double, (2-2^-52)x2^1023
* minsta positiva normalvärde av typen double, 2-1022
* minsta positiva värde som inte är noll av typen double, 2 p-1074

JSON-format: Nummer

Serialiseringsformat: med &#39;.&#39; som decimalavgränsare.

**Litteral representation**

```<integer value>.<integer value>```

**Exempel**

```3.14```

## boolesk {#boolean}

**Beskrivning**

Bokfört booleskt värde med gemener: true eller false

JSON-format: Boolean

**Litteral representation**

```true```

```false```

**Exempel**

```true```

## dateTimeOnly {#date-time-only}

**Beskrivning**

Representerar en datumtid utan tidszon, som visas som en millisekund för år-månad-timme-minut-sekund-millisekund.

Den lagrar inte eller representerar en tidszon. I stället är det en beskrivning av datumet, som används för födelsedagar, kombinerat med lokal tid enligt en väggklocka.

Det kan inte representera en instans på tidslinjen utan ytterligare information som en förskjutning eller tidszon.

Serialiseringsformat: ISO-8601 extended offset date-time format.

Det använder DateTimeFormatter ISO_LOCAL_DATE_TIME för att avserialisera och serialisera värdet. [Läs mer](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**Litteral representation**

```toDateTimeOnly("<dateTimeOnly in ISO-8601 format>")  ```

## dateTime {#date-time}

**Beskrivning**

Datumtidskonstant som även beaktar tidszon. Den representerar ett datum/tid med en förskjutning från UTC.

Den kan visas som ett ögonblick i tid med ytterligare information om förskjutningen. Det är ett sätt att representera ett specifikt &quot;ögonblick&quot; på en viss plats i världen.

JSON-format: Sträng.

Den måste kapslas in i en toDateTime-funktion.

Serialiseringsformat: ISO-8601 extended offset date-time format.

Det använder DateTimeFormatter ISO_OFFSET_DATE_TIME för att avserialisera och serialisera värdet. [Läs mer](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

Du kan också skicka ett heltal som skickar ett epokvärde. [Läs mer](https://www.epochconverter.com)

Tidszonen kan anges med en förskjutningskod eller en tidszonskod (exempel: Europa/Paris, Z - betyder UTC).

**Litteral representation**

```toDateTime("<dateTime in ISO-8601 format>")```

```toDateTime(<integer value of an epoch in milliseconds>)```

**Exempel**

```toDateTime("1977-04-22T06:00:00Z")```

```toDateTime("2011-12-03T15:15:30Z")```

```toDateTime("2011-12-03T15:15:30.123Z")```

```toDateTime("2011-12-03T15:15:30.123+02:00")```

```toDateTime("2011-12-03T15:15:30.123-00:20")```

```toDateTime(1560762190189)```

## varaktighet {#duration}

**Beskrivning**

Den representerar en tidsbaserad tidsmängd, till exempel &quot;34,5 sekunder&quot;. Den modellerar en kvantitet eller tid i millisekunder.

De tidsenheter som stöds är: millisekunder, sekunder, minuter, timmar, dagar där en dag är lika med 24 timmar. År och månader stöds inte eftersom de inte är en fast tidsmängd.

JSON-format: Sträng.

Den måste kapslas in i en toDuration-funktion.

Serialiseringsformat: För att avserialisera ett tidszon-ID används Java-funktionen java.time.

Duration.parse: De format som godkänns baseras på varaktighetsformatet PnDTnHnMn.nS enligt ISO-8601 med dagar som anses vara exakt 24 timmar. [Läs mer](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**Litteral representation**

```toDuration("<duration in ISO-8601 format>")```

```toDuration(<duration in milliseconds>)```

**Exempel**

```toDuration("PT5S")``` tolkar som 5 sekunder

```toDuration(500)``` tolkar som 500 ms

```toDuration("PT20.345S")``` parses as &quot;20,345 seconds&quot;

```toDuration("PT15M") ``` parsas som &quot;15 minuter&quot; (där en minut är 60 sekunder)

```toDuration("PT10H") ``` parsas som&quot;10 timmar&quot; (där en timme är 3 600 sekunder)

```toDuration("P2D") ``` parsas som&quot;2 dagar&quot; (där en dag är 24 timmar eller 86 400 sekunder)

```toDuration("P2DT3H4M") ```parses som &quot;2 dagar, 3 timmar och 4 minuter&quot;

```toDuration("P-6H3M") ``` parsas som &quot;-6 timmar och +3 minuter&quot;

```toDuration("-P6H3M")``` tolkar som&quot;-6 timmar och -3 minuter&quot;

```toDuration("-P-6H+3M") ``` parsas som &quot;+6 timmar och -3 minuter&quot;

## list {#list}

**Beskrivning**

Kommaavgränsad lista med uttryck som använder hakparenteser som avgränsare.

Polymorfism stöds inte, och därför bör alla uttryck i listan ha samma typ.

**Litteral representation**

```[<expression>, <expression>, ... ]```

**Exempel**

```["value1","value2"]```

```[3,5]```

```[toDuration(500),toDuration(800)]```
