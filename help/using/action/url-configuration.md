---
product: adobe campaign
title: URL-konfiguration
description: Läs mer om URL-konfiguration
feature: Resor
role: User
level: Intermediate
exl-id: e7cba6c4-a231-44f9-927a-10115e7ab1dd
source-git-commit: 185c2296a51f58e2092787edcc35ee9e4242bec8
workflow-type: tm+mt
source-wordcount: '127'
ht-degree: 14%

---

# URL-konfiguration {#concept_gbg_1f1_2gb}

När du konfigurerar en anpassad åtgärd måste du definiera följande **[!UICONTROL URL Configuration]**-parametrar:

![](../assets/journeyurlconfiguration.png)

1. Lägg till **[!UICONTROL URL]** för den externa tjänsten.

   >[!NOTE]
   >
   >Vi rekommenderar starkt att HTTPS används av säkerhetsskäl. Vi tillåter inte användning av Adobe-adresser som inte är offentliga och användning av IP-adresser.

1. Markera samtalet **[!UICONTROL Method]**: det kan vara antingen **[!UICONTROL POST]** eller **[!UICONTROL PUT]**.
1. I avsnittet **[!UICONTROL Headers]** klickar du på **[!UICONTROL Add a header field]** för att definiera ett nytt nyckel/värde-par. De motsvarar HTTP-rubrikerna för den begäran som görs till den externa tjänsten. Om du vill ta bort nyckel/värde-par placerar du markören i fältet **[!UICONTROL Headers]** och klickar på ikonen **[!UICONTROL Delete]**.

   **[!UICONTROL Content-Type]** och  **[!UICONTROL Charset]** anges som standard och kan inte tas bort eller åsidosättas.

   >[!NOTE]
   >
   >Sidhuvuden valideras enligt följande [tolkningsregler](https://tools.ietf.org/html/rfc7230#section-3.2.4).
