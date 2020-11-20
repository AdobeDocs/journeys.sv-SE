---
product: adobe campaign
solution: Journey Orchestration
title: Datatyper
description: Lär dig mer om datatyper i avancerade uttryck
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '675'
ht-degree: 3%

---


# Datatyper {#concept_gp3_rj5_dgb}

Tekniskt sett innehåller en konstant alltid en datatyp. I det litterala uttrycket anger vi bara värdet. Datatypen kan härledas från värdet (t.ex. sträng, heltal, decimal). I särskilda fall, till exempel datum och tid, använder vi dedikerade funktioner för representationen.

Så här representeras datatypsuttryck:

<table>
    <thead>
        <tr>
        <td>Datatyp</td>
        <td>Beskrivning</td>
        <td>Litteral representation</td>
        <td>Exempel</td>
        </tr>
    </thead>
    <tbody>
    <tr>
        <td>string</td>
        <td><p>Vanlig teckensekvens.</p><p>Den har ingen specifik storlek förutom den som kommer från miljön, till exempel mängden tillgängligt minne.</p><p>JSON-format: Sträng</p><p>Serialiseringsformat: UTF-8</p></td>
        <td><p>"&lt;värde&gt;"</p><p>&lt;value&gt;</p></td>
        <td><p><pre>"hello world"</pre></p><p><pre>"hello world"</pre></p></td>
    </tr>
    <tr>
        <td>heltal</td>
        <td><p>Heltalsvärde från -2^63 till 2^63-1.</p><p>JSON-format: Nummer</p></td>
        <td>&lt;heltalsvärde&gt;</td>
        <td><p><pre>42</pre></p></td>
    </tr>
    <tr>
        <td>decimal</td>
        <td><p>Decimaltal.</p><p>Det representerar ett flytande värde:</p>
        <p>- det största positiva finite-värdet av typen double, (2-2^-52)x2^1023</p>
        <p> - minsta positiva normalvärde av typen double, 2-1022</p>
        <p> - minsta positiva värde som inte är noll av typen double, 2 p-1074</p><p>JSON-format: Nummer</p><p>Serialiseringsformat: med '.' som decimalavgränsare.</p></td>
        <td>&lt;heltalsvärde&gt;.&lt;heltalsvärde&gt;</td>
        <td><p><pre>3.14</pre></p></td>
    </tr>
    <tr>
        <td>boolesk</td>
        <td><p>Bokfört booleskt värde med gemener: true eller false</p><p>JSON-format: Boolean</p></td>
        <td><p>true</p><p>false</p></td>
        <td><p><pre>true</pre></p></td>
    </tr>
    <tr>
        <td>dateTimeOnly</td>
        <td><p>Representerar en datumtid utan tidszon, som visas som en millisekund för år-månad-timme-minut-sekund-millisekund.</p><p>Den lagrar inte eller representerar en tidszon.</p><p>I stället är det en beskrivning av datumet, som används för födelsedagar, kombinerat med lokal tid enligt en väggklocka.</p><p>Det kan inte representera en instans på tidslinjen utan ytterligare information som en förskjutning eller tidszon.</p><p>Serialiseringsformat: ISO-8601 extended offset date-time format.</p><p>Det använder DateTimeFormatter.</p><p>ISO_LOCAL_DATE_TIME för att deserialisera och serialisera värdet.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_LOCAL_DATE_TIME">Läs mer</a>.</td>
        <td><p>toDateTimeOnly("&lt;dateTimeOnly i ISO-8601-format&gt;")</p></td>
        <td></td>
    </tr>
    <tr>
        <td>dateTime</td>
        <td><p>Datumtidskonstant som även beaktar tidszon.</p><p>Den representerar ett datum/tid med en förskjutning från UTC. Den kan visas som ett ögonblick i tid med ytterligare information om förskjutningen. </p><p>Det är ett sätt att representera ett specifikt "ögonblick" på en viss plats i världen.</p><p>JSON-format: Sträng.</p><p> Den måste kapslas in i en toDateTime-funktion.</p><p>
        Serialiseringsformat: ISO-8601 extended offset date-time format.</p><p> Det använder DateTimeFormatter.ISO_OFFSET_DATE_TIME för att avserialisera och serialisera värdet.</p> <a href="https://docs.oracle.com/javase/8/docs/api/java/time/format/DateTimeFormatter.html#ISO_OFFSET_DATE_TIME">Läs mer</a>. 
        <p>Du kan också skicka ett heltal som skickar ett epokvärde.</p> <a href="https://www.epochconverter.com/">Läs mer</a>.</p>
        <p>Tidszonen kan anges med en förskjutningskod eller en tidszonskod (exempel: Europa/Paris, Z - betyder UTC).</p></td>
        <td><p>toDateTime("&lt;datumTid i ISO-8601-format&gt;")</p>
        <p>toDateTime(&lt;heltalsvärde för en epok i millisekunder&gt;)</p></td>
        <td><p><pre>toDateTime("1977-04-22T06:00:00Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123Z")</pre></p><p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123+02:00")</pre></p>
        <p><pre>toDateTime</pre></p><p><pre>("2011-12-03T15:15:30.123-00:20")</pre></p><p><pre>toDateTime(1560762190189)</pre></p></td>
    </tr>
    <tr>
        <td>varaktighet</td>
        <td><p>Den representerar en tidsbaserad tidsmängd, till exempel "34,5 sekunder".</p><p> Den modellerar en kvantitet eller tid i millisekunder.</p><p>De tidsenheter som stöds är: millisekunder, sekunder, minuter, timmar, dagar där en dag är lika med 24 timmar.</p><p> År och månader stöds inte eftersom de inte är en fast tidsmängd.</p><p>JSON-format: Sträng. Den måste kapslas in i en toDuration-funktion.</p><p>Serialiseringsformat: För att avserialisera ett tidszon-ID används Java-funktionen java.time.</p><p>Duration.parse: De format som godkänns baseras på varaktighetsformatet PnDTnHnMn.nS enligt ISO-8601 med dagar som anses vara exakt 24 timmar.</p><a href="https://docs.oracle.com/javase/8/docs/api/java/time/Duration.html#parse-java.lang.CharSequence-">Läs mer</a>.</td>
        <td><p>toDuration("&lt;duration in ISO-8601 format&gt;")</p><p>toDuration(&lt;varaktighet i millisekunder&gt;)</p></td>
        <td><p><pre>toDuration("PT5S") // 5 sekunder</pre></p>
        <p><pre>toDuration(500) // </pre></p>
        <p><pre>500ms</pre></p>
        <p><pre>toDuration("PT20.345S") </pre></p>
        <p><pre>— parses as "20,345 seconds"</pre></p>
        <p><pre>toDuration("PT15M") </pre></p>
        <p><pre> — parses as "15 minutes"</pre></p>
        <p><pre>(där en minut är 60 sekunder)</pre></p>
        <p><pre>toDuration("PT10H") </pre></p>
        <p><pre>— parses as "10 timmar"</pre></p>
        <p><pre>(där en timme är 3 600 sekunder)</pre></p>
        <p><pre>toDuration("P2D") </pre></p>
        <p><pre>— parses as "2 days"</pre></p>
        <p><pre>(där en dag är </pre></p>
        <p><pre>24 timmar eller 86 400 sekunder)</pre></p>
        <p><pre>toDuration("P2DT3H4M") </pre></p>
        <p><pre>- parser som</pre></p>
        <p><pre>"2 dagar, 3 timmar och 4 minuter"</pre></p>
        <p><pre>toDuration("P-6H3M") </pre></p>
        <p><pre>- parser som</pre></p>
        <p><pre>"-6 timmar och +3 minuter"</pre></p>
        <p><pre>toDuration("-P6H3M") </pre></p>
        <p><pre>- parser som</pre></p>
        <p><pre>"-6 timmar och -3 minuter"</pre></p>
        <p><pre>toDuration("-P-6H+3M") </pre></p>
        <p><pre>- parser som</pre></p>
        <p><pre>"+6 timmar och -3 minuter"</pre></p></td>
    </tr>
    <tr>
        <td>list</td>
        <td>Kommaavgränsad lista med uttryck som använder hakparenteser som avgränsare. Polymorfism stöds inte, och därför bör alla uttryck i listan ha samma typ.</td>
        <td>[&lt;uttryck&gt;, &lt;uttryck&gt;, ... ]</td>
        <td><p><pre>["value1","value2"]</pre></p><p><pre>[3,5]</pre></p><p><pre>[toDuration(500),toDuration(800)]</pre></p></td>
    </tr>
    </tbody>
</table>
