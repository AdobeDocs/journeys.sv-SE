---
product: adobe campaign
title: Ändra egenskaper
description: Lär dig hur du ändrar egenskaper
feature: Journeys
role: User
level: Intermediate
exl-id: 06d26078-b9b8-4dc4-918d-0f2426d00f54
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---

# Ändra egenskaper {#concept_prq_wqt_52b}



>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


Klicka på pennikonen i det övre högra hörnet för att komma åt resans egenskaper.

Du kan ändra namnet på resan, lägga till en beskrivning, tillåta återinträde, välja start- och slutdatum och definiera en **[!UICONTROL Timeout and error]**-varaktighet om du är administratör.

På den här skärmen visas publiceringsdatumet och namnet på den användare som publicerade resan.

Med den tekniska informationen för **Kopiera** kan du kopiera teknisk information om den resa som supportteamet kan använda för att felsöka. Följande information kopieras: JourneyVersion UID, OrgID, orgName, sandboxName, lastDeployedBy, lastDeployedAt.

![](../assets/journey32.png)

## Ingång{#entrance}

Som standard tillåter nya resor återinträde. Du kan avmarkera alternativet för engångsresor, t.ex. om du vill erbjuda en engångsgåva när en person går in i en affär. I så fall vill ni inte att kunden ska kunna registrera sig på nytt och få erbjudandet igen.

När en resa&quot;slutar&quot; får den statusen **[!UICONTROL Closed (no entrance)]**. Resan kommer att sluta låta nya individer komma in på resan. Personer som redan är på resan kommer att slutföra resan normalt.

Efter den globala standardtidsgränsen på 30 dagar växlar resan till statusen **Slutförd**. Se [avsnittet](#global_timeout).

## Tidsgräns och fel i reseaktiviteter {#timeout_and_error}

När du redigerar en åtgärd eller villkorsaktivitet kan du definiera en alternativ sökväg om ett fel eller en timeout inträffar. Om bearbetningen av aktiviteten som förhör ett tredjepartssystem överskrider den tidsgräns som definierats i färdens egenskaper (**[!UICONTROL Timeout and  error]**-fält), väljs den andra sökvägen för att utföra en eventuell reservåtgärd.

Giltiga värden är mellan 1 och 30 sekunder.

Vi rekommenderar att du definierar ett mycket kort **[!UICONTROL Timeout and error]**-värde om din resa är tidskänslig (exempel: reagerar på en persons realtidsplats) eftersom du inte kan fördröja åtgärden i mer än några sekunder. Om resan är mindre tidskänslig kan du använda ett längre värde för att ge mer tid till det system som anropas för att skicka ett giltigt svar.

[!DNL Journey Orchestration] använder också en global timeout. Se [nästa avsnitt](#global_timeout).

## Tidsgräns för global resa {#global_timeout}

Förutom [timeout](#timeout_and_error) som används i reseaktiviteter finns det också en global resetimeout som inte visas i gränssnittet och inte kan ändras. Den här tidsgränsen kommer att stoppa enskilda personers framsteg på resan 30 dagar efter att de har kommit in. Det innebär att en persons resa inte kan vara längre än 30 dagar. Efter timeoutperioden på 30 dagar tas personens data bort. Individer som fortfarande flyter på i slutet av tidsgränsen kommer att stoppas och de kommer att beaktas som fel vid rapporteringen.

>[!NOTE]
>
>[!DNL Journey Orchestration] reagerar inte direkt på begäran om avanmälan, åtkomst eller borttagning av sekretess. Den globala tidsgränsen säkerställer dock att individer aldrig stannar mer än 30 dagar under någon resa.

På grund av den 30-dagars tidsgränsen för resan kan vi inte säkerställa att återinträdesspärren fungerar mer än 30 dagar när resan inte tillåts. Eftersom vi tar bort all information om personer som tagit sig in på resan 30 dagar efter ankomsten, kan vi inte veta vem som tagit sig in tidigare, mer än 30 dagar sedan.

## Tidszon och profiltidszon {#timezone}

Tidszonen definieras på resenivå.

Du kan ange en fast tidszon eller använda Adobe Experience Platform-profiler för att definiera resetidszonen.

Mer information om hantering av tidszoner finns på [den här sidan](../building-journeys/timezone-management.md).
