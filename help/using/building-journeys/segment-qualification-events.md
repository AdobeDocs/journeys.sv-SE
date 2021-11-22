---
product: adobe campaign
title: Segment med kvalificeringshändelser
description: Läs mer om kvalificeringshändelser för segment
feature: Journeys
role: User
level: Intermediate
exl-id: e8e54dbd-8178-4c70-907c-68eb4dc54da7
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '790'
ht-degree: 1%

---

# Segment med kvalificeringshändelser {#segment-qualification}

## Om segmentkvalificeringshändelser{#about-segment-qualification}

Med den här aktiviteten kan din resa lyssna på ingångar och utgångar för profiler i Adobe Experience Platform-segment för att få individer att komma in på eller gå framåt under en resa. Mer information om att skapa segment finns i [section](../segment/about-segments.md).

Säg att du har ett &quot;silverkundssegment&quot;. Med den här aktiviteten kan ni få alla nya silverkunder att ta sig in på en resa och skicka en serie personaliserade meddelanden till dem.

Den här typen av händelse kan placeras som det första steget eller senare under resan.

>[!IMPORTANT]
>
>Tänk på att Adobe Experience Platform-segment beräknas en gång om dagen (**batch** segment) eller i realtid (**direktuppspelad** segment, med alternativet High Frequency Audiences i Adobe Experience Platform).
>
>Om det valda segmentet direktuppspelas kan de personer som tillhör det segmentet komma in på resan i realtid. Om segmentet är en batch kan personer som nyligen är kvalificerade för det här segmentet komma in på resan när segmentberäkningen körs på Adobe Experience Platform.


1. Ta fram **[!UICONTROL Events]** kategori och släpp en **[!UICONTROL Segment qualification]** på arbetsytan.

   ![](../assets/segment5.png)

1. Lägg till en **[!UICONTROL Label]** till aktiviteten. Det här steget är valfritt.

1. Klicka på **[!UICONTROL Segment]** och markera de segment som du vill använda.

   >[!NOTE]
   >
   >Observera att du kan anpassa kolumnerna som visas i listan och sortera dem.

   ![](../assets/segment6.png)

   När segmentet har lagts till visas **[!UICONTROL Copy]** kan du kopiera dess namn och ID:

   `{"name":"Loyalty membership“,”id":"8597c5dc-70e3-4b05-8fb9-7e938f5c07a3"}`

   ![](../assets/segment-copy.png)

1. I **[!UICONTROL Behaviour]** väljer du om du vill lyssna på segmentingångar, utgångar eller både och.

   >[!NOTE]
   >
   >Observera att **[!UICONTROL Enter]** och **[!UICONTROL Exit]** motsvarar **Realiserad** och **Avslutade** segmentdeltagarstatus från Adobe Experience Platform. Mer information om hur du utvärderar ett segment finns i [Dokumentation för segmenteringstjänst](https://experienceleague.adobe.com/docs/experience-platform/segmentation/tutorials/evaluate-a-segment.html?lang=en#interpret-segment-results).

1. Välj ett namnutrymme. Detta behövs bara om händelsen är placerad som det första steget i resan.

   ![](../assets/segment7.png)

Nyttolasten innehåller följande kontextinformation som du kan använda i villkor och åtgärder:

* beteendet (entré, exit)
* tidsstämpel för kvalificeringen
* segment-ID

När du använder uttrycksredigeraren i ett villkor eller en åtgärd som följer en **[!UICONTROL Segment qualification]** -aktivitet, du har tillgång till **[!UICONTROL SegmentQualification]** nod. Du kan välja mellan **[!UICONTROL Last qualification time]** och **[!UICONTROL status]** (ange eller avsluta).

Se [Villkorsaktivitet](../building-journeys/condition-activity.md#about_condition).

![](../assets/segment8.png)

En ny resa som innehåller en segmentkvalificeringshändelse kan användas tio minuter efter att du har publicerat den. Det här tidsintervallet motsvarar cacheuppdateringsintervallet för den dedikerade tjänsten. Du måste därför vänta tio minuter innan du kan använda den här resan.

## God praxis {#best-practices-segments}

The **[!UICONTROL Segment Qualification]** Aktiviteten gör det möjligt att omedelbart ta sig in på resor för personer som kvalificerats eller diskvalificerats från ett Adobe Experience Platform-segment.

Mottagningshastigheten för den här informationen är hög. Mätningarna visar en hastighet på 10 000 mottagna händelser per sekund. Därför bör du se till att du förstår hur höga ingångstoppar kan bli, hur du undviker dem och hur du gör din resa redo för dem.

### Gruppsegment{#batch-speed-segment-qualification}

Observera att en ingångstopp kommer att inträffa vid tidpunkten för den dagliga beräkningen när du använder en segmentkvalificering för ett batchsegment. Toppens storlek beror på antalet personer som dagligen kommer in i (eller avslutar) segmentet.

Om gruppsegmentet dessutom är nyskapat och används omedelbart under en resa kan den första beräkningsomgången få ett mycket stort antal personer att komma in på resan.

### Strömmade segment{#streamed-speed-segment-qualification}

Vid användning av segmentkvalificering för direktuppspelade segment är risken mindre för att få stora toppar av ingångar/utgångar på grund av den kontinuerliga utvärderingen av segmentet. Men om segmentdefinitionen leder till att ett stort antal kunder kvalificerar sig samtidigt kan det ändå bli en topp.

Mer information om direktuppspelningssegmentering finns i [page](https://experienceleague.adobe.com/docs/experience-platform/segmentation/api/streaming-segmentation.html#api)

### Så här undviker du överbelastningar{#overloads-speed-segment-qualification}

Här följer några tips som hjälper dig att undvika att överbelasta system som används på resor (datakällor, anpassade åtgärder, Adobe Campaign Standard-åtgärder).

Använd inte **[!UICONTROL Segment Qualification]** -aktiviteten, ett batchsegment omedelbart efter att det har skapats. Den första beräkningstopp undviks. Observera att det blir en gul varning på arbetsytan om du ska använda ett segment som aldrig har beräknats.

![](../assets/segment-error.png)

Införa en begränsning för datakällor och åtgärder som används under resor för att undvika att överbelasta dem (se [section](../api/capping.md)). Observera att begränsningsregeln inte har några nya försök. Om du vill försöka igen måste du markera kryssrutan för att använda en alternativ sökväg under resan **[!UICONTROL Add an alternative path in case of a timeout or an error]** i villkor eller åtgärder.

Innan du använder segmentet i en produktionsresa ska du alltid först utvärdera antalet individer som kvalificerar sig för det här segmentet varje dag. Om du vill göra det kan du kontrollera **[!UICONTROL Segments]** i Adobe Experience Platform och titta på diagrammet till höger.

![](../assets/segment-overload.png)
