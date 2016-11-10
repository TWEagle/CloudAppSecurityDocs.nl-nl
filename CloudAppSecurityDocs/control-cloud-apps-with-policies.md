---
title: Cloud-apps beheren met beleidsregels | Microsoft Docs
description: In dit onderwerp vindt u informatie over hoe beleidsregels worden gebruikt en ingesteld om het gebruik van cloud-apps te beheren.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 14d10238-0f61-43e9-ab96-71534a27d3d4
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 10b4a9575951007dbee9003fd061fb5aaa2d3823


---
# <a name="control-cloud-apps-with-policies"></a>Cloud-apps beheren met beleidsregels

Met beleidsregels kunt u de manier vastleggen waarop u wilt dat uw gebruikers zich gedragen in de cloud. Beleidsregels helpen u risicovol gedrag, schendingen of verdachte datapunten en -activiteiten binnen uw cloudomgeving te detecteren en, indien vereist, herstelwerkstromen te integreren om een optimale risicobeperking te behalen. Er zijn meerdere typen beleidsregels die samenhangen met de verschillende typen gegevens die u wilt verzamelen over uw cloudomgeving en de soorten herstelacties die u zou willen ondernemen.  
  
Als er bijvoorbeeld een gegevensschendingsbedreiging is die u in quarantaine wilt zetten, heeft u een ander stoort beleid nodig dan wanneer u een risicovolle cloud-app wilt blokkeren voor gebruik binnen uw organisatie.  
  
## <a name="policy-types"></a>Beleidstypen  
De volgende soorten beleidsregels kunnen worden gemaakt:  
  
|Beleidstypen|Gebruik|  
|-----------------|---------|  
|Beleid voor activiteiten|Beleidsregels voor activiteiten zorgen ervoor dat u een breed scala aan geautomatiseerde processen kunt controleren waarbij u gebruikmaakt van de API’s van de app-provider. Met deze beleidsregels kunt u specifieke activiteiten volgen die worden uitgevoerd door verschillende gebruikers of onverwacht hoge frequenties van een bepaald type activiteit volgen.|  
|Beleid voor afwijkingsdetectie|De beleidsregels voor afwijkingsdetectie biedt u de mogelijkheid om ongebruikelijke activiteiten op uw cloud op te sporen op basis van de risicofactoren die u hier instelt, zodat u op de hoogte wordt gebracht wanneer iets afwijkt van de basislijn binnen uw organisatie of de standaardactiviteiten van de gebruiker.|  
|Beleid voor afwijkingsdetectie voor Cloud Discovery|De beleidsregels voor afwijkingsdetectie voor Cloud Discovery kijken naar de logboeken die u voor het detecteren van cloud-apps en het zoeken naar ongebruikelijke voorvallen gebruikt. Voorbeelden zijn wanneer een gebruiker die nog nooit gebruik heeft gemaakt van Dropbox, plotseling 600 GB upload naar Dropbox, of wanneer er veel meer transacties worden uitgevoerd dan gebruikelijk in een bepaalde app.|  
|Beleid voor appdetectie|Beleidsregels voor appdetectie bieden u de mogelijkheid om waarschuwingen in te stellen zodat u op de hoogte bent wanneer er binnen uw organisatie nieuwe apps gedetecteerd worden.|  
|Beleid voor bestanden|Met beleidsregels voor bestanden kunt u uw cloud-apps scannen op specifieke bestanden of bestandstypen (gedeeld, gedeeld met externe domeinen) en gegevens (vertrouwelijke, PII-, creditcardgegevens, enzovoort). Ook kunt u beheeracties uitvoeren op bestanden. Beheeracties zijn specifiek per cloud-app.|  
  
## <a name="identifying-risk"></a>Het identificeren van risico’s  
Cloud App Security helpt u bij het beperken van verschillende risico's in de cloud. U kunt elk beleidsregel en waarschuwing zo configureren dat deze bij een van de volgende risico’s hoort:  
  
-   **Toegangsbeheer:** wie heeft toegang tot wat vanaf waar?  
  
     Houd continu gedrag in de gaten en detecteer afwijkende activiteiten, inclusief interne en externe aanvallen met een hoog risico. Pas een beleid toe om voor een app of voor specifieke acties in een app een waarschuwing, blokkade of identiteitsverificatie in te stellen. Maakt beleidsregels mogelijk voor het beheren van on-premises en mobiele toegang op basis van gebruiker, apparaat en locatie met behulp van abrupte blokkering en gedetailleerde weergave, bewerking en blokkering. Detecteer verdachte aanmeldgebeurtenissen, waaronder mislukte meervoudige verificatiepogingen, mislukte aanmeldpogingen bij passieve accounts en imitatiegebeurtenissen.  
  
-   **Naleving:** worden uw nalevingsvereisten geschonden?  
  
     Rangschik en identificeer gevoelige of gereglementeerde gegevens, waaronder machtigingen voor het delen van elk afzonderlijk bestand, opgeslagen in bestandssynchronisatieservices zodat u voldoet aan regelgeving zoals PCI, SOX en HIPAA.  
  
-   **Configuratiebeheer:** worden er niet-geautoriseerde wijzigingen doorgevoerd in uw configuratie?  
  
     Monitor configuratiewijzigingen met inbegrip van configuratiebewerking op afstand.  
  
-   **Cloud Discovery:** worden er nieuwe, niet-goedgekeurde apps gebruikt binnen uw organisatie? Hebt u een probleem met schaduw IT-apps die zonder uw weten worden gebruikt?  
  
     Breng de algemene risico’s van elke cloud-app in kaart op basis van regelgevings- en branchecertificeringen, en  
    aanbevolen procedures. Dit biedt u de mogelijkheid om het aantal gebruikers, activiteiten, omvang van het verkeer en de gemiddelde gebruiksduur in uren vast te stellen voor  
    elke cloud-app.  
  
-   **DLP:** worden vertrouwelijke bestanden openbaar gedeeld? Moet u de bestanden in quarantaine plaatsen?  
  
     On-premises DLP-integratie zorgt voor integratie en gesloten herstel met bestaande on-premises DLP-oplossingen.  
  
-   **Accounts met bevoegdheden:** is het nodig dat u beheeraccounts monitort?  
  
     Realtimeactiviteitenbewaking en -rapportage voor gebruikers met bevoegdheden en beheerders.  
  
-   **Beheer van deelgedrag:** hoe worden gegevens gedeeld binnen uw cloudomgeving?  
  
     Bekijk de inhoud van bestanden en inhoud in de cloud, en leg beleidsregels voor het intern en extern delen van inhoud op. Houd samenwerkverbanden in de gaten en stel beleidsregels voor het delen op, zoals een blokkade voor het delen buiten uw organisatie.  
  
-   **Bedreigingendetectie:** bedreigen verdachte activiteiten uw cloudomgeving?  
  
     Ontvang realtimemeldingen via sms of e-mail voor iedere beleidsschending of activiteitsdrempel die wordt overschreden. Door machine learning-algoritmen toe te passen, biedt Cloud App Security u de mogelijkheid om gedrag van een gebruiker te detecteren dat mogelijk wijst op misbruik van gegevens.  
  
## <a name="how-to-control-risk"></a>Het beheren van risico’s  
Ga als volgt te werk om met beleidsregels risico’s te beheren:  
  
1.  Maak een beleid via een sjabloon of een query.  
  
2.  Stel het beleid af zodat de gewenste resultaten worden behaald.  
  
3.  Voeg automatische acties toe om te reageren op risico’s en deze automatisch te herstellen.  
  
### <a name="create-a-policy"></a>Een beleid maken  
U kunt als basis voor al uw beleidsregels gebruikmaken van een van de beleidssjablonen van Cloud App Security of uw beleidsregels maken met behulp van een query.  
  
Beleidssjablonen helpen u bij het instellen van de juiste filters en configuraties die nodig zijn voor het detecteren van specifieke gebeurtenissen die van belang zijn binnen uw omgeving. De sjablonen omvatten alle typen beleidsregels en kunnen toegepast worden op diverse services.  
  
Volg de volgende stappen wanneer u een beleid wilt maken met behulp van een **beleidssjabloon**:  
  
1.  Klik in de console op **Besturingselement** gevolgd door **Sjablonen**.  
  
     ![](./media/create-policy-from-template.png)  
  
2.  Klik op de **+** aan de rechterkant van de rij van de sjabloon die u wilt gebruiken. Een pagina voor het maken van beleid wordt geopend, met daarin de vooraf gedefinieerde configuratie van de sjabloon.  
  
3.  Pas de sjabloon aan op uw op maat gemaakte beleid. Elke eigenschap en elk veld van dit nieuwe beleid dat op een sjabloon is gebaseerd, kan aan uw wensen worden aangepast.  
> [!NOTE] 
>Wanneer u de beleidsfilters gebruikt, zoekt **Bevat** alleen naar volledige woorden die zijn gescheiden door komma’s, punten, spaties of onderstrepingstekens. Als u bijvoorbeeld zoekt op **malware** of **virus**, wordt virus_malware_file.exe wel gevonden maar malwarevirusfile.exe niet. Als u zoekt op **malware.exe** vindt u ALLE bestanden met ‘malware’ of ‘exe’ in de bestandsnaam, maar als u zoekt op **”malware.exe”** (met aanhalingstekens) vindt u alleen bestanden die precies “malware.exe” bevatten. 
     **Is gelijk aan** zoekt alleen naar de volledige tekenreeks. Als u bijvoorbeeld zoekt naar **malware.exe** wordt malware.exe wel gevonden maar malware.exe.txt niet.  
4.  Nadat u het nieuwe beleid maakt op basis van een sjabloon, wordt een koppeling naar het nieuwe beleid weergegeven in de kolom **Gekoppelde beleidsregels** in de beleidssjabloontabel naast de sjabloon waarmee het beleid is gemaakt.  
     U kunt vanuit elke sjabloon zoveel beleidsregels maken als u wilt en deze zullen allemaal gekoppeld zijn aan de oorspronkelijke sjabloon. Hierdoor kunt u alle gemaakte beleidsregels volgen met behulp van dezelfde sjabloon.  
  
U kunt ook **een beleid maken tijdens een onderzoek**. Als u **Activiteitenlogboek**, **Bestanden** of **Accounts** onderzoekt, en u zoekt verder naar iets specifieks, kunt u op elk gewenst moment een nieuw beleid maken op basis van de resultaten van uw onderzoek.  
  
Als u bijvoorbeeld kijkt naar de **Activiteitenlogboek** en u ziet dat er bij een van uw beheerdersaccounts wordt aangemeld vanaf een onverwachte geografische locatie, kunt u de resultaten van het **Activiteitenlogboek** filteren zodat alle aanmeldpogingen bij activiteiten van die beheerder worden weergegeven, en vervolgens een rapport maken dat u op de hoogte stelt wanneer er weer een activiteit gedetecteerd wordt van deze gebruiker.  
  
Volg de volgende stappen voor het maken van een beleid gebaseerd op onderzoeksresultaten:  
  
1.  Klik in de console op **Onderzoeken** gevolgd door **Activiteitenlogboek**, **Bestanden** of **Accounts**.  
  
2.  Gebruik de filters bovenaan de pagina om het aantal resultaten te beperken tot het verdachte gebied. Klik bijvoorbeeld in de pagina Activiteitenlogboek op **Gebruiker** en selecteer de beheerder waarbij in het account ongebruikelijke activiteiten zijn waargenomen. Klik vervolgens onder **Activiteit** op **Map kopiëren** en **Bestand kopiëren**.  
  
     ![](./media/create-file-from-investigation.png)  
  
3.  Klik in de rechterbovenhoek van de console op **Nieuw beleid op basis van zoekbewerking**![](./media/new-policy-from-search-button.png).  
  
4.  Een pagina voor het maken van beleid opent en bevat de filters die u gebruikt hebt voor uw onderzoek.  
  
5.  Pas de sjabloon aan op uw op maat gemaakte beleid. Elke eigenschap en elk veld van dit nieuwe beleid dat op een onderzoek is gebaseerd, kan aan uw wensen worden aangepast.  
   
> [!NOTE] 
> Wanneer u de beleidsfilters gebruikt, zoekt **Bevat** alleen naar volledige woorden die zijn gescheiden door komma’s, punten, spaties of onderstrepingstekens. Als u bijvoorbeeld zoekt op **malware** of **virus**, wordt virus_malware_file.exe wel gevonden maar malwarevirusfile.exe niet.  
     **Is gelijk aan** zoekt alleen naar de volledige tekenreeks. Als u bijvoorbeeld zoekt naar **malware.exe** wordt malware.exe wel gevonden maar malware.exe.txt niet.  
  
 
 
![Activiteitenbeleid maken op basis van onderzoek](./media/create-activity-policy-from-investigation.png)
 
 
  
> [!NOTE]  
>  Raadpleeg de bijbehorende documentatie over beleid voor meer informatie over het instellen van de beleidsvelden:  
>   
>  [Beleidsregels voor gebruikersactiviteit](user-activity-policies.md)  
>   
>  [Beleidsregels voor gegevensbescherming](data-protection-policies.md)  
>   
>  [Beleidsregels voor Cloud Discovery](cloud-discovery-policies.md)  
  
### <a name="policy-conflicts"></a>Beleidsconflicten
Als u meerdere beleidsregels hebt gemaakt, kan er een situatie ontstaan waarin de beleidsregels elkaar overlappen. In dit geval worden de beleidsregels als volgt verwerkt in Cloud App Security:
* Als twee beleidsregels acties bevatten die in elkaar zijn opgenomen (bijvoorbeeld wanneer **Externe shares verwijderen** is opgenomen in **Privé maken**), wordt het conflict in Cloud App Security opgelost en wordt de sterkere actie afgedwongen.
* Als de acties volledig onafhankelijk van elkaar zijn (bijvoorbeeld **De eigenaar een melding sturen** en **Privé maken**), worden beide acties uitgevoerd.
* Als de acties conflicteren (bijvoorbeeld **Eigenaar wijzigen in gebruiker A** en **Eigenaar wijzigen in gebruiker B**), kan elke overeenkomst tot andere resultaten leiden. Het is belangrijk uw beleidsregels te wijzigen om conflicten te voorkomen, omdat ze kunnen leiden tot ongewenste wijzigingen in het station die moeilijk te detecteren zijn. 


## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  


<!--HONumber=Oct16_HO4-->

