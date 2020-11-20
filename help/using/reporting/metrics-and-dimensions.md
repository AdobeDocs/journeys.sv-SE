---
product: adobe campaign
solution: Journey Orchestration
title: Mätvärden och mått
description: Läs om mått och mätvärden för Journey Orchestration
translation-type: tm+mt
source-git-commit: 57dc86d775bf8860aa09300cf2432d70c62a2993
workflow-type: tm+mt
source-wordcount: '1035'
ht-degree: 0%

---


# Mätvärden och mått {#concept_rfj_wpt_52b}

>[!NOTE]
>
>Leveransdata fylls bara i om du har Adobe Campaign Standard.

Här finns en lista över alla komponenter som är tillgängliga i dynamiska rapporter samt definitioner av dem.

Tabellen nedan visar en lista över de dimensioner som används i reserapporter och definitioner av dessa.

Mer information om kompatibilitet mellan dimensioner och mätvärden finns på [den här sidan](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Resedimensioner {#MBE_table_wk4_bnj_w2b}

Tabellen nedan visar en lista över de dimensioner som används i reserapporter, definitioner och formler.

| Dimensioner | Definition |
|--- |--- |
| **Åtgärd** | Lista över alla åtgärder (**åtgärdsnamn - åtgärdsetikett**) som används i resor, t.ex. Push - Check out confirmation, Email - Rewards fidelity. |
| **Datakälla** | Förteckning över datakällor (**datakällans namn**) som används för att berika data under en resa, t.ex. Adobe Experience Platform, reservationssystem. |
| **[!UICONTROL Event]** | Lista över alla händelser (**händelsenamn - händelsetikett**) som används i resor, t.ex. Geometrixx-händelse - utcheckning av Geometrixx. |
| **Fältgrupp** | Lista över fältgrupper (**fältgruppsnamn**) som används för att berika data i resor, t.ex. profilfältgrupp, reservationssystem för Geometrixx. |
| **Resa** | Lista över varje resa (**resenamn**) i testläge och i realtid, t.ex. när kunden överger en kundvagn, meddelanden om hotellreservationer. |
| **Reseversion** | Lista över alla publicerade versioner av en resa (**resenamn + versionsnummer**), t.ex. avbruten kundvagn v1, meddelande om hotellreservation v2. |
| **Orchestration** | Lista över alla koordinationsaktiviteter (**villkor, slut, vänta**) som definierats och används i resor. |

## Leveransdimensioner {#delivery-dimensions}

Tabellen nedan visar en lista över de leveransdimensioner som används i reserapporter, definitioner och formler.

| Dimension | Definition |
|--- |--- |
| **Webbläsare** | Webbläsare som meddelandet öppnades eller klickades på. |
| **Leveransnamn** | Etikett och ID för leveransen. |
| **Enhet** | Enhet från vilken e-post/SMS/push-meddelandet öppnades/visades/klickades. |
| **Meddelandetyp** | Kanal som används för leverans, till exempel e-post, SMS, push-meddelanden eller In-App. |
| **Namn på mobilapp** | Mobilprogrammets namn |
| **Plattform** | Plattform för den enhet som meddelandet öppnades/visades/klickades på från. |
| **[!UICONTROL Push platform]** | Plattform för enheten som push-meddelandet öppnades från, till exempel iOS eller Android. |
| **Mottagardomän** | Domän som används för att öppna e-postmeddelandet. |
| **Spårnings-URL** | URL som användaren klickade på i meddelandet. |
| **Kategori för spårnings-URL** | Kategori som tilldelats spårnings-URL:en. |
| **Etikett för spårnings-URL** | En etikett som skickas till URL:en, till exempel spegelsida, kontakta oss eller öppna. |
| **Variant** | Variant av e-postmeddelandet vid A/B-testning. |

## Resemått {#MBE_p_p22_c4j_w2b}

Tabellen nedan visar en lista över mätvärden som används i reserapporter, definitioner och formler.

| Mått | Definition |
|--- |---|
| **Slutförd** | Totalt antal personer som normalt tog slut under resan. |
| **Slutförandegrad** | Totalt antal personer som normalt tog slut under resan jämfört med totalt antal personer som pågick resan. |
| **Aktuell** | Totalt antal personer som för närvarande befinner sig på resan, dvs. hur många personer som har gått in minus personer som har avslutat, fel och tidsgränsen har överskridits. |
| **Aktuell kurs** | Det totala antalet personer som för närvarande befinner sig på resan jämfört med antalet personer som kom in på resan. |
| **Anges** | Totalt antal händelser som inträffat för att starta ett enskilt inträde på resan. |
| **Fel** | Totalt antal fel som uppstod under en resa men som inte hindrade resan från att lyckas. |
| **Fel i åtgärd** | Totalt antal fel som uppstått för åtgärder. |
| **Fel i anrikning** | Totalt antal fel som uppstod för en dataanrikning vid anrop av en datakälla/fältgrupp. |
| **Fel i händelse** | Totalt antal fel som inträffat för händelser. |
| **Felfrekvens** | Totalt antal fel som inträffat under en resa jämfört med totalt antal förekomster under resan. |
| **Utförd åtgärd** | Totalt antal utförda åtgärder för en resa. |
| **Utförd anrikning** | Totalt antal anrikningar som har utförts genom anrop av en datakälla för att hämta specifika fältgrupper. |
| **Händelsen kördes** | Totalt antal utförda åtgärder för en resa. |
| **Utförd Orchestration** | Totalt antal Orchestration-objekt (end, wait, condition) som körts för en resa. |
| **Misslyckades** | Totalt antal resor som inte har slutförts. |
| **Misslyckad frekvens** | Totalt antal resor som inte har genomförts korrekt jämfört med antalet körningar. |

## Leveransstatistik {#delivery-metrics}

Tabellen nedan visar en lista över mätvärden som används i journalrapporter, definitioner och formler.

| Mått | Definition |
|--- |--- |
| **På blockeringslista** | Antal mottagare som har deklarerat ett e-postmeddelande som skräppost eller skräppost. |
| **Blockeringslista ränta** | Totalt antal meddelanden på blockeringslista jämfört med skickade meddelanden. |
| **studsar + fel** | Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden. |
| **Studsa + felfrekvens** | Totalt antal meddelanden som studsade jämfört med skickade meddelanden. |
| **Klicka på** | Antal gånger som ett innehåll klickades i en leverans. |
| **Klicka igenom hastigheten** | Totalt antal klick i en leverans jämfört med antalet levererade meddelanden. |
| **Levererat** | Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden. |
| **Levererad ränta** | Totalt antal meddelanden som har levererats jämfört med skickade meddelanden. |
| **Fel** | Totalt antal fel som uppstod under en resa men som inte hindrade resan från att lyckas. |
| **Hård studs** | Totalt antal permanenta fel, t.ex. fel e-postadress. |
| **Hård studsfrekvens** | Totalt antal leveranser som misslyckades på grund av permanenta fel jämfört med skickade meddelanden. |
| **Spegelsida** | Antal mottagare som klickade på länken för spegelsidan. |
| **Spegelsidhastighet** | Totalt antal klick på spegelsidlänken jämfört med totalt antal levererade meddelanden. |
| **Öppna** | Antal gånger ett meddelande öppnades i en leverans. |
| **Öppen kurs** | Totalt antal öppnade meddelanden jämfört med antalet levererade meddelanden. |
| **Karantän** | Antal meddelanden som studsade och resulterade i karantän för adressen. |
| **Karantänränta** | Totalt antal karantän jämfört med skickade meddelanden. |
| **Avvisad** | Antal meddelanden som klassificerats som skräppost av SMTP-servrar. |
| **Avvisad ränta** | Totalt antal meddelanden som markerats som avvisade jämfört med skickade meddelanden. |
| **Behandlad/skickad** | Totalt antal försändelser för leveransen. |
| **Mjuk studsa** | Totalt antal tillfälliga fel, t.ex. en fullständig inkorg. |
| **Mjuk studsfrekvens** | Totalt antal leveranser som misslyckats på grund av temporära orsaker jämfört med skickade meddelanden. |
| **Unika klick** | Antal mottagare som klickat på ett innehåll i en leverans. |
| **Unika öppningar** | Antal mottagare som öppnade leveransen. |
| **Avbeställ** | Antal klick på länken för att avbryta prenumerationen. |
| **Avbeställningsfrekvens** | Totalt antal prenumerationer per mottagare jämfört med levererade meddelanden. |
