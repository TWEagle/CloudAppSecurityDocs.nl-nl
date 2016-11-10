---
title: Bestanden | Microsoft Docs
description: Dit naslagonderwerp bevat informatie over de bestandstypen en bestandsfilters die worden gebruikt in Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cadcd6db-05b2-4974-91fe-cfac3d57aecd
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 1687dd8d98a2e44acbf3f8ad34f875cbbc0bcdd1


---

# <a name="files"></a>Bestanden

###  <a name="a-namefilefiltersa-file-filters"></a> Bestandsfilters 
 
Met Cloud App Security kunt u elk bestandstype controleren op basis van meer dan twintig metagegevensfilters (bijvoorbeeld toegangsniveau, bestandstype). 
 
Met de ingebouwde DLP-engines van Cloud App Security worden inhoudsinspecties uitgevoerd door tekst te extraheren uit algemene bestandstypen (PDF-, Office-, RTF-, HTML-, codebestanden, enzovoort).

Hieronder volgt een lijst met de bestandsfilters die kunnen worden toegepast. De meeste filters bieden ondersteuning voor meerdere waarden en voor NOT (niet), zodat u over een zeer krachtig hulpprogramma beschikt voor het maken van een beleid.  
> [!NOTE] 
> Wanneer u de beleidsfilters gebruikt, zoekt **Bevat** alleen naar volledige woorden die zijn gescheiden door komma’s, punten, spaties of onderstrepingstekens. Als u bijvoorbeeld zoekt op **malware** of **virus**, wordt virus_malware_file.exe wel gevonden maar malwarevirusfile.exe niet. Als u zoekt op **malware.exe** vindt u ALLE bestanden met ‘malware’ of ‘exe’ in de bestandsnaam, maar als u zoekt op **”malware.exe”** (met aanhalingstekens) vindt u alleen bestanden die precies “malware.exe” bevatten.  **Is gelijk aan** zoekt alleen naar de volledige tekenreeks. Als u bijvoorbeeld zoekt naar **malware.exe** wordt malware.exe wel gevonden maar malware.exe.txt niet. 

   
![Filters bestandsbeleidstype](./media/policy_file-type-filters.png "policy_file type filters")  
  
-   Toegangsniveau – toegangsniveau delen; openbaar, extern, intern of privé.  Zie [General Setup, Set up the portal](getting-started-with-cloud-app-security.md) ('De portal instellen' in het artikel 'Algemene instellingen') voor meer informatie over externe bestanden. Interne bestanden zijn de bestanden in de interne domeinen die u instelt in [Algemene instellingen](General-setup.md). Externe bestanden zijn de bestanden die zijn opgeslagen op locaties die zich niet binnen de ingestelde interne domeinen bevinden. Gedeelde bestanden zijn bestanden met een hoger niveau voor delen dan Privé, inclusief intern gedeelde bestanden (bestanden die binnen uw interne domeinen worden gedeeld), extern gedeelde bestanden (bestanden die worden gedeeld in domeinen die niet in uw interne domeinen worden weergegeven), openbare bestanden met een koppeling (bestanden die met anderen kunnen worden gedeeld via een koppeling) en openbare bestanden (bestanden die kunnen worden gevonden door te zoeken op internet). 

> [!NOTE]
>  Bestanden die door externe gebruikers in uw verbonden apps voor opslag worden gedeeld, worden als volgt verwerkt met Cloud App Security:     - **OneDrive:** In OneDrive wordt een interne gebruiker toegewezen als eigenaar van de bestanden die door een externe gebruiker in uw OneDrive-exemplaar worden geplaatst. Omdat de bestanden vervolgens worden gezien als eigendom van uw organisatie, worden deze bestanden gescand met Cloud App Security en worden beleidsregels op deze bestanden toegepast, zoals voor alle bestanden in OneDrive gebeurt.
     - **Google Drive:** in Google Drive worden deze bestanden gezien als eigendom van de externe gebruiker en vanwege de juridische beperkingen voor bestanden en gegevens die geen eigendom van uw organisatie zijn, heeft Cloud App Security geen toegang tot deze bestanden.
    - **Box:** Omdat bestanden die eigendom zijn van een externe gebruiker in Box worden gezien als privégegevens, kunnen globale beheerders van Box de inhoud van deze bestanden niet bekijken. Om deze reden heeft Cloud App Security geen toegang tot deze bestanden. 
    - **Dropbox:** Omdat bestanden die eigendom zijn van een externe gebruiker in Dropbox worden gezien als privégegevens, kunnen globale beheerders van Box de inhoud van deze bestanden niet bekijken. Om deze reden heeft Cloud App Security geen toegang tot deze bestanden.

-   App – alleen bestanden binnen deze apps zoeken.  
  
-   Samenwerkers – specifieke groepen met samenwerkers opnemen/uitsluiten.  
  
    -   Elke uit domein – als elke willekeurige gebruiker uit dit domein toegang tot het bestand heeft.  
  
    -   Gehele domein – als het gehele domein toegang tot het bestand heeft.  
  
    -   Groepen – als een specifieke groep toegang tot het bestand heeft. Groepen kunnen worden geïmporteerd vanuit Active Directory of cloud-apps. Ook kunnen ze handmatig worden gemaakt in de service.  
  
    -   Gebruikers – een bepaalde reeks gebruikers die mogelijk toegang tot het bestand hebben.  
  
-   Gemaakt – de tijd waarop het bestand is gemaakt. Het filter ondersteunt datums ervoor en erna, evenals een datumbereik.  
  
-   Laatst gewijzigd – de tijd waarop het bestand is gewijzigd. Het filter ondersteunt datums ervoor en erna, een datumbereik en relatieve tijdsexpressies, bijvoorbeeld alle bestanden die niet zijn aangepast in de afgelopen zes maanden.  
  
-   Extensie – gericht op specifieke bestandsextensies, bijvoorbeeld alle bestanden die uitvoerbare bestanden zijn (exe).  
  
-   Bestands-id – zoeken naar specifieke bestands-id's. Dit is een geavanceerde functie waarmee u bepaalde bestanden met een hoge waarde kunt bijhouden zonder afhankelijk te zijn van de eigenaar/locatie/naam.  
  
-   Bestandsnaam – de bestandsnaam of subtekenreeks van de naam zoals deze is gedefinieerd in de cloud-app, bijvoorbeeld Alle bestanden met een wachtwoord in hun naam.  
  
-   Bestandstype – Cloud App Security houdt rekening met het MIME-type dat van de service is ontvangen en scant het bestand om het daadwerkelijke bestandstype te bepalen. Deze scan is van toepassing op bestanden die relevant zijn voor een gegevensscan (documenten, afbeeldingen, presentaties, spreadsheets, tekst- en zipbestanden). Het filter werkt per type bestand/map, bijvoorbeeld Alle mappen die... of Alle spreadsheetbestanden die...


     ![Prullenbak beleidsbestandsfilters](./media/policy_file-filters-trash.png "policy_file filters trash")  
  
-   In de Prullenbak – uitsluiten/opnemen van bestanden in de map Prullenbak. Deze bestanden kunnen nog steeds zijn gedeeld en vormen mogelijk een risico.  
  
-   MIME-type – controle van het MIME-type van een bestand, kan vrije tekst bevatten.  
  
-   Eigenaar - opnemen/uitsluiten van specifieke eigenaren van bestanden, bijvoorbeeld Alle bestanden bijhouden die worden gedeeld door malafide_werknemer_100.  
  
-   Eigenaar van de organisatie-eenheid – opnemen/uitsluiten van bestandseigenaren die deel uitmaken van een bepaalde organisatie-eenheid, bijvoorbeeld Alle openbare bestanden met uitzondering van bestanden die worden gedeeld door EMEA_marketing.  
  
-   Bovenliggende map – opnemen/uitsluiten op basis van de bovenliggende map, bijvoorbeeld Alle openbaar gedeelde bestanden met uitzondering van bestanden in deze map.  
  
-   In quarantaine – is het bestand in quarantaine geplaatst door de service, bijvoorbeeld Weergeven van alle bestanden die in quarantaine zijn geplaatst.  
  
U kunt ook instellen dat het beleid wordt uitgevoerd op specifieke bestanden door het filter **Van toepassing op** in te stellen op Alle bestanden, Geselecteerde mappen of Alle bestanden met uitzondering van geselecteerde mappen, en vervolgens de relevante bestanden of mappen te selecteren.  
  
![Filter Toepassen op](./media/apply-to-filter.png "apply to filter")  
  
### <a name="governance-actions"></a>Beheeracties  
  
-   Meldingen  
  
    -   Waarschuwingen – waarschuwingen kunnen in het systeem worden geactiveerd en worden doorgegeven via e-mail en SMS op basis van de ernst.  
  
    -   E-mailmeldingen voor gebruikers – e-mailberichten kunnen worden aangepast en worden verzonden naar alle eigenaren van bestanden die het beleid schenden.  
  
    -   CC naar manager – op basis van directory-integratie voor gebruikers kunnen e-mailmeldingen ook worden verzonden naar de manager van de persoon die een beleid schendt.  
  
-   Meldingen verzenden naar specifieke gebruikers – specifieke lijst met e-mailadressen die deze meldingen ontvangen.  
  
-   De laatste editor van het bestand informeren – meldingen verzenden naar de laatste persoon die het bestand heeft gewijzigd.  
  
-   Beheeracties in apps  
  
     Gedetailleerde acties kunnen per app worden afgedwongen, specifieke acties zijn afhankelijk van de terminologie in de app.  
  
    -   Delen wijzigen  
  
        -   Openbaar delen verwijderen – alleen toegang geven aan samenwerkers met een naam, bijvoorbeeld: Openbare toegang voor Google Apps verwijderen en Rechtstreekse gedeelde koppeling voor Box verwijderen.  
  
        -   Externe gebruikers verwijderen – alleen toegang tot bedrijfsgebruikers toestaan.  
  
        -   Privé maken – alleen de eigenaar heeft toegang tot het bestand, alle shares worden verwijderd.  
  
        -   Een samenwerker verwijderen – een specifieke samenwerker verwijderen uit het bestand.  
  
    -   Quarantaine  
  
        -   In quarantaine geplaatst door gebruiker – selfservice toestaan door het bestand te verplaatsen naar een door de gebruiker beheerde map voor quarantaine  
  
        -   In quarantaine geplaatst door administrator – het bestand wordt in quarantaine geplaatst op het administrator-station en de administrator moet dit goedkeuren.  
  
-   Prullenbak – het bestand naar de map Prullenbak verplaatsen.
  
![Waarschuwingen maken voor beleid](./media/policy_create-alerts.png "policy_create alerts")  
  
 
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


