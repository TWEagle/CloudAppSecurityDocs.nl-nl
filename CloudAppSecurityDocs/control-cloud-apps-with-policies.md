---
title: Gebruik van cloud-apps beheren door beleidsregels te maken in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u informatie over hoe beleidsregels worden gebruikt en ingesteld om het gebruik van cloud-apps te beheren.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 14d10238-0f61-43e9-ab96-71534a27d3d4
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 0173fd697c6219c9b6cf02e6d17e7a1d70840091
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="control-cloud-apps-with-policies"></a>Cloud-apps beheren met beleidsregels

Met beleidsregels kunt u de manier vastleggen waarop u wilt dat uw gebruikers zich gedragen in de cloud. Beleidsregels helpen u risicovol gedrag, schendingen of verdachte datapunten en activiteiten in uw cloudomgeving detecteren en indien nodig, te integreren herstelwerkstromen voor een optimale risicobeperking te behalen. Er zijn meerdere typen beleidsregels die samenhangen met de verschillende typen gegevens die u wilt verzamelen over uw cloudomgeving en de soorten herstelacties die u zou willen ondernemen.  
  
Bijvoorbeeld, als er een schending bedreiging voor gegevens die u wilt isoleren, moet u een ander type beleid dan als u wilt blokkeren een risicovolle cloud-app wordt gebruikt door uw organisatie.  
  
## <a name="policy-types"></a>Beleidstypen  
Wanneer u bekijkt de **beleid** pagina, de verschillende beleidsregels en sjablonen kunnen worden onderscheiden door het type en pictogram om te zien welke beleidsregels zijn beschikbaar. Beschikbaar beleid is afhankelijk van de gegevensbron en wat u hebt ingeschakeld in de Cloud App Security voor uw organisatie, bijvoorbeeld, als u Cloud Discovery-logboeken geüpload, het beleid met betrekking tot Cloud Discovery weergegeven.

De volgende soorten beleidsregels kunnen worden gemaakt:  
  
|pictogram beleidstype|Beleidstype|Gebruik|  
|-----|-----------------|---------|  
|![pictogram toegang-beleid](./media/proxy-policy.png)|Beleid voor toegang|Toegangsbeleid bieden u realtime-bewaking en controle over gebruikersaanmeldingen naar uw cloud-apps.|
|![pictogram activiteitenbeleid](./media/activity_policy.png)|Beleid voor activiteiten|Beleidsregels voor activiteiten zorgen ervoor dat u een breed scala aan geautomatiseerde processen kunt controleren waarbij u gebruikmaakt van de API’s van de app-provider. Met deze beleidsregels kunt u specifieke activiteiten volgen die worden uitgevoerd door verschillende gebruikers of onverwacht hoge frequenties van een bepaald type activiteit volgen.|  
|![pictogram beleid voor anomaliedetectie](./media/anomaly_detection_policy.png)|Beleid voor afwijkingsdetectie|De beleidsregels voor afwijkingsdetectie biedt u de mogelijkheid om ongebruikelijke activiteiten op uw cloud op te sporen op basis van de risicofactoren die u hier instelt, zodat u op de hoogte wordt gebracht wanneer iets afwijkt van de basislijn binnen uw organisatie of de standaardactiviteiten van de gebruiker.|  
|![pictogram beleidsregels voor Cloud Discovery](./media/discovery_policy.png)|Beleid voor appdetectie|Beleidsregels voor appdetectie bieden u de mogelijkheid om waarschuwingen in te stellen zodat u op de hoogte bent wanneer er binnen uw organisatie nieuwe apps gedetecteerd worden.|  
|![pictogram beleid voor anomaliedetectie](./media/anomaly_detection_policy.png)|Beleid voor afwijkingsdetectie voor Cloud Discovery|De beleidsregels voor afwijkingsdetectie voor Cloud Discovery kijken naar de logboeken die u voor het detecteren van cloud-apps en het zoeken naar ongebruikelijke voorvallen gebruikt. Voorbeelden zijn wanneer een gebruiker die nog nooit gebruik heeft gemaakt van Dropbox, plotseling 600 GB upload naar Dropbox, of wanneer er veel meer transacties worden uitgevoerd dan gebruikelijk in een bepaalde app.|  
|![pictogram bestandsbeleid](./media/file_policy.png)|Bestandsbeleid|Met beleidsregels voor bestanden kunt u uw cloud-apps scannen op specifieke bestanden of bestandstypen (gedeeld, gedeeld met externe domeinen) en gegevens (vertrouwelijke, PII-, creditcardgegevens, enzovoort). Ook kunt u beheeracties uitvoeren op bestanden. Beheeracties zijn specifiek per cloud-app.|  
|![pictogram voor sessie-beleid](./media/proxy-policy.png)|Beleid voor sessies|Sessie-beleid biedt u dankzij realtime-bewaking en controle over gebruikersactiviteit in uw cloud-apps.|

  
## <a name="identifying-risk"></a>Het identificeren van risico’s  
Cloud App Security helpt u bij het beperken van verschillende risico's in de cloud. U kunt elk beleidsregel en waarschuwing zo configureren dat deze bij een van de volgende risico’s hoort:  
  
-   **Toegangsbeheer:** wie heeft toegang tot wat vanaf waar?  
  
     Houd continu gedrag in de gaten en detecteer afwijkende activiteiten, inclusief interne en externe aanvallen met een hoog risico. Pas een beleid toe om voor een app of voor specifieke acties in een app een waarschuwing, blokkade of identiteitsverificatie in te stellen. Maakt beleidsregels mogelijk voor het beheren van on-premises en mobiele toegang op basis van gebruiker, apparaat en locatie met behulp van abrupte blokkering en gedetailleerde weergave, bewerking en blokkering. Detecteer verdachte aanmeldgebeurtenissen, waaronder mislukte meervoudige verificatiepogingen, mislukte aanmeldpogingen bij passieve accounts en imitatiegebeurtenissen.  
  
-   **Naleving:** worden uw nalevingsvereisten geschonden?  
  
     Rangschik en identificeer gevoelige of gereglementeerde gegevens, waaronder machtigingen voor het delen van elk afzonderlijk bestand, opgeslagen in bestandssynchronisatieservices zodat u voldoet aan regelgeving zoals PCI, SOX en HIPAA.  
  
-   **Configuratiebeheer:** worden er niet-geautoriseerde wijzigingen doorgevoerd in uw configuratie?  
  
     Monitor configuratiewijzigingen met inbegrip van configuratiebewerking op afstand.  
  
-   **Cloud Discovery:** worden er nieuwe apps gebruikt binnen uw organisatie? Hebt u een probleem met schaduw IT-apps die zonder uw weten worden gebruikt?  
  
     Algemene risico's voor elke cloud-app op basis van regelgeving beoordelen en branchecertificeringen en best practices, kunt u het aantal gebruikers, activiteiten, omvang van het verkeer en gemiddelde gebruiksduur in uren voor bewaken  
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
  
Beleidssjablonen helpen u de juiste filters en configuraties die nodig zijn voor het detecteren van specifieke gebeurtenissen van belang zijn binnen uw omgeving instellen. De sjablonen omvatten alle typen beleidsregels en kunnen toegepast worden op diverse services.  
  
Maken van een beleid van **beleidssjablonen**, voer de volgende stappen uit:  
  
1. Klik in de console op **Besturingselement** gevolgd door **Sjablonen**.  
  
    ![](./media/create-policy-from-template.png)  
  
2. Klik op de **+** aan de rechterkant van de rij van de sjabloon die u wilt gebruiken. Een pagina voor het maken van beleid wordt geopend, met daarin de vooraf gedefinieerde configuratie van de sjabloon.  
  
3. Pas de sjabloon aan op uw op maat gemaakte beleid. Elke eigenschap en elk veld van dit nieuwe beleid dat op een sjabloon is gebaseerd, kan aan uw wensen worden aangepast.  
   > [!NOTE] 
   >Wanneer u de beleidsfilters **bevat** wordt alleen gezocht naar volledige woorden die zijn gescheiden door komma's, punten, spaties of onderstrepingstekens bevatten. Bijvoorbeeld als u zoeken naar **malware** of **virus**, wordt virus_malware_file.exe gevonden maar malwarevirusfile.exe niet gevonden. Als u zoekt *malware.exe*, u alle bestanden met kwaadaardige software of exe vinden in de bestandsnaam, dat als u zoekt **"malware.exe"** (met aanhalingstekens) vindt u alleen bestanden die bevatten precies "malware.exe". 
    **Is gelijk aan** wordt alleen gezocht naar de volledige tekenreeks, bijvoorbeeld als u zoeken naar *malware.exe* malware.exe gevonden maar malware.exe.txt niet gevonden.  
4. Nadat u het nieuwe beleid maakt op basis van een sjabloon, wordt een koppeling naar het nieuwe beleid weergegeven in de kolom **Gekoppelde beleidsregels** in de beleidssjabloontabel naast de sjabloon waarmee het beleid is gemaakt.   
    U kunt vanuit elke sjabloon zoveel beleidsregels maken als u wilt en deze zullen allemaal gekoppeld zijn aan de oorspronkelijke sjabloon. Hierdoor kunt u alle gemaakte beleidsregels volgen met behulp van dezelfde sjabloon.  
  
U kunt ook **een beleid maken tijdens een onderzoek**. Als u **Activiteitenlogboek**, **Bestanden** of **Accounts** onderzoekt, en u zoekt verder naar iets specifieks, kunt u op elk gewenst moment een nieuw beleid maken op basis van de resultaten van uw onderzoek.  
  
Als u bijvoorbeeld de **activiteitenlogboek**, en zien van een beheerdersactiviteit van buiten uw kantoor-IP-adressen.

  
Voer de volgende stappen uit voor het maken van een beleid dat is gebaseerd op onderzoeksresultaten:  
  
1.  Klik in de console op **onderzoeken** gevolgd door **activiteitenlogboek**, **bestanden**, of **Accounts**.  
  
2.  Gebruik de filters bovenaan de pagina om het aantal resultaten te beperken tot het verdachte gebied. Klik bijvoorbeeld in de pagina Activiteitenlogboek op **Activiteit** en selecteer **Aanmelding beheerder**. Klik vervolgens onder **IP-adres**, selecteer **categorie** en stel de waarde niet op te nemen IP-adres categorieën die u hebt gemaakt voor uw herkende domeinen, zoals de beheerder, het bedrijf en VPN IP-adressen.  
  
     ![Bestand maken op basis van onderzoek](./media/create-file-from-investigation.png)  
  
3.  Klik in de rechterbovenhoek van de console op **Nieuw beleid op basis van zoekbewerking**![](./media/new-policy-from-search-button.png).  
  
4.  Een pagina voor het maken van beleid opent en bevat de filters die u gebruikt hebt voor uw onderzoek.  
  
5.  Pas de sjabloon aan op uw op maat gemaakte beleid. Elke eigenschap en elk veld van dit nieuwe beleid dat op een onderzoek is gebaseerd, kan aan uw wensen worden aangepast.  
   
> [!NOTE] 
> Wanneer u de beleidsfilters **bevat** wordt alleen gezocht naar volledige woorden die zijn gescheiden door komma's, punten, spaties of onderstrepingstekens bevatten. Bijvoorbeeld als u zoeken naar **malware** of **virus**, wordt virus_malware_file.exe gevonden maar malwarevirusfile.exe niet gevonden.  
     **Is gelijk aan** wordt alleen gezocht naar de volledige tekenreeks, bijvoorbeeld als u zoeken naar **malware.exe** malware.exe gevonden maar malware.exe.txt niet gevonden.  
  
 
 
![Activiteitenbeleid maken op basis van onderzoek](./media/create-activity-policy-from-investigation.png)
 
 
  
> [!NOTE]  
>  Zie de bijbehorende documentatie over beleid voor meer informatie over het instellen van de Beleidsvelden:  
>   
>  [Beleidsregels voor gebruikersactiviteit](user-activity-policies.md)  
>   
>  [Beleidsregels voor gegevensbescherming](data-protection-policies.md)  
>   
>  [Beleidsregels voor Cloud Discovery](cloud-discovery-policies.md)  

  
### <a name="add-automated-actions-to-respond-and-remediate-risks-automatically"></a>Automatische acties toevoegen om te reageren op risico’s en deze automatisch te herstellen

Zie [Verbonden apps beheren](governance-actions.md) voor een lijst met beschikbare beheeracties per app.

U kunt het beleid ook zodanig instellen dat u per e-mail of sms een waarschuwing ontvangt wanneer overeenkomsten worden gedetecteerd. 

Ga naar [De portal aanpassen](general-setup.md) om uw meldingsvoorkeuren in te stellen. 
  
> [!NOTE] 
> Het maximum aantal waarschuwingen die worden verzonden via SMS-bericht is 10 per telefoonnummer per dag. De dag wordt berekend op basis van de UTC-tijdzone. 


## <a name="enable-and-disable-policies"></a>Beleid in- en uitschakelen

Nadat u een beleid hebt gemaakt, kunt u dat in- of uitschakelen. Daardoor hoeft u een beleid nadat u het hebt gemaakt niet te verwijderen om het te kunnen stopzetten. In plaats daarvan als u stoppen van het beleid voor een bepaalde reden wilt, uitschakelen tot u het opnieuw inschakelen.

- Als u een beleid wilt inschakelen, klikt u op de pagina **Beleid** op de drie punten aan het einde van de rij van het beleid dat u wilt inschakelen en selecteert u **Inschakelen**. 

![Beleid inschakelen](./media/enable-policy.png)

- Als u een beleid wilt uitschakelen, klikt u op de pagina **Beleid** op de drie punten aan het einde van de rij van het beleid dat u wilt uitschakelen en selecteert u **Uitschakelen**.

![Beleid uitschakelen](./media/disable-policy.png)

Nadat u een nieuw beleid hebt gemaakt, is dat standaard ingeschakeld.

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  