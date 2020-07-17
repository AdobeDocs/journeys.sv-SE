---
title: Definiera meddelandeparametrar
description: Lär dig hur du definierar meddelandeparametrar
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: sauviat
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '214'
ht-degree: 0%

---


# Definiera meddelandeparametrar {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

Klistra in ett exempel på JSON-nyttolasten som ska skickas till den externa tjänsten i **[!UICONTROL Message parameters]** avsnittet.


![](../assets/customactionpayloadmessage.png)

Du kan definiera om parametertypen är rätt (t.ex.: sträng, heltal osv.).

Du kan också välja mellan att ange att en parameter är en konstant eller en variabel:

* Konstant innebär att parametervärdet definieras av en teknisk person i åtgärdskonfigurationsfönstret. Värdet är alltid detsamma oavsett resa. Det kommer inte att variera och marknadsföraren kommer inte att se det när han eller hon använder den anpassade åtgärden under resan. Det kan till exempel vara ett ID som tredjepartssystemet förväntar sig. I så fall är fältet till höger om växlingskonstanten/variabeln det värde som skickas.
* Variabel innebär att parameterns värde varierar. Marknadsföraren som använder den här anpassade åtgärden i en resa kan skicka värdet han vill ha eller ange var värdet för parametern ska hämtas (t.ex. från händelsen, från Adobe Experience Platform). I så fall är fältet till höger om växlingskonstanten/variabeln den etikett som marknadsföraren kommer att se under resan för att namnge den här parametern.
