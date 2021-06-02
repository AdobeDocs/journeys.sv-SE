---
product: adobe campaign
title: toBool
description: Läs om funktionen toBool
feature: Resor
role: Data Engineer
level: Experienced
exl-id: 490144c2-1ecd-4772-ab15-e23b1b7d8f0c
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '75'
ht-degree: 8%

---

# toBool {#toBool}

Konverterar ett argumentvärde till ett booleskt värde, beroende på dess typ.

* Från sträng: försök att konvertera strängvärdet som booleskt, från &quot;true&quot; om strängvärdet är &quot;true&quot;, annars false
* Från numeriska: true om det numeriska värdet inte är lika med 0, annars false

## Kategori

Konvertering

## Funktionssyntax

`toBool(<parameter>)`

## Parametrar

* decimal
* boolesk
* string
* heltal

## Underskrifter och returnerade typer

`toBool(<decimal>)`

`toBool(<boolean>)`

`toBool(<string>)`

`toBool(<integer>)`

Returnera ett booleskt värde.

## Exempel

`toBool("true")`

`toBool(1)`

Returnerar true.

`toBool("this is not a boolean")`

Returnerar false.
