---
product: adobe campaign
solution: Journey Orchestration
title: Segment med kvalificeringshändelser
description: Läs mer om kvalificeringshändelser för segment
feature: Resor
role: Yrkesverksamma inom affärsverksamhet
level: Mellanliggande
translation-type: tm+mt
source-git-commit: ab19cc5a3d998d1178984c5028b1ba650d3e1292
workflow-type: tm+mt
source-wordcount: '713'
ht-degree: 1%

---


# Segment med kvalificeringshändelser {#segment-qualification}

## Om segmentkvalificeringshändelser{#about-segment-qualification}

Med den här aktiviteten kan din resa lyssna på ingångar och utgångar för profiler i Adobe Experience Platform-segment för att få individer att komma in på eller gå framåt under en resa. Mer information om hur du skapar segment finns i [avsnittet](../segment/about-segments.md).

Säg att du har ett &quot;silverkundssegment&quot;. Med den här aktiviteten kan ni få alla nya silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem.

Den här typen av händelse kan placeras som det första steget eller senare under resan.

>[!IMPORTANT]
>
>Kom ihåg att Adobe Experience Platform-segment beräknas antingen en gång om dagen (**batch** segment) eller i realtid (**direktuppspelade** segment, med alternativet High Frequency Audiences i Adobe Experience Platform).
>
>Om det valda segmentet direktuppspelas kan de personer som tillhör det segmentet komma in på resan i realtid. Om segmentet är en batch kan personer som nyligen är kvalificerade för det här segmentet komma in på resan när segmentberäkningen körs på Adobe Experience Platform.


1. Ta fram kategorin **[!UICONTROL Events]** och släpp en **[!UICONTROL Segment qualification]**-aktivitet på arbetsytan.

   ![](../assets/segment5.png)

1. Lägg till en **[!UICONTROL Label]** i aktiviteten. Det här steget är valfritt.

1. Klicka i fältet **[!UICONTROL Segment]** och välj de segment som du vill använda.

   >[!NOTE]
   >
   >Observera att du kan anpassa kolumnerna som visas i listan och sortera dem.

   ![](../assets/segment6.png)

   När segmentet har lagts till kan du med knappen **[!UICONTROL Copy]** kopiera dess namn och ID:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. I fältet **[!UICONTROL Behavior]** väljer du om du vill lyssna på segmentingångar, utgångar eller både och.

1. Välj ett namnutrymme. Detta behövs bara om händelsen placeras som det första steget i resan.

   ![](../assets/segment7.png)

Nyttolasten innehåller följande kontextinformation som du kan använda i villkor och åtgärder:

* beteendet (entré, exit)
* tidsstämpel för kvalificeringen
* segment-ID

När du använder uttrycksredigeraren i ett villkor eller en åtgärd som följer på en **[!UICONTROL Segment qualification]**-aktivitet har du tillgång till noden **[!UICONTROL SegmentQualification]**. Du kan välja mellan **[!UICONTROL Last qualification time]** och **[!UICONTROL status]** (ange eller avsluta).

Se [Villkorsaktivitet](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

## God praxis {#best-practices-segments}

Aktiviteten **[!UICONTROL Segment Qualification]** gör det möjligt att omedelbart ta sig in på resor för personer som kvalificerats eller diskvalificerats från ett Adobe Experience Platform-segment.

Mottagningshastigheten för den här informationen är hög. Mätningarna visar en hastighet på 10 000 mottagna händelser per sekund. Därför bör du se till att du förstår hur höga ingångstoppar kan bli, hur du undviker dem och hur du gör din resa redo för dem.

### Gruppsegment{#batch-speed-segment-qualification}

Observera att en ingångstopp kommer att inträffa vid tidpunkten för den dagliga beräkningen när du använder en segmentkvalificering för ett batchsegment. Toppens storlek beror på antalet personer som dagligen kommer in i (eller avslutar) segmentet.

Om gruppsegmentet dessutom är nyskapat och används omedelbart under en resa kan den första beräkningsomgången få ett mycket stort antal personer att komma in på resan.

### Strömmade segment{#streamed-speed-segment-qualification}

Vid användning av segmentkvalificering för direktuppspelade segment är risken mindre för att få stora toppar av ingångar/utgångar på grund av den kontinuerliga utvärderingen av segmentet. Men om segmentdefinitionen leder till att ett stort antal kunder kvalificerar sig samtidigt kan det ändå bli en topp.

Mer information om direktuppspelningssegmentering finns på den här [sidan](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### Så här undviker du överbelastningar{#overloads-speed-segment-qualification}

Här följer några tips som hjälper dig att undvika att överbelasta system som används på resor (datakällor, anpassade åtgärder, Adobe Campaign Standard-åtgärder).

Använd inte ett gruppsegment i en **[!UICONTROL Segment Qualification]**-aktivitet omedelbart efter att det har skapats. Den första beräkningstopp undviks. Observera att det blir en gul varning på arbetsytan om du ska använda ett segment som aldrig har beräknats.

![](../assets/segment-error.png)

Ställ in en begränsning för datakällor och åtgärder som används under resor för att undvika att överbelasta dem (se [avsnittet](../api/capping.md)). Observera att begränsningsregeln inte har några nya försök. Om du behöver göra ett nytt försök måste du använda en alternativ sökväg under resan genom att markera kryssrutan **[!UICONTROL Add an alternative path in case of a timeout or an error]** under villkor eller åtgärder.

Innan du använder segmentet i en produktionsresa ska du alltid först utvärdera antalet individer som kvalificerar sig för det här segmentet varje dag. Om du vill göra det kan du kontrollera **[!UICONTROL Segments]**-avsnittet i Adobe Experience Platform och titta i diagrammet till höger.

![](../assets/segment-overload.png)
