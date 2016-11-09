---
title: Activiteiten | Microsoft Docs
description: In dit onderwerp vindt u een lijst met de activiteiten, filters en overeenkomstparameters die kunnen worden toegepast op activiteitenbeleidsregels.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: f3af2d25-9286-4e9b-b2ad-35653bec72ff
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 401801da8a4439b3dc0cf5c2f150c72e169a6d16


---

# <a name="activities"></a>Activiteiten
Hieronder volgt een lijst met de activiteitfilters die kunnen worden toegepast. De meeste filters bieden ondersteuning voor meerdere waarden en voor NOT (niet), zodat u over een zeer krachtig hulpprogramma beschikt voor het maken van een beleid.  
  
-   Activiteit – zoek alleen naar specifieke activiteiten, bijvoorbeeld alle uploads van bestanden, aanmeldingen vanaf een nieuw apparaat en mislukte aanmeldingen  
  
-   Activiteit-id - Zoek alleen naar specifieke activiteiten op basis van de id. Dit filter is zeer nuttig wanneer u verbinding maakt tussen MCAS en uw SIEM (met behulp van de SIEM-agent) en u de waarschuwingen in de MCAS-portal verder wilt onderzoeken.  
  
-   Beheeractiviteit – zoek alleen naar beheeractiviteiten.  
  
-   Geïmiteerde activiteit – zoek alleen naar activiteiten die zijn uitgevoerd uit naam van een andere gebruiker.  
  
-   App – zoek alleen naar activiteiten binnen specifieke apps.  
  
-   Datum – de datum waarop de activiteit is uitgevoerd. Het filter ondersteunt datums ervoor en erna, evenals een datumbereik.  
  
-   Gebruiker – de gebruiker die de activiteit heeft uitgevoerd. Als u activiteiten zonder specifieke gebruiker wilt filteren, kunt u de operator 'is niet ingesteld' gebruiken.  
  
     ![Activiteitsverwijzing1](./media/activity-ref1.png "activity ref1")  
  
-   IP-adres – het IP-adres waarop de activiteit is uitgevoerd.  
  
-   IP-categorie – de categorie van het IP-adres waarop de activiteit is uitgevoerd, bijvoorbeeld alle activiteiten van een reeks IP-adressen voor beheer. Zie voor meer informatie over IP-categorieën [Organiseer de gegevens naar eigen gelang](general-setup.md#IPtagsandRanges).  
  
-   IP-label - het label van het IP-adres waarop de activiteit is uitgevoerd, bijvoorbeeld alle activiteiten van IP-adressen met een anonieme proxy. Zie voor meer informatie over IP-tags [Organiseer de gegevens naar eigen gelang](general-setup.md#IPtagsandRanges).  
  
-   Locatie – het land van waaruit de activiteit is uitgevoerd.  
  
-   Geregistreerde ISP – de internetprovider van waaruit de activiteit is uitgevoerd.  
  
     ![Activiteitenbeleidsverwijzing2](./media/activity-policy-ref2.png "activity policy ref2")  
  
-   Apparaattype - alleen naar activiteiten zoeken die zijn uitgevoerd met behulp van een specifiek apparaattype, bijvoorbeeld alle activiteiten van mobiele apparaten.  
  
-   Gebruikersagent – de gebruikersagent van waaruit de activiteit is uitgevoerd.  
  
-   Label van de gebruikersagent – ingebouwd label voor de gebruikersagent, bijvoorbeeld alle activiteiten van een verouderde browser of verouderde besturingssystemen.  
  
-   Organisatie van de gebruiker – de organisatie-eenheid van de gebruiker die de activiteit heeft uitgevoerd, bijvoorbeeld alle activiteiten die worden uitgevoerd door Marketing_gebruikers in EMEA.  
  
- Doelobject - hiermee kunt u een specifiek bestand selecteren. 

-   Gebruikersgroep – specifieke gebruikersgroepen die automatisch door MCAS worden geïmporteerd vanuit de cloud-app, bijvoorbeeld alle activiteiten die worden uitgevoerd door Office 365-administrators.  
  
-   Beschrijving – specifieke trefwoorden in de beschrijving van de activiteit, bijvoorbeeld alle activiteiten met de tekenreeks **gebruiker** in de beschrijving.  
  
-   Overeenkomend beleid – zoek naar activiteiten die overeenkomen met een specifiek beleid dat is ingesteld in de portal.  
  
     ![Activiteitenbeleidsverwijzing3](./media/activity-policy-ref3.png "Activity policy ref3")  
  
## <a name="activity-match-parameters"></a>Activiteit overeenkomstig de parameters  
Geef aan hoe vaak een activiteit moet worden herhaald voordat het overeenkomt met het beleid, bijvoorbeeld het instellen van een beleid om te waarschuwen wanneer een gebruiker 10 mislukte aanmeldpogingen uitvoert binnen 2 minuten.  
De standaardinstelling **Activiteit overeenkomstig de parameters** vindt een overeenkomst voor elke activiteit die voldoet aan alle activiteitfilters.   
Met behulp van **Herhaalde activiteit** kunt u het aantal herhaalde activiteiten instellen, alsmede de periode waarin de activiteiten worden geteld. U kunt zelfs opgeven dat alle activiteiten moeten worden uitgevoerd door dezelfde gebruiker en in dezelfde cloud-app.  
  
### <a name="actions"></a>Acties  
Meldingen  
  
-   Waarschuwingen – waarschuwingen kunnen in het systeem worden geactiveerd en worden doorgegeven via e-mail en SMS op basis van de ernst.  
  
-   E-mailmeldingen voor gebruikers – e-mailberichten kunnen worden aangepast en worden verzonden naar alle eigenaren van bestanden die het beleid schenden.  
  
-   CC naar manager – op basis van directory-integratie voor gebruikers kunnen e-mailmeldingen ook worden verzonden naar de manager van de persoon die een beleid schendt.  
  
-   Meldingen verzenden naar aanvullende gebruikers – specifieke lijst met e-mailadressen die deze meldingen ontvangen.  
  
Beheeracties in apps  
  
-   Gedetailleerde acties kunnen per app worden afgedwongen, specifieke acties zijn afhankelijk van de terminologie in de app.  
  
-   Gebruiker blokkeren – de gebruiker blokkeren in de toepassing.  
  
-   Wachtwoord intrekken – het gebruikerswachtwoord intrekken en afdwingen dat de gebruiker een nieuw wachtwoord instelt bij de volgende aanmelding.  
  
     ![Activiteitenbeleidsverwijzing6](./media/activity-policy-ref6.png "activity policy ref6")  
  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


