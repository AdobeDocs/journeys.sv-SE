---
product: adobe campaign
title: historikstegshändelser, vanliga fält
description: historikstegshändelser, vanliga fält
feature: Journeys
role: User
level: Intermediate
exl-id: 5cf8e6b5-2162-4aa3-b071-96ede31948e6
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '582'
ht-degree: 0%

---

# historikstegshändelser, vanliga fält {#sharing-common-fields}

Den här mixinen delas av travelStepEvent och travelStepProfileEvent.

Det här är de vanliga XDM-fälten som [!DNL Journey Orchestration] skickar till Adobe Experience Platform. Vanliga fält skickas för varje steg som bearbetas under en resa. Mer specifika fält används för anpassade åtgärder och berikning.

Vissa av dessa fält är bara tillgängliga i specifika bearbetningsmönster (åtgärdskörning, datahämtning osv.) för att begränsa storleken på händelser.

## entré

Anger om användaren har gått in i resan. Om det inte finns antar vi att värdet är falskt.

Typ: boolesk

Värden: true/false

## återinträde

Anger om användaren har gjort om resan med samma instans. Om det inte finns antar vi att värdet är falskt.

Typ: boolesk

Värden: true/false

## instanceEnded

Anger om instansen har avslutats (utan fel eller inte).

Typ: boolesk

## eventID

Händelse-ID under bearbetning för stegbearbetning. Om händelsen är en extern händelse är värdet dess eventId. Om händelsen är en intern händelse är värdet det interna eventId (till exempel scheduleNotificationReceived, executionAction).

Typ: sträng

## nodeID

Klientnod-ID (från arbetsytan).

Typ: sträng

## stepID

Unikt ID för det steg som bearbetas just nu.

Typ: sträng

## stepName

Namnet på det steg som bearbetas just nu.

Typ: sträng

## stepType

Typ av steg.

Typ: sträng

Möjliga värden:

* Villkor
* Åtgärd
* Schemaläggare
* Timer

## stepStatus

Status för steget, som representerar status för steget, när bearbetningen har slutförts (och steghändelsen utlösts).

Typ: sträng

Status kan vara:

* avslutad: steget har ingen övergång och bearbetningen har slutförts.
* fel: stegbearbetningen har orsakat ett fel.
* övergångar: steget väntar på att en händelse ska övergå till ett annat steg.
* Mappat: steget har misslyckats på ett fel med begränsning, vilket uppstod under en åtgärd eller anrikning.
* timeout: steget misslyckades på ett timeout-fel, vilket uppstod under en åtgärd eller en anrikning.
* instanceTimedout: bearbetningen av steget har stoppats eftersom instansen har nått sin tidsgräns.

## travelID

ID för resan.

Typ: sträng

## travelVersionID

ID för reseversionen. Detta id representerar identitetsreferensen till resan, när det gäller travelStepEvent.

Typ: sträng

## travelVersionName

Namn på reseversionen.

Typ: sträng

## travelVersion

Version av reseversionen.

Typ: sträng

## instanceID

Internt ID för reseinstansen.

Typ: sträng

## externalKey

Extern nyckel som extraherats från händelsen för att bearbeta den.

Typ: sträng

## parentStepID

Steg-ID för den överordnade för det aktuella bearbetade steget i instansen.

Typ: sträng

## parentStepName

Stegnamn för det överordnade steget i det aktuella steget.

Typ: sträng

## parentTransitionID

ID för övergången som har fört instansen till det bearbetade steget.

Typ: sträng

## parentTransitionName

Namnet på övergången som har fört instansen till det bearbetade steget.

Typ: sträng

## inTest

Anger om den här resan är i testläge eller inte.

Typ: boolesk

## processingTime

Total tid i millisekunder från instansstegsinkomsten till behandlingens slut.

Typ: lång

## instanceType

Anger instanstypen, om den är batch eller unitary.

Typ: sträng

Värden: batch/enhet

## repeatIndex

Index för upprepningen om resan är batch och återkommande (den första körningen har recidiIndex = 1).

Typ: lång

## isBatchToUnitary

Anger om den här enhetsförekomsten har utlösts från en gruppinstans.

Typ: boolesk

## batchExternalKey

Extern nyckel för batchhändelse.

Typ: sträng

## batchInstanceID

detta är batchförekomstens ID.

Typ: sträng

## batchUnitaryBranchID

om instansen har utlösts från en gruppinstans, ett enhetsförgrunds-ID.

Typ: sträng
