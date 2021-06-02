---
product: adobe campaign
title: distinct
description: Lär dig mer om funktionens distinkt
feature: Resor
role: Data Engineer
level: Experienced
exl-id: 034e4d77-2f0e-4117-9fd4-b9e35ef71a39
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '84'
ht-degree: 15%

---

# distinkt {#distinct}

Returnerar de distinkta värdena i listan utan null-värden.

## Kategori

Lista

## Funktionssyntax

`distinct(<parameter>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| Lista | listString |
| Lista | listBoolean |
| Lista | listInteger |
| Lista | listDecimal |
| Lista | listDuration |
| Lista | listDateTime |
| Lista | listDateTimeOnly |

## Underskrifter och returnerade typer

`distinct(<listInteger>)`

Returnerar en lista med heltal.

`distinct(<listDecimal>)`

Returnerar en lista med decimaler.

`distinct(<listString>)`

Returnerar en lista med strängar.

`distinct(<listDateTimeOnly>)`

Returnerar en lista med datum/tid utan hänsyn till tidszon.

`distinct(<listDateTime>)`

Returnerar en lista med datetimes.

`distinct(<listBoolean>)`

Returnerar en lista med boolesk.

`distinct(<listDuration>)`

Returnerar en lista med varaktigheter.

## Exempel

`distinct([10,2,10,null])`

Returnerar `[10, 2]`.
