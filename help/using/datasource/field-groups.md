---
title: Fältgrupper
description: Läs mer om fältgrupper
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
source-git-commit: 017d502e21605b3e0b8c61e5fea0b4f6a65d4470

---



# Fältgrupper {#concept_ntl_ypt_52b}

## Definiera fältgrupper {#section_dsz_kjd_fjb}

För varje datakälla kan du definiera flera fältgrupper, där var och en har en särskild cachevaraktighet. De gör att du kan välja vilka fält som ska hämtas från datakällan som ska användas i dina resor.

Du kan till exempel skapa en fältgrupp med telefonnummer, e-post, förnamn och adress för profilen. Sedan kan ni använda dessa data under resan för att skapa villkor. Du kan till exempel välja att bara skicka ett SMS om profilens telefonnummer inte är tomt. Om den är tom kan du skicka ett e-postmeddelande.

Även om ett standardnamn läggs till automatiskt rekommenderar vi att du ger fältgruppen ett namn. Fältgruppnamnet är synligt för andra användare i Resesamordning. Att ge fältgrupper ett relevant namn är en god vana.

När ett datakällfält används i en resa hämtas alla fält som är definierade för den fältgruppen. Därför är det bäst att bara välja de fält som du behöver för dina resor. Detta minskar svarstiden för förfrågningar i dina resor och därmed ökar prestandan. Observera att du enkelt kan lägga till fler fält i fältgrupper senare.

**[!UICONTROL Cache duration]**är också viktigt eftersom det hjälper dig att optimera prestandan. Cachevaraktighet innebär att om data från en fältgrupp hämtas en gång, cachelagras den tillfälligt i en resa. Om samma data krävs senare under samma resa kommer systemet inte att göra någon ny begäran till datakällan. Konfigurationen av cachevaraktigheten bör anpassas för varje användningsfall. Om du behöver hämta realtidsdata, t.ex. hotellbokningsstatus, väderinformation eller antalet förmånspoäng, associerar du fältgruppen som innehåller dessa fält med en kort cachevaraktighet (t.ex. en sekund). För fält som uppdateras mindre ofta (namn, kön) skapar du en andra fältgrupp med längre cachevaraktighet (till exempel 5 dagar).

Antalet resor som använder en fältgrupp visas i **[!UICONTROL Used in]**fältet. Du kan klicka på**[!UICONTROL View journeys]** knappen om du vill visa en lista över resor med den här fältgruppen.

>[!NOTE]
>
>Observera att om en fältgrupp inte har något fält visas den inte i uttrycksredigeraren.

![](../assets/journey3bis.png)

## Livscykel för fältgrupp {#section_abk_njd_fjb}

Du kan lägga till eller ta bort fält från en fältgrupp som inte används i ett utkast eller en direktresa.

Du kan lägga till men du kan inte ta bort ett fält från en fältgrupp som används i ett eller flera utkast- eller direktresor. På så sätt undviks att resorna bryts.

Följ de här stegen för att ta bort ett fält från en fältgrupp som används i en eller flera resor. Låt oss använda ett exempel på en fältgrupp med namnet&quot;Fältgrupp A&quot;.

1. Placera markören på Fältgrupp A i listan över fältgrupper och klicka på ikonen till höger. Klicka på den **[!UICONTROL Duplicate]**. Ge t.ex. den duplicerade fältgruppen namnet Fältgrupp B.
1. I Fältgrupp B tar du bort de fält som du inte längre vill använda.
1. I Fältgrupp A ska du kontrollera var fältgruppen används. Den här informationen visas i **[!UICONTROL Used in]**fältet.
1. Öppna alla resor som använder fältgrupp A.
1. Skapa nya versioner av varje resa. Redigera alla aktiviteter med fältgrupp A och välj Fältgrupp B.
1. Stoppa gamla versioner av resor som använder fältgrupp A. Du ska då inte ha någon resa med fältgrupp A.
1. Ta bort fältgrupp A eftersom den inte längre används.
