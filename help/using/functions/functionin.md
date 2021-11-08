---
product: adobe campaign
title: in
description: Läs mer om funktionen i
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 6a19ae25-99c9-47f9-8417-c3d247dbbe3f
source-git-commit: 9c33474a72542b6ad1d1ae0854622dfd7575f2d9
workflow-type: tm+mt
source-wordcount: '113'
ht-degree: 15%

---

# in {#in}

Kontrollerar om det första argumentvärdet finns i listan. Kontrollen utförs med en likhetskontroll för varje argumentvärde. Det returnerar true om argumentvärdet hittas, annars false.

Typ av `<expression>` måste matcha med objekt i listan. Typer av objekt i listan måste, som en påminnelse, matcha varandra.

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
| Lista | listDateOnly |

## Signatur och returtyp

`in(<integer>,<listInteger>)`

`in(<decimal>,<listDecimal>)`

`in(<string>,<listString>)`

`in(<boolean>,<listBoolean>)`

`in(<dateTimeOnly>,<listDateTimeOnly>)`

`in(<dateTime>,<listDateTime>)`

`in(<dateOnly>,<listDateOnly>)`

`in(<duration>,<listDuration>)`

Returnera ett booleskt värde.

## Exempel

`in(4,[4,5,3,4])`

Returnerar true.

`in(8,[4,5,3,4])`

Returnerar false.

`in(#{ExperiencePlatform.ProfileFieldGroup.profile.person.gender}, ["male"])`
