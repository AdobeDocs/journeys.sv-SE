---
product: adobe campaign
solution: Journey Orchestration
title: concat
description: Lär dig mer om funktionssammanfogningen
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '40'
ht-degree: 12%

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
