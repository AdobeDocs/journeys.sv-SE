---
title: URL-konfiguration
description: Läs mer om URL-konfiguration
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
source-git-commit: 1bc8d845716044671a11c200e4bab92302841994
workflow-type: tm+mt
source-wordcount: '126'
ht-degree: 0%

---


# URL-konfiguration {#concept_gbg_1f1_2gb}

När du konfigurerar en anpassad åtgärd måste du definiera följande **[!UICONTROL URL Configuration]** parametrar:

![](../assets/journeyurlconfiguration.png)

1. Lägg till den externa **[!UICONTROL URL]** tjänstens namn.

   >[!NOTE]
   >
   >Vi rekommenderar starkt att du använder HTTPS av säkerhetsskäl. Vi tillåter inte användning av Adobe-adresser som inte är offentliga och användning av IP-adresser.

1. Välj samtalet **[!UICONTROL Method]**: det kan vara antingen **[!UICONTROL POST]** eller **[!UICONTROL PUT]**.
1. I **[!UICONTROL Headers]** avsnittet klickar du **[!UICONTROL Add a header field]** för att definiera ett nytt nyckel/värde-par. De motsvarar HTTP-rubrikerna för den begäran som görs till den externa tjänsten. Om du vill ta bort par med nyckel/värde placerar du markören i **[!UICONTROL Headers]** fältet och klickar på **[!UICONTROL Delete]** ikonen.

   **[!UICONTROL Content-Type]** och **[!UICONTROL Charset]** anges som standard och kan inte tas bort eller åsidosättas.

   >[!NOTE]
   >
   >Sidhuvuden valideras enligt följande [tolkningsregler](https://tools.ietf.org/html/rfc7230#section-3.2.4).
