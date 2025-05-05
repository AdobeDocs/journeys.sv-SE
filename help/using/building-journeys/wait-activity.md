---
product: adobe campaign
title: Vänta på aktivitet
description: Läs mer om vänteaktiviteten
feature: Journeys
role: User
level: Intermediate
exl-id: 819ff3c3-0e3e-4d86-b5d2-10c5b10d19e6
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 3%

---

# Vänta på aktivitet{#section_rlm_nft_dgb}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._



Om du vill vänta innan du kör nästa aktivitet i sökvägen kan du använda en **[!UICONTROL Wait]**-aktivitet. Du kan definiera tidpunkten då nästa aktivitet ska köras. Tre alternativ är tillgängliga:

* [Varaktighet](#duration)
* [Egen](#custom)
  <!--* [Email send time optimization](#email_send_time_optimization)-->

## Om aktiviteten Vänta{#about_wait}

Så här prioriterar du vänta när du använder flera bilder parallellt. Om de har samma tidskonfiguration och ett annat, men överlappande, villkor är den ovan angivna väntetiden den som prioriteras. Till exempel är villkoret för den första väntetiden&quot;att vara kvinna&quot; och villkoret för den andra väntetiden parallellt är&quot;att vara en VIP&quot;. Den första vänteaktiviteten kommer att prioriteras.

Observera också att om två olika platser är parallella så kommer den första att prioriteras, oavsett dess lodräta position. Om t.ex. en 1-timmars väntan är över och en 30-minuters väntan är under, efter 30 minuter, kommer 30-minutersväntan att bearbetas.

>[!NOTE]
>
>Maximal väntetid är 30 dagar.
>
>I testläge kan du med parametern **[!UICONTROL Wait time in test]** definiera hur lång tid varje vänteaktivitet ska ta. Den förinställda tiden är tio sekunder. Detta säkerställer att du får testresultaten snabbt. Se [den här sidan](../building-journeys/testing-the-journey.md)

## Väntetid{#duration}

Ange väntetiden innan nästa aktivitet körs.

![](../assets/journey55.png)

## Anpassad väntetid{#custom}

Med det här alternativet kan du definiera ett anpassat datum, till exempel 12 juli 2020 klockan 17.00, med hjälp av ett avancerat uttryck som baseras på ett fält som kommer från en händelse eller en datakälla. Du kan inte definiera en anpassad längd, till exempel 7 dagar. Uttrycket i uttrycksredigeraren ska ha formatet dateTimeOnly. Se [den här sidan](../expression/expressionadvanced.md). Mer information om formatet dateTimeOnly finns på [den här sidan](../expression/data-types.md).

>[!NOTE]
>
>Du kan återanvända ett dateTimeOnly-uttryck eller använda en funktion för att konvertera till dateTimeOnly. Till exempel: toDateTimeOnly(@{Event.offerOpened.activity.endTime}), fältet i händelsen har formatet 2016-08-12T09:46:06Z.
>
>**Tidszonen** förväntas i egenskaperna för din resa. Därför är det inte möjligt i dag från gränssnittet till en direkt punkt vid en fullständig ISO-8601-tidsstämpelblandningstid och tidszonsförskjutning som 2016-08-12T09:46:06.982-05. Läs [den här sidan](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

<!--## Email send time optimization{#email_send_time_optimization}

>[!CAUTION]
>
>The email send time optimization capability is only available to customers who use the [Adobe Experience Platform Data Connector](https://docs.adobe.com/content/help/en/campaign-standard/using/developing/mapping-campaign-and-aep-data/aep-about-data-connector.html).

This type of wait uses a score calculated in the Adobe Experience Platform. The score calculates the propensity to click or open an email in the future based on past behavior. Note that the algorithm calculating the score needs a certain amount of data to work. As a result, when it does not have enough data, the default wait time will apply. At publication time, you'll be notified that the default time applies.

>[!NOTE]
>
>The first event of your journey must have a namespace.
>
>This capability is only available after an **[!UICONTROL Email]** activity. You need to have Adobe Campaign Standard.

1. In the **[!UICONTROL Amount of time]** field, define the number of hours to consider to optimize email sending.
1. In the **[!UICONTROL Optimization type]** field, choose if the optimization should increase clicks or opens.
1. In the **[!UICONTROL Default time]** field, define the default time to wait if the predictive send time score is not available.

    >[!NOTE]
    >
    >Note that the send time score can be unavailable because there is not enough data to perform the calculation. In this case, you will be informed, at publication time, that the default time applies.

![](../assets/journey57bis.png)-->
