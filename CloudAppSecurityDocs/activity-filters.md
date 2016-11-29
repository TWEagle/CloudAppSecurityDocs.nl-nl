---
title: Activiteiten | Microsoft Docs
description: In dit onderwerp vindt u een lijst met de activiteiten, filters en overeenkomstparameters die kunnen worden toegepast op activiteitenbeleidsregels.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/26/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: f3af2d25-9286-4e9b-b2ad-35653bec72ff
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a0b71a03c932ea529000d7545faf8849d99fcb6d
ms.openlocfilehash: 342d9fcc84f9fb4b250578b653578403a06605f1


---
# <a name="activities"></a>Activiteiten
U kunt het activiteitenlogboek filteren om te zoeken naar specifieke activiteiten. Met het basisfilter kunt u snel aan de slag met het filteren van uw activiteiten.

 ![basisfilter logboekactiviteit](media/activity-log-filter-basic.png)

Om in te zoomen op meer specifieke activiteiten, kunt u het basisfilter uitbreiden door te klikken op Geavanceerd.

 ![geavanceerd filter logboekactiviteit](media/activity-log-filter-advanced.png)

## <a name="activity-filters"></a>Activiteitfilters
Hieronder volgt een lijst met de activiteitfilters die kunnen worden toegepast. De meeste filters bieden ondersteuning voor meerdere waarden en voor NOT (niet), zodat u over een zeer krachtig hulpprogramma beschikt voor het maken van een beleid.  
  
-   Activiteit-id - Zoek alleen naar specifieke activiteiten op basis van de id. Dit filter is zeer nuttig wanneer u verbinding maakt tussen MCAS en uw SIEM (met behulp van de SIEM-agent) en u de waarschuwingen in de MCAS-portal verder wilt onderzoeken.  
  
-   Activiteitobjecten - zoek naar bestanden, mappen of site-URL's, of doelobjecten (bestand/map).
    - Bestand, map of site-URL - hiermee kunt u bestanden, mappen en URL's selecteren die beginnen met een bepaalde tekenreeks.
    - Doelobject (bestand/map) - hiermee kunt u een specifiek bestand of specifieke map selecteren. 
    
-   Activiteitstype - zoek naar de app-activiteit.

-   Beheeractiviteit – zoek alleen naar beheeractiviteiten.  
  
-   Waarschuwings-id - zoek naar waarschuwings-id.

-   App – zoek alleen naar activiteiten binnen specifieke apps.  
  
-   Toegepaste actie - zoek naar toegepaste beheeractie: Geblokkeerd, Proxy overslaan, Ontsleuteld, Versleuteld, Versleutelen is mislukt, Geen actie.

-   Datum – de datum waarop de activiteit is uitgevoerd. Het filter ondersteunt datums ervoor en erna, evenals een datumbereik.  
  
-   Beschrijving – specifieke trefwoorden in de beschrijving van de activiteit, bijvoorbeeld alle activiteiten met de tekenreeks **gebruiker** in de beschrijving.  
  
-   Apparaatlabel - zoek naar compatibele, beheerde of geverifieerde apparaten.

-   Apparaattype - zoek alleen naar activiteiten die zijn uitgevoerd met behulp van een specifiek apparaattype, bijvoorbeeld alle activiteiten van mobiele apparaten, pc's of tablets.  
  
-   IP-adres – het onbewerkte IP-adres, de IP-categorie of het IP-label waarop de activiteit is uitgevoerd.  
    - Onbewerkt IP-adres - hiermee kunt u zoeken naar activiteiten die zijn uitgevoerd op of door onbewerkte IP-adressen die gelijk zijn aan, niet gelijk zijn aan, beginnen met of niet beginnen met een bepaalde reeks, of onbewerkte IP-adressen die wel of niet zijn ingesteld. 
    - IP-categorie – de categorie van het IP-adres waarop de activiteit is uitgevoerd, bijvoorbeeld alle activiteiten van een reeks IP-adressen voor beheer. Zie voor meer informatie over IP-categorieën [Organiseer de gegevens naar eigen gelang](general-setup.md#IPtagsandRanges).  
    - IP-label - het label van het IP-adres waarop de activiteit is uitgevoerd, bijvoorbeeld alle activiteiten van IP-adressen met een anonieme proxy. Zie voor meer informatie over IP-tags [Organiseer de gegevens naar eigen gelang](general-setup.md#IPtagsandRanges).
  
-   Geïmiteerde activiteit – zoek alleen naar activiteiten die zijn uitgevoerd uit naam van een andere gebruiker.  

-   Locatie – het land van waaruit de activiteit is uitgevoerd.  

-   Overeenkomend beleid – zoek naar activiteiten die overeenkomen met een specifiek beleid dat is ingesteld in de portal.  

-   Geregistreerde ISP – de internetprovider van waaruit de activiteit is uitgevoerd.   

-  Bron: zoeken op de bron waar de activiteit is gedetecteerd. Dit kan een van de volgende zijn:
  - App-connector: logboeken die rechtstreeks uit de API-connector van de app afkomstig zijn.
  - Analyse van App-connector: verbeteringen van de Cloud App Security-beveiliging op basis van een informatiescan door de API-connector.
  

-   Gebruiker - de gebruiker die de activiteit heeft uitgevoerd, te filteren op domein, groep, naam of organisatie. Als u activiteiten zonder specifieke gebruiker wilt filteren, kunt u de operator 'is niet ingesteld' gebruiken.  
    -   Gebruikersdomein - zoek naar een specifiek gebruikersdomein.
    -   Gebruikersgroep – specifieke gebruikersgroepen die automatisch door Cloud App Security worden geïmporteerd vanuit de cloud-app, bijvoorbeeld alle activiteiten die worden uitgevoerd door Office 365-beheerders.
    -   Gebruikersnaam - zoek naar een specifieke gebruikersnaam.
    -   Organisatie van de gebruiker – de organisatie-eenheid van de gebruiker die de activiteit heeft uitgevoerd, bijvoorbeeld alle activiteiten die worden uitgevoerd door Marketing_gebruikers in EMEA.  

-   Gebruikersagent – de gebruikersagent van waaruit de activiteit is uitgevoerd.  
  
-   Label van de gebruikersagent – ingebouwd label voor de gebruikersagent, bijvoorbeeld alle activiteiten van een verouderde browser of verouderde besturingssystemen.  
    
  
## <a name="working-with-the-activity-drawer"></a>De activiteitslade gebruiken

U kunt meer informatie bekijken over elke activiteit door te klikken op de activiteit in het Activiteitenlogboek. Daarmee opent u de activiteitslade, die de volgende acties bevat die u met het bestand kunt uitvoeren:

- Overeenkomend beleid: klik op de koppeling Overeenkomend beleid om een lijst met beleidsregels te zien waarmee deze activiteit overeenkomt.
- Onbewerkte gegevens weergeven: klik op Onbewerkte gegevens weergeven om te zien welke gegevens daadwerkelijk van de app zijn ontvangen.
- Gebruiker: klik op de gebruiker om de gebruikerspagina weer te geven van de gebruiker die de activiteit heeft uitgevoerd. 
- Apparaattype: klik op het apparaattype om de onbewerkte gegevens van de gebruikersagent weer te geven. 
- Locatie: klik op de locatie om die te openen in Bing Kaarten.
- Categorie en labels IP-adres: klik op het IP-label om de lijst met IP-labels die zijn gevonden in deze activiteit weer te geven. U kunt vervolgens filteren op alle activiteiten die overeenkomen met dit label.    

![activiteitslade](./media/activity-drawer.png "activity drawer")  
  


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
  
  


<!--HONumber=Nov16_HO4-->


