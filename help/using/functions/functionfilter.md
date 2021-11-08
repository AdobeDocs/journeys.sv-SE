---
product: adobe campaign
title: filter
description: Läs mer om funktionsfiltret
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: 19a4b7f8-5636-4b8f-b81f-28ff7da99671
source-git-commit: 5225045f02fb1b2a8505756d9d7f6f60a32b3ed6
workflow-type: tm+mt
source-wordcount: '109'
ht-degree: 8%

---

# filter{#filter}

Returnerar ett listObject med objekt som har nyckelattributet som matchar ett av de angivna nyckelvärdena.

## Kategori

Lista

## Funktionssyntax

`filter(<parameters>)`

## Parametrar

| Parameter | Typ | Beskrivning |
|-----------|------------------|------------------|
| listToFilter | listObject | lista med objekt som ska filtreras. Det måste vara en fältreferens. |
| keyAttributeName | string | attributnamn i objekten i den angivna listan, används som nyckel för filtrering |
| keyValueList | lista | array med nyckelvärden för filtrering |

## Underskrifter och returnerade typer

`filter(listObject, string, listString)`

`filter(listObject, string, listInteger)`

`filter(listObject, string, listDecimal)`

`filter(listObject, string, listDateTime)`

`filter(listObject, string, listDateTimeOnly)`

`filter(listObject, string, listDateOnly)`

`filter(listObject, string, listDuration)`

`filter(listObject, string, listBoolean)`

Returnerar ett listObject.

## Exempel

Här är ett exempel på en nyttolast som skickas i en inkommande händelse, &quot;myevent&quot;:

```json
"productListItems": [{
   "id": "product1",
   "name": "the product 1",
   "price": 20
},{
   "id": "product2",
   "name": "the product 2",
   "price": 30
},{
   "id": "product3",
   "name": "the product 3",
   "price": 50
}]
```

Du kan använda följande uttryck:

```json
filter(
 @{myevent.productListItems},
 "id", 
 ["product2", "product3", "product4"]
)
```

Returnerar ett listObject som innehåller de två objekten med &quot;product2&quot; och &quot;product3&quot; som id.
