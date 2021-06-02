---
product: adobe campaign
title: toDateTime
description: Läs mer om funktionen toDateTime
feature: Resor
role: Data Engineer
level: Experienced
exl-id: 0b8d1a82-a55a-4a4d-ad1b-35499d52b469
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '94'
ht-degree: 6%

---

# toDateTime {#toDateTime}

Konverterar parametrar till ett datum/tid-värde, beroende på deras typer.

## Kategori

Konvertering

## Funktionssyntax

`toDateTime(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| datum och tid i ISO-8601-format | string |
| tidszon-id | string |
| datum tid utan tidszon | dateTimeOnly |
| heltalsvärde för en epok i millisekunder | heltal |

>[!NOTE]
>
>Tidszons-ID måste vara en strängkonstant. Det kan inte vara en fältreferens eller ett uttryck. Mer information om datatyper finns på [den här sidan](../expression/data-types.md).

## Underskrifter och returnerade typer

`toDateTime(<string>)`

`toDateTime(<dateTimeOnly>,<stringified time zone id>)`

`toDateTime(<integer>)`

Returnera en **dateTime**.

<!--`toDateTime(<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`

Returns a date time with default time zone UTC.

`toDateTime(<year>,<month>,<dayOfMonth>)`
`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>)`
`toDateTime(<timeZone>,<year>,<month>,<dayOfMonth>)`

Return a datetime where hour, minute and second set to 0.

`toDateTime(<stringified timeZone>,<year>,<month>,<dayOfMonth>,<hour>,<minute>,<second>)`
`toDateTime(<string>)`
`toDateTime(<string>,<integer>)`
`toDateTime(<stringified timeZone>,<dateTimeOnly)`

`toDateTime(<timeZone>,<integer>)`

Return a datetime.

-->

## Exempel

`toDateTime ("2016-08-18T23:17:59.123Z")`

Returnerar 2016-08-18T23:17:59.123Z

`toDateTime(toDateTimeOnly("2016-08-18T23:17:59.123"),"UTC")`

Returnerar 2016-08-18T23:17:59.123Z

`toDateTime(1560762190189)`

Returnerar 2019-06-17T09:03:10.189Z

<!--`toDateTime ("2016-08-18T23:17:59.123", "UTC")`

Returns 2016-08-18T23:17:59.123Z.

`toDateTime("Z",2016,8,18,23,17,59)`

Returns 2016-08-18T23:17:59.000Z.

`toDateTime("Z",2016,8,18)`

Returns 2016-08-18T00:00:00.000Z.-->
