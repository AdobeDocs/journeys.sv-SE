---
product: adobe campaign
title: Bygga resan
description: Lär dig hur du bygger en enkel ärenderesa
feature: Journeys
role: User
level: Intermediate
exl-id: 22bcd7f4-03ee-4e4c-b221-9f14aeadded6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '393'
ht-degree: 36%

---

# Bygga resan{#concept_eyw_mcy_w2b}

Nu kan **företagsanvändaren** bygga resan. Vår resa omfattar endast en väg med följande aktiviteter:

* &quot;SpaBeacon&quot; **[!UICONTROL Event]**: När en person går nära spaltmarkören får systemet ett evenemang och resan börjar för den personen.
* a **[!UICONTROL Condition]** aktiviteter för att kontrollera att personen är en kvinna
* en **[!UICONTROL Email]** aktivitet (med Adobe Campaign Standard)
* en **[!UICONTROL End]** aktivitet

>[!NOTE]
>
>Aktiviteterna **[!UICONTROL Push]** och **[!UICONTROL Email]** är bara tillgängliga på paletten om du har Adobe Campaign Standard.

Mer information om hur du bygger en resa finns i [den här sidan](../building-journeys/journey.md).

1. Klicka på fliken **[!UICONTROL Home]** och **[!UICONTROL Create]** på den övre menyn för att skapa en ny resa.

   ![](../assets/journey31.png)

1. Redigera resans egenskaper i konfigurationsrutan som visas till höger. Vi kallar det&quot;Spa travel&quot; och sätter det så att det varar en månad, från den första till den 31 december.

   ![](../assets/journeyuc1_8.png)

1. Börja designa din resa genom att dra och släppa SpaBeacon-händelsen från paletten till arbetsytan. Du kan också dubbelklicka på händelsen på paletten och lägga till den på arbetsytan.

   ![](../assets/journeyuc1_9.png)

1. Nu ska vi lägga till ett villkor för att kontrollera att personen är en kvinna. Dra och släpp en villkorlig aktivitet i resan.

   ![](../assets/journeyuc1_10.png)

1. Välj typen **[!UICONTROL Data Source Condition]** och klicka i fältet **[!UICONTROL Expression]**. Du kan även definiera en villkorsetikett som visas på pilen på arbetsytan.

   ![](../assets/journeyuc1_11.png)

1. Använd den enkla uttrycksredigeraren för att leta efter könsfältet (_person > kön_) och släpp det till höger för att skapa följande villkor: &quot;Kön är lika med &quot;kvinna&quot;.

   ![](../assets/journeyuc1_12.png)

1. Släpp **[!UICONTROL Email]** och väljer en mall för transaktionsmeddelanden om&quot;specialrabatt&quot;. Den här mallen har utformats med Adobe Campaign. Se detta [page](https://experienceleague.adobe.com/docs/campaign-standard/using/communication-channels/transactional-messaging/getting-started-with-transactional-msg.html?lang=sv).

   ![](../assets/journeyuc1_13.png)

1. Klicka inuti **[!UICONTROL Email]** och välj e-postadressen från datakällan.

   ![](../assets/journeyuc1_14.png)

1. Definiera på samma sätt för- och efternamnspersonaliseringsfälten från datakällan.

   ![](../assets/journeyuc1_15.png)

1. Släpp **[!UICONTROL End]** aktivitet.

   ![](../assets/journeyuc1_17.png)

1. Klicka på **[!UICONTROL Test]** växla och testa din resa med testprofiler. Om något fel uppstår kan du inaktivera testläget, ändra din resa och testa den igen. Mer information om testläget finns i [den här sidan](../building-journeys/testing-the-journey.md).

   ![](../assets/journeyuc1_18bis.png)

1. När testet är klart kan du publicera din resa från den övre högra rullgardinsmenyn.

   ![](../assets/journeyuc1_18.png)

Nästa gång en kvinna går i närheten av spafyren får hon omedelbart ett personligt&quot;Spa-rabatt&quot;-mejl.
