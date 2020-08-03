---
title: Bygga resan
description: Lär dig hur du bygger en enkel ärenderesa
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470
workflow-type: tm+mt
source-wordcount: '391'
ht-degree: 0%

---


# Bygga resan{#concept_eyw_mcy_w2b}

Nu kan **affärsanvändaren** skapa resan. Vår resa omfattar endast en väg med följande aktiviteter:

* &quot;SpaBeacon&quot; **[!UICONTROL Event]**: När en person går nära spaltmarkören får systemet en händelse och resan börjar för den personen.
* en **[!UICONTROL Condition]** aktivitet för att kontrollera att personen är en kvinna
* en **[!UICONTROL Email]** aktivitet (med Adobe Campaign Standard)
* en **[!UICONTROL End]** aktivitet

>[!NOTE]
>
>Aktiviteter **[!UICONTROL Push]** och **[!UICONTROL Email]** aktiviteter är bara tillgängliga på paletten om du har Adobe Campaign Standard.

Mer information om hur du bygger en resa finns i [](../building-journeys/journey.md).

1. Klicka på **[!UICONTROL Home]** fliken i den övre menyn och **[!UICONTROL Create]** skapa en ny resa.

   ![](../assets/journey31.png)

1. Redigera resans egenskaper i konfigurationsrutan som visas till höger. Vi kallar det&quot;Spa travel&quot; och sätter det så att det varar en månad, från den första till den 31 december.

   ![](../assets/journeyuc1_8.png)

1. Börja designa din resa genom att dra och släppa SpaBeacon-händelsen från paletten till arbetsytan. Du kan också dubbelklicka på händelsen på paletten för att lägga till den på arbetsytan.

   ![](../assets/journeyuc1_9.png)

1. Nu ska vi lägga till ett villkor för att kontrollera att personen är en kvinna. Dra och släpp en villkorsaktivitet på resan.

   ![](../assets/journeyuc1_10.png)

1. Välj **[!UICONTROL Data Source Condition]** typ och klicka i **[!UICONTROL Expression]** fältet. Du kan också definiera en villkorsetikett som ska visas på pilen på arbetsytan.

   ![](../assets/journeyuc1_11.png)

1. Använd den enkla uttrycksredigeraren för att leta efter genusfältet (_person > kön_) och släpp det till höger för att skapa följande villkor: &quot;Kön är lika med &quot;kvinna&quot;.

   ![](../assets/journeyuc1_12.png)

1. Släpp en **[!UICONTROL Email]** aktivitet och välj en mall för transaktionsmeddelanden om&quot;Spa-rabatt&quot;. Den här mallen har utformats med Adobe Campaign. Se den här [sidan](https://docs.adobe.com/content/help/en/campaign-standard/using/communication-channels/transactional-messaging/about-transactional-messaging.html).

   ![](../assets/journeyuc1_13.png)

1. Klicka i **[!UICONTROL Email]** fältet och välj e-postadressen från datakällan.

   ![](../assets/journeyuc1_14.png)

1. Definiera på samma sätt för- och efternamnspersonaliseringsfälten från datakällan.

   ![](../assets/journeyuc1_15.png)

1. Släpp en **[!UICONTROL End]** aktivitet.

   ![](../assets/journeyuc1_17.png)

1. Klicka på **[!UICONTROL Test]** växla och testa din resa med testprofiler. Om något fel uppstår kan du inaktivera testläget, ändra din resa och testa det igen. Mer information om testläget finns i [](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. När testet är klart kan du publicera din resa från den övre högra menyn.

   ![](../assets/journeyuc1_18.png)

Nästa gång en kvinna går i närheten av spafyren får hon omedelbart ett personligt&quot;Spa-rabatt&quot;-mejl.
