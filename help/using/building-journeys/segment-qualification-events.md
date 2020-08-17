---
title: Segmentkvalificeringshändelser
description: Läs mer om kvalificeringshändelser för segment
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
source-git-commit: 2ef3ce546a816f1d7d0398acc418a20803886a20
workflow-type: tm+mt
source-wordcount: '655'
ht-degree: 0%

---


# Segmentkvalificeringshändelser {#segment-qualification}

## Om segmentkvalificeringshändelser{#about-segment-qualification}

Med den här aktiviteten kan din resa lyssna på ingångar och utgångar för profiler i Adobe Experience Platform-segment för att få individer att komma in på eller gå framåt under en resa. For more information on segment creation, refer to this [section](../segment/about-segments.md).

Säg att du har ett &quot;silverkundssegment&quot;. Med den här aktiviteten kan ni få alla nya silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem.

Den här typen av händelse kan placeras som det första steget eller senare under resan.

Om segmentet direktuppspelas med alternativet High Frequency Audiences i Adobe Experience Platform avlyssnas ingångs- och utgångar i realtid. Om segmentet inte direktuppspelas beaktas ingångar och utgångar vid segmentberäkningstillfället.

1. Ge kategorin en ny **[!UICONTROL Events]** dimension och släpp en **[!UICONTROL Segment qualification]** aktivitet på arbetsytan.

   ![](../assets/segment5.png)

1. Lägg till en **[!UICONTROL Label]** aktivitet. Det här steget är valfritt.

1. Klicka i **[!UICONTROL Segment]** fältet och markera de segment som du vill använda.

   >[!NOTE]
   >
   >Observera att du kan anpassa kolumnerna som visas i listan och sortera dem.

   ![](../assets/segment6.png)

   När du har lagt till segmentet kan du med knappen kopiera dess namn och ID: **[!UICONTROL Copy]**

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. I **[!UICONTROL Behavior]** fältet väljer du om du vill lyssna på segmentingångar, utgångar eller både och.

1. Välj ett namnutrymme. Detta behövs bara om händelsen placeras som det första steget i resan.

   ![](../assets/segment7.png)

Nyttolasten innehåller följande kontextinformation som du kan använda i villkor och åtgärder:

* beteendet (entré, exit)
* tidsstämpel för kvalificeringen
* segment-ID

När du använder uttrycksredigeraren i ett villkor eller en åtgärd som följer på en **[!UICONTROL Segment qualification]** aktivitet, har du tillgång till **[!UICONTROL SegmentQualification]** noden. Du kan välja mellan **[!UICONTROL Last qualification time]** och **[!UICONTROL status]** (Enter eller exit).

Se [Villkorsaktivitet](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

## God praxis {#best-practices-segments}

Denna **[!UICONTROL Segment Qualification]** verksamhet gör det möjligt att omedelbart ta sig in på resor för personer som kvalificerats eller diskvalificerats från ett Adobe Experience Platform-segment.

Mottagningshastigheten för den här informationen är hög. Mätningarna visar en hastighet på 10 000 mottagna händelser per sekund. Därför bör du se till att du förstår hur höga ingångstoppar kan bli, hur du undviker dem och hur du gör din resa redo för dem.

### Gruppsegment{#batch-speed-segment-qualification}

Observera att en ingångstopp kommer att inträffa vid tidpunkten för den dagliga beräkningen när du använder en segmentkvalificering för ett batchsegment. Toppens storlek beror på antalet personer som dagligen kommer in i (eller avslutar) segmentet.

Om gruppsegmentet dessutom är nyskapat och används omedelbart under en resa kan den första beräkningsomgången få ett mycket stort antal personer att komma in på resan.

### Strömmade segment{#streamed-speed-segment-qualification}

Vid användning av segmentkvalificering för direktuppspelade segment är risken mindre för att få stora toppar av ingångar/utgångar på grund av den kontinuerliga utvärderingen av segmentet. Men om segmentdefinitionen leder till att ett stort antal kunder kvalificerar sig samtidigt kan det ändå bli en topp.

### Så här undviker du överbelastningar{#overloads-speed-segment-qualification}

Här följer några tips som hjälper dig att undvika att överbelasta system som används på resor (datakällor, anpassade åtgärder, Adobe Campaign Standard-åtgärder).

Använd inte ett batchsegment i en **[!UICONTROL Segment Qualification]** aktivitet omedelbart efter att det har skapats. Den första beräkningstopp undviks. Observera att det blir en gul varning på arbetsytan om du ska använda ett segment som aldrig har beräknats.

![](../assets/segment-error.png)

Införa en regel för begränsning av antalet datakällor och åtgärder som används under resor för att undvika överbelastning (se detta [avsnitt](../api/capping.md)). Observera att begränsningsregeln inte har några nya försök. Om du behöver göra ett nytt försök måste du använda en alternativ sökväg under resan genom att markera kryssrutan **[!UICONTROL Add an alternative path in case of a timeout or an error]** under villkor eller åtgärder.

Innan du använder segmentet i en produktionsresa ska du alltid först utvärdera antalet individer som kvalificerar sig för det här segmentet varje dag. Om du vill göra det kan du kontrollera **[!UICONTROL Segments]** avsnittet i Adobe Experience Platform och titta i diagrammet till höger.

![](../assets/segment-overload.png)
