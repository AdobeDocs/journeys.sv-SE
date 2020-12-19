---
product: adobe campaign
solution: Journey Orchestration
title: Allmänt
description: Lär dig mer om avancerad uttrycksgeneralitet
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 2%

---


# Allmänt {#concept_rcy_qj5_dgb}

## Parenteser och uttrycksprioritet{#section_edf_fks_bgb}

Parenteser kan användas för att göra ett komplext uttryck mer läsbart. _(&lt;expression>)_ motsvarar  _&lt;expression>_. Parenteser kan också användas för att definiera utvärderingsordningen och associativiteten.

Uttrycken utvärderas från vänster till höger. Associativiteten för aritmetiska operatorer måste tillämpas: multiplikationer och indelningar prioriteras framför tillägg och subtraktioner. För att införa en viss ordning måste parenteser läggas till för att avgränsa operationerna. Exempel:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Uttryck | Utvärdering |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; har högre prioritet än &#39;+&#39;: 2 * 10 utvärderas → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Parenteserna ändrar prioriteten: (4 + 2) utvärderas → 6</li><li> 6 * 10 → 60</li></ul> |

## Skiftlägeskänslighet{#section_lrb_xh5_dgb}

Här är de olika reglerna för skiftlägeskänslighet:

* Alla operatorer (och, eller, osv.) ska skrivas med gemener. Till exempel är _`<expression1>`och`<expression2>`_ ett giltigt uttryck medan uttrycket _`<expression1>`AND`<expression2>`_ inte är det.
* Alla funktionsnamn är skiftlägeskänsliga. Till exempel är _inSegment()_ giltigt medan funktionen _INSEGMENT()_ inte är giltig.
* Fältreferenser och konstanta värden är skiftlägeskänsliga: de inte är inbyggda element i språket (till skillnad från operatorer och funktioner), de författas av slutanvändaren.

## Returnerad uttryckstyp{#section_gyc_435_53b}

Beroende på användningssammanhanget kan uttrycksredigeraren returnera olika värden.

| Avancerad användning av uttrycksredigeraren | Returnerad uttryckstyp förväntades |
|--- |--- |
| Villkor (datakällans villkor, datumvillkor) | boolesk |
| Anpassad timer | dateTimeOnly |
| Mappning av åtgärdsparametrar | Alla |
