---
title: Onderzoeken | Microsoft Docs
description: In dit onderwerp vindt u een overzicht van het proces voor het onderzoeken van waarschuwingen, problemen en verdachte activiteiten met Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a9b00c2a-2f71-499e-8f57-67e560daedc1
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 186643ab8efa7391b06a09dd2cddbb22ba583e71


---

# <a name="investigate"></a>Onderzoeken
Nadat Cloud App Security wordt uitgevoerd in uw cloudomgeving, hebt u eerst een fase nodig waarin u meer leert en onderzoekt met de hulpprogramma's van Cloud App Security om een meer inzicht te krijgen in wat er in uw cloudomgeving gebeurt. Vervolgens kunt u bepalen welke vereisten nodig zijn om uw organisatie te beschermen tegen risico’s op basis van uw specifieke omgeving en hoe deze wordt gebruikt.  
  
In deze sectie wordt beschreven hoe u een diepgaand onderzoek uitvoert om een beter inzicht te krijgen in wat er in uw cloudomgeving gebeurt.  
  
## <a name="dashboards"></a>Dashboards  
De volgende dashboards kunnen u helpen bij het onderzoeken van wat er gebeurt met apps in uw cloudomgeving:  
  
|Dashboard|Beschrijving|  
|---------------|-----------------|  
|Hoofddashboard|Overzicht van cloudstatus (gebruikers, bestanden, activiteiten), evenals de vereiste acties (waarschuwingen, schendingen van activiteiten en schendingen van inhoud)|  
|Toepassingsdashboard - algemeen|Overzicht van het gebruik van toepassingen per locatie, gebruiksgrafieken per aantal gebruikers|  
|Toepassingsdashboard – inzichten|Analyse van gegevens die zijn opgeslagen in de app; onderverdeeld op basis van het bestandstype en het niveau van bestandsdeling|  
|Toepassingsdashboard – bestanden|Inzoomen op bestanden, de mogelijkheid te filteren op basis van eigenaar, niveau van delen, enzovoort, alsmede het uitvoeren van beheeracties (zoals quarantaine)|  
|Toepassingsdashboard – apps van derden|Inzoomen op apps van derden die momenteel zijn geïmplementeerd, zoals Google Apps, en het beleid voor deze apps definiëren|  
|Gebruikersdashboard|Een volledig overzicht van het gebruikersprofiel in de cloud met inbegrip van groepen, locaties, recente activiteiten, gerelateerde waarschuwingen en gebruikte browsers|  
  
##  <a name="a-namesanctionappa-sanction-or-unsanction-apps"></a>Apps goedkeuren of de goedkeuring van apps intrekken  
De eerste stap om meer inzicht te krijgen in uw cloud is het goedkeuren van apps. Nadat u een app hebt goedgekeurd, kunt u filteren op apps die niet zijn goedgekeurd en migratie naar goedgekeurde apps van hetzelfde type initiëren.  
  
-   Klik in de Cloud App Security-console op **Detecteren** en vervolgens op **Detectiedashboard**.  
  
-   In de lijst met gedetecteerde apps klikt u in de rij waarin de app die u wilt goedkeuren wordt weergegeven op de drie puntjes aan het einde van de rij ![drie puntjes voor goedkeuren](./media/sanction-three-dots.png "Sanction three dots") en selecteert u **Als goedgekeurd markeren**.  
  
     ![Als goedgekeurd markeren](./media/mark-as-sanctioned.png "mark as sanctioned")  
  
> [!NOTE]  
>  Voor elke app die u met de Cloud App Security-API-integratie wilt controleren, kunt u het beste een beheerdersserviceaccount maken dat is toegewezen aan Cloud App Security.  
  
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
  
    -   Zijn er bestanden met een gevoelige naam?  
  
    -   Worden er bestanden gedeeld met iemands persoonlijke account?  
  
3.  Ga naar **Onderzoeken**, vervolgens naar **Accounts** en controleer het volgende:  
  
    -   Zijn er accounts die gedurende een lange periode niet actief zijn geweest in een bepaalde service, en kunt u mogelijk de licentie van die service voor die gebruiker intrekken?  
  
    -   Wilt u weten welke gebruikers een specifieke rol hebben?  
  
    -   Is er iemand ontslagen, maar heeft deze medewerker nog steeds toegang tot een app en kan hij of zij die toegang gebruiken om gegevens te stelen?  
  
    -   Wilt u de machtigingen van een gebruiker voor een specifieke app intrekken of vereisen dat een specifieke gebruiker meervoudige verificatie uitvoert?  
  
4.  Ga naar **Onderzoeken** en selecteer vervolgens een app. U gaat naar het dashboard van de app, waar u informatie en inzichten krijgt zodat u de tabbladen aan de bovenzijde kunt gebruiken om het volgende te controleren:  
  
     ![App onderzoeken](./media/investigate-app.png "investigate app")  
  
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
  
    -   Zijn er voor de alternatieve oplossing cloud-apps waarvoor u de erkenning wilt verwijderen uit uw organisatie?  
  
    -   Zijn er cloud-apps die worden gebruikt, maar het beleid van uw organisatie niet naleven?  
  
## <a name="how-to-use-reports-to-investigate-risk"></a>Het gebruik van rapporten voor het onderzoeken van risico’s  
Wanneer u controle probeert te krijgen over uw cloudomgeving, doet u bepaalde veronderstellingen op basis van wat u verwacht te vinden - u kent uw cloud nog niet goed. En op basis van deze veronderstellingen kunt u beleidsregels maken. Vervolgens, nadat Cloud App Security wordt uitgevoerd in uw cloudomgeving, kunt u de ingebouwde rapporten (en aangepaste rapporten) gebruiken om te zien wat er echt gebeurt in de cloud. Op basis hiervan voegt u opnieuw uitzonderingen toe aan het beleid, zodat het beleid uiteindelijk zeer weinig fout-positieven registreert.  
  
Ingebouwde rapporten bieden u geaggregeerde weergaven voor onderzoek.  
  
Als u met ingebouwde rapporten wilt werken, gaat u naar **Onderzoeken** en klikt u op **Ingebouwde rapporten**. Zie het Engelstalige artikel [Built-in report reference](built-in-report-reference.md) (Naslaginformatie voor ingebouwde rapporten) voor meer informatie over de verschillende ingebouwde rapporten.  
  
## <a name="sample-investigation"></a>Voorbeeldonderzoek  
Stel dat u ervan uitgaat dat u geen toegang hebt tot uw cloudomgeving via riskante IP-adressen (bijvoorbeeld anonieme proxy's en Tor). U maakt echter een beleid voor riskante IP’s om dit te controleren:  
  
1.  In de portal gaat u naar **Beheer** en selecteert u **Beleidsregels**.  
  
2.  In het **Beleidscentrum** klikt u op het tabblad **Sjablonen**.  
  
3.  Klik aan het einde van de rij **Gebruikersaanmelding vanaf een niet-gecategoriseerd IP-adres** op het plusteken (**+**) om een nieuw beleid te maken.  
  
4.  Wijzig de naam van het beleid zodat u dit beleid kunt identificeren.  
  
5.  Onder **Activiteitfilters** klikt u op de **+** om een filter toe te voegen. Schuif omlaag naar **IP-label** en selecteer vervolgens **Anoniem** en **Tor**.  
  
     ![Voorbeeldbeleid riskante IP-adressen](./media/example-policy-risky-ips.png "example policy risky ips")  
  
Nu u het beleid hebt geïmplementeerd, ziet u tot uw verrassing een waarschuwing dat het beleid is geschonden.  
  
1.  Ga naar de pagina **Waarschuwingen** en bekijk de waarschuwing over de schending van het beleid.  
  
2.  Als u ziet dat het op een echte schending lijkt, wilt u de schending herstellen of het risico beperken.  
  
     Om het risico te beperken, kunt u de gebruiker een melding sturen om te vragen of de schending opzettelijk was en of de gebruiker zich hiervan bewust was.  
  
     U kunt ook inzoomen op de waarschuwing en de gebruiker blokkeren totdat u kunt achterhalen welke taken moeten worden uitgevoerd.  
  
3.  Als het een toegestane gebeurtenis is die waarschijnlijk niet wordt herhaald, kunt u de waarschuwing sluiten.  
  
     Als het toegestaan is en u verwacht dat het wordt herhaald, kunt u het beleid aanpassen om te voorkomen dat dit type gebeurtenis in de toekomst wordt beschouwd als een schending.  
  
## <a name="see-also"></a>Zie ook  
[Beheer](control.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


