---
title: Versionsinformation
description: Läs om versionsinformation
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
source-git-commit: 8023d7780d43f1de4447c63568f641ce204722c7

---


# Versionsinformation {#release-notes}

På den här sidan visas alla nya funktioner och förbättringar för resesamordning.
Du kan även läsa [Dokumentationsuppdateringar](../release-notes/documentation-updates.md).

## Q1 Release - februari 2019 {#q1-release---february-2019}

**Tidszonshantering**

Tidszoner hanteras nu på resenivå. Två parametrar har lagts till i resans egenskaper:

![](../assets/rn-timezone.png)

* I listrutan **Tidszon** kan du välja en viss tidszon. Som standard används webbläsarens tidszon.

* I kryssrutan Tidszon för **profil** kan du använda tidszonen Experience Platform-profil för den person som går in på resan, om den är tillgänglig. Annars används den tidszon som definieras i listrutan. Den här funktionen är inte kompatibel med resor utan namnutrymme.

**Sammanhangsberoende hjälp**

En sammanhangsberoende hjälpfunktion finns nu tillgänglig för olika sorteringsskärmar på resan. Det innebär att du med ett enda klick direkt kan få tillgång till dokumentationen om de funktioner som du för närvarande använder.

Om du vill visa sammanhangsberoende hjälp klickar du på ikonen&quot;i&quot; i skärmens övre högra hörn.

Den här funktionen är för närvarande tillgänglig på listskärmarna Hem, Datakällor, Händelser och Åtgärder.

**Andra ändringar**

* I testläge kan du med en ny parameter definiera tidsökaren.  tidsvänteaktiviteter kan hålla i sig. På så sätt kan du snabbt komma åt testresultaten.

* I testläge kan du nu utlösa alla händelser på resan.


* Med en ny parameter kan du definiera tidslinjen.  tidsvänteaktiviteter kan hålla i sig. På så sätt kan du snabbt komma åt testresultaten.

* Journeys Orchestration finns nu i EMEA.

* Ny ikon på paletten för att visa eller inte visa tillgängliga objekt. sans namespace. par standard.

* canvas, deconnection, petite icone, qui dit disconnected node.

* short cut C ttes les list

* palettens användargränssnitt, ikon de search results

* Pouvoir capper les anropar en des APIS externes (datakällor eller åtgärder). marque n&#39;accept que 500 call par second, elle pourra mettre un capping a 500 call seconds qui evite de surcharger system de loyalty levels

* loggar du test log. Avantstatus = fel. quand on apply systemtieds. Possibility de voir code erreur phrase qu&#39;à renvoyé le systeme. -> ds un test en cas d&#39;erreur, systemlayers, error code, error response.

* stoppad borttagning av resa

* resa: version 1 il the met is latest

1er mars.


## GA-release - december 2019 {#ga-release---december-2019}

Journey Orchestration är nu GA.

Bygg realtidssamordning med hjälp av kontextuella data lagrade i händelser eller datakällor.

Journey Orchestration möjliggör realtidssamordning som bygger på kontextuella data från händelser, information från Adobe Experience Platform eller data från API-tjänster från tredje part. I flerstegsflöden som kallas resor bestämmer programmet vilka av de bästa åtgärder som är specifika för konsumenten utifrån deras profil och beteende. Detta omfattar både den optimala tidpunkten och typen av åtgärd, till exempel att skicka ett push-meddelande till konsumenten via transaktionsmeddelandefunktionerna i Adobe Campaign Standard (kräver Adobe Campaign Standard) eller ett meddelande om ett tredjepartssystem. Dessa beslut fattas utifrån regler och Sensei-poäng.

[Läs mer](../action/working-with-adobe-campaign.md) om Journey Orchestration.

Ytterligare resurser:

* [Självstudiekurser](https://docs.adobe.com/content/help/en/platform-learn/tutorials/journey-orchestration/introduction.html)
* [Community](https://www.adobe.com/go/journeyorchestrationcommunity)