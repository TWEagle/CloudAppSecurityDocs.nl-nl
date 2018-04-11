---
title: Beleidsregels voor anomaliedetectie maken in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u een beschrijving van beleidsregels voor anomaliedetectie en naslaginformatie over de bouwstenen van een beleid voor anomaliedetectie.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/5/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: ab9bc377-d2f5-4f4c-a419-f1728a15d1c7
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 61fc81896742213a616f132a6c8e74f6789be434
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="get-instantaneous-behavioral-analytics-and-anomaly-detection"></a>Onmiddellijk gebruikersgedrag analytics en afwijkingsdetectie detectie ophalen

Beleidsregels voor afwijkingsdetectie voor cloud App Security Geef out-of-the-box-gebruiker en entity Behavior analytics (UEBA) en machine learning-(ML) zodat u geavanceerde bedreigingsdetectie onmiddellijk in uw cloudomgeving uitvoeren kunt. Omdat ze worden automatisch ingeschakeld, bieden de nieuwe beleidsregels voor afwijkingsdetectie onmiddellijke resultaten dankzij de onmiddellijke detecties, die gericht is op talrijke gedragsafwijkingen via uw gebruikers en computers en apparaten die zijn verbonden met uw netwerk.  Het nieuwe beleid tonen bovendien meer gegevens uit de Cloud App Security-detectie-engine, kunt u het versnellen onderzoek en doorlopende bedreigingen kunnen bevatten. 

De beleidsregels voor afwijkingsdetectie worden automatisch ingeschakeld, maar de Cloud App Security heeft een initiële learning periode van zeven dagen gedurende welke niet alle afwijkingsdetectie detectiewaarschuwingen worden gegenereerd. Na deze periode wordt elke sessie vergeleken met de activiteiten, de tijd dat gebruikers actief waren, de IP-adressen, de apparaten, enzovoort die de afgelopen maand zijn gedetecteerd en wordt naar de risicoscore van deze activiteiten gekeken.  Deze detecties zijn onderdeel van de afwijkingsdetectie heuristische detectie-engine die profielen van uw omgeving en activeert waarschuwingen met betrekking tot een basislijn die is doorgegeven voor de activiteit van uw organisatie. Deze detecties gebruikmaken van machine learning-algoritmen is ontworpen voor het profiel van de gebruikers en aanmelden met een patroon voor valse positieven te reduceren.

Als u de gebruikersactiviteit scant, worden afwijkingen gedetecteerd. Het risico wordt geëvalueerd door te kijken dan 30 verschillende risico indicatoren, gegroepeerd in meerdere risicofactoren, als volgt: 
          
 -   Riskante IP-adres
 -   Mislukte aanmeldingen
 -   Beheerdersactiviteit
 -   Inactieve accounts
 -   Locatie  
 -   Onmogelijk traject
 -   Apparaat en gebruikersagent
 -   Snelheid van de activiteit

Beveiligingswaarschuwingen worden op basis van de beleidsresultaten geactiveerd. Cloud App Security analyseert elke gebruikerssessie op uw cloud-waarschuwingen u wanneer er iets gebeurt die verschilt van de basislijn van uw organisatie of van de gewone activiteit van de gebruiker. 


U ziet de beleidsregels voor afwijkingsdetectie voor in de portal door te klikken op **besturingselement** en vervolgens **beleid**.

 ![nieuwe beleidsregels voor afwijkingsdetectie](./media/new-anomaly-detection-policies.png)

De volgende beleidsregels voor afwijkingsdetectie zijn beschikbaar:

**Onmogelijke reis**
-  Deze detectie worden twee gebruikersactiviteiten (is één of meerdere sessies) die afkomstig zijn van geografisch verafgelegen locaties binnen een periode korter is dan de tijd die het zou hebben genomen door de gebruiker van de eerste locatie naar de tweede, die aangeeft gaan dat een andere gebruiker dezelfde referenties gebruikt is. Deze detectie maakt gebruik van een machine learning-algoritme dat wordt genegeerd voor de hand liggende 'valse positieven' bijdragen aan de voorwaarde onmogelijke reis zoals VPN-verbindingen en de locaties die regelmatig worden gebruikt door andere gebruikers in de organisatie. De detectie heeft een initiële learning periode van zeven dagen gedurende welke het patroon van een nieuwe gebruiker-activiteit leert.


**Activiteit van incidentele land**
- Deze detectie beschouwt voorbij activiteit locaties om te bepalen van de nieuwe en incidentele locaties. De afwijkingsdetectie detectie-engine bevat informatie over de voorgaande locaties die worden gebruikt door gebruikers in de organisatie. Een waarschuwing wordt geactiveerd wanneer een activiteit plaatsvindt vanaf een locatie die niet onlangs of nooit door de gebruiker of door een gebruiker in de organisatie bezocht is. 


**Activiteit vanaf anonieme IP-adressen**
- Deze detectie identificeert of de gebruikers actief vanaf een IP-adres dat is geïdentificeerd als een anonieme proxy IP-adres zijn. Deze proxy's worden gebruikt door mensen die u wilt verbergen, IP-adres van het apparaat en kan worden gebruikt voor kwade bedoelingen. Deze detectie maakt gebruik van een machine learning-algoritme dat reduceert 'valse positieven', zoals niet-gecodeerde IP-adressen die algemeen worden gebruikt door gebruikers in de organisatie.

**Activiteit van verdachte IP-adressen**
- Deze detectie identificeert of de gebruikers actief vanaf een IP-adres dat door Microsoft dreigingen is geïdentificeerd als riskant zijn. Deze IP-adressen zijn die zijn betrokken bij schadelijke activiteiten, zoals Botnet C & C, en kunnen wijzen op verdacht account. Deze detectie maakt gebruik van een machine learning-algoritme dat reduceert 'valse positieven', zoals niet-gecodeerde IP-adressen die algemeen worden gebruikt door gebruikers in de organisatie.


**Ongebruikelijke activiteiten (door gebruiker)**

Deze detecties identificeren gebruikers die uitvoeren:

 - Ongebruikelijke meerdere bestand downloaden activiteiten
 - Ongebruikelijke file share activiteiten
 - Activiteiten van ongebruikelijke bestand verwijderen
 - Ongebruikelijke geïmiteerde activiteiten
 - Ongebruikelijke administratieve activiteiten
 
Deze beleidsregels zoek naar activiteiten binnen één sessie ten opzichte van de basislijn hebt geleerd, dit erop op een poging tot inbreuk duiden kan. Deze detecties gebruikmaken van een machine learning-algoritme die profielen de gebruikers zich patroon aanmelden en fout-positieven vermindert. Deze detecties zijn onderdeel van de afwijkingsdetectie heuristische detectie-engine die profielen van uw omgeving en activeert waarschuwingen met betrekking tot een basislijn die is doorgegeven voor de activiteit van uw organisatie.

**Meerdere mislukte aanmeldingspogingen**
- Deze detectie identificeert gebruikers die niet meerdere aanmeldingspogingen in één sessie ten opzichte van de basislijn hebt geleerd, dit kan betekenen dat er bij een poging geschonden. 


## <a name="triaging-anomaly-detection-alerts"></a>Afwijkingsdetectie detectiewaarschuwingen gesorteerd

U kunt de diverse waarschuwingen geactiveerd door de nieuwe beleidsregels voor afwijkingsdetectie snel sorteren en bepalen welke u moeten eerst worden afgehandeld. Om dit te doen, moet u de context voor de waarschuwing, zodat u de grotere afbeelding zien en of er iets schadelijke inderdaad begrijpen zijn.  

1. In de **activiteitenlogboek**, kunt u een activiteit om de lade activiteit weer te openen. Klik op **gebruiker** om het tabblad gebruiker inzichten weer te geven. Dit omvat informatie, zoals het aantal waarschuwingen, activiteiten, en wanneer ze verbinding hebt gemaakt uit, wat belangrijk is in een onderzoek is. 

   ![afwijkingsdetectie detectie alert1](./media/anomaly-alert-user1.png)
   ![afwijkingsdetectie detectie alert1](./media/anomaly-alert-user2.png)

 
2. Hiermee kunt u om te begrijpen wat de verdachte activiteiten zijn dat wordt uitgevoerd door de gebruiker en krijgen diepere vertrouwen over de vraag of de account is geknoeid. Bijvoorbeeld, een waarschuwing op meerdere mislukte aanmeldingen inderdaad verdachte worden en kan duiden op mogelijke beveiligingsaanval echter het kan ook worden veroorzaakt door een toepassing onjuiste configuratie, waardoor de waarschuwing onschadelijk echt positief zijn. Als er een waarschuwing voor meerdere mislukte aanmeldingen met extra verdachte activiteiten, klik is er echter een grotere kans dat het account is geknoeid. In het volgende voorbeeld kunt u zien dat de **meerdere mislukte aanmeldingspogingen** waarschuwing werd gevolgd door **activiteit van een TOR IP-adres** en **onmogelijke reis activiteit**, beide sterke indicatoren van inbreuk (IOCs) zelf. Als dit niet genoeg verdachte, dan u zien kunt dat wordt uitgevoerd door dezelfde gebruiker een **massaal downloaden activiteit**, dit is vaak een indicator van de aanvaller uitvoeren exfiltration van gegevens. 

   ![afwijkingsdetectie detectie alert1](./media/anomaly-alert-user3.png)
   ![afwijkingsdetectie detectie alert1](./media/anomaly-alert-user4.png)

 


  

  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  
