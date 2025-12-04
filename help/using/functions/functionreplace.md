---
product: adobe campaign
title: ersätta
description: Läs mer om funktionsersättningen
feature: Journeys
role: Developer
level: Experienced
exl-id: f30377c2-4d5e-4905-a972-8f4ccb272bc0
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 2%

---

# ersätta {#replace}

Ersätter den första förekomsten som matchar målsträngen med ersättningssträngen i bassträngen.

Ersättningen fortsätter från början av strängen till slutet, t.ex. om&quot;a&quot; ersätts med&quot;b&quot; i strängen&quot;aaa&quot; resulterar det i&quot;ba&quot; i stället för&quot;ab&quot;.

## Kategori

Sträng

## Funktionssyntax

`replace(<parameters>)`

## Parametrar

| Parameter | Typ |
|-----------|--------------|
| bas | string |
| target | sträng (RegExp) |
| ersättare | string |

## Signatur och returtyp

`replace(<base>,<target>,<replacement>)`

Returnera en sträng.

## Exempel 1

`replace("Hello World", "l", "x")`

Returnerar &quot;Hexlo World&quot;.

## Exempel 2 {#example_2}

Eftersom målparametern är en RegExp, beroende på vilken sträng du vill ersätta, kan du behöva undvika vissa tecken. Här är ett exempel:

* sträng som ska utvärderas: `|OFFER_A|OFFER_B`
* tillhandahålls av ett profilattribut `#{ExperiencePlatform.myFieldGroup.profile.myOffers}`
* Sträng som ska ersättas: `|OFFER_A`
* Sträng ersatt av: `''`
* Du måste lägga till `\\` före tecknet `|`.

Uttrycket är:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|OFFER_A', '')`

Den returnerade strängen är: `|OFFER_B`

Du kan också skapa strängen som ska ersättas från ett visst attribut:

`replace(#{ExperiencePlatform.myFieldGroup.profile.myOffers}, '\\|' + #{ExperiencePlatform.myFieldGroup.profile.myOfferCode}, '')`
