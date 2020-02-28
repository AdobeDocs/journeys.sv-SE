---
title: Vänta på aktivitet
description: Läs mer om vänteaktiviteten
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
source-git-commit: 3f8f7eb34a11f0ff87ed3c55e7294b5bdbfb9383

---


# Vänta på aktivitet{#section_rlm_nft_dgb}

Om du vill vänta innan du kör nästa aktivitet i sökvägen kan du använda en **[!UICONTROL Wait]** aktivitet. Du kan definiera tidpunkten då nästa aktivitet ska köras. Fyra alternativ är tillgängliga:

* [Varaktighet](#duration)
* [Fast datum](#fixed_date)
* [Egen](#custom)
* [Tidsoptimering för e-postsändning](#email_send_time_optimization)

## Om aktiviteten Vänta{#about_wait}

Så här prioriterar du vänta när du använder flera bilder parallellt. Om de har samma tidskonfiguration och ett annat, men överlappande, villkor är den ovan angivna väntetiden den som prioriteras. Till exempel är villkoret för den första väntetiden&quot;att vara kvinna&quot; och villkoret för den andra väntetiden parallellt är&quot;att vara en VIP&quot;. Den första vänteaktiviteten kommer att prioriteras

Observera också att om två olika platser är parallella så kommer den första att prioriteras, oavsett dess lodräta position. Om t.ex. en 1-timmars väntan är över och en 30-minuters väntan är under, efter 30 minuter, kommer 30-minutersväntan att bearbetas.

Du kan definiera ett villkor om du vill begränsa väntetiden till en viss population.

>[!NOTE]
>
>Maximal väntetid är 30 dagar.
>
>I testläge kan du med parametern **Väntetid i test** definiera hur lång tid varje vänteaktivitet ska ta. Standardtiden är 10 sekunder. Detta säkerställer att du får testresultaten snabbt. Se [](../building-journeys/testing-the-journey.md)

## Väntetid{#duration}

Ange väntetiden innan nästa aktivitet körs.

![](../assets/journey55.png)

## Vänta fast{#fixed_date}

Välj datumet för körningen av nästa aktivitet.

![](../assets/journey56.png)

## Anpassad väntetid{#custom}

Med det här alternativet kan du definiera ett anpassat datum, till exempel 12 juli 2020 klockan 17.00, med hjälp av ett avancerat uttryck som baseras på ett fält som kommer från en händelse eller en datakälla. Du kan inte definiera en anpassad längd, till exempel 7 dagar. Uttrycket i uttrycksredigeraren ska ha formatet dateTimeOnly. Se [](../expression/expressionadvanced.md). Mer information om formatet dateTimeOnly finns i [](../expression/data-types.md).

>[!NOTE]
>
>Du kan återanvända ett dateTimeOnly-uttryck eller använda en funktion för att konvertera till dateTimeOnly. Till exempel: toDateTimeOnly(@{Event.offerOpened.activity.endTime}), fältet i händelsen har formatet 2016-08-12T09:46:06.
>
>Tidszonen **** förväntas i egenskaperna för din resa. Därför är det inte möjligt i dag från gränssnittet till en direkt punkt vid en fullständig ISO-8601-tidsstämpelblandningstid och tidszonsförskjutning som 2016-08-12T09:46:06.982-05. Se [](../building-journeys/timezone-management.md).

![](../assets/journey57.png)

## Tidsoptimering för e-postsändning{#email_send_time_optimization}

>[!CAUTION]
>
>Funktionen för tidsoptimering för e-postutskick är bara tillgänglig för kunder som använder datatjänsten Adobe Campaign Standard.

Den här typen av väntan använder en bakgrundsmusik som beräknas i plattformen. Poängen beräknar sannolikheten för att klicka eller öppna ett e-postmeddelande i framtiden baserat på tidigare beteenden. Observera att algoritmen som beräknar poängen behöver en viss mängd data för att fungera. Om det inte finns tillräckligt med data används därför standardväntetiden. Vid publiceringen får du ett meddelande om att standardtiden gäller.

>[!NOTE]
>
>Den första händelsen i din resa måste ha ett namnutrymme.
>
>Den här funktionen är bara tillgänglig efter en **[!UICONTROL Email]** aktivitet. Ni måste ha Adobe Campaign Standard.

1. I **[!UICONTROL Amount of time]** fältet anger du hur många timmar e-postutskick ska optimeras.
1. I **[!UICONTROL Optimization type]** fältet väljer du om optimeringen ska öka antalet klick eller öppna.
1. I fältet **Standardtid** anger du den väntetid som ska vara standard om poängen för den prediktiva sändningstiden inte är tillgängliga.

   >[!NOTE]
   >
   >Observera att poängen för sändningstid inte är tillgängliga eftersom det inte finns tillräckligt med data för att utföra beräkningen. I så fall kommer du att informeras om att standardtiden gäller vid publiceringen.

![](../assets/journey57bis.png)
