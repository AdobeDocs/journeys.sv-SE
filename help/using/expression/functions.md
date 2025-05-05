---
product: adobe campaign
title: Funktioner
description: Läs om funktioner
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: b514d2e9-1444-46d5-a1ac-3591e62807c1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 26%

---

# Funktioner {#concept_p1r_qj5_dgb}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


En funktion kan ha olika signaturer (en annan uppsättning ordnade parametrar). En funktionssignatur kan ha 0-N-uttryck som ordnade parametrar.

`<function name>`(`<expression as param 1>`, `<expression as param 2>`, ..., `<expression as param N>`)

Varje funktion har en specifik returtyp.

Här är en lista över funktioner som stöds.

## Huvudfunktioner

| Kategori | Funktion |
|-------------|-----------------------|
| Adobe Experience Platform | [inSegment](../functions/functioninsegment.md) |
| Aggregering | [avg](../functions/functionavg.md) |
| Aggregering | [count](../functions/functioncount.md) |
| Aggregering | [countOnlyNull](../functions/functioncountonlynull.md) |
| Aggregering | [countWithNull](../functions/functioncountwithnull.md) |
| Aggregering | [distinctCount](../functions/functiondistinctcount.md) |
| Aggregering | [distinctCountWithNull](../functions/functiondistinctcountwithnull.md) |
| Aggregering | [max](../functions/functionmax.md) |
| Aggregering | [min](../functions/functionmin.md) |
| Aggregering | [sum](../functions/functionsum.md) |
| Konvertering | [toBool](../functions/functiontobool.md) |
| Konvertering | [toDateOnly](../functions/functiontodateonly.md) |
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
| Datum | [now](../functions/functionnow.md) |
| Datum | [nowWithDelta](../functions/functionnowwithdelta.md) |
| Datum | [setHours](../functions/functionsethours.md) |
| Datum | [setDays](../functions/functionsetdays.md) |
| Datum | [updateTimeZone](../functions/functionupdatetimezone.md) |
| Lista | [distinct](../functions/functiondistinct.md) |
| Lista | [distinctWithNull](../functions/functiondistinctwithnull.md) |
| Lista | [filter](../functions/functionfilter.md) |
| Lista | [getListItem](../functions/functiongetlistitem.md) |
| Lista | [in](../functions/functionin.md) |
| Lista | [överlappa](../functions/functionintersect.md) |
| Lista | [listSize](../functions/functionlistsize.md) |
| Lista | [serializeList](../functions/functionserializelist.md) |
| Lista | [sort](../functions/functionsort.md) |
| Matematik | [random](../functions/functionrandom.md) |
| Matematik | [round](../functions/functionround.md) |
| Sträng | [concat](../functions/functionconcat.md) |
| Sträng | [contain](../functions/functioncontain.md) |
| Sträng | [containIgnoreCase](../functions/functioncontainwithignorecase.md) |
| Sträng | [endWith](../functions/functionendwith.md) |
| Sträng | [endWithIgnoreCase](../functions/functionendwithignorecase.md) |
| Sträng | [equalIgnoreCase](../functions/functionequalignorecase.md) |
| Sträng | [indexOf](../functions/functionindexof.md) |
| Sträng | [isEmpty](../functions/functionisempty.md) |
| Sträng | [isNotEmpty](../functions/functionisnotempty.md) |
| Sträng | [lastIndexOf](../functions/functionlastindexof.md) |
| Sträng | [length](../functions/functionlength.md) |
| Sträng | [lower](../functions/functionlower.md) |
| Sträng | [matchRegExp](../functions/functionmatchregexp.md) |
| Sträng | [notEqualIgnoreCase](../functions/functionnotequalignorecase.md) |
| Sträng | [replace](../functions/functionreplace.md) |
| Sträng | [replaceAll](../functions/functionreplaceall.md) |
| Sträng | [startWith](../functions/functionstartwith.md) |
| Sträng | [startWithIgnoreCase](../functions/functionstartwithignorecase.md) |
| Sträng | [substr](../functions/functionsubstr.md) |
| Sträng | [trim](../functions/functiontrim.md) |
| Sträng | [upper](../functions/functionupper.md) |
| Sträng | [uuid](../functions/functionuuid.md) |
