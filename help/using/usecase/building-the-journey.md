---
title: Bygga resan
description: 'Lär dig hur du bygger en avancerad ärenderesa '
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
source-git-commit: 771b2b35e0aba412e4eb9e12a5d57de3d4c7068c
workflow-type: tm+mt
source-wordcount: '839'
ht-degree: 0%

---


# Bygga resan {#concept_owm_kdy_w2b}

Nu kan **affärsanvändaren** skapa resan. Vår resa kommer att omfatta följande aktiviteter:

* två **[!UICONTROL Event]** verksamheter: &quot;LobbyBeacon&quot; och &quot;RestaurantBeacon&quot;
* två **[!UICONTROL Condition]** verksamheter
* tre **[!UICONTROL Push]** verksamheter och en **[!UICONTROL Email]** verksamhet (med Adobe Campaign Standard)
* en **[!UICONTROL Wait]** aktivitet
* fyra **[!UICONTROL End]** verksamheter

>[!NOTE]
>
>Aktiviteter **[!UICONTROL Push]** och **[!UICONTROL Email]** aktiviteter är bara tillgängliga på paletten om du har Adobe Campaign Standard.

Mer information om hur du bygger en resa finns i [](../building-journeys/journey.md).

## Första steget{#section_ntb_ws1_ffb}

1. Klicka på **[!UICONTROL Home]** fliken i den övre menyn och **[!UICONTROL Create]** skapa en ny resa.

   ![](../assets/journey31.png)

1. Redigera resans egenskaper i konfigurationsrutan som visas till höger. Lägg till ett namn och ställ in det så att det varar i en månad, från den 1 till den 31 december.

   ![](../assets/journeyuc2_12.png)

1. Börja designa din resa genom att dra och släppa händelsen&quot;LobbyBeacon&quot; från paletten till arbetsytan. Du kan också dubbelklicka på händelsen på paletten för att lägga till den på arbetsytan.

   ![](../assets/journeyuc2_13.png)

1. Nu ska vi lägga till ett villkor för att kontrollera att personen inte har kontaktats under de senaste 24 timmarna och kontrollera om han är en lojalitetsmedlem. Dra och släpp en villkorsaktivitet på resan.

   ![](../assets/journeyuc2_14.png)

1. Välj **[!UICONTROL Data Source Condition]** typ och klicka i **[!UICONTROL Expression]** fältet. Du kan också definiera en villkorsetikett som ska visas på pilen på arbetsytan. I vårt exempel ersätter vi&quot;Villkor 1&quot; med&quot;Lojalitetsmedlem&quot;.

   ![](../assets/journeyuc2_15.png)

1. Klicka på **[!UICONTROL Advanced mode]** och definiera följande villkor baserat på fälten &quot;timestamp&quot; och &quot;directMarketing.sending.value&quot; som kommer från datakällan för Adobe Experience Platform. Uttryckets syntax är:

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
   and
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   ![](../assets/journeyuc2_30.png)

1. Klicka på **[!UICONTROL Add a path]** knappen och skapa en andra kundväg för kunder som inte har kontaktats de senaste 24 timmarna och inte är lojalitetsmedlem. Namnge sökvägen&quot;Inte lojalitetsmedlem&quot;. Uttryckets syntax är:

   ```
   count(#{ExperiencePlatformDataSource.MarltonExperience.experienceevent.all(
       currentDataPackField.directMarketing.sends.value > 0 and
       currentDataPackField.timestamp > nowWithDelta(-1, "days").timestamp}) == 0
   and not
       #{ExperiencePlatformDataSource.MarltonProfiles.Profile._customer.marlton.loyaltyMember}
   ```

   >[!NOTE]
   >
   >I den andra delen av uttrycket är &quot;Profil&quot; valfri.

1. Vi måste välja ett namnutrymme. Ett namnutrymme är förvalt baserat på schemaegenskaper. Du kan behålla den förmarkerade. Mer information om namnutrymmen finns i [](../event/selecting-the-namespace.md).

I vårt fall vill vi bara reagera på dessa två villkor, så vi markerar inte rutan **[!UICONTROL Show path for other cases than the one(s) above]**.

Två banor skapas efter ditt villkor:

* _Kunder som inte har kontaktats de senaste 24 timmarna och som är lojalitetsmedlemmar._
* _Kunder som inte har kontaktats de senaste 24 timmarna och inte är lojalitetsmedlemmar._

![](../assets/journeyuc2_16.png)

## Första sökväg: kunden är en lojalitetsmedlem {#section_otb_ws1_ffb}

1. I den första banan ska vi lägga till ett villkor för att kontrollera om han har en reservation. Dra och släpp en villkorsaktivitet på resan.

   ![](../assets/journeyuc2_17.png)

1. Välj **[!UICONTROL Data Source Condition]** typ och definiera villkoret baserat på den reservationsstatusinformation som hämtas från reservationssystemet:

   ```
   #{MarltonReservation.MarltonFieldGroup.reservation} == true
   ```

   ![](../assets/journeyuc2_18.png)

1. När du väljer ett fält från en extern datakälla visar den högra delen av skärmen listan med parametrar som definierades när den externa datakällan konfigurerades (se [](../usecase/configuring-the-data-sources.md)). Klicka på parameternamnet och definiera värdet för reservationssystemnyckeln, Experience Cloud-ID, i följande exempel:

   ```
   @{LobbyBeacon.endUserIDs._experience.mcid.id}
   ```

   ![](../assets/journeyuc2_19.png)

1. Eftersom vi även vill reagera på kunder som inte har någon reservation måste vi markera kryssrutan **[!UICONTROL Show path for other cases than the one(s) above]**.

   ![](../assets/journeyuc2_20.png)

   Två banor skapas:

   * _Kunder som har bokat ett rum_
   * _Kunder som inte har bokat ett rum._

   ![](../assets/journeyuc2_21.png)

1. I den första sökvägen (rumsbokad) släpper du en **[!UICONTROL Push]** aktivitet, väljer din mobilapp och din välkomstmall.

   ![](../assets/journeyuc2_22.png)

1. Definiera de **[!UICONTROL Target]** fält som krävs för att skicka push-meddelandet.

   * **[!UICONTROL Push platform]**: välj plattform: **[!UICONTROL Apple Push Notification Server]** (Apple) eller **[!UICONTROL Firebase Cloud Messaging]** (Android).
   * **[!UICONTROL Registration token]**: lägg till följande uttryck (baserat på den konfigurerade händelsen) med det avancerade läget:

      ```
      @{LobbyBeacon._experience.campaign.message.profileSnapshot.pushNotificationTokens.first().token}
      ```

1. Definiera personaliseringsfält för push-meddelanden. I vårt exempel: förnamn och efternamn.

1. Lägg till en RestaurantBeacon-händelse.

   ![](../assets/journeyuc2_23.png)

1. Lägg till en ny **[!UICONTROL Push]** aktivitet, välj mallen&quot;Måltidsrabatt&quot; och definiera **[!UICONTROL Address]** - och **[!UICONTROL Personalization]** -fälten. Lägg till en **[!UICONTROL End]** aktivitet.

   ![](../assets/journeyuc2_24.png)

1. Vi vill bara skicka ett push-meddelande om måltidsrabatt om personen kommer in på restaurangen inom 6 timmar efter välkomstpushet. För att göra detta måste vi använda en vänteaktivitet. Placera markören på välkomstpush-aktiviteten och klicka på plustecknet (+). Lägg till en vänteaktivitet i den nya sökvägen och definiera en varaktighet på 6 timmar. Den första stödberättigande aktiviteten kommer att väljas. Om restauranghändelsen tas emot mindre än 6 timmar efter välkomstsändningen skickas push-aktiviteten. Om ingen restauranghändelse tas emot inom de kommande 6 timmarna väljs väntetiden. Placera en **[!UICONTROL End]** aktivitet efter vänteaktiviteten.

   ![](../assets/journeyuc2_31.png)

1. I den andra sökvägen som följer reservationsvillkoret (ingen rumsbokning) lägger du till en **[!UICONTROL Push]** aktivitet och väljer mallen&quot;Rumstariffer&quot;. Lägg till en **[!UICONTROL End]** aktivitet.

   ![](../assets/journeyuc2_25.png)

## Andra sökväg: kunden inte är en lojalitetsmedlem{#section_ptb_ws1_ffb}

1. I den andra sökvägen som följer det första villkoret (kunden är inte en lojalitetsmedlem) lägger du till en **[!UICONTROL Email]** aktivitet och väljer mallen&quot;Lojalitetsmedlemskap&quot;.

   ![](../assets/journeyuc2_26.png)

1. I **[!UICONTROL Address]** fältet väljer du e-postadressen från datakällan.

   ![](../assets/journeyuc2_27.png)

1. Definiera för- och efternamnspersonaliseringsfälten från datakällan.

   ![](../assets/journeyuc2_28.png)

1. Lägg till en **[!UICONTROL End]** aktivitet.

Klicka på **[!UICONTROL Test]** växlingsknappen och testa din resa. Om något fel uppstår kan du inaktivera testläget, ändra din resa och testa det igen. Mer information om testläget finns i [](../building-journeys/testing-the-journey.md).

![](../assets/journeyuc2_32bis.png)

När testet är klart kan du publicera din resa från den övre högra menyn.

![](../assets/journeyuc2_32.png)
