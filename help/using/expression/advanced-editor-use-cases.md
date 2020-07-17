---
title: Använda den avancerade uttrycksredigeraren
description: Lär dig hur du skapar avancerade uttryck
page-status-flag: never-activated
uuid: 269d590c-5a6d-40b9-a879-02f5033863fc
contentOwner: benzaama
audience: rns
content-type: reference
topic-tags: journeys
discoiquuid: 5df34f55-135a-4ea8-afc2-f9427ce5ae7b
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: eb4474313d3c0470448f9959ed757902ef0ecd2a
workflow-type: tm+mt
source-wordcount: '541'
ht-degree: 0%

---


# Använda den avancerade uttrycksredigeraren

Den avancerade uttrycksredigeraren kan användas för att skapa villkor som gör att du kan filtrera användare på dina resor. Dessa villkor gör att ni kan inrikta er på användare i tid, på datum, plats, varaktighet eller åtgärder som att köpa eller avstå från kundvagnar så att de kan återställas under resan.

>[!NOTE]
>
>Händelser börjar med @, datakällor med #.

## Bygga villkor för upplevelsehändelser

Den avancerade uttrycksredigeraren är obligatorisk för att utföra frågor på tidsserier som en lista över inköp eller tidigare klick på meddelanden. Sådana frågor kan inte utföras med den enkla redigeraren.

Erfarenhetshändelserna hämtas från Adobe Experience Platform som en samling i omvänd kronologisk ordning, vilket innebär att

* den första funktionen returnerar den senaste händelsen
* den sista funktionen returnerar den äldsta.

Låt oss till exempel säga att ni vill rikta er mot kunder som har övergett en kundvagn de senaste 7 dagarna för att skicka ett meddelande när kunden närmar sig en butik, med ett erbjudande på artiklar han vill ha som finns i butik.

**Du måste skapa följande villkor:**

Först och främst målkunder som surfar i onlinebutiken men inte slutfört beställningen de senaste sju dagarna.

<!--**This expression looks for a specified value in a string value:**

`In (“addToCart”, #{field reference from experience event})`-->

**Det här uttrycket söker efter alla händelser för den här användaren som har angetts under de senaste 7 dagarna:**

Sedan markeras alla tilläggshändelser som inte omvandlades till completePurchase.

>[!NOTE]
>
>Om du snabbt vill infoga fält i uttrycket dubbelklickar du på fältet på den vänstra panelen i redigeraren.

Den angivna tidsstämpeln fungerar som datum-/tidsvärde, den andra är antalet dagar.

    &quot;
    In( &quot;addToCart&quot;, #{ExperiencePlatformDataSource
    .ExperienceEventFieldGroup
    .experienceevent
    .all(
    inLastDays(currentDataPackField.timestamp, 7 ))
    .productData
    .productInteraction})
    
    AndNot(In( &quot;completePurchase&quot;, #{Experience} PlatformDataSource
    .ExperienceEventFieldGroup
    
    
    
    
    
    
    .experienceevent.all(inLastDays(currentDataPackField.timestamp, 7 )).productData¥.productInteraction})¥&quot;

Det här uttrycket returnerar ett booleskt värde.

**Nu ska vi skapa ett uttryck som kontrollerar att produkten finns i lager**

* I Inventory söker det här uttrycket efter kvantitetsfält för en produkt och anger att det ska vara större än 0.

`#{Inventory.fieldgroup3.quantity} > 0`

* Till höger anges nödvändiga värden, här måste vi hämta platsen för butiken som mappas från platsen för händelsen ArriveLumaStudio:

`#{ArriveLumaStudio._acpevangelists1.location.location}`

* Ange SKU och använd funktionen `first` för att hämta den senaste&quot;addToCart&quot;-interaktionen:

   ```
       #{ExperiencePlatformDataSource
                       .ExperienceEventFieldGroup
                       .experienceevent
                       .first(
                       currentDataPackField
                       .productData
                       .productInteraction == “addToCart”
                       )
                       .SKU}
   ```

Därifrån kan ni lägga till ytterligare en väg på resan när produkten inte finns i butik och skicka meddelanden med engagemangserbjudandet. Konfigurera meddelandena därefter och använd personaliseringsdata för att förbättra meddelandets mål.

## Exempel på strängändringar med den avancerade uttrycksredigeraren

**I villkor**

Detta villkor hämtar endast geofence-händelser som utlöses i&quot;Arlington&quot;:

    &quot;
    @{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name} == &quot;Arlington&quot;
    &quot;

Förklaring: Det här är en strikt strängjämförelse (skiftlägeskänslig), som motsvarar en fråga i enkelt läge som använder `equal to` med `Is sensitive` checked.

Samma fråga med `Is sensitive` omarkerad genererar följande uttryck i avancerat läge:

    &quot;
    equalIgnoreCase(@{GeofenceEntry
    .placeContext
    .POIinteraction
    .POIDetail
    .name}, &quot;Arlington&quot;)
    
    &quot;

**I åtgärder**

Följande uttryck gör att du kan definiera CRM-ID:t i ett åtgärdspersonaliseringsfält:

    &quot;
    substr(@{MobileAppLaunch
    ._myorganization
    .Identification
    .crmid}, 1,
    lastIndexOf(@{MobileAppLaunch
    ._mittorganisation
    .identifiering
    .crmid}
    }
    ))
    
    &quot;

Förklaring: I det här exemplet används `substr` och `lastIndexOf` funktioner för att ta bort klammerparenteser som omger det CRM-ID som skickas med en starthändelse för en mobilapp.

Titta på [den här videon](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/create-a-journey.html)om du vill veta mer om hur du använder den avancerade uttrycksredigeraren.
