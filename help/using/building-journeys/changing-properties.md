---
title: Ändra egenskaper
description: Lär dig hur du ändrar egenskaper
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
source-git-commit: 76369cd714c513e0038278ad058bf1ba43fcd240

---



# Ändra egenskaper {#concept_prq_wqt_52b}

Klicka på pennikonen i det övre högra hörnet för att komma åt resans egenskaper.

Du kan ändra namnet på resan, lägga till en beskrivning, tillåta återinträde, välja start- och slutdatum och definiera en **[!UICONTROL Timeout and error]** varaktighet om du är administratör.

![](../assets/journey32.png)

## Ingång{#entrance}

Som standard tillåter nya resor återinträde. Du kan avmarkera alternativet för engångsresor, till exempel om du vill erbjuda en engångsgåva när en person går in i en affär. I så fall vill ni inte att kunden ska kunna registrera sig på nytt och få erbjudandet igen.

När en resa&quot;slutar&quot; får den statusen **[!UICONTROL Finished]**. Resan kommer att sluta låta nya individer komma in på resan. Personer som redan är på resan kommer att slutföra resan normalt.

## Tidsgräns och fel i reseaktiviteter {#timeout_and_error}

När du redigerar en åtgärd eller villkorsaktivitet kan du definiera en alternativ sökväg om ett fel eller en timeout inträffar. Om bearbetningen av aktiviteten som förhör ett tredjepartssystem överskrider den tidsgräns som anges i färdens egenskaper (**[!UICONTROL Timeout and  error]** fält), väljs den andra vägen för att utföra en eventuell reservåtgärd.

Giltiga värden är mellan 1 och 30 sekunder.

Vi rekommenderar att du definierar ett mycket kort **[!UICONTROL Timeout and error]** värde om din resa är tidskänslig (exempel: att reagera på en persons realtidsplats) eftersom du inte kan fördröja åtgärden i mer än några sekunder. Om resan är mindre tidskänslig kan du använda ett längre värde för att ge mer tid till det system som anropas för att skicka ett giltigt svar.

Journey Orchestration använder också en global timeout. Se [nästa avsnitt](#global_timeout).

## Tidsgräns för global resa {#global_timeout}

Förutom den [tidsgräns](#timeout_and_error) som används i reseaktiviteter finns det också en global tidsgräns för resan som inte visas i gränssnittet och som inte kan ändras. Den här tidsgränsen kommer att stoppa enskilda personers framsteg på resan 30 dagar efter att de har kommit in. Det innebär att en persons resa inte kan vara längre än 30 dagar. Efter timeoutperioden på 30 dagar tas personens data bort. Individer som fortfarande flyter på i slutet av tidsgränsen kommer att stoppas och de kommer att beaktas som fel vid rapporteringen.

>[!NOTE]
>
>Resesamordning reagerar inte direkt på förfrågningar om avanmälan, åtkomst eller radering av sekretess. Den globala tidsgränsen säkerställer dock att individer aldrig stannar mer än 30 dagar under någon resa.

På grund av den 30-dagars tidsgränsen för resan kan vi inte säkerställa att återinträdesspärren fungerar mer än 30 dagar när resan inte tillåts. Eftersom vi tar bort all information om personer som tagit sig in på resan 30 dagar efter ankomsten, kan vi inte veta vem som tagit sig in tidigare, mer än 30 dagar sedan.

## Tidszon och profiltidszon {#timezone}

Tidszonen definieras på resenivå.

Du kan ange en fast tidszon eller använda Experience Platform-profiler för att definiera resetidszonen.

Mer information om hantering av tidszoner finns i [](../building-journeys/timezone-management.md).
