---
product: adobe campaign
solution: Journey Orchestration
title: Funktioner
description: Läs om funktioner
feature: Journeys
role: Data Engineer
level: Experienced
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '171'
ht-degree: 71%

---


# Funktioner {#concept_p1r_qj5_dgb}

En funktion kan ha olika signaturer (en annan uppsättning ordnade parametrar). En funktionssignatur kan ha 0-N-uttryck som ordnade parametrar.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ... ,`<expression as param N>`)

Varje funktion har en specifik returtyp.

Här är en lista över funktioner som stöds.

## Huvudfunktioner

| Kategori |  -funktion |
|-------------|-----------------------|
| Adobe Experience Platform | [inSegment](../functions/functioninsegment.md) |
| Aggregera | [medel](../functions/functionavg.md) |
| Aggregera | [antal](../functions/functioncount.md) |
| Aggregera | [countOnlyNull](../functions/functioncountonlynull.md) |
| Aggregera | [countWithNull](../functions/functioncountwithnull.md) |
| Aggregera | [distinctCount](../functions/functiondistinctcount.md) |
| Aggregera | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| Aggregera | [max](../functions/functionmax.md) |
| Aggregera | [min](../functions/functionmin.md) |
| Aggregera | [summa](../functions/functionsum.md) |
| Konvertering | [toBool](../functions/functiontobool.md) |
| Konvertering | [toDateTime](../functions/functiontodatetime.md) |
| Konvertering | [toDateTimeOnly](../functions/functiontodatetimeonly.md) |
| Konvertering | [toDecimal](../functions/functiontodecimal.md) |
| Konvertering | [toDuration](../functions/functiontoduration.md) |
| Konvertering | [toInteger](../functions/functiontointeger.md) |
| Konvertering | [toString](../functions/functiontostring.md) |
| Datum | [currentTimeInMillis](../functions/functioncurrenttimeinmillis.md) |
| Datum | [inLastDays](../functions/functioninlastdays.md) |
| Datum | [inLastHours](../functions/functioninlasthours.md) |
| Datum | [inLastMonths](../functions/functioninlastmonths.md) |
| Datum | [inLastYears](../functions/functioninlastyears.md) |
| Datum | [inNextDays](../functions/functioninnextdays.md) |
| Datum | [inNextHours](../functions/functioninnexthours.md) |
| Datum | [inNextMonths](../functions/functioninnextmonths.md) |
| Datum | [inNextYears](../functions/functioninnextyears.md) |
| Datum | [nu](../functions/functionnow.md) |
| Datum | [nowWithDelta](../functions/functionnowwithdelta.md) |
| Datum | [setHours](../functions/functionsethours.md) |
| Datum | [setDays](../functions/functionsetdays.md) |
| Lista | [distinkt](../functions/functiondistinct.md) |
| Lista | [clearCount](../functions/functiondistinctcount.md) |
| Lista | [i](../functions/functionin.md) |
| Lista | [listSize](../functions/functionlistsize.md) |
| Lista | [serializeList](../functions/functionserializelist.md) |
| Lista | [sortera](../functions/functionsort.md) |
| Matematik | [slumpmässig](../functions/functionrandom.md) |
| Matematik | [rund](../functions/functionround.md) |
| Sträng | [concat](../functions/functionconcat.md) |
| Sträng | [innehåller](../functions/functioncontain.md) |
| Sträng | [containWithIgnoreCase](../functions/functioncontainwithignorecase.md) |
| Sträng | [endWith](../functions/functionendwith.md) |
| Sträng | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| Sträng | [equalWithIgnoreCase](../functions/functionequalignorecase.md) |
| Sträng | [indexOf](../functions/functionindexof.md) |
| Sträng | [isEmpty](../functions/functionisempty.md) |
| Sträng | [isNotEmpty](../functions/functionisnotempty.md) |
| Sträng | [lastIndexOf](../functions/functionlastindexof.md) |
| Sträng | [length](../functions/functionlength.md) |
| Sträng | [nedre](../functions/functionlower.md) |
| Sträng | [matchRegExp](../functions/functionmatchregexp.md) |
| Sträng | [notEqualWithIgnoreCase](../functions/functionnotequalignorecase.md) |
| Sträng | [ersätt](../functions/functionreplace.md) |
| Sträng | [replaceAll](../functions/functionreplaceall.md) |
| Sträng | [startWith](../functions/functionstartwith.md) |
| Sträng | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| Sträng | [substr](../functions/functionsubstr.md) |
| Sträng | [trimma](../functions/functiontrim.md) |
| Sträng | [upper](../functions/functionupper.md) |
| Sträng | [uuid](../functions/functionuuid.md) |