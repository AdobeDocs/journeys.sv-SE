---
product: adobe campaign
title: limit
description: Läs mer om funktionsgränsen
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 052ecdeb0813dcc2c4c870e8ec6b12676fbf60f1
workflow-type: tm+mt
source-wordcount: '135'
ht-degree: 4%

---

# limit {#limit}

Returnerar det första eller sista N-elementet i en lista.

## Kategori

Lista

## Funktionssyntax

`limit(<parameters>)`

## Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToProcess | listString, listBoolean, listInteger, listDecimal, listDuration, listDateTime, listDateTimeOnly, listDateOnly eller listObject | Lista att sortera ut. För listObject måste det vara en fältreferens. |
| numberOfItems | heltal | Antal objekt som ska returneras från den angivna listan. |
| firstOrLastItems | boolesk | Den här parametern är valfri (true som standard). true returnerar de första objekten. false returnerar de sista objekten. |

## Signatur och returtyp

`limit(<listString>,<integer>)`
`limit(<listString>,<integer>,<boolean>)`

Returnerar en lista med strängar.

`limit(<listInteger>,<integer>)`
`limit(<listInteger>,<integer>,<boolean>)`

Returnerar en lista med heltal.

`limit(<listDecimal>,<integer>)`
`limit(<listDecimal>,<integer>,<boolean>)`

Returnerar en lista med decimaler.

`limit(<listBoolean>,<integer>)`
`limit(<listBoolean>,<integer>,<boolean>)`

Returnerar en lista med boolesk.

`limit(<listDateOnly>,<integer>)`
`limit(<listDateOnly>,<integer>,<boolean>)`

Returnerar en lista med datum.

`limit(<listDateTimeOnly>,<integer>)`
`limit(<listDateTimeOnly>,<integer>,<boolean>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`limit(<listDateTime>,integer>)`
`limit(<listDateTime>,<integer>,<boolean>)`

Returnerar en lista med datetimes.

`limit(<listDuration>,<integer>)`
`limit(<listDuration>,<integer>,<boolean>)`

Returnerar en lista med varaktigheter.

`limit(<listObject>,<integer>)`
`limit(<listObject>,<integer>,<boolean>)`

Returnerar en lista med objekt.

## Exempel

`limit(["A", "B", "C", "D", "E"], 3)`

Returnerar `["A","B","C"]`.

`limit(["A", "B", "C", "D", "E"], 3, false)`

Returnerar `["C","D","E"]`.
