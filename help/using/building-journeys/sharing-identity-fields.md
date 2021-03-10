---
product: adobe campaign
solution: Journey Orchestration
title: journeyStep, händelser, identitetsfält
description: journeyStep, händelser, identitetsfält
feature: Resor
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '63'
ht-degree: 19%

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