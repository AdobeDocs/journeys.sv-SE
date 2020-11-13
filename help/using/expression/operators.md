---
title: Operatorer
description: Lär dig mer om operatorer i avancerade uttryck
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: eec6203f63fa6d7ea706595ea866d2b330d284a8
workflow-type: tm+mt
source-wordcount: '618'
ht-degree: 4%

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

## Logisk

<table>
<thead>
<tr><th>Operatör</th><th>Literalt uttryck</th><th>Exempel</th></tr>
</thead>
<tbody>
<tr><td>och</td><td><p><pre>&lt;expression1&gt; och &lt;expression2&gt;</pre></p>Både &lt;expression1&gt; och &lt;expression2&gt; måste vara booleska. Resultatet är booleskt.</td><td><pre>3.14 &gt; 2 och 3.15 &lt; 1</pre></td></tr>
<tr><td>eller</td><td><p><pre>&lt;expression1&gt; eller &lt;expression2&gt;</pre></p><p>Både &lt;expression1&gt; och &lt;expression2&gt; måste vara booleska.</p><p> Resultatet är booleskt.</p></td><td><p><pre>3.14 &gt; 2 eller 3.15 &lt; 1</pre></p></td></tr>
<tr><td>not</td><td><p><pre>inte &lt;expression&gt;</pre></p><p>&lt;expression&gt; måste vara booleskt.</p><p> Resultatet är booleskt.</p></td><td><pre>inte 3,15 &lt; 1</pre></td></tr>
</tbody>
</table>

## Jämförelse

<table>
<thead>
<tr><th>Operatör</th><th>Literalt uttryck </th><th>Exempel</th></tr>
</thead>
<tbody><tr><td>är null</td><td><p><pre>&lt;expression&gt; är null</pre></p><p>Resultatet är booleskt.</p><p>Observera att null betyder att uttrycket inte har något utvärderat värde.</p></td><td><pre>@{BarBeacon.location} är null</pre></td></tr>
<tr><td>är inte null</td><td><p><pre>&lt;expression&gt; är inte null</pre></p><p>Resultatet är booleskt.</p><p>Observera att null betyder att uttrycket inte har något utvärderat värde.</p></td><td><pre>@ är inte null</pre></td></tr>
<tr><td>har null</td><td><p><pre>&lt;expression&gt; har null</pre>&lt;expression&gt; måste vara en lista.</p><p>Resultatet är booleskt.</p><p>Användbart för att identifiera att en lista innehåller minst ett null-värde.</p></td><td><p><pre>["foo", "bar", null] har null</pre></p>returnerar true<p><pre>["foo", "bar", ""] har null</pre></p> returnerar false eftersom "" inte betraktas som null.</td></tr>
<tr><td>==</td><td><p><pre>&lt;expression1&gt; == &lt;expression2&gt;</pre></p><p>Både &lt;expression1&gt; och &lt;expression2&gt; måste ha samma datatyp.</p><p> Resultatet är booleskt.</p></td><td><pre>3.14 == 42</pre><br /><pre>"foo" == "bar"</pre></td></tr>
<tr><td>!=</td><td><p><pre>&lt;expression1&gt; != &lt;expression2&gt;</pre></p><p> Både &lt;expression1&gt; och &lt;expression2&gt; måste ha samma datatyp.</p><p> Resultatet är booleskt.</p></td><td><pre>3.14 != 42</pre><br /><pre>"foo" != "bar"</pre></td></tr>
<tr><td>&gt;</td><td><p><pre>&lt;expression1&gt; &gt; &lt;expression2&gt;</pre></p><p>Datetime kan jämföras med Datetime.</p><p>Datetimeonly kan jämföras med Datetimeonly.</p><p>Både heltal och decimal kan jämföras med både heltal och decimal.</p><p>Alla andra kombinationer är förbjudna.</p><p>Resultatet är booleskt.</p></td><td><pre>3.14 &gt; 42</pre></td></tr>
<tr><td>&gt;=</td><td><p><pre>&lt;expression1&gt; &gt;= &lt;expression2&gt;</pre></p><p>Datetime kan jämföras med Datetime.</p><p>Datetimeonly kan jämföras med Datetimeonly.</p><p>Både heltal och decimal kan jämföras med både heltal och decimal.</p><p>Alla andra kombinationer är förbjudna.</p><p>Resultatet är booleskt.</p></td><td><pre>42 &gt;= 3.14</pre></td></tr>
<tr><td>&lt;</td><td><p><pre>&lt;expression1&gt; &lt; &lt;expression2&gt;</pre></p><p>Datetime kan jämföras med Datetime.</p><p>Datetimeonly kan jämföras med Datetimeonly.</p><p>Både heltal och decimal kan jämföras med både heltal och decimal.</p><p>Alla andra kombinationer är förbjudna.</p><p>Resultatet är booleskt.</p></td><td><pre>42 &lt; 3.14</pre></td></tr>
<tr><td>&lt;=</td><td><p><pre>&lt;expression1&gt; &lt;= &lt;expression2&gt;</pre></p><p>Datetime kan jämföras med Datetime.</p><p>Datetimeonly kan jämföras med Datetimeonly.</p><p>Både heltal och decimal kan jämföras med både heltal och decimal.</p><p>Alla andra kombinationer är förbjudna.</p><p>Resultatet är booleskt.</p></td><td><pre>42 &lt;= 3.14</pre></td></tr>
</tbody>
</table>

## Aritmetisk

<table>
<thead>
<tr><th>Operatör</th><th>Literalt uttryck </th><th>Exempel</th></tr>
</thead>
<tbody><tr><td>+</td><td><p><pre>&lt;expression1&gt; + &lt;expression2&gt;</pre></p><p>Båda uttrycken måste vara numeriska (heltal eller decimal). </p><p>Resultatet är också numeriskt.</p></td><td><p><p><pre>1 + 2</pre></p></p><br /><p>Returnerar 3</p></td></tr>
<tr><td>-</td><td><p><pre>&lt;expression1&gt; - &lt;expression2&gt;</pre></p><p> Båda uttrycken måste vara numeriska (heltal eller decimal).</p><p> Resultatet är också numeriskt.</p></td><td><p><pre>2 - 1</pre></p>Returnerar 1</td></tr>
<tr><td>/</td><td><p><pre>&lt;expression1&gt; / &lt;expression2&gt;</pre></p><p>Båda uttrycken måste vara numeriska (heltal eller decimal). </p><p>Resultatet är också numeriskt.</p><p>&lt;expression2&gt; får inte vara lika med 0 (returnerar 0).</p></td><td><p><pre>4 / 2</pre></p>Returnerar 2</td></tr>
<tr><td>*</td><td><p><pre>&lt;expression1&gt; * &lt;expression2&gt;</pre></p><p> Båda uttrycken måste vara numeriska (heltal eller decimal). </p><p>Resultatet är också numeriskt.</p></td><td><p><pre>3 * 4</pre></p>Returnerar 12</td></tr>
<tr><td>%</td><td><p><pre>&lt;expression1&gt; % &lt;expression2&gt;</pre></p><p>Båda uttrycken måste vara numeriska (heltal eller decimal).</p><p> Resultatet är också numeriskt.</p></td><td><p><pre>3 % 2</pre></p>Returnerar 1.</td></tr>
</tbody>
</table>

## Matematik

<table>
<thead>
<tr><th>Operatör</th><th>Literalt uttryck</th><th>Exempel</th></tr>
</thead>
<tbody><tr><td>är numerisk</td><td><p><pre>&lt;expression&gt; är numeriskt</pre></p><p>Uttryckstypen är heltal eller decimal.</p></td><td><pre>@ är numeriskt</pre></td></tr>
<tr><td>är heltal</td><td><p><pre>&lt;expression&gt; är heltal</pre></p><p>Uttryckstypen är ett heltal.</p></td><td><pre>@ är heltal</pre></td></tr>
<tr><td>är decimal</td><td><p><pre>&lt;expression&gt; är decimal</pre></p><p>Uttryckstypen är decimal.</p></td><td><pre>@ är decimalt</pre></td></tr>
</tbody>
</table>

## Sträng

<table>
<thead>
<tr><th>Operatör</th><th>Literalt uttryck </th><th>Exempel</th></tr>
</thead>
<tbody><tr><td>+</td><td><p><pre>&lt;sträng&gt; + &lt;uttryck&gt;</pre></p><p><pre>&lt;expression&gt; + &lt;string&gt;</pre></p><p>Det sammanfogar två uttryck. </p><p>Ett uttryck måste vara en kedjad sträng.</p></td><td><p><pre>"den aktuella tiden är " + (now())</pre></p> Returnerar"den aktuella tiden är 2019-09-23T09:30:06.693Z"<p><pre>(now()) + " är aktuell tid"</pre></p>Returnerar "2019-09-23T09:30:06.693Z är den aktuella tiden"<p><pre>"a" + "b" + "c" + 1234</pre></p> Returnerar "abc1234".</td></tr>
</tbody>
</table>

## Datum

<table>
<thead>
<tr><th>Operatör</th><th>Literalt uttryck </th><th>Exempel</th></tr>
</thead>
<tbody>
<tr><td>+</td><td><p><pre>&lt;expression + &lt;duration&gt;</pre></p><p>Lägg till en varaktighet för ett dateTime, ett dateTimeOnly eller en varaktighet.</p></td><td><p><pre>toDateTime("2011-12-03T15:15:30Z")</pre></p><p><pre> + toDuration("PT15M")</pre></p><p>Returnerar 2011-12-03T15:30:30Z</p><p><pre>toDateTimeOnly("2011-12-03T15:15:30")</pre></p><p><pre> + toDuration("PT15M")</pre></p>Returnerar 2011-12-03T15:30:30<p><pre>now() + toDuration("PT1H")</pre></p><p>Returnerar en dateTime (med UTC-tidszon) en timme senare från aktuell tid</p><p><pre>toDuration("PT1H") + toDuration("PT1H")</pre></p><p>Returnerar PT2H</p></td></tr>
</tbody>
</table>