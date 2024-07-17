---
product: adobe campaign
title: Allmänt
description: Lär dig mer om avancerade uttrycksgeneraliseringar
feature: Journeys
role: Data Engineer
level: Experienced
exl-id: ba474219-7c9e-4f93-8e9c-16c317131614
source-git-commit: 712f66b2715bac0af206755e59728c95499fa110
workflow-type: tm+mt
source-wordcount: '224'
ht-degree: 1%

---

# Allmänt {#concept_rcy_qj5_dgb}

## Parenteser och uttrycksprioritet{#section_edf_fks_bgb}

Parenteser kan användas för att göra ett komplext uttryck mer läsbart. _(&lt;expression>)_ är motsvarigheten till _&lt;expression>_. Parenteser kan också användas för att definiera utvärderingsordningen och associativiteten.

Uttrycken utvärderas från vänster till höger. Associativiteten för aritmetiska operatorer måste tillämpas: multiplikationer och indelningar prioriteras framför tillägg och subtraktioner. För att införa en viss ordning måste parenteser läggas till för att avgränsa operationerna. Exempel:

<!--```5 + 2 * 10 = 25, and (5 + 2) * 10 = 70```-->

| Uttryck | Utvärdering |
|--- |--- |
| `4 + 2 * 10` | <ul><li>&#39;*&#39; har högre prioritet än &#39;+&#39;: 2 * 10 utvärderas → 20</li><li>4 + 20 → 24</li></ul> |
| `(4 + 2) * 10` | <ul><li>Parenteserna ändrar prioriteten: (4 + 2) utvärderas → 6</li><li> 6 * 10 → 60</li></ul> |

## Skiftlägeskänslighet{#section_lrb_xh5_dgb}

Här är de olika reglerna för skiftlägeskänslighet:

* Alla operatorer (och, eller, osv.) ska skrivas med gemener. _`<expression1>`och`<expression2>`_ är till exempel ett giltigt uttryck, men uttrycket _`<expression1>`AND`<expression2>`_ är inte det.
* Alla funktionsnamn är versalkänsliga. Till exempel är _inSegment()_ giltig medan funktionen _INSEGMENT()_ inte är det.
* Fältreferenser och konstanta värden är skiftlägeskänsliga: de är inte inbyggda element i språket (till skillnad från operatorer och funktioner), utan skapas av slutanvändaren.

## Returnerad uttryckstyp{#section_gyc_435_53b}

Beroende på användningssammanhanget kan uttrycksredigeraren returnera olika värden.

| Avancerad användning av uttrycksredigerare | Returnerad uttryckstyp förväntades |
|--- |--- |
| Villkor (datakällans villkor, datumvillkor) | boolesk |
| Anpassad timer | dateTimeOnly |
| Mappning av åtgärdsparametrar | Alla |
