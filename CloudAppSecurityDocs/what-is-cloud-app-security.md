---
title: Wat is Cloud App Security? | Microsoft Docs
description: In dit onderwerp wordt Cloud App Security en de werking ervan beschreven.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/23/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: d46756b1-7dd8-4190-9799-3a97688f1266
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 480a94edbb36cc421b5ff64ea29268f0041326bc
ms.openlocfilehash: dfc9ec25d2c7822d9239685375136c1dc0d1a3bc


---
# <a name="what-is-cloud-app-security"></a>Wat is Cloud App Security?

> [!NOTE]
> Zie het Engelstalige artikel [Advanced Security Management](https://support.office.com/article/Get-started-with-Advanced-Management-Security-d9ee4d67-f2b3-42b4-9c9e-c4529904990a) voor informatie over Advanced Security Management en Cloud App Security voor Office 365.

Hoewel overstappen naar de cloud voor meer flexibiliteit voor werknemers en lagere IT-kosten zorgt, introduceert het ook nieuwe uitdagingen en complexiteit voor het beveiligen van uw organisatie. Om volledig te kunnen profiteren van cloudtoepassingen, moeten IT-teams de juiste balans vinden tussen het ondersteunen van toegang en het houden van controle om kritieke gegevens te beschermen.  

Cloud App Security is een essentieel onderdeel van de Microsoft Cloud Security-stack. Het is een uitgebreide oplossing die uw organisatie kan helpen te profiteren van de belofte van cloudtoepassingen terwijl u de controle houdt met verbeterde zichtbaarheid in de activiteit. Het verhoogt ook de beveiliging van essentiële gegevens in cloudtoepassingen. Met hulpprogramma's om schaduw-IT te onthullen, risico's te beoordelen, beleid af te dwingen, activiteiten te onderzoeken en bedreigingen te stoppen, kan uw organisatie veiliger overstappen naar de cloud terwijl de controle over essentiële gegevens wordt behouden.  

## <a name="the-cloud-app-security-framework"></a>Het Cloud App Security-framework  

|       |   |   |
|-------|---|:---|
|![Ontdekken](./media/discovery-icon.png)|Ontdekken|Onthul Shadow IT met Cloud App Security. Krijg meer inzicht door apps, activiteiten, gebruikers, gegevens en bestanden in uw cloudomgeving te detecteren. Detecteer apps van derden die zijn verbonden met uw cloud.|
|![Onderzoeken](./media/investigate-icon.png)|Onderzoeken|Onderzoek uw cloud-apps met forensische hulpprogramma's voor de cloud om riskante apps, specifieke gebruikers en bestanden in uw netwerk diepgaand te onderzoeken. Vind patronen in de gegevens die vanuit de cloud worden verzameld. U kunt rapporten genereren om uw cloud te bewaken.|
|![Beheer](./media/control-icon.png)|Beheer|Beperk risico's door beleidsregels en waarschuwingen in te stellen om maximale controle over het netwerkverkeer in de cloud te behalen. Gebruik Cloud App Security om uw gebruikers te migreren naar veilige, goedgekeurde alternatieven voor de cloud-app.|
|![Beschermen](./media/protect-icon.png)|Beschermen|Gebruik Cloud App Security om toepassingen goed te keuren of de goedkeuring in te trekken, voorkomen van gegevensverlies af te dwingen, machtigingen en delen te beheren en aangepaste rapporten en waarschuwingen te genereren.|


## <a name="architecture"></a>Architectuur  

Met Cloud App Security wordt zichtbaarheid met uw cloud geïntegreerd door:  

-   Cloud Discovery te gebruiken om uw cloudomgeving en de cloud-apps die uw organisatie gebruikt te identificeren en toe te wijzen.
-   Apps in de cloud goed te keuren en de goedkeuring ervan in te trekken.  
-   Gebruik te maken van eenvoudig te implementeren app-connectors die gebruikmaken van API's van providers voor zichtbaarheid op en beheer van apps waarmee u verbinding maakt.  
-   U te helpen doorlopend controle te hebben doordat u beleidsregels kunt instellen en aanpassen.  

![Architectuur van Cloud App Security](./media/architecture.png)  

> [!NOTE]  
> Wanneer Cloud App Security inhoudsinspectie uitvoert, wordt gegevensprivacy afgedwongen. Uw gegevens worden niet opgeslagen in de Cloud App Security-database; alleen de metagegevens van de bestandsrecords en eventuele schendingen die zijn gedetecteerd, worden opgeslagen in de Cloud App Security-database. Lees het [privacybeleid](http://go.microsoft.com/fwlink/?LinkId=512132) of ga naar het [Vertrouwenscentrum van Microsoft Trust](https://www.microsoft.com/TrustCenter/Privacy/You-are-in-control-of-your-data) voor meer informatie over gegevensretentie.
In Cloud App Security worden gegevens als volgt bewaard:
>- Activiteitenlogboek: 180 dagen
>- Detectiegegevens: 90 dagen
>- Waarschuwingen: 180 dagen

Nadat gegevens uit deze bronnen zijn verzameld, voert Cloud App Security een geavanceerde analyse uit op de gegevens. U wordt direct op de hoogte gesteld van afwijkende activiteiten en u krijgt meer inzicht in uw cloudomgeving. U kunt een beleid configureren in Cloud App Security en dit vervolgens gebruiken om alles in uw cloudomgeving te beveiligen.  

### <a name="cloud-discovery"></a>Cloud Discovery  

Cloud Discovery gebruikt uw verkeerslogboeken om op een dynamische manier te ontdekken en analyseren welke cloud-apps worden gebruikt in uw organisatie. Als u een momentopnamerapport wilt maken van het cloudgebruik van uw organisatie, kunt u handmatig logboekbestanden van uw firewalls of proxy's uploaden voor analyse. Als u doorlopende rapporten wilt instellen, gebruikt u Cloud App Security-logboekverzamelaars om uw logboeken periodiek door te sturen.  

Zie het Engelstalige artikel [Set up Cloud Discovery](set-up-cloud-discovery.md) (Cloud Discovery instellen) voor meer informatie over Cloud Discovery.

### <a name="sanctioning-and-unsanctioning-an-app"></a>Apps goedkeuren en de goedkeuring van apps intrekken  

U kunt Cloud App Security gebruiken om apps goed te keuren of de goedkeuring ervan in te trekken in uw organisatie met behulp van de *catalogus met cloud-apps*. Het Microsoft-team van analisten heeft een uitgebreide en voortdurend groeiende catalogus van meer dan 13.000 cloud-apps die worden beoordeeld en gewaardeerd op basis van industrienormen. U kunt de cloud-app-catalogus gebruiken om het risico voor uw cloud-apps te classificeren op basis van regelgevingscertificeringen, industrienormen en best practices. U kunt vervolgens de scores en het gewicht van de verschillende parameters aanpassen aan de behoeften van uw organisatie. Op basis van deze scores laat Cloud App Security u weten hoe riskant de app is volgens meer dan 50 risicofactoren die van invloed zijn op uw omgeving.  

### <a name="app-connectors"></a>App-connectors  
App-connectors maken gebruik van API's van cloud-app-providers voor de integratie van Cloud App Security en andere cloud-apps. Met app-connectors worden controle en beveiliging uitgebreid. Daarnaast kunt u met app-connectors rechtstreeks vanuit cloud-apps toegang krijgen tot gegevens voor Cloud App Security-analyses.  

Als u een app wilt koppelen en de beveiliging wilt uitbreiden, autoriseert de app-beheerder Cloud App Security voor toegang tot de app. Vervolgens voert Cloud App Security in de app een query uit op de activiteitenlogboeken en worden de gegevens, accounts en cloudinhoud gescand. Cloud App Security kan beleidsregels afdwingen, bedreigingen detecteren en beheeracties bieden voor het oplossen van problemen.  

Cloud App Security maakt gebruik van de API's die door de cloudprovider worden verstrekt. Elke app heeft een eigen framework en API-beperkingen. Cloud App Security gebruikt de app-providers om het gebruik van API's te optimaliseren en om de beste prestaties te leveren. Rekening houdend met de verschillende beperkingen die de apps opleggen aan de API's (zoals beperking, API-limieten, dynamisch verschuiven van API-tijdsvensters, enzovoort), maken de Cloud App Security-engines gebruik van de toegestane capaciteit. Bepaalde bewerkingen, zoals het scannen van alle bestanden in de tenant, vereisen een grote hoeveelheid API's en worden daarom verdeeld over een langere periode. Ga ervan uit dat sommige beleidsregels gedurende enkele uren tot dagen worden uitgevoerd.  

### <a name="policy-control"></a>Beleidsbeheer  

U kunt beleidsregels gebruiken om het gedrag van uw gebruikers in de cloud te definiëren. Gebruik beleidsregels om riskant gedrag, schendingen of verdachte gegevenspunten en activiteiten in uw cloudomgeving te detecteren. Indien nodig kunt u beleidsregels gebruiken voor het integreren van herstelprocessen om alle risico's te beperken. Verschillende typen beleidsregels hangen samen met de verschillende typen gegevens die u wilt verzamelen over uw cloudomgeving en de soorten herstelacties die u zou willen uitvoeren.  

## <a name="see-also"></a>Zie ook  

Zie [Aan de slag met Cloud App Security](getting-started-with-cloud-app-security.md) voor meer informatie over de basisprincipes.    
Ga naar de [ondersteuningspagina van Cloud App Security](http://support.microsoft.com/oas/default.aspx?prid=16031) voor technische ondersteuning.   
Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit [Premier Portal](https://premier.microsoft.com/) kiezen.   



<!--HONumber=Nov16_HO5-->


