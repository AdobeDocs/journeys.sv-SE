---
product: adobe campaign
title: Hoppa från en resa till en annan
description: Hoppa från en resa till en annan
feature: Journeys
role: User
level: Intermediate
exl-id: 520376aa-2cb5-46d6-8f21-3e03544f5da1
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '822'
ht-degree: 2%

---

# Hoppa från en resa till en annan {#jump}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._



Åtgärdsaktiviteten **[!UICONTROL Jump]** gör att du kan flytta personer från en resa till en annan. Med den här funktionen kan du:

* förenkla utformningen av mycket komplexa resor genom att dela upp dem i flera.
* bygga resor baserat på gemensamma och återanvändbara resemönster

Lägg bara till en **[!UICONTROL Jump]**-aktivitet och välj en målresa i den ursprungliga resan. När personen går in i steget **[!UICONTROL Jump]** skickas en intern händelse till den första händelsen i målresan. Om åtgärden **[!UICONTROL Jump]** lyckas fortsätter personen att göra framsteg i resan. Beteendet liknar andra åtgärder.

Under målresan kommer den första händelsen som utlöses internt av aktiviteten **[!UICONTROL Jump]** att få det enskilda flödet i resan.

## Livscykel

Säg att du har lagt till en **[!UICONTROL Jump]**-aktivitet i en resa A på en resa B. Resa A är den **ursprungliga resan** och resa B, den **målresan**.
Här är de olika stegen i körningsprocessen:

**Resan A** utlöses från en extern händelse:

1. Resa A får en extern händelse som rör en individ.
1. Personen når steget **[!UICONTROL Jump]**.
1. Personen flyttas till resa B och fortsätter till nästa steg i resa A, efter steget **[!UICONTROL Jump]**.

Under resa B utlöses den första händelsen internt via aktiviteten **[!UICONTROL Jump]** från resa A:

1. Resan B fick en intern händelse från resa A.
1. Personen börjar flyta i resa B.

>[!NOTE]
>
>Resa B kan också utlösas via en extern händelse.

## God praxis och begränsningar

### Redigering

* Aktiviteten **[!UICONTROL Jump]** är bara tillgänglig på resor som använder ett namnutrymme.
* Du kan bara hoppa till en resa som använder samma namnutrymme som ursprungsresan.
* Du kan inte hoppa till en resa som börjar med en **segmentkvalificeringshändelse**.
* Du kan inte ha en **[!UICONTROL Jump]**-aktivitet och en **Segmentkvalificeringshändelse** på samma resa.
* Du kan inkludera så många **[!UICONTROL Jump]** aktiviteter som du behöver under en resa. Efter en **[!UICONTROL Jump]** kan du lägga till alla aktiviteter som behövs.
* Du kan ha så många hoppnivåer som behövs. Till exempel hoppar resa A till resa B, som hoppar till resa C och så vidare.
* Målresan kan även innehålla så många **[!UICONTROL Jump]** aktiviteter som behövs.
* Loopmönster stöds inte. Det finns inget sätt att länka samman två eller flera resor som skulle skapa en oändlig slinga. Aktivitetskonfigurationsskärmen **[!UICONTROL Jump]** förhindrar dig från att göra detta.

### Körning

* När aktiviteten **[!UICONTROL Jump]** körs aktiveras den senaste versionen av målresan.
* Som vanligt kan en unik individ bara vara närvarande en gång under samma resa. Om den person som har åsamkats från ursprungsresan redan befinner sig på målresan, kommer personen alltså inte att ta sig in på målresan. Inget fel rapporteras för aktiviteten **[!UICONTROL Jump]** eftersom detta är ett normalt beteende.

## Konfigurera hoppaktiviteten

1. Utforma din **ursprungliga resa**.

   ![](../assets/jump1.png)

1. Lägg till en **[!UICONTROL Jump]**-aktivitet från kategorin **[!UICONTROL ACTIONS]** när som helst under resan. Lägg till en etikett och en beskrivning.

   ![](../assets/jump2.png)

1. Klicka i fältet **Målresa**.
I listan visas alla reseversioner som är utkast, live eller i testläge. Resurser som använder ett annat namnutrymme eller som börjar med en **Segmentkvalificeringshändelse** är inte tillgängliga. Målresor som skulle skapa ett slingmönster filtreras också bort.

   ![](../assets/jump3.png)

   >[!NOTE]
   >
   >Du kan klicka på ikonen **Öppna målresa** till höger för att öppna målresan på en ny flik.

1. Välj den målresa som du vill hoppa till.
Fältet **Första händelsen** är förifyllt med namnet på målresans första händelse. Om målresan innehåller flera händelser tillåts endast **[!UICONTROL Jump]** för den första händelsen.

   ![](../assets/jump4.png)

1. Avsnittet **Åtgärdsparametrar** visar alla fält i målhändelsen. På samma sätt som för andra typer av åtgärder mappar du varje fält med fält från ursprungshändelsen eller datakällan. Den här informationen skickas till målresan vid körning.
1. Lägg till nästa aktiviteter för att slutföra din ursprungliga resa.

   ![](../assets/jump5.png)


   >[!NOTE]
   >
   >Personens identitet mappas automatiskt. Den här informationen visas inte i gränssnittet.

Din **[!UICONTROL Jump]**-aktivitet har konfigurerats. Så snart din resa är live eller i testläge kommer personer som når steget **[!UICONTROL Jump]** att pushas från till målresan.

När en **[!UICONTROL Jump]**-aktivitet har konfigurerats på en resa läggs en **[!UICONTROL Jump]**-postikon automatiskt till i början av målresan. Detta hjälper dig att identifiera att resan kan utlösas externt men också internt från en **[!UICONTROL Jump]**-aktivitet.

![](../assets/jump7.png)

## Felsökning

När resan publiceras eller i testläge inträffar fel om:
* målresan inte längre existerar
* målresan är utkast, avslutad eller stoppad
* om den första händelsen i målresan har ändrats och mappningen är bruten

![](../assets/jump6.png)
