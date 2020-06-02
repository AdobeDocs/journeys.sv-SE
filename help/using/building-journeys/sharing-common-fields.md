---
title: historikstegshändelser, vanliga fält
description: historikstegshändelser, vanliga fält
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
source-git-commit: 10402a774bda66629f30869102d5e6ceca267535
workflow-type: tm+mt
source-wordcount: '583'
ht-degree: 0%

---


# historikstegshändelser, vanliga fält {#sharing-common-fields}

Den här mixinen delas av travelStepEvent och travelStepProfileEvent.

Detta är de vanligaste XDM-fälten som Journey Orchestration skickar till Adobe Data Platform. Vanliga fält skickas för varje steg som bearbetas under en resa. Mer specifika fält används för anpassade åtgärder och berikning.

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

Typ: string

## nodeID

Klientnod-ID (från arbetsytan).

Typ: string

## stepID

Unikt ID för det steg som bearbetas just nu.

Typ: string

## stepName

Namnet på det steg som bearbetas just nu.

Typ: string

## stepType

Typ av steg.

Typ: string

Möjliga värden:

* Villkor
* Åtgärd
* Schemaläggare
* Timer

## stepStatus

Status för steget, som representerar status för steget, när bearbetningen har slutförts (och steghändelsen utlösts).

Typ: string

Status kan vara:

* avslutad: steget saknar övergång och bearbetningen har slutförts.
* fel: Stegbearbetningen har orsakat ett fel.
* övergångar: steget väntar på att en händelse ska övergå till ett annat steg.
* med tak: Steget har misslyckats på ett fel med begränsning, vilket uppstod under en åtgärd eller anrikning.
* tidsgräns: steget har misslyckats på ett timeout-fel som uppstod under en åtgärd eller en anrikning.
* instanceTimedout: steget har stoppat bearbetningen eftersom instansen har nått sin timeout.

## travelID

ID för resan.

Typ: string

## travelVersionID

ID för reseversionen. Detta id representerar identitetsreferensen till resan, när det gäller travelStepEvent.

Typ: string

## travelVersionName

Namn på reseversionen.

Typ: string

## travelVersion

Version av reseversionen.

Typ: string

## instanceID

Internt ID för reseinstansen.

Typ: string

## externalKey

Extern nyckel som extraherats från händelsen för att bearbeta den.

Typ: string

## parentStepID

Steg-ID för den överordnade för det aktuella bearbetade steget i instansen.

Typ: string

## parentStepName

Stegnamn för det överordnade steget i det aktuella steget.

Typ: string

## parentTransitionID

ID för övergången som har fört instansen till det bearbetade steget.

Typ: string

## parentTransitionName

Namnet på övergången som har fört instansen till det bearbetade steget.

Typ: string

## inTest

Anger om den här resan är i testläge eller inte.

Typ: boolesk

## processingTime

Total tid i millisekunder från instansstegsinkomsten till behandlingens slut.

Typ: long

## instanceType

Anger instanstypen, om den är batch eller unitary.

Typ: string

Värden: batch/unitary

## repeatIndex

Index för upprepningen om resan är batch och återkommande (den första körningen har recidiIndex = 1).

Typ: long

## isBatchToUnitary

Anger om den här enhetsförekomsten har utlösts från en gruppinstans.

Typ: boolesk

## batchExternalKey

Extern nyckel för batchhändelse.

Typ: string

## batchInstanceID

detta är batchförekomstens ID.

Typ: string

## batchUnitaryBranchID

om instansen har utlösts från en gruppinstans, ett enhetsförgrunds-ID.

Typ: string
