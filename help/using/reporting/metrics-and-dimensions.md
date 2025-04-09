---
product: adobe campaign
title: Mätvärden och dimensioner
description: Läs om mått och mätvärden för Journey Orchestration
feature: Journeys
role: User
level: Intermediate
exl-id: f6897011-0a5e-4094-a18e-ba2aa25f902c
source-git-commit: 69471a36b113e04a7bb0953a90977ad4020299e4
workflow-type: tm+mt
source-wordcount: '1080'
ht-degree: 0%

---

# Mätvärden och dimensioner {#concept_rfj_wpt_52b}


>[!CAUTION]
>
>**Söker du Adobe Journey Optimizer**? Klicka [här](https://experienceleague.adobe.com/en/docs/journey-optimizer/using/ajo-home){target="_blank"} för Journey Optimizer-dokumentation.
>
>
>_Den här dokumentationen hänvisar till äldre Journey Orchestration-material som har ersatts av Journey Optimizer. Kontakta ditt kontoteam om du har frågor om din åtkomst till Journey Orchestration eller Journey Optimizer._


>[!NOTE]
>
>Leveransdata fylls bara i om du har Adobe Campaign Standard.

Här finns en lista över alla komponenter som är tillgängliga i dynamiska rapporter samt definitioner av dem.

Tabellen nedan visar en lista över de dimensioner som används i reserapporter och definitioner av dessa.

Mer information om kompatibilitet mellan dimensioner och mått finns på [den här sidan](../assets/do-not-localize/dynamic_report_compatibility_journey.pdf).

## Resedimensioner {#MBE_table_wk4_bnj_w2b}

Tabellen nedan visar en lista över de dimensioner som används i reserapporter, definitioner och formler.

| Dimensioner | Definition |
|--- |--- |
| **Åtgärd** | Lista över alla åtgärder (**åtgärdsnamn - åtgärdsetikett**) som används i resor, t.ex. Push - Checka ut bekräftelse, Email - Rewards-återgivning. |
| **Datakälla** | Lista över datakällor (**datakällans namn**) som används för att förbättra data under en resa, t.ex. Adobe Experience Platform, Reservation System. |
| **[!UICONTROL Event]** | Lista över alla händelser (**händelsenamn - händelseetikett**) som används i resor, t.ex. Geometrixx event - Geometrixx-utcheckning. |
| **Fältgrupp** | Lista över fältgrupper (**fältgruppnamn**) som används för att förbättra data i resor, t.ex. profilfältgrupp, Geometrixx reservationssystem. |
| **Resa** | Lista över varje resa (**resenamn**) i testläge och live, t.ex. kundvagnsöverlämning, Hotel-reservationsmeddelande. |
| **Resversion** | Lista över alla publicerade versioner av en resa (**kundens namn + versionens nummer**), t.ex. kundvagnens överlämnande v1, Hotel-reservationsmeddelande v2. |
| **Orchestration** | Lista över alla koordinationsaktiviteter (**Condition, End, Wait**) som definierats och används i resor. |

## Leveransdimensioner {#delivery-dimensions}

Tabellen nedan visar en lista över de leveransdimensioner som används i reserapporter, definitioner och formler.

| Dimension | Definition |
|--- |--- |
| **Webbläsare** | Webbläsare som meddelandet öppnades eller klickades på. |
| **Leveransnamn** | Etikett och ID för leveransen. |
| **Enhet** | Enhet från vilken e-post/SMS/push-meddelandet öppnades/visades/klickades. |
| **Meddelandetyp** | Kanal som används för leverans, till exempel e-post, SMS, push-meddelanden eller In-App. |
| **Mobilappsnamn** | Mobilprogrammets namn |
| **Plattform** | Plattform för den enhet som meddelandet öppnades/visades/klickades på från. |
| **[!UICONTROL Push platform]** | Plattform för den enhet från vilken push-meddelandet öppnades, till exempel iOS eller Android. |
| **Mottagardomän** | Domän som används för att öppna e-postmeddelandet. |
| **URL för spårning** | URL som användaren klickade på i meddelandet. |
| **Kategorin URL för spårning** | Kategori som tilldelats spårnings-URL:en. |
| **URL-etikett för spårning** | En etikett som skickas till URL:en, till exempel spegelsida, kontakta oss eller öppna. |
| **Variant** | Variant av e-postmeddelandet vid A/B-testning. |

## Resemått {#MBE_p_p22_c4j_w2b}

Tabellen nedan visar en lista över mätvärden som används i reserapporter, definitioner och formler.

| Mått | Definition |
|--- |---|
| **Slutförd** | Totalt antal personer som normalt tog slut under resan. |
| **Slutförandefrekvens** | Totalt antal personer som normalt tog slut under resan jämfört med totalt antal personer som pågick resan. |
| **Aktuell** | Totalt antal personer som för närvarande befinner sig på resan, dvs. hur många personer som har gått in minus personer som har avslutat, fel och tidsgränsen har överskridits. |
| **Aktuell hastighet** | Det totala antalet personer som för närvarande befinner sig på resan jämfört med antalet personer som kom in på resan. |
| **Anges** | Totalt antal händelser som inträffat för att starta ett enskilt inträde på resan. |
| **Fel** | Totalt antal fel som uppstod under en resa men som inte hindrade resan från att lyckas. |
| **Fel i åtgärd** | Totalt antal fel som uppstått för åtgärder. |
| **Fel i anrikning** | Totalt antal fel som uppstod för en dataanrikning vid anrop av en datakälla/fältgrupp. |
| **Fel i händelse** | Totalt antal fel som inträffat för händelser. |
| **Felfrekvens** | Totalt antal fel som inträffat under en resa jämfört med totalt antal förekomster under resan. |
| **Utförd åtgärd** | Totalt antal utförda åtgärder för en resa. |
| **Utförd anrikning** | Totalt antal anrikningar som har utförts genom att anropa en datakälla för att hämta specifika fältgrupper. |
| **Händelsen** har körts | Totalt antal utförda åtgärder för en resa. |
| **Utförd Orchestration** | Totalt antal Orchestration-objekt (end, wait, condition) som körts för en resa. |
| **Misslyckades** | Totalt antal resor som inte har slutförts. |
| **Misslyckad frekvens** | Totalt antal resor som inte har genomförts korrekt jämfört med antalet körningar. |

## Leveransstatistik {#delivery-metrics}

Tabellen nedan visar en lista över mätvärden som används under resan
rapporter, definitioner och formler.

| Mått | Definition |
|--- |--- |
| **På blockeringslista** | Antal mottagare som har deklarerat ett e-postmeddelande som skräppost eller skräppost. |
| **Blockeringslista ränta** | Totalt antal meddelanden på blockeringslista jämfört med skickade meddelanden. |
| **studsar + fel** | Totalt antal fel som sammanställts under leverans och automatisk returbehandling i relation till totalt antal skickade meddelanden. |
| **Studsa + felfrekvens** | Totalt antal meddelanden som studsade jämfört med skickade meddelanden. |
| **Klicka** | Antal gånger som ett innehåll klickades i en leverans. |
| **Klicka genom frekvens** | Totalt antal klick i en leverans jämfört med antalet levererade meddelanden. |
| **Levererat** | Antal meddelanden som har skickats, i relation till det totala antalet skickade meddelanden. |
| **Levererad frekvens** | Totalt antal meddelanden som har levererats jämfört med skickade meddelanden. |
| **Fel** | Totalt antal fel som uppstod under en resa men som inte hindrade resan från att lyckas. |
| **Hårt studs** | Totalt antal permanenta fel, t.ex. fel e-postadress. |
| **Hård studsfrekvens** | Totalt antal leveranser som misslyckades på grund av permanenta fel jämfört med skickade meddelanden. |
| **Spegelsida** | Antal mottagare som klickade på länken för spegelsidan. |
| **Spegelvänd sidhastighet** | Totalt antal klick på spegelsidlänken jämfört med totalt antal levererade meddelanden. |
| **Öppna** | Antal gånger ett meddelande öppnades i en leverans. |
| **Öppen frekvens** | Totalt antal öppnade meddelanden jämfört med antalet levererade meddelanden. |
| **Karantän** | Antal meddelanden som studsade och resulterade i karantän för adressen. |
| **Karantänhastighet** | Totalt antal karantän jämfört med skickade meddelanden. |
| **Avvisad** | Antal meddelanden som klassificerats som skräppost av SMTP-servrar. |
| **Avvisad frekvens** | Totalt antal meddelanden som markerats som avvisade jämfört med skickade meddelanden. |
| **Behandlad/skickad** | Totalt antal försändelser för leveransen. |
| **Mjukt studs** | Totalt antal tillfälliga fel, till exempel en fullständig inkorg. |
| **Mjuk studsfrekvens** | Totalt antal leveranser som misslyckats på grund av temporära orsaker jämfört med skickade meddelanden. |
| **Unika klick** | Antal mottagare som klickat på ett innehåll i en leverans. |
| **Unika öppningar** | Antal mottagare som öppnade leveransen. |
| **Avbeställ** | Antal klick på länken för att avbryta prenumerationen. |
| **Avbeställningsfrekvens** | Totalt antal prenumerationer per mottagare jämfört med levererade meddelanden. |
