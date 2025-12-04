---
product: adobe campaign
title: Använda den avancerade uttrycksredigeraren
description: Läs mer om hur du skapar avancerade uttryck
feature: Journeys
role: Developer
level: Experienced
exl-id: 724ae59e-d1b5-4de9-b140-d37064e22ac6
source-git-commit: d3de66b9b28efa2636f5c0fd5a0d7ccb6132dbdd
workflow-type: tm+mt
source-wordcount: '535'
ht-degree: 9%

---

# Exempel på avancerade uttryck


>[!CAUTION]
>
>**Letar du efter Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


Den avancerade uttrycksredigeraren kan användas för att skapa villkor som gör att du kan filtrera användare på dina resor. Dessa villkor gör att ni kan inrikta er på användare i tid, på datum, plats, varaktighet eller åtgärder som att köpa eller avstå från kundvagnar så att de kan återställas under resan.

>[!NOTE]
>
>Händelser börjar med @, datakällor med #.

## Bygga villkor för upplevelsehändelser

Den avancerade uttrycksredigeraren är obligatorisk för att utföra frågor på tidsserier som en lista över inköp eller tidigare klick på meddelanden. Sådana frågor kan inte utföras med den enkla redigeraren.

Erfarenhetshändelserna hämtas från Adobe Experience Platform som en samling i omvänd kronologisk ordning, vilket innebär att

* den första funktionen returnerar den senaste händelsen
* den sista funktionen returnerar den äldsta.

Låt oss till exempel säga att ni vill rikta er mot kunder som har övergett en kundvagn de senaste 7 dagarna för att skicka ett meddelande när kunden närmar sig en butik, med ett erbjudande på artiklar de vill ha som finns i butik.

**Du måste skapa följande villkor:**

Först och främst målkunder som surfar i onlinebutiken men inte slutfört beställningen de senaste sju dagarna.

<!--**This expression looks for a specified value in a string value:**

`In ("addToCart", #{field reference from experience event})`-->

**Det här uttrycket söker efter alla händelser för den här användaren som har angetts under de senaste 7 dagarna:**

Sedan markeras alla tilläggshändelser som inte omvandlades till completePurchase.

>[!NOTE]
>
>Om du snabbt vill infoga fält i uttrycket dubbelklickar du på fältet på den vänstra panelen i redigeraren.

Den angivna tidsstämpeln fungerar som datum-/tidsvärde, den andra är antalet dagar.

```json
        in( "addToCart", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction})
        and
        not(in( "completePurchase", #{ExperiencePlatformDataSource
                        .ExperienceEventFieldGroup
                        .experienceevent
                        .all(
                        inLastDays(currentDataPackField.timestamp, 7 ))
                        .productData
                        .productInteraction}))
```

Det här uttrycket returnerar ett booleskt värde.

**Låt oss nu skapa ett uttryck som kontrollerar att produkten finns i lager**

* I Inventory söker det här uttrycket efter kvantitetsfält för en produkt och anger att det ska vara större än 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* Till höger anges de nödvändiga värdena, här måste vi hämta platsen för butiken som mappas från platsen för händelsen ArriveLumaStudio:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Ange SKU och använd funktionen `first` för att hämta den senaste addToCart-åtgärden:

  ```json
      #{ExperiencePlatformDataSource
                      .ExperienceEventFieldGroup
                      .experienceevent
                      .first(
                      currentDataPackField
                      .productData
                      .productInteraction == "addToCart"
                      )
                      .SKU}
  ```

Därifrån kan ni lägga till ytterligare en väg på resan när produkten inte finns i butik och skicka meddelanden med engagemangserbjudandet. Konfigurera meddelandena därefter och använd personaliseringsdata för att förbättra meddelandets mål.

## Exempel på strängändringar med den avancerade uttrycksredigeraren

**I villkor**

Detta villkor hämtar endast geofence-händelser som utlöses i&quot;Arlington&quot;:

```json
        @{GeofenceEntry
                    .placeContext
                    .POIinteraction
                    .POIDetail
                    .name} == "Arlington"
```

Förklaring: Detta är en strikt strängjämförelse (skiftlägeskänslig), som motsvarar en fråga i enkelt läge där `equal to` används med `Is sensitive` markerat.

Samma fråga med `Is sensitive` avmarkerat genererar följande uttryck i avancerat läge:

```json
        equalIgnoreCase(@{GeofenceEntry
                        .placeContext
                        .POIinteraction
                        .POIDetail
                        .name}, "Arlington")
```

**I åtgärder**

Följande uttryck gör att du kan definiera CRM-ID:t i ett åtgärdspersonaliseringsfält:

```json
substr(
   @{MobileAppLaunch
   ._myorganization
   .identification
   .crmid},
   1, 
   lastIndexOf(
     @{MobileAppLaunch
     ._myorganization
     .identification
     .crmid},
     '}'
   )
)
```

Förklaring: I det här exemplet används funktionerna `substr` och `lastIndexOf` för att ta bort klammerparenteser som omger det CRM-ID som skickas med en starthändelse för en mobilapp.

Titta på [den här videon](https://experienceleague.adobe.com/docs/platform-learn/tutorials/journey-orchestration/create-a-journey.html) om du vill veta mer om hur du använder den avancerade uttrycksredigeraren.
