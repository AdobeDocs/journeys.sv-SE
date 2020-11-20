---
product: adobe campaign
solution: Journey Orchestration
title: distinkt
description: Lär dig mer om funktionens distinkt
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '83'
ht-degree: 13%

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
