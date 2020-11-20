---
product: adobe campaign
solution: Journey Orchestration
title: i
description: Läs mer om funktionen i
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '111'
ht-degree: 11%

---


# i {#in}

Kontrollerar om det första argumentvärdet finns i listan. Kontrollen utförs med en likhetskontroll för varje argumentvärde. Det returnerar true om argumentvärdet hittas, annars false.

Typen av `<expression>` måste matcha objekten i listan. Typer av objekt i listan måste, som en påminnelse, matcha varandra.

## Kategori

Lista

## Funktionssyntax

`in(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| Sträng | Sträng |
| Boolean | Boolean |
| Heltal | Heltal |
| Decimal | Decimal |
| Varaktighet | Varaktighet |
| DateTime | DateTime |
| DateTimeOnly | DateTimeOnly |
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |

## Signatur och returtyp

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<duration>,<listDuration>)`

Returnera ett booleskt värde.

## Exempel

`in(4,[4,5,3,4])`

Returnerar true.

`in(8,[4,5,3,4])`

Returnerar false.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
