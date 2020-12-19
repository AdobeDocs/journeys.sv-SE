---
product: adobe campaign
solution: Journey Orchestration
title: Definiera meddelandeparametrar
description: Lär dig hur du definierar meddelandeparametrar
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '210'
ht-degree: 3%

---


# Definiera meddelandeparametrar {#concept_wy4_bf1_2gb}

![](../assets/messageparameterssection.png)

I avsnittet **[!UICONTROL Message parameters]** klistrar du in ett exempel på JSON-nyttolasten som ska skickas till den externa tjänsten.

![](../assets/customactionpayloadmessage.png)

Du kan definiera parametertypen (t.ex.: sträng, heltal osv.).

Du kan också välja mellan att ange om en parameter är en konstant eller en variabel:

* Konstant innebär att parametervärdet definieras av en teknisk person i åtgärdskonfigurationsfönstret. Värdet är alltid detsamma oavsett resa. Det kommer inte att variera och marknadsföraren kommer inte att se det när han eller hon använder den anpassade åtgärden under resan. Det kan till exempel vara ett ID som tredjepartssystemet förväntar sig. I så fall är fältet till höger om växlingskonstanten/variabeln det värde som skickas.
* Variabel innebär att parameterns värde varierar. Marknadsföraren som använder den här anpassade åtgärden i en resa kan skicka värdet han vill ha eller ange var värdet för den här parametern ska hämtas (t.ex. från händelsen, från Adobe Experience Platform). I så fall är fältet till höger om växlingskonstanten/variabeln den etikett som marknadsföraren kommer att se under resan för att namnge den här parametern.

![](../assets/customactionpayloadmessage2.png)
