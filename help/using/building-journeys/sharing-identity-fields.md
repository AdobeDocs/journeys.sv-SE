---
product: adobe campaign
solution: Journey Orchestration
title: journeyStep, händelser, identitetsfält
description: journeyStep, händelser, identitetsfält
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
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