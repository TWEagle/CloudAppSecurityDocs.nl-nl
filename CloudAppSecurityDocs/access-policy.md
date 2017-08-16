---
title: Toegangsbeleid voor monitor en blokkeren van toegang tot uw cloud-apps maken | Microsoft Docs
description: Dit onderwerp beschrijft de procedure voor het instellen van een toegangsbeleid voor monitor en blokkeren van toegang tot uw cloud-apps.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/8/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: ddeabd1d-f017-4756-94b2-194292e60c07
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b070c4f6364f8beccd397102fa00642560414326
ms.sourcegitcommit: 4cf65f627f2d370ee4a4decae1acbb9658874056
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2017
---
# <a name="access-policies"></a>Beleidsregels voor toegang  
Toegangsbeleid kunnen u voor monitor en blokkeren van toegang tot bepaalde apps op basis van gebruiker, locatie of het apparaat.

Voordat u een toegangsbeleid maken kunt, is het nodig zijn voor [implementeren van de Proxy](proxy-deployment.md). Toegangsbeleid kunnen u regels die bepalen hoe u beheren en bewaken van uw gebruikers toegang tot uw cloud-apps in te stellen.
U kunt bijvoorbeeld een beleid instellen op:
- Blokkeer de toegang tot alle cloud-apps van niet-beheerde apparaten.
- Blokkeer de toegang van specifieke landen, zoals alle landen die geen Engeland.
- Toegang blokkeren voor alle gebruikersgroepen die geen verkoop en Salesforce-beheerders.
- Toegang toestaan, maar alle aanmeldingspogingen en waarschuwing bewaken wanneer iemand probeert aan te melden die is niet van een bepaalde gebruikersgroep.

Volg deze procedure voor het maken van een nieuw beleid voor toegang:  
  
1.  Klik in de console op **Beheer** gevolgd door **Beleidsregels**.  
  
2.  Klik op **beleid maken** en selecteer **toegangsbeleid**.  
  
3.  Geef uw beleid een naam en beschrijving, wat u indien gewenst kunt baseren op een sjabloon. Voor meer informatie over beleidssjablonen, bekijk [Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md).  
  
3. Geef een **ernstniveau van beleid** op voor uw beleid. Als u in Cloud App Security hebt ingesteld dat u meldingen krijgt over beleidsovereenkomsten voor een specifiek ernstniveau van beleid, wordt aan de hand hiervan bepaald of er op basis van de overeenkomsten van dit beleid een melding wordt gedaan.

4.  Binnen **Categorie** koppelt u het beleid aan het meest geschikte type risico. Dit veld is alleen informatief en hiermee kunt u later zoeken naar specifieke beleidsregels en waarschuwingen, op basis van het type risico.  Het risico is mogelijk al vooraf geselecteerd volgens de categorie die u hebt gekozen om het beleid te maken. Standaard-beleidsregels zijn ingesteld op **toegangsbeheer**.  
  
5.  Om in te stellen door welke gedetecteerde apps dit beleid wordt geactiveerd **maakt u een filter voor de bestanden waarop dit beleid wordt toegepast**. 

 > [!NOTE] 
 > Wanneer u de beleidsfilters gebruikt, zoekt **Bevat** alleen naar volledige woorden die zijn gescheiden door komma’s, punten, spaties of onderstrepingstekens. Als u bijvoorbeeld zoekt op **malware** of **virus**, wordt virus_malware_file.exe wel gevonden maar malwarevirusfile.exe niet. Als u zoekt op **malware.exe** vindt u ALLE bestanden met ‘malware’ of ‘exe’ in de bestandsnaam, maar als u zoekt op **”malware.exe”** (met aanhalingstekens) vindt u alleen bestanden die precies “malware.exe” bevatten. **Is gelijk aan** zoekt alleen naar de volledige tekenreeks. Als u bijvoorbeeld zoekt naar **malware.exe** wordt malware.exe wel gevonden maar malware.exe.txt niet.  

6.   Onder **activiteitbron**, selecteer welke apps het beleid van toepassing op alle apps of specifieke apps.

7. De filters gebruiken om te selecteren welke gebruikers, apps en apparaten die u wilt een overeenkomst beleid activeren. Zie voor een volledige lijst met filters [toegang tot de beleidsfilters](#access-policy-filters).

8.  Kies de **acties** gewenste Cloud App Security moet worden uitgevoerd wanneer een overeenkomst wordt gedetecteerd:
    - Toestaan en een waarschuwing: als u toestaat, toegang tot de apps worden bewaakt maar niet geblokkeerd. Standaard als **toestaan** is geselecteerd, worden waarschuwingen automatisch verzonden naar de Cloud App Security-portal. 
    - Blokkeren: Als u selecteert **blok**, wanneer het beleid vereisten wordt voldaan, de gebruiker of het apparaat kan niet worden voor toegang tot de cloud-app. De gebruiker ontvangt een bericht dat geen toegang tot de app hebben.
  
>[!WARNING]
>Het is raadzaam eerst maken van het beleid voor gebruik van de **toestaan** actie, en de resultaten controleren en pas nadat u hebt vastgesteld dat het beleid niet iedereen onbedoeld blokkeert, schakelt u het beleid **blok** toegang.
  
9. Stel de waarschuwingen die u wilt ontvangen wanneer het beleid wordt vergeleken. U kunt een limiet kunt instellen, zodat u geen te veel waarschuwingen ontvangt en u kunt aangeven of de waarschuwingen krijgt als een e-mailbericht of SMS-bericht of beide.

10. Als u wilt weergeven van access policy komt overeen met **besturingselement** en vervolgens **beleid**. Filteren van de resultaten om weer te geven alleen de beleidsregels voor toegang met behulp van de **Type** filter aan de bovenkant. Klik op een beleid voor meer informatie over de overeenkomsten voor elk beleid. Klik op de **geschiedenis** tabblad een historisch overzicht terug naar maximaal zes maanden van beleid overeenkomsten.     
  
## Beleidsverwijzing toegang<a name="access-policy-filters"></a>

Deze sectie bevat een verwijzing naar meer informatie over de beleidsfilters toegang. 

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
    
>[!NOTE]
> Als op elk moment dat u wilt wissen van de filters, u doen kunt door te klikken op het pictogram filters wissen ![filters wissen pictogram](./media/clear-filters.png).


## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  