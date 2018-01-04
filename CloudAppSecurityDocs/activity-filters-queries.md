---
title: Werken met Cloud App Security activiteitfilters en query's | Microsoft Docs
description: Dit onderwerp bevat een lijst met Cloud App Security activiteitfilters en query's en wordt uitgelegd hoe u ermee.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/3/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 9ba5c7d3-c733-4048-9b99-bf41a0f46695
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 72674e6cdc1b2ed96aa14a21090d1fee4296b426
ms.sourcegitcommit: bbf4a2715d1ea3fd21c1a1b87c7f5a2947d2ca68
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/04/2018
---
# <a name="activity-filters-and-queries"></a>Activiteitfilters en query 's

## <a name="activity-filters"></a>Activiteitfilters

Hieronder volgt een lijst met de activiteitfilters die kunnen worden toegepast. De meeste filters bieden ondersteuning voor meerdere waarden en voor NOT (niet), zodat u over een zeer krachtig hulpprogramma beschikt voor het maken van een beleid.  
  
-   Activiteit-id - Zoek alleen naar specifieke activiteiten op basis van de id. Dit filter is zeer nuttig wanneer u verbinding maakt tussen Cloud App Security en uw SIEM (met behulp van de SIEM-agent) en u de waarschuwingen in de Cloud App Security-portal verder wilt onderzoeken.  
  
-   Activiteitobjecten - zoek naar de objecten waarvoor de activiteit werd uitgevoerd. Dit filter wordt toegepast op bestands-, map-, gebruikers- of app-objecten. 
    - Activiteitobject-id - de id van het object (bestands-, map-, gebruikers- of app-id).
    - Bestand, map of site-URL - hiermee kunt u bestanden, mappen en URL's selecteren die beginnen met een bepaalde tekenreeks.
    - Doelobject (bestand/map) - hiermee kunt u een specifiek bestand of specifieke map selecteren. 
    - Item - Hiermee kunt u zoeken op de naam of id van een activiteitsobject (bijvoorbeeld: gebruikersnamen, bestanden, parameters, sites). Voor het filter **Items van activiteitsobjecten** kunt u selecteren of u wilt filteren op items die het specifieke item **bevatten**, die er **gelijk** aan zijn of die ermee **beginnen**.
    
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
    - IP-categorie – de categorie van het IP-adres waarop de activiteit is uitgevoerd, bijvoorbeeld alle activiteiten van een reeks IP-adressen voor beheer. De categorieën moeten worden geconfigureerd om de relevante IP-adressen op te nemen, met uitzondering van de categorie 'Riskant' die vooraf is geconfigureerd en die twee IP-labels bevat: Anonieme proxy en Tor. Zie [De gegevens volgens uw behoeften ordenen](ip-tags.md) voor informatie over het configureren van IP-categorieën.  
    - IP-label - het label van het IP-adres waarop de activiteit is uitgevoerd, bijvoorbeeld alle activiteiten van IP-adressen met een anonieme proxy. Cloud App Security maakt een aantal ingebouwde IP-labels die niet kunnen worden geconfigureerd. Bovendien kunt u uw eigen IP-labels configureren. Zie [De gegevens volgens uw behoeften ordenen](ip-tags.md) voor meer informatie over het configureren van IP-labels.
   De ingebouwde IP-labels zijn onder andere:
    - Microsoft-apps (14 hiervan)
    - Anonieme proxy
    - Botnet (ziet u dat de activiteit is uitgevoerd door een botnet met een koppeling voor meer informatie over de specifieke botnet)
    - Darknet scanning IP (IP voor darknet scannen)
    - C & C-server van malware
    - Remote Connectivity Analyzer
    - Satelliet-providers
    - Slimme proxy en toegangsproxy (met opzet weggelaten)
    - Tor-eindknooppunten
    - Zscaler


-   Geïmiteerde activiteit – zoek alleen naar activiteiten die zijn uitgevoerd uit naam van een andere gebruiker.  

-   Locatie – het land van waaruit de activiteit is uitgevoerd.  

-   Overeenkomend beleid – zoek naar activiteiten die overeenkomen met een specifiek beleid dat is ingesteld in de portal.  

-   Geregistreerde ISP – de internetprovider van waaruit de activiteit is uitgevoerd.   

-  Bron: zoeken op de bron waar de activiteit is gedetecteerd. Dit kan een van de volgende zijn:
  - App-connector: logboeken die rechtstreeks uit de API-connector van de app afkomstig zijn.
  - Analyse van App-connector: verbeteringen van de Cloud App Security-beveiliging op basis van een informatiescan door de API-connector.
  

-   Gebruiker - de gebruiker die de activiteit heeft uitgevoerd, te filteren op domein, groep, naam of organisatie. Als u activiteiten zonder specifieke gebruiker wilt filteren, kunt u de operator 'is niet ingesteld' gebruiken.  
    -   Gebruikersdomein - zoek naar een specifiek gebruikersdomein.
    -   Organisatie van de gebruiker – de organisatie-eenheid van de gebruiker die de activiteit heeft uitgevoerd, bijvoorbeeld alle activiteiten die worden uitgevoerd door Marketing_gebruikers in EMEA.  
    -   Gebruikersgroep – specifieke gebruikersgroepen die u kunt importeren uit verbonden apps, zoals Office 365-beheerders.  
    -   Gebruikersnaam - zoek naar een specifieke gebruikersnaam. Voor een overzicht van gebruikers in een bepaalde gebruikersgroep klikt u in de **Activiteitenlade** op de naam van de gebruikersgroep. Hiermee gaat u naar de pagina Accounts waar een lijst met alle gebruikers in de groep staat. Van daaruit kunt u inzoomen op de details van de accounts van specifieke gebruikers in de groep.
       -  De filters **Gebruikersgroep** en **Gebruikersnaam** kunnen verder worden gefilterd met behulp van de filter **Als** en door de rol van de gebruiker te selecteren. De rol kan een van de volgende mogelijkheden zijn:
            - Alleen activiteitsobject - dit betekent dat de geselecteerde gebruiker of gebruikersgroep niet de betreffende activiteit heeft uitgevoerd, maar object van de activiteit was
            - Alleen uitvoerder - dit betekent dat de gebruiker of gebruikersgroep de activiteit heeft uitgevoerd
            - Alle rollen - dit betekent dat de gebruiker of gebruikersgroep betrokken was bij de activiteit, ofwel als uitvoerder van de activiteit of als het object ervan

-   Gebruikersagent – de gebruikersagent van waaruit de activiteit is uitgevoerd.  
  
-   Label van de gebruikersagent – ingebouwd label voor de gebruikersagent, bijvoorbeeld alle activiteiten van een verouderde browser of verouderde besturingssystemen.  
    
>[!NOTE]
> Als op elk moment dat u wilt wissen van de filters, u doen kunt door te klikken op het pictogram filters wissen ![filters wissen pictogram](./media/clear-filters.png).


## <a name="activity-queries"></a>Activiteit-query 's

Een eenvoudiger onderzoek zelfs kunt u nu aangepaste query's maken en opslaan voor later gebruik. 

1. In de **activiteitenlogboek** pagina, gebruikt u de filters zoals hierboven wordt beschreven om Inzoomen op uw apps indien nodig. 

2. Nadat u de gewenste resultaten hebben bereikt, klikt u op de **opslaan als** knop in de rechterbovenhoek van de filters. 

3. In de **opslaan query** pop-up naam van uw query.

 ![Nieuwe query](./media/new-activity-query.png)

4. Gebruik deze query opnieuw in de toekomst onder **query's**, schuif omlaag naar **opgeslagen query's** en selecteert u uw query. 

 ![query openen](./media/select-activity-query.png)


Cloud App Security kunt u met **voorgestelde query's** en kunt u aangepaste query's die u vaak gebruikt opslaan. Voorgestelde query's bieden u aanbevolen mogelijkheden van onderzoek die uw activiteiten filteren met behulp van de volgende optionele voorgestelde query's:

 - Activiteiten van de beheerder - filtert alle activiteiten om alleen beheerders betrokken activiteiten weer te geven.

 - Download activiteiten - filters alle uw activiteiten om weer te geven alleen de activiteiten die zijn activiteiten, met inbegrip van de gebruikerslijst downloaden als een vile, CSV downloaden van de gedeelde inhoud en het downloaden van een map downloaden.

 - Mislukte aanmelden - filtert alle activiteiten om weer te geven alleen mislukte aanmeldingen en aanmelden via eenmalige aanmelding is mislukt 

 - Bestanden en mappen activiteiten - filters alle activiteiten om weer te geven alleen activiteiten die betrokken bestanden en mappen, met inbegrip van uploaden en downloaden van mappen, toegang tot mappen; maken, verwijderen, uploaden, downloaden, in quarantaine plaatsen en toegang krijgen tot bestanden; en de overdracht van inhoud. 

 - Imitatie activiteiten - filtert alle activiteiten om alleen imitatie activiteiten weer te geven.

 - Postvak activiteiten - alle filters te maken van uw activiteiten wordt alleen Microsoft Exchange Online activiteiten, zoals weergegeven item, berichten van het Postvak opschonen, bericht en verzenden bericht verzenden als machtigingen (ASP.NET-imitatie) bijwerken.

 - Wachtwoord wijzigt en opnieuw instellen van aanvragen - filtert alle activiteiten om alleen activiteiten dat met betrekking tot opnieuw instellen van wachtwoorden, wachtwoord wijzigen en het afdwingen van de gebruiker moet wachtwoord bij volgende aanmelding wijzigen weer te geven.

 - Beveiligingsrisico's - filtert alle activiteiten om alleen de activiteiten die overeenkomen met DLP-beleidsregels weer te geven.

 - Delen van activiteiten - filtert alle activiteiten om alleen activiteiten die betrekking hebben op delen van mappen en bestanden, waaronder het maken van de koppeling van een bedrijf, een anonieme verbinding maken en machtigingen voor lezen/schrijven weer te geven.

 - Geslaagde aanmelding - filtert alle activiteiten om weer te geven alleen de activiteiten die betrekking hebben op geslaagde aanmeldingen, met inbegrip van actie imiteren, geïmiteerde aanmelding logboek voor eenmalige aanmelding en aanmelden vanaf een nieuw apparaat.

![query-activiteiten](./media/queries-activity.png)
 
Bovendien kunt u de voorgestelde query's als uitgangspunt voor een nieuwe query. Selecteer eerst een van de voorgestelde query's. Vervolgens wijzigingen aanbrengen en klik tot slot **opslaan als** Maak een nieuwe **query opgeslagen**.


## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  