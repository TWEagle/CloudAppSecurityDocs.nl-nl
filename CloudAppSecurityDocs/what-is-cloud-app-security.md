---
title: Wat is Cloud App Security? | Microsoft Docs
description: In dit onderwerp vindt u informatie over wat Cloud App Security is en hoe het werkt.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: d46756b1-7dd8-4190-9799-3a97688f1266
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 2cb87afa3c5342e01cfd4049669ac4b3b7efa4fe
ms.openlocfilehash: c6df59d7c5ced9dc378463bc5bef411259294c47


---
# <a name="what-is-cloud-app-security"></a>Wat is Cloud App Security?
 
> [!NOTE] 
> Zie het Engelstalige artikel [Advanced Security Management](https://support.office.com/article/Get-started-with-Advanced-Management-Security-d9ee4d67-f2b3-42b4-9c9e-c4529904990a) voor informatie over de mogelijkheden van Advanced Security Management - Cloud App Security in Office 365. 
 
Hoewel overstappen naar de cloud voor meer flexibiliteit voor werknemers en lagere IT-kosten heeft gezorgd, heeft het ook nieuwe complexiteit en uitdagingen geïntroduceerd voor het beveiligen van uw organisatie. Om het volledige voordeel van cloud-toepassingen te krijgen, moeten IT-teams de juiste balans vinden in het mogelijk maken van toegang terwijl controle wordt behouden om kritieke gegevens te beschermen.  
  
Cloud App Security is een essentieel onderdeel van de Microsoft Cloud Security-stack. Het is een uitgebreide oplossing die organisaties helpt te profiteren van de belofte van cloud-toepassingen terwijl controle wordt behouden met verbeterde zichtbaarheid in de activiteit. Het verhoogt ook de beveiliging van essentiële gegevens in cloud-toepassingen. Met hulpprogramma’s om schaduw-IT te onthullen, risico’s te beoordelen, beleid af te dwingen, activiteiten te onderzoeken en bedreigingen te stoppen, kunnen organisaties veilig overstappen naar de cloudbeheer over essentiële gegevens wordt behouden.  
  
## <a name="the-cloud-app-security-framework"></a>Het Cloud App Security-framework  

|       |   |   |
|-------|---|:---|
|![Ontdekken](./media/discovery-icon.png)|Ontdekken|Onthul Shadow IT met Cloud App Security. Krijg meer inzicht door apps, activiteiten, gebruikers, gegevens en bestanden in uw cloudomgeving te detecteren, evenals apps van derden die zijn verbonden met uw cloud.|
|![Onderzoeken](./media/investigate-icon.png)|Onderzoeken|Onderzoek uw cloud-apps met forensische hulpprogramma's voor de cloud om riskante apps, specifieke gebruikers en bestanden in uw netwerk diepgaand te onderzoeken en om patronen te vinden in de verzamelde gegevens van uw cloud en rapporten te genereren om uw cloud te controleren.|
|![Beheer](./media/protect-icon.png)|Beheer|Beperk risico’s door beleidsregels en waarschuwingen in te stellen om maximale controle over het netwerkverkeer in de cloud te behalen. Gebruik Cloud App Security om uw gebruikers te migreren naar veilige, goedgekeurde alternatieven voor de cloud-app.|
|![Beschermen](./media/protect-icon.png)|Beschermen|Gebruik Cloud App Security om toepassingen goed te keuren/de goedkeuring in te trekken, voorkomen van gegevensverlies (DLP) af te dwingen, machtigingen en delen te beheren en aangepaste rapporten en waarschuwingen te genereren.|


## <a name="architecture"></a>Architectuur  

Cloud App Security maakt de integratie van zichtbaarheid in uw cloud mogelijk op de volgende manieren:  
  
-   Zichtbaarheid door Cloud Discovery te gebruiken om uw cloudomgeving en de cloud-apps die u gebruikt te identificeren en toe te wijzen.  
-   De mogelijkheid om apps in uw cloud goed te keuren en de goedkeuring in te trekken.  
-   Zichtbaarheid op en beheer van apps waarmee u verbinding maakt via onze eenvoudig te implementeren app-connectors die gebruikmaken van API's van providers.  
-   Doorlopend controle doordat u beleidsregels kunt instellen en aanpassen.  
  
![](./media/architecture.png)  
  
> [!NOTE]  
>  Wanneer Cloud App Security inhoudsinspectie uitvoert, wordt gegevensprivacy afgedwongen. Uw gegevens worden niet opgeslagen in de Cloud App Security-database, alleen de metagegevens van de bestandsrecords en de schendingen die zijn geïdentificeerd. Zie ons [privacybeleid](http://go.microsoft.com/fwlink/?LinkId=512132) en het [Vertrouwenscentrum van Microsoft](https://www.microsoft.com/TrustCenter/Privacy/You-are-in-control-of-your-data) voor meer informatie over het bewaren van gegevens.
In Cloud App Security worden gegevens als volgt bewaard:
>- Activiteitenlogboek: 180 dagen
>- Detectiegegevens: 90 dagen
>- Waarschuwingen: onbeperkt 

Nadat de gegevens van deze bronnen zijn verzameld, voert Cloud App Security geavanceerde analyses uit, wordt u gewaarschuwd voor afwijkende activiteiten en kunt u diep inzicht krijgen. Vervolgens kunt u een beleid configureren in Cloud App Security en dit vervolgens gebruiken om alles in uw cloudomgeving te beveiligen.  
  
###  <a name="how-cloud-discovery-works"></a>Hoe Cloud Discovery werkt  

Cloud Discovery gebruikt uw verkeerslogboeken om op een dynamische manier te ontdekken en analyseren welke cloud-apps worden gebruikt in uw organisatie.  
  
U kunt een momentopnamerapport van het cloudgebruik in uw organisatie maken door handmatig logboekbestanden vanuit uw firewalls of proxy's te uploaden, of u kunt doorlopende rapporten instellen door de logboekverzamelaars van Cloud App Security te gebruiken om uw logboeken op regelmatige basis door te sturen.  

Zie het Engelstalige artikel [Set up Cloud Discovery](set-up-cloud-discovery.md) (Cloud Discovery instellen) voor meer informatie over Cloud Discovery.
  
### <a name="how-sanctioning-and-unsanctioning-an-app-works"></a>Hoe werkt goedkeuren van apps en de goedkeuring ervan intrekken?  

Met Cloud App Security kunt u apps goedkeuren/goedkeuring intrekken in uw organisatie met behulp van de **catalogus met cloud-apps**.  
  
Het Microsoft-team van analisten heeft een uitgebreide en voortdurend groeiende catalogus van meer dan 13.000 cloud-apps die worden beoordeeld en gewaardeerd op basis van industrienormen. De **cloud-appcatalogus** classificeert risico’s voor uw cloud-apps op basis van regelgevingscertificeringen, industrienormen en best practices. U kunt vervolgens de scores en het gewicht van de verschillende parameters aanpassen aan de behoeften van uw organisatie. Op basis van deze scores laat Cloud App Security u weten hoe riskant de app is volgens meer dan 50 risicofactoren die van invloed zijn op uw omgeving.  
  
### <a name="how-app-connectors-work"></a>Hoe werken app-connectors?  
App-connectors maken gebruik van API's die worden geleverd door verschillende cloud-app-providers om de Cloud App Security-cloud in staat te stellen te integreren met andere cloud-apps en beheer en beveiliging uit te breiden. Hierdoor kan Cloud App Security informatie rechtstreeks uit de cloud-apps halen voor analyse.  
Om een app te verbinden en beveiliging uit te breiden, machtigt de app-beheerder Cloud App Security voor toegang tot de app en vraagt Cloud App Security de app vervolgens om activiteitenlogboeken, scant gegevens, accounts en cloudinhoud. Cloud App Security kan vervolgens beleidsregels afdwingen, bedreigingen detecteren en gegevensbeheeracties bieden voor het oplossen van problemen.  
  
Cloud App Security maakt gebruik van de API's die door de cloudprovider worden verstrekt; elke app heeft een eigen framework en API-beperkingen. Cloud App Security gebruikt de app-providers om het gebruik van de API's te optimaliseren en om de beste prestaties te leveren. Rekening houdend met de verschillende beperkingen die de apps opleggen aan de API's (zoals beperking, API-limieten, dynamisch verschuiven van API-tijdsvensters, enzovoort), maken de Cloud App Security-engines gebruik van de toegestane capaciteit. Bepaalde bewerkingen, zoals het scannen van alle bestanden in de tenant vereisen een grote hoeveelheid API's en worden daarom verdeeld over een langere periode. Ga ervan uit dat sommige beleidsregels gedurende enkele uren tot dagen worden uitgevoerd.  
  
### <a name="how-policy-control-works"></a>Hoe beheer van beleidsregels werkt  

Met beleidsregels kunt u de manier vastleggen waarop u wilt dat uw gebruikers zich gedragen in de cloud. Beleidsregels helpen u risicovol gedrag, schendingen of verdachte datapunten en -activiteiten binnen uw cloudomgeving te detecteren en, indien vereist, herstelprocessen te integreren om een optimale risicobeperking te behalen. Er zijn meerdere typen beleidsregels die samenhangen met de verschillende typen gegevens die u wilt verzamelen over uw cloudomgeving en de soorten herstelacties die u zou willen ondernemen.  
  
## <a name="see-also"></a>Zie ook  

[Aan de slag met Cloud App Security](getting-started-with-cloud-app-security.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO5-->


