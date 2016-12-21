---
title: Activiteiten | Microsoft Docs
description: In dit onderwerp vindt u een lijst met de activiteiten, filters en overeenkomstparameters die kunnen worden toegepast op activiteitenbeleidsregels.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/12/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: f3af2d25-9286-4e9b-b2ad-35653bec72ff
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 156dccf0c77bf7e46c0328ebf6bd1e0ad9609845
ms.openlocfilehash: f1dc1e39309cfe06037a13da55d92935786bed81


---
# <a name="activities"></a>Activiteiten
Voor de beveiliging van gegevens maakt Cloud App Security alle activiteiten van uw verbonden apps voor u zichtbaar. Nadat u Cloud App Security hebt verbonden met een app met behulp van de App-connector, scant Cloud App Security alle activiteiten die hebben plaatsgevonden, waarbij de retroactieve scantijd per app verschilt. Daarna wordt Cloud App Security voortdurend bijgewerkt met nieuwe activiteiten. U kunt beleidsregels maken op basis van de activiteiten en vervolgens aangeven waarvoor u waarschuwingen wilt ontvangen. U kunt ook zoeken naar activiteiten die worden uitgevoerd op bepaalde bestanden. Het type activiteiten en de informatie die we voor elke activiteit ophalen, hangen af van de app en van het soort gegevens dat de app kan leveren. 

U kunt bijvoorbeeld met het logboek **Activiteit** zoeken naar gebruikers in uw organisatie die gebruikmaken van besturingssystemen of browsers die verouderd zijn. Dat doet u als volgt: nadat u Office 365, Google Apps, Box, Dropbox, Okta, Amazon Web Services of Salesforce hebt verbonden met Cloud App Security op de pagina **Activiteitenlogboek**, gebruikt u het geavanceerde filter en selecteert u **Code gebruikersagent**. Selecteer vervolgens **Verouderde browser** of **Verouderd besturingssysteem**. Als u ziet dat er **vertrouwelijke** bestanden zijn die buiten uw organisatie worden gedeeld, kunt u klikken op **Nieuw beleid op basis van zoekopdracht** om een activiteitenbeleid te maken waarmee verouderde browsers en besturingssystemen worden gedetecteerd en gebruikers automatisch een melding ontvangen.

 ![Voorbeeld van activiteit verouderde browser](media/activity-outdated-example.png)

 

U kunt het activiteitenlogboek filteren om te zoeken naar specifieke activiteiten. Met het basisfilter kunt u snel aan de slag met het filteren van uw activiteiten.

 ![basisfilter logboekactiviteit](media/activity-log-filter-basic.png)

Om in te zoomen op meer specifieke activiteiten, kunt u het basisfilter uitbreiden door te klikken op Geavanceerd.

 ![geavanceerd filter logboekactiviteit](media/activity-log-filter-advanced.png)

## <a name="activity-filters"></a>Activiteitfilters
Hieronder volgt een lijst met de activiteitfilters die kunnen worden toegepast. De meeste filters bieden ondersteuning voor meerdere waarden en voor NOT (niet), zodat u over een zeer krachtig hulpprogramma beschikt voor het maken van een beleid.  
  
-   Activiteit-id - Zoek alleen naar specifieke activiteiten op basis van de id. Dit filter is zeer nuttig wanneer u verbinding maakt tussen MCAS en uw SIEM (met behulp van de SIEM-agent) en u de waarschuwingen in de MCAS-portal verder wilt onderzoeken.  
  
-   Activiteitobjecten - zoek naar de objecten waarvoor de activiteit werd uitgevoerd. Dit filter wordt toegepast op bestands-, map-, gebruikers- of app-objecten.
    - Activiteitobject-id - de id van het object (bestands-, map-, gebruikers- of app-id).
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

![activiteitlade](./media/activity-drawer.png "activiteitlade")  
  
Zie [Activiteit overeenkomstig de parameters](governance-actions.md#activity-match-parameters) voor een lijst met beschikbare beheeracties.


## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Dec16_HO2-->


