---
product: adobe campaign
title: korsa
description: Lär dig mer om funktionsöverlappningen
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: f2f5cc29f5079419662439f1cb1dee8fcb1b1ab9
workflow-type: tm+mt
source-wordcount: '79'
ht-degree: 8%

---

# korsa{#intersect}

Returnerar de gemensamma värdena i de två indatalistorna. Om en av de två listorna är null returneras en tom lista.

## Kategori

Lista

## Funktionssyntax

`intersect(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| lista 1 | lista |
| lista 2 | lista |

## Underskrifter och returnerade typer

`intersect(listString,listString)`: listString 
`intersect(listDecimal,listDecimal)`: listDecimal 
`intersect(listInteger,listInteger)`: listInteger 
`intersect(listDateTime,listDateTime)`: listDateTime 
`intersect(listDateTimeOnly,listDateTimeOnly)`: listDateTimeOnly 
`intersect(listDateOnly,listDateOnly)`: listDateOnly 
`intersect(listDuration,listDuration)`: listDuration 
`intersect(listBoolean,listBoolean)`: listBoolean

Returnerar en lista.

## Exempel

```
intersect(
    ["sports", "news", "documentary"],
    ["sports", "movies", "documentary"]
)
```

Returnerar [&quot;sport&quot;, &quot;news&quot;]

```
intersect(
    #{ExperienceDataPlatform.profile.interests},
    ["sports", "news", "documentary"]
)
```

Returnerar vanliga objekt mellan profilattribut och angiven lista med kategorier.

```
intersect(
        	#{ExperienceDataPlatform.profile.interests},
            @{myEvent.sport_interests}
)
```

Returnerar vanliga objekt mellan profilattribut och angivet händelsefält.