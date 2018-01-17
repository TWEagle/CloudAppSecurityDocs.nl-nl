---
title: Risicovolle cloud-apps en verdachte activiteiten onderzoeken met Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u een overzicht van het proces voor het onderzoeken van waarschuwingen, problemen en verdachte activiteiten met Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a9b00c2a-2f71-499e-8f57-67e560daedc1
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: e0d61fcd3147b25b84c7e5071ba8e7a02bc05f67
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2018
---
# <a name="investigate"></a>Onderzoeken
Nadat Cloud App Security wordt uitgevoerd in uw cloudomgeving, hebt u eerst een fase nodig waarin u leert en onderzoekt hoe u de hulpprogramma's van Cloud App Security kunt gebruiken om meer inzicht te krijgen in wat er in uw cloudomgeving gebeurt. Vervolgens kunt u op basis van uw specifieke omgeving en hoe deze wordt gebruikt bepalen welke vereisten nodig zijn om uw organisatie te beschermen tegen risico's.

In dit onderwerp wordt beschreven hoe u een onderzoek uitvoert om een beter inzicht te krijgen in wat er in uw cloudomgeving gebeurt.  

## <a name="dashboards"></a>Dashboards  
De volgende dashboards kunnen u helpen bij het onderzoeken van apps in uw cloudomgeving:  

|Dashboard|Description|  
|---------------|-----------------|  
|Hoofddashboard|Overzicht van cloudstatus (gebruikers, bestanden, activiteiten) en de vereiste acties (waarschuwingen, schendingen van activiteiten en schendingen van inhoud)|  
|Toepassingsdashboard: algemeen|Overzicht van het gebruik van toepassingen per locatie, gebruiksgrafieken per aantal gebruikers|  
|Toepassingsdashboard: inzichten|Analyse van gegevens die zijn opgeslagen in de app, onderverdeeld op basis van het bestandstype en het niveau van bestandsdeling|  
|Toepassingsdashboard: bestanden|Inzoomen op bestanden, de mogelijkheid te filteren op basis van eigenaar, niveau van delen, enzovoort, alsmede het uitvoeren van beheeracties (zoals quarantaine)|  
|Toepassingsdashboard: apps van derden|Inzoomen op apps van derden die momenteel zijn geïmplementeerd, zoals G Suite, en het beleid voor deze apps definiëren|  
|Gebruikersdashboard|Een volledig overzicht van het gebruikersprofiel in de cloud met inbegrip van groepen, locaties, recente activiteiten, gerelateerde waarschuwingen en gebruikte browsers|  

##  <a name="sanctionapp"></a> Apps labelen als goedgekeurd of niet-goedgekeurd  
Een belangrijke stap voor het krijgen van inzicht in uw cloud, is het labelen van apps als goedgekeurd of niet-goedgekeurd. Nadat u een app hebt goedgekeurd, kunt u filteren op apps die niet zijn goedgekeurd en migratie naar goedgekeurde apps van hetzelfde type initiëren.  

-   Ga in de Cloud App Security-console naar de app-catalogus of gedetecteerde apps.  

-   In de lijst met apps kiest u in de rij met de app die u wilt labelen als goedgekeurd de drie puntjes aan het einde van de rij ![Puntjes voor labelen als goedgekeurd](./media/sanction-three-dots.png "Puntjes voor labelen als goedgekeurd") en kiest u **Als goedgekeurd markeren**.  

     ![Labelen als goedgekeurd](./media/mark-as-sanctioned.png "Labelen als goedgekeurd")  


## <a name="use-the-investigation-tools"></a>Gebruik de hulpprogramma's voor onderzoek  

1.  Ga in de Cloud App Security-portal naar **Onderzoeken**, bekijk het **activiteitenlogboek** en filter op een specifieke app. Controleer het volgende:  

    -   Wie heeft er toegang tot uw cloudomgeving?  

    -   Vanaf welk IP-bereik?  

    -   Wat is de activiteit van administrators?  

    -   Vanaf welke locaties maken administrators verbinding?  

    -   Zijn er verouderde apparaten die verbinding maken met uw cloudomgeving?  

    -   Zijn er mislukte aanmeldingen die afkomstig zijn van verwachte IP-adressen?  

2.  Ga naar **Onderzoeken**, vervolgens naar **Bestanden** en controleer het volgende:  

    -   Hoeveel bestanden zijn openbaar gedeeld, zodat iedereen toegang heeft tot de bestanden zonder een koppeling?  

    -   Met welke partners deelt u bestanden (delen van uitgaande gegevens)?  

    -   Zijn er bestanden met gevoelige namen?  

    -   Worden er bestanden gedeeld met iemands persoonlijke account?  

3.  Ga naar **Onderzoeken**, vervolgens naar **Accounts** en controleer het volgende:  

    -   Zijn er in een bepaalde service accounts gedurende een lange periode inactief? (Mogelijk kunt u de licentie voor die gebruiker voor die service intrekken?)  

    -   Wilt u weten welke gebruikers een specifieke rol hebben?  

    -   Is er iemand ontslagen, maar heeft deze medewerker nog steeds toegang tot een app en kan hij of zij die toegang gebruiken om gegevens te stelen?  

    -   Wilt u de machtigingen van een gebruiker voor een specifieke app intrekken of vereisen dat een specifieke gebruiker meervoudige verificatie uitvoert?  
    
    -   U kunt ook inzoomen op het gebruikersaccount op het tandwiel aan het einde van de rij van het gebruikersaccount te klikken. Selecteer dan een actie, zoals **Toegang tijdelijk intrekken** of **Samenwerkingen van gebruiker verwijderen**. Als de gebruiker is geïmporteerd uit Azure Active Directory kunt u ook klikken op **Azure AD-accountinstellingen** voor eenvoudige toegang tot geavanceerde gebruikersbeheerfuncties, bijvoorbeeld voor groepsbeheer, MFA, details over de aanmeldingen van de gebruiker en het blokkeren van aanmeldingen.

4.  Ga naar **Onderzoeken** en selecteer vervolgens een app. Het app-dashboard wordt geopend en biedt u informatie en inzichten. U kunt de tabbladen aan de bovenzijde gebruiken om het volgende te controleren:  

     ![App-dashboard](./media/investigate-app.png "app onderzoeken")  

    -   Welke soorten apparaten gebruiken uw gebruikers om verbinding te maken met de app?  

    -   Welke typen bestanden slaan ze op in de cloud?  

    -   Welke activiteit gebeurt er nu in de app?  

    -   Zijn er apps van derden verbonden met uw omgeving?  

    -   Bent u bekend met deze apps?  

    -   Hebben ze een machtiging voor het toegangsniveau dat voor ze is toegestaan?  

    -   Hoeveel gebruikers hebben ze geïmplementeerd? Hoe gebruikelijk zijn deze apps in het algemeen?  

5.  Ga naar het **Cloud Discovery-dashboard** en controleer het volgende:  

    -   Welke cloud-apps worden er gebruikt, in welke mate en door wie?  

    -   Voor welke doelen worden ze gebruikt?  

    -   Hoeveel gegevens worden er geüpload naar deze cloud-apps?  

    -   In welke categorieën beschikt u over erkende cloud-apps en gebruiken de gebruikers toch nog alternatieve oplossingen?  

    -   Zijn er voor de alternatieve oplossingen cloud-apps waarvoor u de goedkeuring wilt intrekken in uw organisatie?  

    -   Zijn er cloud-apps die worden gebruikt, maar het beleid van uw organisatie niet naleven?  

## <a name="use-reports-to-investigate-risk"></a>Rapporten gebruiken om risico's te onderzoeken  
Wanneer u controle probeert te krijgen over uw cloudomgeving, doet u bepaalde veronderstellingen op basis van wat u verwacht te vinden - u kent uw cloud nog niet goed. Op basis van deze veronderstellingen kunt u beleidsregels maken.

Nadat Cloud App Security in uw cloudomgeving wordt uitgevoerd, gebruikt u de ingebouwde rapporten (en aangepaste rapporten) om te zien wat er in de cloud gebeurt. Op basis hiervan kunt u uw beleidsregels opnieuw aanpassen en uitzonderingen opnemen, zodat uw beleid uiteindelijk weinig valspositieven bevat.  

Ingebouwde rapporten bieden u geaggregeerde weergaven voor onderzoek. Als u met ingebouwde rapporten wilt werken, gaat u naar **Onderzoeken** en klikt u op **Ingebouwde rapporten**. Zie het Engelstalige artikel [Built-in report reference](built-in-report-reference.md) (Naslaginformatie voor ingebouwde rapporten) voor meer informatie over de verschillende ingebouwde rapporten.  

## <a name="sample-investigation"></a>Voorbeeldonderzoek  
Stel dat u ervan uitgaat dat u geen toegang hebt tot uw cloudomgeving via riskante IP-adressen (bijvoorbeeld anonieme proxy's en Tor). U maakt echter een beleid voor riskante IP's om dit te controleren:  

1.  In de portal gaat u naar **Beheer** en kiest u **Beleidsregels**.  

2.  In het **Beleidscentrum** kiest u het tabblad **Sjablonen**.  

3.  Kies aan het einde van de rij **Gebruikersaanmelding vanaf een niet-gecategoriseerd IP-adres** het plusteken (**+**) om een nieuw beleid te maken.  

4.  Wijzig de naam van het beleid zodat u dit beleid kunt identificeren.  

5.  Onder **Activiteitfilters** kiest u de **+** om een filter toe te voegen. Schuif omlaag naar **IP-tag** en kies vervolgens **Anoniem** en **Tor**.  

     ![Voorbeeldbeleid riskante IP-adressen](./media/example-policy-risky-ips.png "voorbeeldbeleid riskante IP-adressen")  

Nu u het beleid hebt geïmplementeerd, ziet u tot uw verrassing een waarschuwing dat het beleid is geschonden.  

1.  Ga naar de pagina **Waarschuwingen** en bekijk de waarschuwing over de schending van het beleid.  

2.  Als u ziet dat het op een echte schending lijkt, wilt u de schending herstellen of het risico beperken.  

     Om het risico te beperken, kunt u de gebruiker een melding sturen om te vragen of de schending opzettelijk was en of de gebruiker zich hiervan bewust was.  

     U kunt ook inzoomen op de waarschuwing en de gebruiker blokkeren totdat u kunt achterhalen welke taken moeten worden uitgevoerd.  

3.  Als het een toegestane gebeurtenis is die waarschijnlijk niet wordt herhaald, kunt u de waarschuwing sluiten.  

     Als het is toegestaan is en u verwacht dat het wordt herhaald, kunt u het beleid aanpassen zodat dit type gebeurtenis in de toekomst niet meer wordt beschouwd als een schending.  

## <a name="see-also"></a>Zie ook  
Zie [Beheer](control.md) voor meer informatie over hoe u de cloud-apps in uw organisatie kunt beheren.   

Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit [Premier Portal](https://premier.microsoft.com/) kiezen.  
