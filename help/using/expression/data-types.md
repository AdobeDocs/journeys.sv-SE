---
product: adobe campaign
title: Datatyper
description: Läs mer om datatyper i avancerade uttryck
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 343f61b8-2315-4971-8b2b-6aa815bd9ced
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '611'
ht-degree: 4%

---

# Datatyper {#concept_gp3_rj5_dgb}

Tekniskt sett innehåller en konstant alltid en datatyp. I det litterala uttrycket anger vi bara värdet. Datatypen kan härledas från värdet (t.ex. sträng, heltal, decimal). I särskilda fall, till exempel datum och tid, använder vi dedikerade funktioner för representationen.

Avsnitten nedan innehåller information om de olika datatypsuttrycken och hur de återges.

## string {#string}

**Beskrivning**

Vanlig teckensekvens. Den har ingen specifik storlek förutom den som kommer från miljön, till exempel mängden tillgängligt minne.

JSON-format: String

Serialiseringsformat: UTF-8

**Litteral representation**

```json
"<value>"
```

```json
'<value>'
```

**Exempel**

```json
"hello world"
```

```json
'hello world'
```

## heltal {#integer}

**Beskrivning**

Heltalsvärde från -2^63 till 2^63-1.

JSON-format: Number

**Litteral representation**

```json
<integer value>
```

**Exempel**

```json
42
```

## decimal {#decimal}

**Beskrivning**

Decimaltal. Det representerar ett flytande värde:

* det största positiva, ändliga värdet av typen double, (2-2^-52)x2^1023
* minsta positiva normalvärde av typen double, 2-1022
* minsta positiva värde som inte är noll av typen double, 2 p-1074

JSON-format: Number

Serialiseringsformat: använder . som decimalavgränsare.

**Litteral representation**

```json
<integer value>.<integer value>
```

**Exempel**

```json
3.14
```

## boolesk {#boolean}

**Beskrivning**

Booleskt värde skrivet med gemener: true eller false

JSON-format: Boolean

**Litteral representation**

```json
true
```

```json
false
```

**Exempel**

```json
true
```

## dateOnly {#date-only}

**Beskrivning**

Representerar endast ett datum utan tidszon, vilket visas som en dag i månaden.

Det är en beskrivning av datumet, som används för födelsedagar.

JSON-format: String.

Formatet är: YYY-MM-DD (ISO-8601), t.ex. &quot;2021-03-11&quot;.

Den kan kapslas in i en toDateOnly-funktion.

Det använder DateTimeFormatter ISO_LOCAL_DATE_TIME för att avserialisera och serialisera värdet. [Läs mer](https://datatracker.ietf.org/doc/html/rfc3339#section-5.6)

**Litteral representation**

```json
date("<dateOnly in ISO-8601 format>")  
```

**Exempel**

```json
date("2021-02-19")
```

## dateTimeOnly {#date-time-only}

**Beskrivning**

Representerar en datumtid utan tidszon, som visas som en millisekund för år-månad-timme-minut-sekund-millisekund.

JSON-format: String.

Den lagrar inte eller representerar en tidszon. I stället är det en beskrivning av datumet, som används för födelsedagar, kombinerat med lokal tid enligt en väggklocka.

Det kan inte representera en instans på tidslinjen utan ytterligare information som en förskjutning eller tidszon.

Den kan kapslas in i en toDateTimeOnly-funktion.

Serialiseringsformat: ISO-8601 utökat förskjutningsformat för datum och tid.

Det använder DateTimeFormatter ISO_LOCAL_DATE_TIME för att avserialisera och serialisera värdet. [Läs mer](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME&quot;)

**Litteral representation**

```json
date("<dateTimeOnly in ISO-8601 format>")  
```

**Exempel**

```json
date("2021-02-19T00.00.000")
date("2021-02-19T00.00")
```

## dateTime {#date-time}

**Beskrivning**

Datumtidskonstant som även beaktar tidszon. Den representerar ett datum/tid med en förskjutning från UTC.

Den kan visas som ett ögonblick i tid med ytterligare information om förskjutningen. Det är ett sätt att representera ett specifikt &quot;ögonblick&quot; på en viss plats i världen.

JSON-format: String.

Den kan kapslas in i en toDateTime-funktion.

Serialiseringsformat: ISO-8601 utökat förskjutningsformat för datum och tid.

Det använder DateTimeFormatter ISO_OFFSET_DATE_TIME för att avserialisera och serialisera värdet. [Läs mer](https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME)

Du kan också skicka ett heltal som skickar ett epokvärde. [Läs mer](https://www.epochconverter.com)

Tidszonen kan anges med en förskjutning eller en tidszonskod (exempel: Europa/Paris, Z - betyder UTC).

**Litteral representation**

```json
toDateTime("<dateTime in ISO-8601 format>")
```

```json
date("<dateTime in ISO-8601 format>")
```

```json
toDateTime(<integer value of an epoch in milliseconds>)
```

**Exempel**

```json
date("2021-02-19T00.00.000Z")
```

```json
toDateTime("1977-04-22T06:00:00Z")
```

```json
toDateTime("2011-12-03T15:15:30Z")
```

```json
toDateTime("2011-12-03T15:15:30.123Z")
```

```json
toDateTime("2011-12-03T15:15:30.123+02:00")
```

```json
toDateTime("2011-12-03T15:15:30.123-00:20")
```

```json
toDateTime(1560762190189)
```

## varaktighet {#duration}

**Beskrivning**

Den representerar en tidsbaserad tidsmängd, till exempel &quot;34,5 sekunder&quot;. Den modellerar en kvantitet eller tid i millisekunder.

De tidsenheter som stöds är: millisekunder, sekunder, minuter, timmar och dagar där en dag motsvarar 24 timmar. År och månader stöds inte eftersom de inte är en fast tidsmängd.

JSON-format: String.

Den måste kapslas in i en toDuration-funktion.

Serialiseringsformat: Om du vill deserialisera ett tidszons-ID använder du Java-funktionen java.time.

Duration.parse: De format som accepteras baseras på varaktighetsformatet PnDTnHnMn.nS enligt ISO-8601 med dagar som anses vara exakt 24 timmar. [Läs mer](https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-)

**Litteral representation**

```json
toDuration("<duration in ISO-8601 format>")
```

```json
toDuration(<duration in milliseconds>)
```

**Exempel**

```json
toDuration("PT5S") -- parses as 5 seconds
```

```json
toDuration(500) -- parses as 500ms
```

```json
toDuration("PT20.345S") -- parses as "20.345 seconds"
```

```json
toDuration("PT15M") -- parses as "15 minutes" (where a minute is 60 seconds)
```

```json
toDuration("PT10H")  -- parses as "10 hours" (where an hour is 3600 seconds)
```

```json
toDuration("P2D") -- parses as "2 days" (where a day is 24 hours or 86400 seconds)
```

```json
toDuration("P2DT3H4M") -- parses as "2 days, 3 hours and 4 minutes"
```

```json
toDuration("P-6H3M") -- parses as "-6 hours and +3 minutes"
```

```json
toDuration("-P6H3M") -- parses as "-6 hours and -3 minutes"
```

```json
toDuration("-P-6H+3M") -- parses as "+6 hours and -3 minutes"
```

## list {#list}

**Beskrivning**

Kommaavgränsad lista med uttryck som använder hakparenteser som avgränsare.

Polymorfism stöds inte, och därför bör alla uttryck i listan ha samma typ.

**Litteral representation**

```json
[<expression>, <expression>, ... ]
```

**Exempel**

```json
["value1","value2"]
```

```json
[3,5]
```

```json
[toDuration(500),toDuration(800)]
```
