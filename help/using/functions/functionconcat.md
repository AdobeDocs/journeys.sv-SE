---
product: adobe campaign
title: concat
description: Lär dig mer om funktionssammanfogningen
feature: Journeys
role: Developer
level: Experienced
exl-id: 7a516705-2bbe-4b42-97fc-aeae11082002
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 10%

---

# concat {#concat}

Sammanfogar två strängparametrar eller en lista med strängar.

## Kategori

Sträng

## Funktionssyntax

`concat(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|------------------|
| Lista | listString |
| string | string |

## Signatur och returtyp

`concat(<string>,<string>)`

`concat(<listString>)`

Returnerar en sträng.

## Exempel

`concat("Hello","World")`

Returnerar&quot;HelloWorld&quot;.

`concat(["Hello"," ","World"])`

Returnerar &quot;Hello World&quot;.
