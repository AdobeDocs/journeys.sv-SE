---
title: journeyStep, händelser, identitetsfält
description: journeyStep, händelser, identitetsfält
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
translation-type: tm+mt
source-git-commit: b852c08a488a1bec02b8b31a1fccf1a8773b99af
workflow-type: tm+mt
source-wordcount: '59'
ht-degree: 20%

---


# journeyStep, händelser, identitetsfält {#sharing-identity-fields}

Den här mixinen är specifik för travelStepEvent: den här händelsen är relaterad till resan och har inte identityMap, som beskriver profidentiteten, om någon.

För travelStepEvent måste vi även lägga till fält som är relaterade till identiteten:

## profileID

Profilidentifierare

Typ: string

## profileNamespace

Namnutrymme för profilidentifierare

Typ: string