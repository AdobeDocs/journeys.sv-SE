---
title: Hanteringsfunktioner för samlingar
description: Läs mer om datatyper i samlingshanteringsfunktioner
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

---


# Hanteringsfunktioner för samlingar {#collection-management-functions}

Uttrycksspråket innehåller även en uppsättning funktioner för att fråga efter samlingar.

Dessa funktioner förklaras nedan. I följande exempel använder vi händelsenyttolasten som innehåller en samling:

```
                { 
   "_experience":{ 
      "campaign":{ 
         "message":{ 
            "profile":{ 
               "pushNotificationTokens":[ 
                  { 
                     "token":"token_1",
                     "application":{ 
                        "_id":"APP1",
                        "name":"MarltonMobileApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_2",
                     "application":{ 
                        "_id":"APP2",
                        "name":"MarketplaceApp",
                        "version":"1.0"
                     }
                  },
                  { 
                     "token":"token_3",
                     "application":{ 
                        "_id":"APP3",
                        "name":"VendorApp",
                        "version":"2.0"
                     }
                  }
               ]
            }
         }
      }
   },
   "timestamp":"1536160728"
}
```

**Funktionen &quot;all(`<condition>`)&quot;**

Funktionen **[!UICONTROL all]**aktiverar definitionen av ett filter i en given samling genom att använda ett booleskt uttryck.

```
<listExpression>.all(<condition>)
```

Bland alla appanvändare kan du till exempel hämta de som använder IOS 13 (booleskt uttryck &quot;app used == IOS 13&quot;). Resultatet av den här funktionen är den filtrerade lista som innehåller objekt som matchar det booleska uttrycket (exempel: appanvändare 1, appanvändare 34, appanvändare 432).

I en aktivitet i Datakällans villkor kan du kontrollera om resultatet av **[!UICONTROL all]**funktionen är null eller inte. Du kan också kombinera den här**[!UICONTROL all]** funktionen med andra funktioner som **[!UICONTROL count]**. Mer information finns i Villkor för[datakälla](../building-journeys/condition-activity.md#data_source_condition).

**Exempel 1:**

Vi vill kontrollera om en användare har installerat en specifik version av ett program. För detta får vi alla push-meddelandetoken som är kopplade till mobilprogram som har version 1.0. Sedan utför vi ett villkor med funktionen för att kontrollera att den returnerade listan med tokens innehåller minst ett element. **[!UICONTROL count]**

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all(currentEventField.application.version == "1.0").token}) > 0
```

Resultatet är sant.

**Exempel 2:**

Här använder vi **[!UICONTROL count]**funktionen för att kontrollera om det finns push-meddelandetoken i samlingen.

```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) > 0
```

Resultatet blir sant.

<!--Alternatively, you can check if there is no token in the collection:

   ```
   count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token}) == 0
   ```

The result will be false.

Here we use the count function in a condition to count the number of push notification tokens in the event.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().token})`

The result is true.

Note that when the condition in the **all()** function is empty, the filter will return all the elements in the list. Hence, the expression above is equivalent to:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.application.name})`

In both cases, the result of the expression is **3**.

A query of experience events recorded on the platform may or may not include the current event that triggered the current Journey. This will depend on the relative processing time with which Journey Orchestration sees an event and started evaluating conditions, versus the time it takes for that event to be ingested into the platform. For example, when using the .all() syntax to query experience events from the platform, we recommend enforcing the exclusion of the current event (by requiring an
earlier timestamp) in order to only consider prior events.-->

>[!NOTE]
>
>När filtervillkoret i funktionen **all()** är tomt returnerar filtret alla element i listan. **För att antalet element i en samling ska kunna räknas krävs dock inte funktionen all.**


```
count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.token})
```

Resultatet av uttrycket är **3**.

**Exempel 3:**

Här kontrollerar vi om en individ inte har fått någon information inom de senaste 24 timmarna. Vi filtrerar samlingen av upplevelsehändelser som hämtats från ExperiencePlatform-datakällan med två uttryck som baseras på två element i samlingen. I synnerhet jämförs tidsstämpeln för händelsen med dateTime som returneras av **[!UICONTROL nowWithDelta]**funktionen.

```
count(#{ExperiencePlatform.MarltonExperience.experienceevent.all(
   currentDataPackField.directMarketing.sends.value > 0 and
   currentDataPackField.timestamp > nowWithDelta(-1, "days")).timestamp}) == 0
```

Resultatet blir true om det inte finns någon upplevelsehändelse som matchar de två villkoren.

**Exempel 4:**

Här ska vi kontrollera om en individ har startat minst en gång ett program de senaste 7 dagarna, till exempel för att utlösa ett push-meddelande som bjuder in honom att starta en självstudiekurs.

```
count(
 #{ExperiencePlatform.AnalyticsData.experienceevent.all(
 nowWithDelta(-7,"days") <= currentDataPackField.timestamp
 and currentDataPackField.application.firstLaunches.value > 0
)._id}) > 0
```


<!--**"All + Count" example 4:** here we use the count function in a boolean expression to see if there is push notification tokens in the collection.

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) > 0`

The result will be:

`true`

Alternatively, you can check if there is NO token in the collection:

`count(@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.all().application.name}) =0`

The result will be:

`false`-->

>[!NOTE]
>
>**[!UICONTROL currentEventField]**är bara tillgängligt när händelsesamlingar och** currentDataPackField ändras **>när du hanterar datakällsamlingar. När vi bearbetar samlingar med**[!UICONTROL all]**, **[!UICONTROL first]**och**[!UICONTROL last]**,
>slinga för varje element i samlingen ett i taget. **[!UICONTROL currentEventField]**och** currentDataPackField **>motsvarar elementet som repeteras.

**Funktionerna &quot;first(`<condition>`)&quot; och &quot;last(`<condition>`)&quot;**

Funktionerna **[!UICONTROL first]**och**[!UICONTROL last]** aktiverar även definitionen av ett filter i samlingen samtidigt som det första/sista elementet i listan som uppfyller filtret returneras.

_`<listExpression>.first(<condition>)`_

_`<listExpression>.last(<condition>)`_

**Exempel 1:**

Det här uttrycket returnerar den första push-meddelandetoken som är associerad med mobilprogram för vilka versionen är 1.0.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.first(currentEventField.application.version == "1.0").token
```

Resultatet är &quot;token_1&quot;.

**Exempel 2:**

Det här uttrycket returnerar den senaste push-meddelandetoken som är associerad med mobilprogram för vilka versionen är 1.0.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.last&#8203;(currentEventField.application.version == "1.0").token}
```

Resultatet är &quot;token_2&quot;.

>[!NOTE]
>
>Erfarenhetshändelserna hämtas från Experience Platform som en samling i omvänd kronologisk ordning, vilket innebär att
>* **[!UICONTROL first]**funktionen returnerar den senaste händelsen
>* **[!UICONTROL last]**returnerar den äldsta.


**Exempel 3:**

Vi kontrollerar om den första (senaste) Adobe Analytics-händelsen med ett värde som inte är noll för DMA ID har ett värde som är lika med 602.

```
#{ExperiencePlatform.AnalyticsProd_EvarsProps.experienceevent.first(
currentDataPackField.placeContext.geo.dmaID > 0).placeContext.geo.dmaID} == 602
```

**Funktionen &quot;at(`<index>`)&quot;**

Med funktionen kan du referera till ett visst element i en samling enligt ett index. **[!UICONTROL at]**Index 0 är samlingens första index.

_`<listExpression>`.at(`<index>`)_

**Exempel:**

Det här uttrycket returnerar listans andra push-meddelandetoken.

```
@{LobbyBeacon._experience.campaign.message.profile.pushNotificationTokens.at(1).token}
```

Resultatet är &quot;token_2&quot;.