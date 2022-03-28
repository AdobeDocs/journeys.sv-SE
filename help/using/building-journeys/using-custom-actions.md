---
product: adobe campaign
title: Använda anpassade åtgärder
description: Läs mer om åtgärdsaktiviteter
feature: Journeys
role: User
level: Intermediate
exl-id: 9996d1eb-ddef-46dd-aaa9-c37fa9deb2f9
source-git-commit: 8980df5cc238a7195f01a1631e418a8de677fbea
workflow-type: tm+mt
source-wordcount: '253'
ht-degree: 9%

---

# Använda anpassade åtgärder {#section_f2c_hbg_nhb}

I aktivitetskonfigurationsrutan visas URL-konfigurationsparametrarna och autentiseringsparametrarna som har konfigurerats för den anpassade åtgärden. [Läs mer](../action/about-custom-action-configuration.md).

## URL-konfiguration

### Dynamisk sökväg

Om URL:en innehåller en dynamisk sökväg anger du sökvägen i **[!UICONTROL Path]** fält.

>[!NOTE]
>
>Du kan inte konfigurera den statiska delen av URL-adressen i resan, utan i den globala konfigurationen för den anpassade åtgärden. [Läs mer](../action/about-custom-action-configuration.md).

Om du vill sammanfoga fält och enkla textsträngar använder du strängfunktionerna eller plustecknet (+) i den avancerade uttrycksredigeraren. Omsluter enkla textsträngar med enkla citattecken (&#39;) eller inom dubbla citattecken (&quot;). [Läs mer](../expression/expressionadvanced.md).

I den här tabellen visas ett exempel på konfiguration:

| Fält | Värde |
| --- | --- |
| URL | `https://xxx.yyy.com:8080/somethingstatic/` |
| Bana | `The id of marketingCampaign + '/messages'` |

Den sammanfogade URL:en har följande format:

`https://xxx.yyy.com:8080/somethingstatic/`\&lt;campaign id=&quot;&quot;>`/messages`

![](../assets/journey-custom-action-url.png)

### Sidhuvuden

The **[!UICONTROL URL Configuration]** -avsnittet visar de dynamiska rubrikfälten, men inte de konstanta rubrikfälten. Dynamiska rubrikfält är HTTP-rubrikfält vars värde är konfigurerat som en variabel. [Läs mer](../action/about-custom-action-configuration.md).

Ange vid behov värdet för dynamiska rubrikfält:

1. Välj den anpassade åtgärden under resan.
1. Klicka på pennikonen bredvid rubrikfältet i konfigurationsfönstret **[!UICONTROL URL Configuration]** -avsnitt.

   ![](../assets/journey-dynamicheaderfield.png)

1. Markera ett fält och klicka på **[!UICONTROL OK]**.

## Åtgärdsparametrar

I **[!UICONTROL Action parameters]** visas meddelandeparametrar som _&quot;Variabel&quot;_. För de här parametrarna kan du definiera var informationen ska hämtas (exempel: händelser, datakällor), skicka värden manuellt eller använd den avancerade uttrycksredigeraren för avancerade användningsområden. Avancerade användningsområden kan vara datahantering och annan funktionsanvändning. [Läs mer](../expression/expressionadvanced.md).

**Relaterade ämnen**

[Konfigurera en åtgärd](../action/about-custom-action-configuration.md)
