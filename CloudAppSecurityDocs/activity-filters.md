---
title: Inzicht in activiteiten van cloud-apps | Microsoft-documenten
description: In dit onderwerp vindt u een lijst met de activiteiten, filters en overeenkomstparameters die kunnen worden toegepast op activiteitenbeleidsregels.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/24/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: f3af2d25-9286-4e9b-b2ad-35653bec72ff
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 835ffc05fb84117bf9bbf848d5718de4557e5e15
ms.sourcegitcommit: 8759541301241e03784c5ac87b56986f22bd0561
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2017
---
# <a name="activities"></a>Activiteiten
Cloud App Security maakt alle activiteiten van uw verbonden apps voor u zichtbaar. Nadat u Cloud App Security hebt verbonden met een app met behulp van de App-connector, scant Cloud App Security alle activiteiten die hebben plaatsgevonden, waarbij de retroactieve scantijd per app verschilt. Daarna wordt Cloud App Security voortdurend bijgewerkt met nieuwe activiteiten. 

> [!NOTE] 
> Zie [Zoek in het auditlogboek in het Office 365-beveiligings- en compliancecentrum](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c?ui=en-US&rs=en-US&ad=US#ID0EABAAA=Audited_activities) voor een volledige lijst van door Cloud App Security bewaakte Office 365-activiteiten

U kunt het **activiteitenlogboek** filteren om te zoeken naar specifieke activiteiten. U kunt beleidsregels maken op basis van de activiteiten en vervolgens aangeven waarvoor u waarschuwingen wilt ontvangen en actie wilt ondernemen. U kunt ook zoeken naar activiteiten die worden uitgevoerd op bepaalde bestanden. Het type activiteiten en de informatie die we voor elke activiteit ophalen, hangen af van de app en van het soort gegevens dat de app kan leveren. 

U kunt bijvoorbeeld met het **activiteitenlogboek** zoeken naar gebruikers in uw organisatie die gebruikmaken van besturingssystemen of browsers die verouderd zijn. Dat doet u als volgt: nadat u een app hebt verbonden met Cloud App Security op de pagina **Activiteitenlogboek**, gebruikt u het geavanceerde filter en selecteert u **User agent tag** (Tag gebruikersagent). Selecteer vervolgens **Verouderde browser** of **Verouderd besturingssysteem**.

 ![Voorbeeld van activiteit verouderde browser](media/activity-example-outdated.png)

Als u wilt controleren of er buiten uw organisatie toegang wordt verkregen tot **vertrouwelijke** bestanden, stelt u het filter **Activiteitobject** in om te zoeken op **Classificatielabel** en selecteert u het label **Vertrouwelijk**. Stel het filter **IP-adres** zo in dat wordt gezocht naar **Categorie** en sluit de IP-adressen van uw kantoor uit (IP-categorieën kunnen worden geconfigureerd in het menu **Instellingen**). U kunt klikken op **Nieuw beleid op basis van zoekbewerking** om een activiteitsbeleid te maken op basis van de filters die u hebt gedefinieerd, en automatisch de gebruikers op de hoogte te brengen.

 ![Voorbeeld van vertrouwelijke bestanden activiteit extern](media/activity-example-ip.png)

 
Met het basisfilter kunt u snel aan de slag met het filteren van uw activiteiten.

 ![basisfilter logboekactiviteit](media/activity-log-filter-basic.png)

Om in te zoomen op meer specifieke activiteiten, kunt u het basisfilter uitbreiden door te klikken op Geavanceerd.

 ![geavanceerd filter logboekactiviteit](media/activity-log-filter-advanced.png)

## <a name="activity-filters"></a>Activiteitfilters
Hier volgt een lijst van activiteitfilters die kunnen worden toegepast. De meeste filters bieden ondersteuning voor meerdere waarden en niet, zodat u over een krachtig hulpprogramma voor het maken van beleid.  
  
-   Activiteit-id - Zoek alleen naar specifieke activiteiten op basis van de id. Dit filter is handig als u Cloud App Security verbinding met uw SIEM (met behulp van de SIEM-agent) en u verder wilt onderzoeken waarschuwingen in de Cloud App Security-portal.  
  
-   Activiteitobjecten - zoek naar de objecten waarvoor de activiteit werd uitgevoerd. Dit filter wordt toegepast op bestand, map, gebruiker of app-objecten. 
    - Activiteitobject-id - de id van het object (bestands-, map-, gebruikers- of app-id).
    - Bestand, map of URL van de site - kunt u bestanden, mappen en URL's die beginnen met een specifieke tekenreeks.
    - Doelobject (bestand/map) - hiermee kunt u een specifiek bestand of specifieke map selecteren. 
    - Item - Hiermee kunt u zoeken op de naam of id van een activiteitsobject (bijvoorbeeld: gebruikersnamen, bestanden, parameters, sites). Voor de **activiteitsobject Item** filter, kunt u selecteren of u wilt filteren op items die **bevatten**, **gelijk**, of **begint met** het item.
    
-   Activiteitstype - zoek naar de app-activiteit.

-   Beheeractiviteit – zoek alleen naar beheeractiviteiten.  
  
-   Waarschuwings-id - zoek naar waarschuwings-id.

-   App – zoek alleen naar activiteiten binnen specifieke apps.  
  
-   Toegepaste actie - zoek naar toegepaste beheeractie: Geblokkeerd, Proxy overslaan, Ontsleuteld, Versleuteld, Versleutelen is mislukt, Geen actie.

-   Datum – de datum waarop de activiteit is uitgevoerd. Het filter ondersteunt datums ervoor en erna, evenals een datumbereik.  
  
-   Beschrijving – specifieke trefwoorden in de beschrijving van de activiteit, bijvoorbeeld alle activiteiten met de tekenreeks **gebruiker** in de beschrijving.  
  
-   Apparaatlabel - zoek naar compatibele, beheerde of geverifieerde apparaten.

-   Apparaattype - zoek alleen naar activiteiten die zijn uitgevoerd met behulp van een specifiek apparaattype, bijvoorbeeld alle activiteiten van mobiele apparaten, pc's of tablets.  
  
-   IP-adres – de onbewerkte IP-adres, categorie of code van waaruit de activiteit is uitgevoerd.  
    - Onbewerkt IP-adres - hiermee kunt u zoeken naar activiteiten die zijn uitgevoerd op of door onbewerkte IP-adressen die gelijk zijn aan, niet gelijk zijn aan, beginnen met of niet beginnen met een bepaalde reeks, of onbewerkte IP-adressen die wel of niet zijn ingesteld. 
    - IP-categorie – de categorie van het IP-adres waarop de activiteit is uitgevoerd, bijvoorbeeld alle activiteiten van een reeks IP-adressen voor beheer. De categorieën moeten zodanig worden geconfigureerd dat deze de relevante IP-adressen, met uitzondering van de categorie "Riskant" die vooraf is geconfigureerd en bevat twee IP-tags - anonieme proxy en Tor. Zie [De gegevens volgens uw behoeften ordenen](ip-tags.md) voor informatie over het configureren van IP-categorieën.  
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

-  Bron: zoeken op de bron waar de activiteit is gedetecteerd. Kan bestaan uit een van de volgende bronnen:
  - App-connector: logboeken die rechtstreeks uit de API-connector van de app afkomstig zijn.
  - Analyse van App-connector: verbeteringen van de Cloud App Security-beveiliging op basis van een informatiescan door de API-connector.
  

-   Gebruiker – de gebruiker die de activiteit kan worden gefilterd in het domein, groep, naam of organisatie heeft uitgevoerd. Als u activiteiten zonder specifieke gebruiker wilt filteren, kunt u de operator 'is niet ingesteld' gebruiken.  
    -   Gebruikersdomein - zoek naar een specifiek gebruikersdomein.
    -   Organisatie van de gebruiker – de organisatie-eenheid van de gebruiker die de activiteit heeft uitgevoerd, bijvoorbeeld alle activiteiten die worden uitgevoerd door Marketing_gebruikers in EMEA.  
    -   Gebruikersgroep – specifieke gebruikersgroepen die u kunt importeren uit verbonden apps, zoals Office 365-beheerders.  
    -   Gebruikersnaam - zoek naar een specifieke gebruikersnaam. Voor een overzicht van gebruikers in een bepaalde gebruikersgroep klikt u in de **Activiteitenlade** op de naam van de gebruikersgroep. Hiermee gaat u naar de pagina voor Accounts met een lijst met alle gebruikers in de groep. Van daaruit, kunt u inzoomen op de details van de accounts van specifieke gebruikers in de groep.
       -  De filters **Gebruikersgroep** en **Gebruikersnaam** kunnen verder worden gefilterd met behulp van de filter **Als** en door de rol van de gebruiker te selecteren. De rol kan een van de volgende mogelijkheden zijn:
            - Alleen activiteitsobject - dit betekent dat de geselecteerde gebruiker of gebruikersgroep niet de betreffende activiteit heeft uitgevoerd, maar object van de activiteit was
            - Alleen uitvoerder - dit betekent dat de gebruiker of gebruikersgroep de activiteit heeft uitgevoerd
            - Alle rollen - dit betekent dat de gebruiker of gebruikersgroep betrokken was bij de activiteit, ofwel als uitvoerder van de activiteit of als het object ervan

-   Gebruikersagent – de gebruikersagent van waaruit de activiteit is uitgevoerd.  
  
-   Label van de gebruikersagent – ingebouwd label voor de gebruikersagent, bijvoorbeeld alle activiteiten van een verouderde browser of verouderde besturingssystemen.  
    
>[!NOTE]
> Als op elk moment dat u wilt wissen van de filters, u doen kunt door te klikken op het pictogram filters wissen ![filters wissen pictogram](./media/clear-filters.png).

## <a name="the-activity-drawer"></a>De activiteit lade

### <a name="working-with-the-activity-drawer"></a>De activiteitslade gebruiken

U kunt meer informatie bekijken over elke activiteit door te klikken op de activiteit in het activiteitenlogboek. Hiermee opent u de sectie van de activiteit met de volgende aanvullende acties en inzichten voor elke activiteit:
    - Overeenkomend beleid: klik op de koppeling Overeenkomend beleid om een lijst met beleidsregels te zien waarmee deze activiteit overeenkomt.
    - Onbewerkte gegevens weergeven: klik op Onbewerkte gegevens weergeven om te zien welke gegevens daadwerkelijk van de app zijn ontvangen.
    - Gebruiker: klik op de gebruiker om de gebruikerspagina weer te geven van de gebruiker die de activiteit heeft uitgevoerd. 
    - Apparaattype: klik op het apparaattype om de onbewerkte gegevens van de gebruikersagent weer te geven. 
    - Locatie: klik op de locatie om die te openen in Bing Kaarten.
    - Categorie en labels IP-adres: klik op het IP-label om de lijst met IP-labels die zijn gevonden in deze activiteit weer te geven. U kunt vervolgens filteren op alle activiteiten die overeenkomen met dit label.    

 De velden in de Activiteitenlade bieden contextuele koppelingen naar aanvullende activiteiten en meer details die u rechtstreeks vanuit de lade kunt uitvoeren. Als u bijvoorbeeld de cursor naast de categorie IP-adres verplaatst, kunt u het pictogram ![Toevoegen aan filter](./media/add-to-filter-icon.png) gebruiken om het IP-adres rechtstreeks toe te voegen aan het filter van de huidige pagina. U kunt ook het tandwielpictogram ![Instellingen](./media/contextual-settings-icon.png) dat wordt weergegeven gebruiken om rechtstreeks naar de instellingenpagina te gaan die nodig is om de configuratie van een van de velden, zoals **Gebruikersgroepen**, aan te passen.


![activiteitlade](./media/activity-drawer.png "activiteitlade")  
  
Zie [Governance-acties voor activiteiten](governance-actions.md#activity-governance-actions) voor een lijst met beschikbare governance-acties.

#### <a name="user-insights"></a>Gebruiker insights

De ervaring onderzoek bevat out-of-the-box inzicht in de uitvoerende gebruiker. Met een enkele klik, als u krijgt een uitgebreid overzicht van de gebruiker die met inbegrip van welke locatie ze verbonden uit hoeveel openstaande waarschuwingen zijn ze zijn betrokken bij en informatie over de metagegevens.

Gebruiker insights weergeven:

1. Klik op de activiteit zelf in de **activiteitenlogboek**.

2. Klik vervolgens op de **gebruiker** tabblad. <br></br> Hiermee opent u de activiteit lade **gebruiker** tabblad bevat de volgende inzichten over de gebruiker:
    - **Waarschuwingen openen**: het aantal openstaande waarschuwingen die de gebruiker betrokken.
    - **Schending van het bestand**: het aantal schendingen van het bestand voor bestanden die eigendom zijn van de gebruiker.
    - **Activiteiten**: het aantal activiteiten uitgevoerd door de gebruiker in de afgelopen 30 dagen.
    - **Landen**: het aantal landen die de gebruiker uit in de afgelopen 30 dagen verbonden.
    - **ISP's**: het aantal ISP's die de gebruiker van afgelopen 30 dagen verbonden.
    - **IP-adressen**: het aantal IP-adressen van de gebruiker verbonden uit in de afgelopen 30 dagen.

![gebruiker inzicht in de Cloud App Security](./media/user-insights.png)

#### <a name="ip-address-insights"></a>IP-adres insights

Omdat het IP-adresgegevens is van cruciaal belang voor bijna alle onderzoek, kunt u gedetailleerde informatie over IP-adressen weergeven in de sectie van de activiteit. Uit binnen een bepaalde activiteit, kunt u op het tabblad IP-adres om samengevoegde gegevens over de IP-adres zoals het aantal openstaande waarschuwingen voor het specifieke IP-adres, een grafiek trend van recente activiteiten en een locatiekaart weer te geven. Hierdoor kunnen eenvoudig Inzoomen op, bijvoorbeeld wanneer onderzoeken onmogelijke reis waarschuwingen, gemakkelijk kunt begrijpen waar het IP-adres is gebruikt en als deze is betrokken bij verdachte activiteiten of niet. U kunt ook acties uitvoeren rechtstreeks in de sectie van de IP-adres waarmee u kunt de code van een IP-adres als riskant, VPN, of in een bedrijfsnetwerk te vereenvoudigen toekomstig onderzoek en -beleid maken.

IP-adres insights weergeven:

1. Klik op de activiteit zelf in de **activiteitenlogboek**.

2. Klik vervolgens op de **IP-adres** tabblad. <br></br> Hiermee opent u de activiteit lade **IP-adres** tabblad bevat de volgende inzichten over de IP-adres:
    - **Waarschuwingen openen**: het aantal openstaande waarschuwingen die het IP-adres betrokken.
    - **Activiteiten**: het aantal activiteiten uitgevoerd door het IP-adres in de afgelopen 30 dagen.
    - **Locatie van de IP-**: de geografische locaties van waaruit het IP-adres die zijn verbonden uit in de afgelopen 30 dagen.
    - **Activiteiten**: het aantal activiteiten van dit IP-adres in de afgelopen 30 dagen uitgevoerd.
    - **Activiteiten van de beheerder**: het aantal administratieve activiteiten van dit IP-adres in de afgelopen 30 dagen uitgevoerd.
    - U kunt de volgende IP-adres acties uitvoeren:
        - Als riskant tag 
        - Label als VPN-IP-adres
        - Riskante IP-tag en toevoegen aan geblokkeerde groep

![IP-adres inzicht in de Cloud App Security](./media/ip-address-insights.png)


## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  