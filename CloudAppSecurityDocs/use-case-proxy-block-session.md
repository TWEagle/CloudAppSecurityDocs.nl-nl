---
title: Het blokkeren van gevoelige gegevens van niet-beheerde apparaten worden gedownload | Microsoft Docs
description: Dit onderwerp beschrijft het scenario voor het beveiligen van uw organisatie tegen downloads van gevoelige gegevens door niet-beheerde apparaten.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/15/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: d1861218-a16f-4058-bd0e-34cc4a9413d6
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 4936805c3777ce4ff82735637941cbe528315eb4
ms.sourcegitcommit: 84f358a5dd0ab7f362dd3a2cf9999a6184fba856
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2017
---
# <a name="blocking-downloads-on-unmanaged-devices"></a>Downloads op onbeheerde apparaten worden geblokkeerd

De hedendaagse IT-beheerder is vastgelopen tussen een steen en vaste place: enerzijds, u wilt uw werknemers productief inschakelen en dit betekent dat toegang en de mogelijkheid om te werken van alle tijd, vanaf elk apparaat. Aan de andere kant u wilt beveiligen van het bedrijf en die bedrijfseigen en bevoorrechte informatie bevat. Hoe kunt u uw werknemers toegang tot uw cloud-apps, maar uw gegevens beschermen inschakelen? De Cloud App Security Proxy biedt u een hoog niveau van controle over wat u doet en niet is toegestaan in uw cloud-apps. 

## <a name="how-does-cloud-app-security-detect-unmanaged-devices"></a>Hoe detecteert Cloud App Security niet-beheerde apparaten
.

>[!NOTE]
> Deze gebruiksvoorbeeld van toepassing op.

## <a name="the-threat"></a>DE BEDREIGING
Een accountmanager in uw organisatie wil iets in Salesforce thuis tijdens het weekend, op zijn persoonlijke mobiele telefoon te controleren. Het account bevat informatie client creditcard of persoonlijke gegevens kan bevatten. De telefoon is niet-beheerde, betekent dat als hij documenten van Salesforce gedownload naar de telefoon, deze kan worden geïnfecteerd met kwaadaardige software of als het apparaat is zoekgeraakt of gestolen, niet zijn kan beveiligd met een wachtwoord en iedereen die deze hebben toegang tot gevoelige informatie vindt.

## <a name="the-solution"></a>DE OPLOSSING
Beveiligen van uw organisatie door gebruik van cloud-app in de Cloud App Security controleren en maken van een proxybeleid om te bepalen en activiteiten van niet-beheerde apparaten blokkeren.

## <a name="prerequisites"></a>Vereisten

[Implementeer](proxy-deployment.md) de Cloud App Security-Proxy voor Salesforce.

## <a name="set-up-unmanaged-device-detection"></a>Detectie van niet-beheerde apparaten instellen


## <a name="create-a-session-policy"></a>Een sessie-beleid maken
Sessie-beleidsregels kunt u voor het bewaken van alles wat die een gebruiker binnen een sessie en kunt die u mogelijkheden heeft bepalen zodat u kunt blokkeren en downloaden van bestanden beveiligen.


1.  Klik in de console op **Beheer** gevolgd door **Beleidsregels**.  
  
2.  Klik op **beleid maken** en selecteer **sessie beleid**.  
  
3.  Geef uw beleid een naam en beschrijving, zoals **blok SF downloads op niet-beheerde apparaten**.  
  
3. Geef een **ernstniveau van beleid** op voor uw beleid. Als u in Cloud App Security hebt ingesteld dat u meldingen krijgt over beleidsovereenkomsten voor een specifiek ernstniveau van beleid, wordt aan de hand hiervan bepaald of er op basis van de overeenkomsten van dit beleid een melding wordt gedaan.

4.  U kunt laten de **categorie** instellen als de **DLP**.  
  
6. Onder **sessie besturingselementtype**, selecteer **alle activiteiten bewaken en beheren van het downloaden van bestand**. Hiermee geeft u de mogelijkheid voor het bewaken van alles wat gebruikers doen tijdens een sessie van Salesforce en krijgt u beheren blok en downloads in realtime te beveiligen. Ook is mogelijk om te filteren op basis van de Cloud App Security ingebouwde DLP of een externe DLP bestandsinhoud.
 
7. Onder **activiteitbron**, klikt u op **apps selecteren in de onderstaande lijst** en selecteer **Salesforce**.

8. Selecteer in het gedeelte van de filters activiteit **apparaattype** en vervolgens **is niet gelijk aan** en selecteer **compatibele**, **verbonden met het domein** en **geldig clientcertificaat**.
  
8. Cloud App Security voor het herkennen van welke bestanden en gegevens die u persoonlijke beschouwt instellen:

    - Selecteer uw vertrouwelijke bestanden in de sectie filters van bestand. Als u met Azure Information Protection werkt, kunt u **classificatie label** en selecteer vervolgens de labels die u voor de geclassificeerde bestanden gebruikt.
    
    -  Schakel **inhoudscontrole** om in te schakelen op de interne Cloud App Security om uw bestanden voor de geclassificeerde inhoud te scannen, kunt u bijvoorbeeld selecteren **bestanden bevatten die overeenkomen met een vooraf ingestelde expressie** en selecteer vervolgens **alle landen: Finance: creditcardnummer**.

10. Op dit stadium, onder **acties** om te worden uitgevoerd wanneer het beleid wordt gevonden, selecteer:
    - Toestaan: Als u toestaat, kunnen gebruikers de bestanden te downloaden. 
    of
    - Beveiligen: Als u selecteert **beveiligen**, de gebruiker is mogelijk om de bestanden te downloaden, maar ze worden versleuteld met Azure RMS. U kunt ook een standaardactie moeten worden uitgevoerd als versleuteling niet instellen (blokkeren of toestaan dat het downloaden).
 
 >[!WARNING]
 >Het is raadzaam dat u geen **blok** gedownload voordat de eerste waarop het beleid **toestaan** modus en controleren of de resultaten zijn zoals verwacht en pas nadat u hebt vastgesteld dat het beleid niet iedereen onbedoeld blokkeert, schakelt u het beleid **blok** downloadt.
 
 9. Stel de waarschuwingen die u wilt ontvangen wanneer het beleid wordt vergeleken. U kunt een limiet kunt instellen, zodat u geen te veel waarschuwingen ontvangt en u kunt aangeven of de waarschuwingen krijgt als een e-mailbericht of SMS-bericht of beide.

10. Als u wilt weergeven van de sessie beleid overeenkomsten **besturingselement** en vervolgens **beleid**. Filteren van de resultaten om weer te geven alleen de sessie beleidsregels met behulp van de **Type** filter aan de bovenkant. Klik op een beleid voor meer informatie over de overeenkomsten voor elk beleid. Klik op de **geschiedenis** tabblad een historisch overzicht terug naar maximaal zes maanden van beleid overeenkomsten.     
  
## <a name="validate-your-policy"></a>Valideren van het beleid

1. Meld u aan bij Salesforce om te simuleren van een waarschuwing, van een onbeheerd apparaat, en een bestand probeert te downloaden.
3. Ga naar het beleidsrapport. Een sessie beleid overeenkomst moet binnenkort worden weergegeven. 
4. U kunt op de overeenkomst klikken om te zien welke bestanden zijn gedownload. De overeenkomst zelf wordt gemaskeerd ter bescherming van gevoelige gegevens. 

## <a name="blocking-and-protecting-your-sensitive-information"></a>Blokkeren en bescherming van gevoelige informatie

Nadat u het hebt gevalideerd en het beleid op uw wensen hebt afgestemd, verwijdert u mogelijke valse positieven die overeenkomen met uw beleid. Ga als volgt verder: 

1. Wanneer een sessie-beleid wordt gevonden, kunt u het herstellen door het instellen van geautomatiseerde [beheeracties](governance-actions.md).

2. Om dit te doen, bewerkt u hiervoor hebt gemaakt en stel **acties** naar **blok** downloadt wanneer het beleid wordt vergeleken. De gebruiker niet mogelijk om de bestanden te downloaden en wordt een bericht weergegeven dat ze bent niet gemachtigd om de bestanden te downloaden.
  
 
 ## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  