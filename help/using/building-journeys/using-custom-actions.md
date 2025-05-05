---
product: adobe campaign
title: Använda anpassade åtgärder
description: Läs mer om åtgärdsaktiviteter
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '298'
ht-degree: 7%

---

# Använda anpassade åtgärder {#section_f2c_hbg_nhb}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/sv/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


I aktivitetskonfigurationsrutan visas URL-konfigurationsparametrarna och autentiseringsparametrarna som har konfigurerats för den anpassade åtgärden. [Läs mer](../action/about-custom-action-configuration.md).

## URL-konfiguration

### Dynamisk sökväg

Om URL:en innehåller en dynamisk sökväg anger du sökvägen i fältet **[!UICONTROL Path]**.

>[!NOTE]
>
>Du kan inte konfigurera den statiska delen av URL-adressen i resan, utan i den globala konfigurationen för den anpassade åtgärden. [Läs mer](../action/about-custom-action-configuration.md).

Om du vill sammanfoga fält och enkla textsträngar använder du strängfunktionerna eller plustecknet (+) i den avancerade uttrycksredigeraren. Omsluter enkla textsträngar med enkla citattecken (&#39;) eller inom dubbla citattecken (&quot;). [Läs mer](../expression/expressionadvanced.md).

I den här tabellen visas ett exempel på konfiguration:

| Fält | Värde |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Sökväg | `The id of marketingCampaign + '/messages'` |

Den sammanfogade URL:en har följande format:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;kampanj-ID\>`/messages`

![](../assets/journey-custom-action-url.png)

### Sidhuvuden

Avsnittet **[!UICONTROL URL Configuration]** visar de dynamiska rubrikfälten, men inte de konstanta rubrikfälten. Dynamiska rubrikfält är HTTP-rubrikfält vars värde är konfigurerat som en variabel. [Läs mer](../action/about-custom-action-configuration.md).

Ange vid behov värdet för dynamiska rubrikfält:

1. Välj den anpassade åtgärden under resan.
1. Klicka på pennikonen bredvid rubrikfältet i avsnittet **[!UICONTROL URL Configuration]** i konfigurationsfönstret.

   ![](../assets/journey-dynamicheaderfield.png)

1. Markera ett fält och klicka på **[!UICONTROL OK]**.

## Åtgärdsparametrar

I avsnittet **[!UICONTROL Action parameters]** ser du meddelandeparametrarna som är definierade som _&quot;Variabel&quot;_. För de här parametrarna kan du definiera var informationen ska hämtas (till exempel händelser, datakällor), skicka värden manuellt eller använda den avancerade uttrycksredigeraren för avancerade användningsfall. Avancerade användningsområden kan vara datahantering och annan funktionsanvändning. [Läs mer](../expression/expressionadvanced.md).

**Relaterade ämnen**

[Konfigurera en åtgärd](../action/about-custom-action-configuration.md)
