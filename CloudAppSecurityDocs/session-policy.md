---
title: Sessie beleidsregels maken om te diep meer inzicht verkrijgen in sessie gebruikersactiviteiten en blokkeren downloads | Microsoft Docs
description: Dit onderwerp beschrijft de procedure voor het instellen van een beleid voor Cloud App Security Proxy sessies grondige meer inzicht verkrijgen in sessie gebruikersactiviteiten en het blok downloadt.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/8/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 745df28a-654c-4abf-9c90-203841169f90
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 4b12d52703aa6b81a76e54626f06e5732fb3a6bf
ms.sourcegitcommit: 84f358a5dd0ab7f362dd3a2cf9999a6184fba856
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2017
---
# <a name="session-policies"></a>Sessie-beleid  
Sessie-beleidsregels kunt u voor het bewaken van alles wat die een gebruiker in een sessie heeft en hebt u meer mogelijkheden voor het blokkeren van gebruikers voor specifieke activiteiten controle uitvoeren binnen deze sessies, zoals het downloaden van bestanden.

Voordat u een sessie-beleid maken kunt, is het nodig zijn voor [implementeren van de Proxy](proxy-deployment.md). Sessie-beleid kunnen u regels die bepalen hoe u beheren en bewaken van uw gebruikers, sessies instellen.
U kunt bijvoorbeeld een beleid instellen op:
- Blok downloadt van een bestand met het Azure Information Protection classificatie label 'geclassificeerd' van niet-beheerde apparaten.
- Downloads van alle niet-beheerde apparaten, met Azure RMS-versleuteling-bestanden beveiligen.
- 

Volg deze procedure voor het maken van een nieuwe sessie beleid:  
  
1.  Klik in de console op **Beheer** gevolgd door **Beleidsregels**.  
  
2.  Klik op **beleid maken** en selecteer **sessie beleid**.  
  
3.  Geef uw beleid een naam en beschrijving, wat u indien gewenst kunt baseren op een sjabloon. Voor meer informatie over beleidssjablonen, bekijk [Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md).  
  
3. Geef een **ernstniveau van beleid** op voor uw beleid. Als u in Cloud App Security hebt ingesteld dat u meldingen krijgt over beleidsovereenkomsten voor een specifiek ernstniveau van beleid, wordt aan de hand hiervan bepaald of er op basis van de overeenkomsten van dit beleid een melding wordt gedaan.

4.  Binnen **Categorie** koppelt u het beleid aan het meest geschikte type risico. Dit veld is alleen informatief en hiermee kunt u later zoeken naar specifieke beleidsregels en waarschuwingen, op basis van het type risico.  Het risico is mogelijk al vooraf geselecteerd volgens de categorie die u hebt gekozen om het beleid te maken. Sessie-beleidsregels zijn standaard ingesteld op **DLP**.  
  
5.  Om in te stellen door welke gedetecteerde apps dit beleid wordt geactiveerd **maakt u een filter voor de bestanden waarop dit beleid wordt toegepast**. 

 > [!NOTE] 
 > Wanneer u de beleidsfilters gebruikt, zoekt **Bevat** alleen naar volledige woorden die zijn gescheiden door komma’s, punten, spaties of onderstrepingstekens. Als u bijvoorbeeld zoekt op **malware** of **virus**, wordt virus_malware_file.exe wel gevonden maar malwarevirusfile.exe niet. Als u zoekt op **malware.exe** vindt u ALLE bestanden met ‘malware’ of ‘exe’ in de bestandsnaam, maar als u zoekt op **”malware.exe”** (met aanhalingstekens) vindt u alleen bestanden die precies “malware.exe” bevatten. **Is gelijk aan** zoekt alleen naar de volledige tekenreeks. Als u bijvoorbeeld zoekt naar **malware.exe** wordt malware.exe wel gevonden maar malware.exe.txt niet.  

6. Selecteer de **sessie besturingselementtype**.
    - Alle activiteiten bewaken: als u een Monitor selecteert, de apps sessie activiteiten worden bewaakt maar niet wordt geblokkeerd. U kunt zich elke specifieke interne pagina in de cloud-app die is geopend en elke downloaden gedaan in elke specifieke app bewaken. Waarschuwingen worden standaard automatisch verzonden naar de Cloud App Security-portal. Hiermee kunt u ook [exporteren van het gehele controlelogboek](#export-the-audit-log) voor sessie-activiteiten van het tabblad Proxy.
    - Alle activiteiten bewaken en beheren van het downloaden van bestand: selecteren bewaking en beheer, krijgt u de mogelijkheden die hierboven worden vermeld in **bewaken van alle activiteiten** met de extra beveiligingslaag besturingselement dat u specifieke activiteiten kunt, zoals het downloaden van bestanden in realtime te blokkeren. Ook is mogelijk om te filteren op basis van de Cloud App Security ingebouwde DLP of een externe DLP bestandsinhoud.
 
7. Onder **activiteitbron**, selecteer welke apps het beleid van toepassing op alle apps of specifieke apps.

8. De filters gebruiken om te selecteren welke gebruikers, apps en apparaten die u wilt een overeenkomst beleid activeren. Zie voor een volledige lijst met filters [sessie beleidsfilters](#session-policy-filters).
  
9. Als u wilt **alle activiteiten bewaken en beheren van bestandsoverdracht**, kunt u ook instellen [bestandsfilters](#session-file-filters)

10. Als u wilt **alle activiteiten bewaken en beheren van bestandsoverdracht**, kunt u ook instellen **inhoudscontrole** opties. Met de ingebouwde DLP kunt u bestanden filteren op de inhoud ervan. Selecteren om te scannen bestanden voor inhoud, naast ingebouwde DLP. Zodra inhoudscontrole is ingeschakeld, kunt u vooraf ingestelde expressies gebruiken of zoeken naar andere aangepaste expressies als een subtekenreeks of als een reguliere expressie van uzelf.
Bovendien kunt u een reguliere expressie opgeven als u een bestand wilt uitsluiten van de resultaten. Dit is zeer nuttig als u een standaard voor trefwoorden met de binnenste classificatie hebt die u wilt uitsluiten van het beleid.
U kunt bepalen wat het minimumaantal schendingen van inhoud is dat moet worden bereikt voordat het bestand wordt beschouwd als een schending. U kunt bijvoorbeeld 10 kiezen als u waarschuwingen wilt ontvangen voor bestanden waarin ten minste 10 creditcardnummers worden gevonden.
Wanneer inhoud wordt vergeleken met de geselecteerde expressie, wordt de schendende tekst vervangen door X-tekens. Standaard worden schendingen volledig gemaskeerd en in context weergegeven, waarbij 40 tekens vóór en na de schending worden weergegeven. Getallen in de context van de expressie worden vervangen door #-tekens en worden nooit opgeslagen in Cloud App Security. U kunt de optie Ontmaskert u de laatste 4 tekens van een schending te maskeren, de laatste 4 tekens van de schending zelf.

10. Als u wilt **alle activiteiten bewaken en beheren van bestandsoverdracht**, kunt u ook instellen **acties** moeten worden uitgevoerd wanneer het beleid wordt vergeleken:
    - Toestaan: Als u toestaat, kunnen gebruikers de bestanden te downloaden. 
    - Blokkeren: Als u selecteert **blok**, wanneer de vereisten wordt voldaan, de gebruiker kan niet worden de bestanden te downloaden. De gebruiker ontvangt een bericht dat ze bent niet gemachtigd om de bestanden te downloaden.
    - Beveiligen: Als u selecteert **beveiligen**, de gebruiker is mogelijk om de bestanden te downloaden, maar ze worden versleuteld met Azure RMS. U kunt ook een standaardactie moeten worden uitgevoerd als versleuteling niet instellen (blokkeren of toestaan dat het downloaden).
 >[!WARNING]
 >Het is raadzaam eerst maken van het beleid voor gebruik van de **toestaan** actie, en de resultaten controleren en pas nadat u hebt vastgesteld dat het beleid niet iedereen onbedoeld blokkeert, schakelt u het beleid **blok** downloadt.
 
 9. Stel de waarschuwingen die u wilt ontvangen wanneer het beleid wordt vergeleken. U kunt een limiet kunt instellen, zodat u geen te veel waarschuwingen ontvangt en u kunt aangeven of de waarschuwingen krijgt als een e-mailbericht of SMS-bericht of beide.

10. Als u wilt weergeven van de sessie beleid overeenkomsten **besturingselement** en vervolgens **beleid**. Filteren van de resultaten om weer te geven alleen de sessie beleidsregels met behulp van de **Type** filter aan de bovenkant. Klik op een beleid voor meer informatie over de overeenkomsten voor elk beleid. Klik op de **geschiedenis** tabblad een historisch overzicht terug naar maximaal zes maanden van beleid overeenkomsten.     
  
## <a name="session-policy-reference"></a>Beleidsverwijzing sessie  

Deze sectie bevat een verwijzing naar meer informatie over de beleidsfilters sessie. 

### Sessie-filters<a name="session-policy-filters"></a>

- Apparaat-tag - apparaat tag kunt u filteren beheerde apparaten door het selecteren van **compatibele**, **verbonden met het domein** en **geldig clientcertificaat**.
- Apparaattype: Er is geen waarde, PC, mobiele, Tablet, andere
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

-   Locatie – het land van waaruit de toegang is aangevraagd.    

- Geregistreerde ISP: 

-   Gebruiker - de gebruiker die de activiteit heeft uitgevoerd, te filteren op domein, groep, naam of organisatie. Als u activiteiten zonder specifieke gebruiker wilt filteren, kunt u de operator 'is niet ingesteld' gebruiken.  
    -   Organisatie van de gebruiker – de organisatie-eenheid van de gebruiker die de activiteit heeft uitgevoerd, bijvoorbeeld alle activiteiten die worden uitgevoerd door Marketing_gebruikers in EMEA.  
    -   Gebruikersgroep – specifieke gebruikersgroepen die u kunt importeren uit verbonden apps, zoals Office 365-beheerders.  
    -   Gebruikersnaam - zoek naar een specifieke gebruikersnaam. Voor een overzicht van gebruikers in een bepaalde gebruikersgroep klikt u in de **Activiteitenlade** op de naam van de gebruikersgroep. Hiermee gaat u naar de pagina Accounts waar een lijst met alle gebruikers in de groep staat. Van daaruit kunt u inzoomen op de details van de accounts van specifieke gebruikers in de groep.
       -  De filters **Gebruikersgroep** en **Gebruikersnaam** kunnen verder worden gefilterd met behulp van de filter **Als** en door de rol van de gebruiker te selecteren. De rol kan een van de volgende mogelijkheden zijn:
            - Alleen activiteitsobject - dit betekent dat de geselecteerde gebruiker of gebruikersgroep niet de betreffende activiteit heeft uitgevoerd, maar object van de activiteit was
            - Alleen uitvoerder - dit betekent dat de gebruiker of gebruikersgroep de activiteit heeft uitgevoerd
            - Alle rollen - dit betekent dat de gebruiker of gebruikersgroep betrokken was bij de activiteit, ofwel als uitvoerder van de activiteit of als het object ervan

-   Gebruikersagent – de gebruikersagent van waaruit de activiteit is uitgevoerd.  
  
-   Label van de gebruikersagent – ingebouwd label voor de gebruikersagent, bijvoorbeeld alle activiteiten van een verouderde browser of verouderde besturingssystemen.  

### Bestandsfilters sessie<a name="session-file-filters"></a>

-   Classificatie label - zoeken naar bestanden met specifieke labels ingesteld. Dit zijn beide:
    - Azure Information Protection labels. Hiervoor is integratie met Azure Information Protection vereist.
    - Cloud App Security-tags. biedt nu meer inzicht in de bestanden dat wordt gescand. Voor elk bestand dat wordt gescand met Cloud App Security DLP, kunt u nu weet als de bestanden zijn geblokkeerd worden geïnspecteerd omdat ze zijn versleuteld of beschadigd. Bijvoorbeeld: u kunt beleidsregels instellen om te waarschuwen en quarantaine wachtwoord beveiligde bestanden die worden gedeeld extern, als volgt: 
        - Azure RMS versleuteld – bestanden waarvan de inhoud is niet gecontroleerd omdat ze een Azure RMS-versleuteling-set hebben.
        - Wachtwoord versleuteld – bestanden waarvan de inhoud is niet gecontroleerd omdat ze een wachtwoord beveiligd door de gebruiker zijn.
        - Beschadigd bestand – bestanden waarvan de inhoud is niet gecontroleerd omdat hun inhoud kan niet worden gelezen.

-   Bestandstype – Cloud App Security houdt rekening met het MIME-type dat van de service is ontvangen en scant het bestand om het daadwerkelijke bestandstype te bepalen. Deze scan is van toepassing op bestanden die relevant zijn voor een gegevensscan (documenten, afbeeldingen, presentaties, spreadsheets, tekst- en zipbestanden). Het filter werkt per type bestand/map, bijvoorbeeld Alle mappen die... of Alle spreadsheetbestanden die...
-   Extensie – gericht op specifieke bestandsextensies, bijvoorbeeld alle bestanden die uitvoerbare bestanden zijn (exe).  
  
-   Bestandsnaam – de bestandsnaam of subtekenreeks van de naam zoals deze is gedefinieerd in de cloud-app, bijvoorbeeld Alle bestanden met een wachtwoord in hun naam.   
  
-   De bestandsgrootte – grootte in MB - groter is dan een bepaalde grootte, samller dan een bepaalde grootte of tussen een bereik.    


>[!NOTE]
> Als op elk moment dat u wilt wissen van de filters, u doen kunt door te klikken op het pictogram filters wissen ![filters wissen pictogram](./media/clear-filters.png).

  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  