---
product: adobe campaign
title: filter
description: Läs mer om funktionsfiltret
feature: Journeys
role: Data Engineer
level: Experienced
source-git-commit: 2195ee3863b38ead504eb6785ceb3c37735fade9
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
