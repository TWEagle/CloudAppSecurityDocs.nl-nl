---
title: Bestanden | Microsoft Docs
description: Dit naslagonderwerp bevat informatie over de bestandstypen en bestandsfilters die worden gebruikt in Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/27/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cadcd6db-05b2-4974-91fe-cfac3d57aecd
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: bf862116fb4db1d4a50c25497d72634a97bb3a80
ms.openlocfilehash: 8fca376e5d414192bdb7c99a7741c97ebcaf3892


---

# <a name="files"></a>Bestanden

U kunt het bestandslogboek filteren om te zoeken naar specifieke bestanden. Met het basisfilter kunt u snel aan de slag met het filteren van uw activiteiten.

 ![basisfilter bestandslogboek](media/file-log-filter-basic.png)

Om in te zoomen op meer specifieke bestanden, kunt u het basisfilter uitbreiden door te klikken op Geavanceerd.

 ![geavanceerd filter bestandslogboek](media/file-log-filter-advanced.png)
 
###  <a name="a-namefilefiltersa-file-filters"></a><a name="Filefilters"></a> Bestandsfilters 
 
Met Cloud App Security kunt u elk bestandstype controleren op basis van meer dan twintig metagegevensfilters (bijvoorbeeld toegangsniveau, bestandstype). 
 
Met de ingebouwde DLP-engines van Cloud App Security worden inhoudsinspecties uitgevoerd door tekst te extraheren uit algemene bestandstypen (PDF-, Office-, RTF-, HTML-, codebestanden, enzovoort).

Hieronder volgt een lijst met de bestandsfilters die kunnen worden toegepast. De meeste filters bieden ondersteuning voor meerdere waarden en voor NOT (niet), zodat u over een zeer krachtig hulpprogramma beschikt voor het maken van een beleid.  
> [!NOTE] 
> Wanneer u de beleidsfilters voor bestanden gebruikt, zoekt **Bevat** alleen naar volledige woorden die zijn gescheiden door komma’s, punten, spaties of onderstrepingstekens. Als u woorden tussen aanhalingstekens zet, krijgt u hetzelfde resultaat als wanneer u AND zou gebruiken; als u bijvoorbeeld zoekt op **"malware”****”virus”**, wordt het bestand virus_malware_file.exe gevonden, maar niet malwarevirusfile.exe of malware.exe. Spaties tussen woorden hebben hetzelfde resultaat als het gebruik van OR; als u bijvoorbeeld zoekt op **malware** **virus**, worden alle bestanden gevonden met malware of virus in de naam, dus zowel malware-virus.exe als virus.exe.   **Is gelijk aan** zoekt alleen naar de volledige tekenreeks. Als u bijvoorbeeld zoekt naar **malware.exe** wordt malware.exe wel gevonden maar malware.exe.txt niet. 

-   Toegangsniveau – toegangsniveau delen; openbaar, extern, intern of privé.  Zie [General Setup, Set up the portal](getting-started-with-cloud-app-security.md) ('De portal instellen' in het artikel 'Algemene instellingen') voor meer informatie over externe bestanden. Interne bestanden zijn de bestanden in de interne domeinen die u instelt in [Algemene instellingen](General-setup.md). Externe bestanden zijn de bestanden die zijn opgeslagen op locaties die zich niet binnen de ingestelde interne domeinen bevinden. Gedeelde bestanden zijn bestanden met een hoger niveau voor delen dan Privé, inclusief intern gedeelde bestanden (bestanden die binnen uw interne domeinen worden gedeeld), extern gedeelde bestanden (bestanden die worden gedeeld in domeinen die niet in uw interne domeinen worden weergegeven), openbare bestanden met een koppeling (bestanden die met anderen kunnen worden gedeeld via een koppeling) en openbare bestanden (bestanden die kunnen worden gevonden door te zoeken op internet). 

> [!NOTE]
>  Bestanden die door externe gebruikers zijn gedeeld in uw gekoppelde opslag-apps worden als volgt verwerkt door Cloud App Security:
> - **OneDrive:** OneDrive wijst een interne gebruiker toe als eigenaar van ieder bestand dat door een externe gebruiker in uw OneDrive wordt geplaatst. Omdat de bestanden vervolgens worden gezien als eigendom van uw organisatie, worden deze bestanden gescand met Cloud App Security en worden beleidsregels op deze bestanden toegepast, zoals voor alle bestanden in OneDrive gebeurt.
> - **Google Drive:** in Google Drive worden deze bestanden gezien als eigendom van de externe gebruiker en vanwege de juridische beperkingen voor bestanden en gegevens die geen eigendom van uw organisatie zijn, heeft Cloud App Security geen toegang tot deze bestanden.
> - **Box:** Omdat bestanden die eigendom zijn van een externe gebruiker in Box worden gezien als privégegevens, kunnen globale beheerders van Box de inhoud van deze bestanden niet bekijken. Om deze reden heeft Cloud App Security geen toegang tot deze bestanden. 
> - **Dropbox:** Omdat bestanden die eigendom zijn van een externe gebruiker in Dropbox worden gezien als privégegevens, kunnen globale beheerders van Box de inhoud van deze bestanden niet bekijken. Om deze reden heeft Cloud App Security geen toegang tot deze bestanden.

-   App – alleen bestanden binnen deze apps zoeken.  
  
-   Samenwerkers – specifieke groepen met samenwerkers opnemen/uitsluiten.  
  
    -   Elke uit domein – als elke willekeurige gebruiker uit dit domein toegang tot het bestand heeft.  
  
    -   Gehele domein – als het gehele domein toegang tot het bestand heeft.  
  
    -   Groepen – als een specifieke groep toegang tot het bestand heeft. Groepen kunnen worden geïmporteerd vanuit Active Directory of cloud-apps. Ook kunnen ze handmatig worden gemaakt in de service.  
  
    -   Gebruikers – een bepaalde reeks gebruikers die mogelijk toegang tot het bestand hebben.  
  
-   Gemaakt – de tijd waarop het bestand is gemaakt. Het filter ondersteunt datums ervoor en erna, evenals een datumbereik.  
  
-   Extensie – gericht op specifieke bestandsextensies, bijvoorbeeld alle bestanden die uitvoerbare bestanden zijn (exe).  
  
-   Bestands-id – zoeken naar specifieke bestands-id's. Dit is een geavanceerde functie waarmee u bepaalde bestanden met een hoge waarde kunt bijhouden zonder afhankelijk te zijn van de eigenaar/locatie/naam.  
  
-   Bestandsnaam – de bestandsnaam of subtekenreeks van de naam zoals deze is gedefinieerd in de cloud-app, bijvoorbeeld Alle bestanden met een wachtwoord in hun naam.   
  
-   Bestandslabel - zoek naar bestanden met specifieke labels die zijn ingesteld door Azure Information Protection. Hiervoor is integratie met Azure Information Protection vereist.

-   Bestandstype – Cloud App Security houdt rekening met het MIME-type dat van de service is ontvangen en scant het bestand om het daadwerkelijke bestandstype te bepalen. Deze scan is van toepassing op bestanden die relevant zijn voor een gegevensscan (documenten, afbeeldingen, presentaties, spreadsheets, tekst- en zipbestanden). Het filter werkt per type bestand/map, bijvoorbeeld Alle mappen die... of Alle spreadsheetbestanden die...


 ![Prullenbak beleidsbestandsfilters](./media/policy_file-filters-trash.png "policy_file filters trash")  

  
-   In de Prullenbak – uitsluiten/opnemen van bestanden in de map Prullenbak. Deze bestanden kunnen nog steeds zijn gedeeld en vormen mogelijk een risico.  
  
-   Laatst gewijzigd – de tijd waarop het bestand is gewijzigd. Het filter ondersteunt datums ervoor en erna, een datumbereik en relatieve tijdsexpressies, bijvoorbeeld alle bestanden die niet zijn aangepast in de afgelopen zes maanden.  

-   Overeenkomend beleid - bestanden die overeenkomen met een actief beleid van Cloud App Security.

-   MIME-type – controle van het MIME-type van een bestand, kan vrije tekst bevatten.  
  
-   Eigenaar - opnemen/uitsluiten van specifieke eigenaren van bestanden, bijvoorbeeld Alle bestanden bijhouden die worden gedeeld door malafide_werknemer_100.  
  
-   Eigenaar van de organisatie-eenheid – opnemen/uitsluiten van bestandseigenaren die deel uitmaken van een bepaalde organisatie-eenheid, bijvoorbeeld Alle openbare bestanden met uitzondering van bestanden die worden gedeeld door EMEA_marketing.  
  
-   Bovenliggende map – opnemen/uitsluiten op basis van de bovenliggende map, bijvoorbeeld Alle openbaar gedeelde bestanden met uitzondering van bestanden in deze map.  
  
-   In quarantaine – is het bestand in quarantaine geplaatst door de service, bijvoorbeeld Weergeven van alle bestanden die in quarantaine zijn geplaatst.  
  
U kunt ook instellen dat het beleid wordt uitgevoerd op specifieke bestanden door het filter **Van toepassing op** in te stellen op Alle bestanden, Geselecteerde mappen of Alle bestanden met uitzondering van geselecteerde mappen, en vervolgens de relevante bestanden of mappen te selecteren.  
  
![Filter Toepassen op](./media/apply-to-filter.png "apply to filter")  
  
## <a name="working-with-the-file-drawer"></a>Werken met de bestandslade

U kunt meer informatie bekijken over elk bestand door te klikken op het bestand in het Bestandslogboek. Daarmee opent u de bestandslade, die de volgende acties bevat die u met het bestand kunt uitvoeren:

- URL: hiermee gaat u naar de bestandslocatie.
- Bestands-id’s: als u klikt op Bestands-id’s, wordt er een pop-up geopend met onbewerkte details over het bestand, waaronder de bestands-id en versleutelingssleutels.
- Eigenaar: klik op de eigenaar om de gebruikerspagina van de eigenaar van dit bestand weer te geven.
- Overeenkomend beleid: klik op de koppeling Overeenkomend beleid om een lijst met beleidsregels te zien waarmee dit bestand overeenkomt.
- Classificatielabel: klik op het classificatielabel om de lijst met Azure Information Protection-classificatielabels te zien die in het bestand zijn gevonden. U kunt vervolgens filteren op alle bestanden die overeenkomen met dit label.    

![Bestandslade](./media/file-drawer.png "File drawer")  
  
Zie [Bestandsbeheeracties](governance-actions.md#file-governance-actions) voor een lijst met beschikbare beheeracties.

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO5-->


