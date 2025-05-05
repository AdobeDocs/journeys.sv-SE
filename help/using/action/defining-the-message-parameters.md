---
product: adobe campaign
title: Definiera åtgärdsparametrarna
description: Lär dig hur du definierar åtgärdsparametrar
feature: Journeys
role: User
level: Intermediate
exl-id: ea9cdb1d-dde6-4080-8f35-7f8cd3cf3644
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '271'
ht-degree: 2%

---

# Definiera åtgärdsparametrarna {#concept_wy4_bf1_2gb}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


![](../assets/messageparameterssection.png)

I avsnittet **[!UICONTROL Action parameters]** klistrar du in ett exempel på JSON-nyttolasten som ska skickas till den externa tjänsten.

![](../assets/customactionpayloadmessage.png)

>[!NOTE]
>
>Fältnamn i nyttolasten får inte innehålla &quot;.&quot; tecken. De kan inte börja med tecknet &quot;$&quot;.

Du kan definiera parametertypen (t.ex. sträng, heltal).

Du kan också välja mellan att ange om en parameter är en konstant eller en variabel:

* Konstant innebär att parameterns värde definieras av en teknisk person i åtgärdskonfigurationsfönstret. Värdet är alltid detsamma oavsett resa. Det kommer inte att variera och marknadsföraren kommer inte att se det när han eller hon använder den anpassade åtgärden under resan. Det kan till exempel vara ett ID som tredjepartssystemet förväntar sig. I så fall är fältet till höger om växlingskonstanten/variabeln det värde som skickas.
* Variabel innebär att parameterns värde varierar. Marknadsföraren som använder den här anpassade åtgärden i en resa kan skicka värdet han vill ha eller ange var värdet för den här parametern ska hämtas (t.ex. från händelsen, från Adobe Experience Platform). I så fall är fältet till höger om växlingskonstanten/variabeln den etikett som marknadsföraren kommer att se under resan för att namnge den här parametern.

![](../assets/customactionpayloadmessage2.png)
