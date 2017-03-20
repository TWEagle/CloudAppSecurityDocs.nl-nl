---
title: Releaseopmerkingen en versies van Cloud App Security | Microsoft Docs
description: Dit onderwerp wordt regelmatig bijgewerkt, zodat u weet wat er nieuw is in de meest recente versie van Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/5/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: d418ef3d-76ee-45d5-b5ae-21346e5239a3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 23870c7ba734acc3095f1dcd097f19954fee5e79
ms.sourcegitcommit: 064afc7148de42c0e81763f96ec13fb2c92f02a9
translationtype: HT
---
# <a name="release-notes"></a>Opmerkingen bij de release


## <a name="cloud-app-security-release-90-91-92"></a>Cloud App Security-release 90, 91, 92
Uitgebracht februari 2017

**Speciale aankondiging**

Cloud App Security is nu officieel gecertificeerd met Microsoft Naleving voor modelcIausules van de EU, ISO, HIPAA, CSA STAR en meer. Ga naar [Microsoft Compliance Offerings](https://www.microsoft.com/trustcenter/compliance/complianceofferings) (Aanbiedingen voor Microsoft Naleving, Engelstalig) en selecteer Cloud App Security voor de volledige lijst met certificaten.

**Nieuwe functies**

-  **Gebruikersgroepen importeren (preview)** wanneer u apps verbindt met behulp van API-connectors, kunt u nu met Cloud App Security gebruikersgroepen importeren uit Office 365 en Azure Active Directory. Typische scenario's die gebruikmaken van de geïmporteerde gebruikersgroepen zijn: onderzoeken welke documenten de HR-mensen bekijken of controleren of er iets vreemds gebeurt in de managementgroep of dat er iemand uit de beheergroep een activiteit buiten de Verenigde Staten heeft uitgevoerd. Zie voor meer informatie en instructies [Gebruikersgroepen importeren](user-groups.md).

-  In het activiteitenlogboek kunt u nu gebruikers en gebruikers in groepen filteren om weer te geven welke activiteiten door een specifieke gebruiker zijn uitgevoerd en welke zijn uitgevoerd op een specifieke gebruiker. U kunt bijvoorbeeld activiteiten onderzoeken waarin de gebruiker zich voor iemand anders heeft uitgegeven en activiteiten waarin anderen zich voor deze gebruiker hebben uitgegeven. Zie voor meer informatie [Activiteiten](activity-filters.md).

- Als u bij het onderzoeken van een bestand in de pagina **Bestanden** inzoomt op de **Deelnemers** van een specifiek bestand, ziet u nu meer informatie over de deelnemers, inclusief of zij intern of extern zijn, schrijvers of lezers (bestandsmachtigingen) en, als een bestand wordt gedeeld met een groep, kunt u nu alle gebruikers zien die lid zijn van de groep. Hiermee kunt u zien of de leden van de groep externe gebruikers zijn.

-  IPv6-ondersteuning is nu beschikbaar voor alle apparaten.

-    Cloud Discovery ondersteunt nu Baracuda-apparaten.

-    Cloud App Security-systeemwaarschuwingen omvatten nu SIEM-verbindingsfouten. Zie voor meer informatie [SIEM-integratie](siem.md).

-    Cloud App Security biedt nu ondersteuning voor de volgende activiteiten:

     **Office 365, SharePoint/OneDrive**: Toepassingsconfiguratie bijwerken, Eigenaar van groep verwijderen, Site verwijderen, Map maken

     **Dropbox**: Lid aan groep toevoegen, Lid uit groep verwijderen, Groep maken, Naam groep wijzigen, Naam teamlid wijzigen

     **Vak**: Item uit groep verwijderen, Item delen bijwerken, Gebruiker aan groep toevoegen, Gebruiker uit groep verwijderen


## <a name="cloud-app-security-release-89"></a>Cloud App Security-release 89
Uitgebracht op 22 januari 2017

**Nieuwe functies**
-    We maken een begin met het implementeren van de mogelijkheid om DLP-gebeurtenissen uit het beveiligings- en compliancecentrum van Office 365 weer te geven in Cloud App Security. Als u DLP-beleid hebt geconfigureerd in het beveiligings- en compliancecentrum van Office 365, worden gedetecteerde beleidsovereenkomsten weergegeven in het activiteitenlogboek van Cloud App Security. De informatie in het activiteitenlogboek omvat het bestand of het e-mailbericht dat de overeenkomst heeft geactiveerd en het overeenkomende beleid of de waarschuwing. Met de activiteit "Security event" (Beveiligingsgebeurtenis) kunt u overeenkomsten met DLP-beleid in Office 365 weergeven in het activiteitenlogboek van Cloud App Security. Met deze functie kunt u het volgende doen:
    -    Alle DLP-resultaten weergeven die afkomstig zijn van de DLP-engine van Office&365;.
    -    Waarschuwen als DLP-beleid in Office 365 overeenkomt met een bepaald bestand, een bepaalde SharePoint-site of een bepaald beleid.
    -    DLP-overeenkomsten met een bredere context onderzoeken, bijvoorbeeld externe gebruikers die een bestand hebben geopend of gedownload dat overeenkomst met een DLP-beleid heeft geactiveerd.
 
-    Beschrijvingen van activiteiten zijn verbeterd voor meer duidelijkheid en consistentie. Voor elke activiteit is er nu een feedbackknop. Als er iets onduidelijk is of als u een vraag hebt, kunt u het ons laten weten. 
 
**Verbeteringen**  
-    Er is een nieuwe beheeractie voor Office 365 toegevoegd waarmee u alle externe gebruikers van een bestand kunt verwijderen. Hierdoor kunt u bijvoorbeeld beleidsregels implementeren die **externe shares verwijderen uit bestanden met de classificatie Alleen intern**.
-    Verbeterde identificatie van externe gebruikers in SharePoint Online. Bij het filteren van de groep 'externe gebruikers' wordt het systeemaccount app@sharepoint niet weergegeven.



## <a name="cloud-app-security-release-88"></a>Cloud App Security-release 88
Uitgebracht op 8 januari 2017
 
**Nieuwe functies**
- Uw SIEM verbinden met Cloud App Security. U kunt nu waarschuwingen en activiteiten automatisch naar de gewenste SIEM-oplossing verzenden door SIEM-agents te configureren. Nu beschikbaar als een openbare preview.  Raadpleeg het gedeelte over integratie met SIEM voor volledige documentatie en details.
- Cloud Discovery biedt nu ondersteuning voor IPv6. We hebben ondersteuning voor Palo Alto en Juniper geïmplementeerd en in toekomstige releases worden meer apparaten geïmplementeerd.
 
**Verbeteringen**
- De catalogus met cloud-apps bevat een nieuwe risicofactor. U kunt nu een app beoordelen op basis van het feit of gebruikersverificatie voor de app vereist is. Apps die verificatie afdwingen en geen anoniem gebruik toestaan, krijgen een gezondere risicoscore.
- We implementeren nieuwe activiteitenbeschrijvingen, die bruikbaarder en consistenter zijn. Zoeken naar activiteiten wordt hierdoor niet beïnvloed.
- We hebben verbeterde gebruiker- en apparaat-identificatie opgenomen, zodat Cloud App Security apparaatgegevens kan verstrekken voor een groter aantal gebeurtenissen.
 
## <a name="cloud-app-security-release-87"></a>Cloud App Security-release 87
25 december 2016 uitgebracht

**Nieuwe functies**
-    We zijn bezig om [het anoniem maken van gegevens](cloud-discovery-anonymizer.md) uit te rollen, zodat u kunt profiteren van Cloud Discovery en tegelijkertijd de privacy van gebruikers kunt beveiligen. Het anoniem maken van gegevens wordt uitgevoerd door informatie over de gebruikersnaam te versleutelen.
-    We zijn bezig om de mogelijkheid uit te rollen waarbij een blokkeerscript van Cloud App Security naar meer apparaten wordt geëxporteerd. U kunt met het script eenvoudig schaduw-IT reduceren door verkeer naar niet-toegestane apps te blokkeren. Deze optie is nu beschikbaar voor: 
    -    BlueCoat ProxySG
    -    Cisco ASA
    -    Fortinet
    -    Juniper SRX
    -    Palo Alto
    -    Websense
-    Er is een nieuwe governance-actie voor bestanden toegevoegd waarmee u kunt afdwingen dat een bestand machtigingen van de bovenliggende map overneemt waarbij alle unieke machtigingen voor het bestand of de map worden verwijderd. Met deze governance-actie voor bestanden kunt u de machtigingen van uw bestand of map zo wijzigen dat deze worden overgenomen van de bovenliggende map. 
-    Er is een nieuwe gebruikersgroep toegevoegd met de naam Extern. Dit is een standaardgebruikersgroep die vooraf is geconfigureerd door Cloud App Security, voor alle gebruikers die geen deel uitmaken van uw interne domeinen. U kunt deze gebruikersgroep als een filter gebruiken. U kunt bijvoorbeeld activiteiten zoeken die worden uitgevoerd door externe gebruikers.
-    De functie Cloud Discovery ondersteunt nu Sophos Cyberoam-apparaten.
 
**Oplossingen voor problemen**
-    SharePoint Online- en OneDrive voor Bedrijven-bestanden worden in het rapport voor bestandsbeleid en op de pagina Bestanden als Intern in plaats van Privé weergegeven. Dit is opgelost.
 


## <a name="cloud-app-security-release-86"></a>Cloud App Security-release 86
13 december 2016 uitgebracht

**Nieuwe functies**
- Alle zelfstandige Cloud App Security-licenties bieden de mogelijkheid het scannen met Azure Information Protection in te schakelen vanuit de algemene instellingen (zonder dat een beleid hoeft worden gemaakt). 
 
**Verbeteringen**
- U kunt nu 'of' gebruiken in het bestandsfilter voor de bestandsnaam en in het filter voor het MIME-type voor bestanden en beleidsregels. Hierdoor zijn scenario's mogelijk zoals het invoeren van het woord 'passport' OF 'stuurprogramma' bij het maken van een beleid met PII. Het resultaat is alle bestanden die 'passport' of 'stuurprogramma' in de bestandsnaam hebben. 
- Wanneer een DLP-inhoudsinspectiebeleid wordt uitgevoerd, worden de gegevens in de resulterende schendingen standaard gemaskeerd. U kunt nu de laatste vier tekens van de schending zichtbaar maken. 

**Kleine verbeteringen**
- Nieuwe, aan postvakken gerelateerde Office 365 (Exchange)-gebeurtenissen die betrekking hebben op regels voor doorsturen en het toevoegen en verwijderen van postvakmachtigingen voor gemachtigden.
- Nieuwe gebeurtenis die het verlenen van toestemming aan nieuwe apps in Azure Active Directory controleert. 




## <a name="cloud-app-security-release-85"></a>Cloud App Security-release 85
Uitgebracht: 27 november 2016

**Nieuwe functies**
- Er is onderscheid gemaakt tussen goedgekeurde apps en verbonden apps. Goedkeuren en niet goedkeuren is nu een label dat kan worden toegepast op gedetecteerde apps en apps in de catalogus. Verbonden apps zijn apps die u hebt verbonden via de API-connector, voor meer zichtbaarheid en controle. U kunt apps nu labelen als goedgekeurd of niet-goedgekeurd of ze verbinden met de app-connector, indien beschikbaar. 
 
- Als onderdeel van deze wijziging is de pagina Goedgekeurde apps vervangen met een nieuw ontworpen pagina **Verbonden apps**, waarop statusgegevens over de connectors extern wordt weergegeven. 
 
- De logboekverzamelaars zijn gemakkelijker toegankelijk op hun eigen regel in het menu **Instellingen** onder **Bronnen**. 
- Bij het maken van een beleidsfilter voor activiteiten kunt u het aantal fout-positieven verminderen door herhaalde activiteiten te negeren wanneer die door dezelfde gebruiker worden uitgevoerd op hetzelfde doelobject. Daardoor wordt er bijvoorbeeld geen waarschuwing geactiveerd bij meerdere downloadpogingen voor hetzelfde bestand door dezelfde gebruiker. 
- Er zijn verbeteringen aangebracht in de activiteitslade. Wanneer u nu op een activiteitsobject in de activiteitslade klikt, kunt u inzoomen voor meer informatie.

**Verbeteringen**
- Er zijn verbeteringen aangebracht in de anomaliedetectie-engine, waaronder de waarschuwingen voor onmogelijke trajecten, waarvoor nu IP-informatie wordt gegeven in de beschrijving van de waarschuwing.
- Er zijn verbeteringen aangebracht in de complexe filters, waardoor hetzelfde filter nu meerdere malen kan worden toegevoegd om gefilterde resultaten nog verder te filteren. 
- Activiteiten met bestanden en mappen in Dropbox zijn nu gescheiden voor meer zichtbaarheid. 
  
**Oplossingen voor problemen**
- Er is een probleem opgelost in het mechanisme voor systeemwaarschuwingen dat leidde tot fout-positieven.

## <a name="cloud-app-security-release-84"></a>Cloud App Security-release 84
Uitgebracht: 13 november 2016

**Nieuwe functies**
-    Cloud App Security biedt nu ondersteuning voor Microsoft Azure Information Protection, met verbeterde integratie en automatische inrichting. U kunt uw bestanden filteren en bestandsbeleidsregels instellen met behulp van veilige classificaties van tags en vervolgens het classificatielabel instellen dat u wilt weergeven. Daarnaast geven de labels aan of de classificatie is ingesteld door iemand in uw organisatie of door personen van een andere tenant (extern). U kunt ook beleidsregels voor activiteiten instellen op basis van de Azure Information Protection-classificatielabels en automatisch scannen voor de classificatielabels in Office 365 inschakelen. Zie [Integratie van Azure Information Protection](azip-integration.md) voor meer informatie over hoe u kunt profiteren van deze geweldige nieuwe functie.
 
**Verbeteringen**
-    Er zijn verbeteringen aangebracht in het activiteitenlogboek van Cloud App Security: 
   -    Office 365-gebeurtenissen uit het beveiligings- en compliancecentrum zijn nu geïntegreerd met Cloud App Security en worden weergegeven in het **activiteitenlogboek**.
   -    Alle activiteiten van Cloud App Security worden in het activiteitenlogboek van Cloud App Security geregistreerd als beheeractiviteit.
-    Als hulp bij het onderzoeken van waarschuwingen met betrekking tot bestanden kunt u nu voor elke waarschuwing die het resultaat is van een bestandsbeleid de lijst met activiteiten weergegeven die voor het overeenkomende bestand zijn uitgevoerd.
-    Het algoritme voor onmogelijke trajecten in de anomaliedetectie-engine is verbeterd en biedt nu betere ondersteuning voor kleine tenants. 
 
**Kleine verbeteringen**
-    De **limiet voor het exporteren van activiteiten** is verhoogd naar 10.000. 
-    Bij het maken van een **momentopnamerapport** ontvangt u tijdens het handmatig uploaden van logboeken in Cloud Discovery nu een nauwkeurige schatting van hoe lang de logboekverwerking gaat duren. 
-    In een bestandsbeleid kunt u de beheeractie **Samenwerker verwijderen** nu gebruiken voor groepen.
-    Er zijn kleine verbeteringen aangebracht in de pagina **App-machtigingen**. 
-    Als meer dan 10.000 gebruikers machtigingen hadden voor een app die is verbonden met Office 365, werd de lijst langzaam geladen. Dit probleem is opgelost.
-    Er zijn aanvullende kenmerken toegevoegd aan de **app-catalogus** met betrekking tot PCI (Payment Card Industry).


## <a name="cloud-app-security-release-83"></a>Cloud App Security release 83
Uitgebracht: 30 oktober 2016

**Nieuwe functies**
-    Om het filteren in het [Activiteitenlogboek](activity-filters.md) en het [Bestandslogboek](file-filters.md) te vereenvoudigen, zijn vergelijkbare filters samengevoegd. U kunt gebruikmaken van de activiteitenfilters Activiteitobject, IP-adres en Gebruiker. Gebruik het filter Medewerkers om precies te vinden wat u zoekt.
-    Klik in de activiteitenlogboeklade onder **Bron** op de koppeling **Onbewerkte gegevens bekijken** om de onbewerkte gegevens die zijn gebruikt voor het genereren van het activiteitenlogboek te downloaden, zodat u verder kunt inzoomen op app-gebeurtenissen. 
-    Aanvullende ondersteuning voor extra aanmeldactiviteiten in Okta. [Afgeschermd voorbeeld]
-    Aanvullende ondersteuning voor extra aanmeldactiviteiten in Salesforce. 

**Verbeteringen**
-    Verbeterde bruikbaarheid van Cloud Discovery-momentopnamerapporten en het oplossen van problemen.
-    Verbeterde zichtbaarheid van waarschuwingen voor meerdere apps in de lijst met waarschuwingen.
-    Verbeterde functie voor het maken van doorlopende rapporten in Cloud Discovery.
-    Verbeterde bruikbaarheid van het Beheerlogboek.



## <a name="cloud-app-security-release-82"></a>Cloud App Security-release 82
Uitgebracht: 9 oktober 2016

**Verbeteringen**

- De activiteiten **E-mailadres wijzigen** en **Wachtwoord wijzigen** zijn nu onafhankelijk van de algemene activiteit **Gebruikers beheren** in Salesforce.
- Er is een uitleg toegevoegd voor de limiet voor het aantal waarschuwingen via sms per dag. Er worden maximaal tien berichten per telefoonnummer, per dag (UTC) verzonden.
- Er is een nieuw certificaat toegevoegd aan de Cloud Discovery-kenmerken voor Privacy Shield die Safe Harbor vervangen (alleen relevant voor leveranciers in de VS).
- Probleemoplossing is toegevoegd aan de foutberichten van API-connector zodat problemen eenvoudiger kunnen worden opgelost.
- Verbetering van de updatefrequentie van de app-scan van derden voor Office 365.
- Verbeteringen in het Cloud Discovery-dashboard.
- De Syslog-parser van het controlepunt is verbeterd.
- Verbeteringen in het beheerlogboek voor het uitsluiten van apps van derden en het ongedaan maken hiervan.
 
**Oplossingen voor problemen**
 
- Verbeterd proces voor het uploaden van een logo.
 
## <a name="cloud-app-security-release-81"></a>Cloud App Security-release 81
Uitgebracht: 18 september 2016

**Verbeteringen**
- Cloud App Security is nu een eigen app in Office 365. Vanaf nu kunt u met één klik een verbinding maken tussen Office 365 en Cloud App Security.

- Nieuw uiterlijk van het beheerlogboek: vanaf nu wordt hetzelfde overzichtelijke en handige uiterlijk als het activiteitenlogboek en de bestandstabel gebruikt. Gebruik de nieuwe filters om gemakkelijk te vinden wat u nodig hebt en uw beheeracties te controleren. 
- Er zijn verbeteringen aangebracht in de anomaliedetectie-engine voor meerdere mislukte aanmeldingspogingen en aanvullende risicofactoren.
- Er zijn verbeteringen aangebracht in de momentopnamerapporten van Cloud Discovery.
- Er zijn verbeteringen aangebracht in de beheeractiviteiten in het activiteitenlogboek; voor Wachtwoord wijzigen, Gebruiker bijwerken en Wachtwoord opnieuw instellen wordt nu aangeven of de activiteit is uitgevoerd als een beheeractiviteit.
- De waarschuwingsfilters voor systeemwaarschuwingen zijn verbeterd. 
- Het label voor een beleid in een waarschuwing bevat nu een koppeling terug naar het beleidsrapport.
- Als voor een Dropbox-bestand geen eigenaar is opgegeven, worden e-mailmeldingen naar de ingestelde ontvanger verzonden. 
- Cloud App Security biedt ondersteuning voor 24 extra talen, waardoor nu in totaal 41 talen worden ondersteund.  


## <a name="cloud-app-security-release-80"></a>Cloud App Security-release 80
Uitgebracht: 4 september 2016 

**Verbeteringen**
- Wanneer de DLP-scan mislukt, wordt nu een uitleg weergegeven waarom het bestand niet kan worden gescand met Cloud App Security. Zie [Inhoudsinspectie](https://aka.ms/aka.ms/cas-contentinspection) voor meer informatie.
- Er zijn verbeteringen aangebracht in de anomaliedetectie-engines, waaronder verbeteringen in waarschuwingen voor onmogelijke trajecten.
- Er zijn verbeteringen aangebracht in de ervaring voor het negeren van waarschuwingen. U kunt nu ook feedback toevoegen, zodat u het team van Cloud App Security kunt laten weten of en waarom de waarschuwing interessant was zodat uw feedback kan worden gebruikt om de detecties van Cloud App Security te verbeteren.
- De Cloud Discovery-parsers voor Cisco ASA zijn verbeterd.
- U ontvangt nu een e-mailmelding wanneer het handmatig uploaden van uw Cloud Discovery-logboek is voltooid.
   



## <a name="cloud-app-security-release-79"></a>Cloud App Security-release 79
Uitgebracht: 21 augustus 2016 

**Nieuwe functies**

- **Nieuw Cloud Discovery-dashboard**  
Er is nu een volledig nieuw Cloud Discovery-dashboard beschikbaar, waarmee u meer inzicht hebt in de manier waarop cloud-apps in uw organisatie worden gebruikt. Met het dashboard kunt u in één oogopslag een overzicht bekijken van de apps die worden gebruikt, uw openstaande waarschuwingen en de risiconiveaus van de apps in uw organisatie. Daarnaast kunt u zien wie de belangrijkste gebruikers in uw organisatie zijn en wordt een app-hoofdkantoorkaart weergegeven.
Het nieuwe dashboard heeft meer opties voor het filteren van gegevens, zodat u specifieke weergaven kunt genereren (afhankelijk van de gegevens die het interessantst zijn voor u), en eenvoudig te begrijpen afbeeldingen zodat u in één oogopslag een volledig beeld krijgt.

- **Nieuwe Cloud Discovery-rapporten** Als u de resultaten van Cloud Discovery wilt weergeven, kunt u nu twee typen rapporten genereren: momentopnamerapporten en doorlopende rapporten.
Met momentopnamerapporten hebt u ad-hoczichtbaarheid in een set met verkeerslogboeken die u handmatig kunt uploaden vanuit uw firewalls en proxy's. In doorlopende rapporten worden de resultaten weergegeven van alle logboeken die vanuit uw netwerk worden doorgestuurd met behulp van de logboekverzamelaars van Cloud App Security. Deze nieuwe rapporten bieden verbeterde zichtbaarheid van alle gegevens, automatische identificatie van afwijkend gebruik zoals geïdentificeerd door de Machine Learning-anomaliedetectie-engine van Cloud App Security en identificatie van afwijkend gebruik zoals gedefinieerd door u met behulp van de krachtige en gedetailleerde beleidsengine. Zie het Engelstalige artikel [Set up Cloud Discovery](set-up-cloud-discovery.md) (Cloud Discovery instellen) voor meer informatie.
 
**Verbeteringen**
- Algemene verbeteringen in de bruikbaarheid van de volgende pagina's: beleidspagina's, Algemene instellingen, E‑mailinstellingen.
- In de tabel Waarschuwingen kunt u nu gemakkelijker onderscheid maken tussen de gelezen en ongelezen waarschuwingen. Links van gelezen waarschuwingen wordt een blauwe lijn weergegeven en ze zijn lichter gekleurd om aan te geven dat u ze al hebt gelezen.
- De parameters voor **herhaalde activiteiten** van het activiteitenbeleid zijn bijgewerkt. 
- Aan de pagina Accounts is de kolom **Type** voor gebruikers toegevoegd, zodat u kunt zien welk type gebruikersaccount elke gebruiker heeft. De gebruikerstypen zijn app-specifiek. 
- Near realtime-ondersteuning is toegevoegd voor bestandsgerelateerde activiteiten in OneDrive en SharePoint. Wanneer een bestand wordt gewijzigd, wordt in Cloud App Security vrijwel direct een scan gestart.


## <a name="cloud-app-security-release-78"></a>Cloud App Security-release 78
Uitgebracht: 7 augustus 2016

**Verbeteringen**
- Vanuit een bestand kunt u nu met de rechtermuisknop klikken en **verwante items zoeken**. In het activiteitenlogboek kunt u gebruikmaken van het filter Doelobject en vervolgens het gewenste bestand selecteren.

- Verbeterde parsers voor Cloud Discovery-logboekbestanden, met onder ander de toevoeging van Juniper en Cisco ASA.
- Met Cloud App Security kunt u tijdens het negeren van waarschuwingen feedback geven over de verbeterde waarschuwingen. U kunt de kwaliteit van de waarschuwingsfunctie in Cloud App Security helpen verbeteren door te laten weten waarom u de waarschuwing negeert, bijvoorbeeld omdat deze niet interessant is, omdat u te veel vergelijkbare waarschuwingen hebt ontvangen, omdat de werkelijke urgentie van de waarschuwing lager moet zijn of omdat de waarschuwing niet juist is.
- In de weergave Bestandsbeleid, of wanneer u een bestand bekijkt, kunt u tijdens het openen van de bestandslade gebruikmaken van een nieuwe koppeling naar overeenkomende beleidsregels. Wanneer u op de koppeling klikt, kunt u alle overeenkomsten weergegeven en kunt u nu alle overeenkomsten negeren. 
- De organisatie-eenheid waartoe een gebruiker behoort, wordt nu aan alle relevante waarschuwingen toegevoegd.
- Er wordt een e-mailmelding verzonden zodat u weet wanneer de verwerking van uw handmatig geüploade logboeken is voltooid.


## <a name="cloud-app-security-release-77"></a>Cloud App Security-release 77
Uitgebracht: 24 juli 2016

**Verbeteringen**
- De bruikbaarheid van het pictogram voor de knop Exporteren van Cloud Discovery is verbeterd.
- Tijdens het onderzoeken van een activiteit kunt u nu de onbewerkte gegevens weergeven als de gebruikersagent niet is geparseerd.
- Er zijn twee nieuwe risicofactoren aan de anomaliedetectie-engine toegevoegd: 
    - In Cloud App Security wordt nu voor de berekening van risico's gebruikgemaakt van de IP-adrestags die aan een botnet zijn gekoppeld en van anonieme IP-adressen. 
    - Office 365-activiteiten worden nu gecontroleerd op hoge downloadsnelheden. Als de downloadsnelheid van Office 365 veel hoger is dan de normale downloadsnelheid van uw organisatie of van een specifieke gebruiker, wordt een anomaliedetectiewaarschuwing geactiveerd. 
- Cloud App Security is nu compatibel met de nieuwe Dropbox-API voor de [functionaliteit voor beveiligd delen](https://blogs.dropbox.com/dropbox/2016/06/new-dropbox-productivity-tools/). 
- Er zijn verbeteringen aangebracht met betrekking tot het toevoegen van details aan parseerfouten in het detectielogboek, waaronder: Geen cloudgerelateerde transacties, Alle gebeurtenissen zijn verouderd, Beschadigd bestand en Logboekindeling komt niet overeen.
- Het datumfilter voor het activiteitenlogboek is verbeterd en bevat nu de mogelijkheid op tijd te filteren.
- De bruikbaarheid van de pagina IP-adresbereiken is verbeterd.
- Cloud App Security biedt nu ondersteuning voor Microsoft Azure Information Protection (preview-versie). U kunt uw bestanden filteren en bestandsbeleidsregels instellen met behulp van veilige classificaties van tags en vervolgens het niveau van het classificatielabel instellen dat u wilt weergeven. Daarnaast geven de labels aan of de classificatie is ingesteld door iemand in uw organisatie of door personen van een andere tenant (extern). 



## <a name="cloud-app-security-release-76"></a>Cloud App Security-release 76
Uitgebracht: 10 juli 2016

**Verbeteringen**

- De lijst met gebruikers in de ingebouwde rapporten kan nu worden geëxporteerd.
- Het beleid voor samengestelde activiteiten is nu beter bruikbaar.
- Verbeterde ondersteuning voor de parser voor TMG W3C-firewalllogboekberichten.
- Bruikbaarheid van de vervolgkeuzelijst voor de bestandsbeheeracties is verbeterd en onderverdeeld in acties voor samenwerking, beveiliging en onderzoek.
- Verbeterde detectie van onmogelijke trajecten voor Exchange Online-activiteit voor het verzenden van e-mail.
- Er is een nieuwe lijst met titels (breadcrumbs) aan de bovenkant van de pagina's Waarschuwingen en Beleid toegevoegd voor eenvoudigere navigatie.

**Oplossingen voor problemen**
- De vooraf ingestelde expressie voor Creditcard in DLP-instellingen voor bestandbeleidsregels is gewijzigd in Alle: Financieel: Creditcard.


## <a name="cloud-app-security-release-75"></a>Cloud App Security-release 75
Uitgebracht: 27 juni 2016


**Nieuwe functies**
* Nieuwe toevoegingen aan onze groeiende lijst met ondersteunde Salesforce-gebeurtenissen, met inbegrip van gebeurtenissen die inzicht bieden in rapporten, gedeelde koppelingen, inhoudsdistributie, geïmiteerde aanmelding en meer.
* De pictogrammen van verbonden apps in het Cloud App Security-dashboard sluiten aan bij de status van de apps zoals weergegeven in het dashboard om de afgelopen 30 dagen te laten zien.
* Ondersteuning voor schermen met volledige breedte.


**Oplossingen voor problemen**
* Telefoonnummers voor waarschuwingen via sms worden nu gecontroleerd bij het invoegen.

## <a name="cloud-app-security-release-74"></a>Cloud App Security-release 74
Uitgebracht: 13 mei 2016
* Het scherm Waarschuwing is bijgewerkt zodat u in een oogopslag meer informatie kunt bekijken. Zo kunt u nu alle gebruikersactiviteiten in een oogopslag zien: een toewijzing van activiteiten, gerelateerde gebruikersbeheerlogboeken, een beschrijving van de reden waarvoor de waarschuwing geactiveerd is, en extra grafieken en toewijzingen van de gebruikerspagina. 
* Gebeurtenissen die worden gegenereerd door de Cloud App Security omvatten nu het gebeurtenistype, de indeling, het beleid, de groepen, de verwante objecten en een beschrijving.
* Nieuwe IP-adreslabels zijn toegevoegd voor Office 365 ProPlus, OneNote, Office Online en Exchange Online Protection.
* U hebt nu de mogelijkheid om logboeken van het hoofdmenu Detectie te uploaden.
* Het categoriefilter voor het IP-adres is verbeterd. De IP-adrescategorie Null is nu Niet-gecategoriseerd genoemd en een nieuwe categorie met de naam Geen waarde is toegevoegd om alle activiteiten die geen IP-adresgegevens hebben te omvatten.
* Beveiligingsgroepen in de Cloud App Security heten voortaan gebruikersgroepen om verwarring met Active Directory-beveiligingsgroepen te voorkomen.
* Het is nu mogelijk om te filteren op IP-adres en gebeurtenissen zonder een IP-adres weg te filteren. 
* Er zijn wijzigingen aangebracht in de instellingen voor verzonden meldingsberichten wanneer overeenkomsten worden gedetecteerd in de beleidsregels voor activiteiten en bestanden. U kunt nu e-mailadressen toevoegen voor geadresseerden die u via CC de melding ook wilt toesturen.


## <a name="cloud-app-security-release-73"></a>Cloud App Security-release 73
Uitgebracht: 29 mei 2016

* Bijgewerkte waarschuwingsmogelijkheden: u kunt nu per beleid waarschuwingen instellen die moeten worden verzonden via e-mail of als een SMS-bericht.
* De pagina Waarschuwingen: verbeterd ontwerp voor beter uitvoering van geavanceerde opties voor oplossingen en incidentmanagement.
* Aangepast beleid: waarschuwingen stellen u nu in staat om rechtstreeks vanuit de opties voor oplossingen van waarschuwingen naar de pagina met beleidsinstellingen te gaan om deze gemakkelijker aan te passen op basis van de waarschuwingen.
* Verbeteringen in de berekening van de risicoscore van de anomaliedetectie en een verminderd aantal fout-positieven op basis van feedback van klanten.
* Geëxporteerde activiteitenlogboeken bevatten nu informatie over de gebeurtenis-id, de gebeurteniscategorie en de typenaam voor de gebeurtenis.
* Verbeterde vormgeving en bruikbaarheid van beheeracties voor het maken van beleidsregels.
* Vereenvoudigd onderzoek en beheer voor Office 365: bij selectie van Office 365 worden automatisch alle apps geselecteerd die deel uitmaken van het Office 365-pakket.
* Meldingen worden nu verzonden naar het e-mailadres dat is geconfigureerd in de verbonden app. 
* Bij verbindingsfouten wordt nu een gedetailleerde beschrijving van de fout verstrekt door de cloud-app.
* Wanneer een bestand overeenkomt met een beleid, is er nu een URL voor toegang tot het bestand beschikbaar in de bestandslade.
* Wanneer een waarschuwing wordt geactiveerd door een activiteitenbeleid of een anomaliedetectiebeleid, wordt er een nieuwe gedetailleerde melding verzonden met informatie over de overeenkomst. 
* Er wordt automatisch een systeemwaarschuwing geactiveerd wanneer de verbinding met een app-connector is verbroken.
* U kunt nu één waarschuwing of een selectie waarschuwingen sluiten en oplossen vanaf de pagina Waarschuwingen.

## <a name="cloud-app-security-release-72"></a>Cloud App Security-release 72
Uitgebracht: 15 mei 2016

*  Algemene verbeteringen aan de vormgeving en infrastructuur, waaronder:
    * Nieuw diagram voor meer assistentie bij het handmatig uploaden van Cloud Discovery-logboeken.
    * Verbeterd proces voor het bijwerken van niet-herkende logboekbestanden (Overig), met een pop-upvenster waarin wordt aangegeven dat het bestand moet worden gecontroleerd. U ontvangt een melding wanneer de gegevens beschikbaar zijn.
    * Er worden meer overtredingen van de beleidsregels voor activiteiten en bestanden gemarkeerd bij het onderzoeken van activiteiten- en bestandslogboeken voor verouderde browsers en besturingssystemen.
* Verbeterde parsers voor Cloud Discovery-logboekbestanden, met onder ander de toevoeging van Cisco ASA, Cisco FWSM, Cisco Meraki en W3C.
* Oplossingen voor bekende problemen met Cloud Discovery.
* Nieuwe activiteitenfilters toegevoegd voor het domein en de interne of externe relatie van de eigenaar.
* Er is een nieuw filter toegevoegd dat het mogelijk maakt om te zoeken naar Office 365-objecten (bestanden, mappen en URL's).
* De mogelijkheid om een minimale risicoscore te configureren voor beleidsregels voor anomaliedetectie is toegevoegd.
* Als u instelt dat er een waarschuwing moet worden verzonden wanneer een beleid wordt geschonden, kunt u een minimale waarde voor de ernst van de waarschuwing instellen waarbij u wilt worden gewaarschuwd. U kunt ervoor kiezen om de standaardinstelling van uw organisatie hiervoor te gebruiken en u kunt een specifieke waarschuwingsinstelling als standaard instellen voor uw organisatie.

## <a name="see-also"></a>Zie ook  
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  