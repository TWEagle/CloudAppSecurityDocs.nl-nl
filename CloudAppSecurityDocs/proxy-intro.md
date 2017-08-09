---
title: Werken met de Cloud App Security Proxy | Microsoft Docs
description: Dit onderwerp bevat informatie over de werking van de Cloud App Security-Proxy.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/31/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 28317b70-1851-4610-b1d6-863bc5994bb6
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 82e1ee0b5161dce88db815dc8eea06340bdbc532
ms.sourcegitcommit: f9851779aa15b11f559e56ac818f1333f027c000
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/07/2017
---
# <a name="working-with-the-cloud-app-security-proxy"></a>Werken met de Cloud App Security-Proxy

Vandaag de dag is het vaak niet genoeg om te weten wat er gebeurt in uw cloudomgeving achteraf, u wilt stoppen schendingen en lekken in realtime kunnen voordat werknemers opzettelijk of per ongeluk risico voor uw gegevens en uw organisatie. U moet kunnen laten gebruikers in uw organisatie optimaal gebruik van de services en hulpprogramma's die voor hen beschikbaar in de cloud-apps en hun eigen apparaten meebrengen naar het werk. Op hetzelfde moment moet u de hulpprogramma's om u te helpen uw organisatie te beveiligen tegen lekken, ransomware aanvallen en massaopslag gegevensdiefstal. 

## <a name="introducing-the-cloud-app-security-proxy"></a>Inleiding tot de Cloud App Security-Proxy
Proxy voor cloud App Security kunt u de hulpmiddelen die u nodig hebt om uit te voeren realtime bewaking en beheer van de toegang tot uw cloudomgeving, evenals de activiteiten die worden uitgevoerd binnen het.
U kunt uw organisatie te beveiligen met de Cloud App Security-Proxy:
- Voorkomen van gegevenslekken door downloads worden geblokkeerd voordat ze optreden
- Uw blootstelling aan ransomware minimaliseren door het beheer van en toegang tot uw netwerk blokkeren van niet-beheerde apparaten die niet wachtwoord zijn beveiligd of antivirussoftware hebt geïnstalleerd
- Setregels die gegevens opgeslagen en gedownload vanuit de cloud moet worden beveiligd met versleuteling forceren
- Meer inzicht verkrijgen in niet-beveiligde eindpunten zodat u kunt controleren wat op onbeheerde apparaten wordt uitgevoerd
- Toegang van riskante IP-adressen en verouderde id-providers beheren

Gebruik de twee niveaus van besturingselement geleverd door de Proxy zodat deze de unieke mogelijkheden: toegangsbeheer en beheer van sessies. Beide typen besturingselement gebruikmaken van gebruikersgegevens, informatie over de locatie en apparaatgegevens (gebruikt om te bepalen welke apparaten worden beheerd en zonder begeleiding) om beleid beslissingen te nemen voor elke app.

### <a name="access-control"></a>Toegangsbeheer
<more information about what is access control including examples>De Proxy-toegangsbeheer kunt u krachtige toegangsbeleid voor uw cloud-apps maken en biedt u de volgende mogelijkheden:

Toegangsbeheer gebruiken in de Cloud App Security, implementeert de Proxy door enkele wijzigingen aan uw bestaande configuratie van de id-provider en stel een beleid voor het beheren van uw cloud-toegangspunten. 

> [!NOTE]
> -  Er is niet nodig voor de identiteitsprovider bestaande beleidsregels wijzigen.

#### <a name="supported-apps-and-identity-providers"></a>Ondersteunde apps en id-providers

De Proxy-toegangsbeheer is ontworpen ter ondersteuning van elke app en een identiteitsprovider die SAML of WS-Federation-protocollen ondersteunt. De Cloud App Security-team is het testen van de toonaangevende id-providers en de toonaangevende apps met de mogelijkheden voor het beheer van toegang. Echter, aangezien er zijn veel id-providers en veel cloud-apps, niet voor elke combinatie van id-providers en app wordt getest. Het is raadzaam om het proces voor eenmalige aanmelding met de id-provider en de app op een sandbox- of testomgeving te testen voordat u deze implementeert in een productieomgeving.

### <a name="session-control"></a>Beheer van sessies

Sessie-besturingselement is een extra beschermingslaag geregeld door de Proxy. Kunt u nog meer gedetailleerde, realtime-controle over uw cloudtoepassingen. U kunt in plaats van het instellen van een beleid collectief wilt toestaan of blokkeren van toegang tot een bepaalde app toegang toestaan en vervolgens bij de bewaking van elke gebruikerssessie in de app, de toegang op verschillende manieren te beperken. Bijvoorbeeld, kunt u die bepalen van bepaalde apparaten of voor sessies die afkomstig zijn van specifieke locaties, die u wilt toestaan dat de gebruiker toegang tot de toepassing, maar het downloaden van gevoelige bestanden beperken.

#### <a name="supported-apps-and-flows"></a>Ondersteunde apps en -stromen

Op dit moment kunt Sessiecontrole u downloaden van het bestand blokkeren en de uitvoer van de rapporten in Salesforce.com. U kunt beleid op basis van gebruiker, de locatie en apparaten, evenals op basis van de inhoud die u wilt downloaden.

Bovendien ondersteunt deze versie beperkt sessies voor gebruikers die zich aanmelden browsers. Bijvoorbeeld, als u toegang beperken voor sessies die afkomstig zijn van systeemeigen apps wilt, moet u voor het definiëren van een toegangsbeleid voor het blokkeren van dergelijke wanneer toegang tot het filter **label van de gebruikersagent** gelijk is aan **Native client**.

SalesForce is getest op alle normale stromen. Echter, aangezien Salesforce talrijke 3e apps van derden heeft, kunnen er enkele 3e apps van derden die zijn niet getest en mogelijk niet met de sessie besturingselement werken en zelfs sommige's niet werken. Om te bevestigen dat dit inderdaad een 3e partij app probleem is, verwijdert u alle 3e apps van derden en de app testen met de sessie-besturingselement. Als alles goed werkt, toevoegen van de 3e partij apps één voor één totdat u de problematische app niet vinden. 

## <a name="device-management"></a>Apparaatbeheer

Cloud App Security kunt u om te bepalen en Proxy-beleid op basis van het apparaat houding maken. Om te bepalen of een apparaat of niet wordt beheerd, Cloud App Security maakt gebruik van het mechanisme voor clientcertificaten op waarin clientcomputers de certificaten die zijn geïmplementeerd op de beheerde apparaten van uw organisatie. Nadat gebruikers aanmeldingen bij een app hebt uitgevoerd, wordt ze gevraagd om het clientcertificaat op hun apparaat geïnstalleerd. Als een clientcertificaat is opgegeven, Cloud App security met betrekking tot een apparaat als beheerd. 
> [!NOTE]
>  De gebruiker niet akkoord met de client verzenden van certificaten kunt selecteren en in dit geval het apparaat wordt beschouwd als niet-beheerd.
< OK klikt, zodat u weet als deze wordt beheerd of niet - wat doet u met deze? >

### <a name="supported-browsers-and-native-apps"></a>Ondersteunde browsers en systeemeigen apps

De Proxy van Cloud App Security kunt u... op basis van clientcertificaten...

Clientcertificaten is een bekende mechanisme dat browser ontwikkelaars en systeemeigen toepassingsontwikkelaars kunnen bepalen of een niet implementeren. De meeste browsers op de meeste platforms ondersteunen, maar het artikel in systeemeigen apps is gecompliceerdere.

De ondersteuning voor clientcertificaten in systeemeigen apps, waaronder zowel desktop-apps en mobiele apps, kan soms variëren, afhankelijk van het platform en zelfs op de status van het apparaat. Bijvoorbeeld in Salesforce1, de mobiele app Salesforce werken clientcertificaten alleen als er een MDM geïmplementeerd op het apparaat en Salesforce1 is geconfigureerd voor het verzenden van clientcertificaten.

Clientcertificaten zijn is getest op Internet Explorer, Edge Chrome, Safari en Firefox op de nieuwste versies van Windows, OSX, Android en iOS (elk met de relevante browsers).

> [!NOTE]
> In iOS werkt alleen in de Safari-browser met een clientcertificaat.

Zelfs in gevallen waarin browsers of systeemeigen apps bieden ondersteuning voor clientcertificaten er sommige gevallen waar de gebruikers problemen hebben dat het certificaat, bijvoorbeeld als een gebruiker-dalingen voor het verzenden van een clientcertificaat slechts één keer de browser of systeemeigen app mogelijk Vergeet niet de keuze en de gebruiker voor een certificaat niet opnieuw wordt gevraagd. Als u wilt opheffen dergelijke problemen, wordt aangeraden sluiten alle geopende exemplaren van de browser en vervolgens nieuwe te openen of alle cookies wissen en probeer het opnieuw.

Aan de andere kant zijn sommige browsers en systeemeigen apps die ondersteuning voor de optie voor het onderdrukken van de pop-server van dat clientcertificaten aanvragen en in plaats daarvan automatisch verzendt.

In het algemeen is het raadzaam client certificaataanvragen van gebruikers testen zonder het afdwingen van beleid, maar in een modus voor monitor alleen. U kunt dit doen door het maken van een **alleen** beleid om beheerde apparaten te identificeren.

## <a name="architecture"></a>Architectuur

De Proxy is geïntegreerd met de id-provider en de app en beide moeten worden geconfigureerd voor aanmeldingsaanvragen omleiden naar de Proxy.

Bovendien in volgorde van beheerde apparaten te identificeren, de Proxy clientcertificaten van beheerde apparaten kan aanvragen. Zodra een clientcertificaat is ontvangen door de Proxy, het apparaat wordt beschouwd als beheerd en beleid op beheerde en onbeheerde apparaten te laten treden.

Zie de sectie implementatie voor meer informatie over het implementatieproces.

![Cloud App Security Proxy-architectuur](./media/proxy-architecture.png)

## <a name="user-login-flow"></a>Aanmelding gebruikersstroom

Het bovenstaande diagram beschrijft een aanmelding die wordt gestart door de identiteitsprovider, ook wel bekend als *identiteitsprovider geïnitieerd aanmelding*. Als de gebruiker wordt gestart vanuit de app, ook wel *serviceprovider geïnitieerd aanmelding*vervolgens zij wordt omgeleid naar de Cloud App Security-Proxy die vervolgens de gebruiker naar de id-provider leidt en de rest van de aanmelding is vergelijkbaar met de *identiteitsprovider geïnitieerd aanmelding* stroom.

Dit is de *identiteitsprovider geïnitieerd aanmelding* stroom:
-   Gebruiker verzendt een aanvraag naar de id-provider en referenties

-   Als de toegang is toegestaan, de id-provider wordt de gebruiker omgeleid naar de Cloud App Security-Proxy

-   Als de gebruiker een certificaat geïnstalleerd heeft en er is een relevante beleid waarmee wordt gecontroleerd of beheerd of onbeheerd apparaten, wordt de gebruiker gevraagd om clientcertificaten te verlenen. In beide gevallen moet wordt een toegangsbeleid geëvalueerd

-   Er zijn op dit moment 3 opties:

    -   De gebruiker is toegang tot de app toegestaan

    -   De gebruiker is toegang krijgen tot de app geblokkeerd

    -   De gebruiker toegang tot de app is toegestaan, maar in de bewaakte modus

        -   In dit geval wordt wordt de gebruiker opnieuw omgeleid naar de Cloud App Security Proxy, die de hele sessie tussen de gebruiker en de app wordt bewaakt

        -   Bij de bewaking van, de Proxy evalueert het beleid van de sessie en kan dienovereenkomstig blokkerende acties uitvoeren

## <a name="how-access-control-works"></a>Hoe toegang tot werking van toegangsbeheer

Als onderdeel van de implementatie van de Proxy moet u de configuraties in zowel de id-provider en de app die u wilt wijzigen om te bepalen. Dit omvat wijzigingen van de URL, zodat zowel de id-provider en de app aanmeldingsaanvragen worden omgeleid naar de Proxy. Bovendien en indien nodig, certificaten ook worden vervangen.

Zodra deze stappen zijn voltooid, gaat u alle gebeurtenissen van de aanmelding via de Proxy- en de Proxy kunt bepalen als ze toegang de app tot, geen toegang hebben, of in de bewaakte modus toegang heeft tot. Houd er rekening mee dat in deze fase wordt de Proxy kan clientcertificaten van het apparaat aanvragen, en de status van het apparaat gebruiken om beleid beslissingen te nemen.

## <a name="how-session-control-works"></a>De werking van Sessiecontrole

De Proxy-Sessiecontrole is ingebouwd in toegangsbeheer. Als u toegang tot een app, kunt u bepalen, gebaseerd op toegangsbeleid voor het bewaken van de sessie door de sessies omleiden naar de Proxy-Sessiecontrole. Daarna gaan aanvragen van gebruikers en -antwoorden via de Proxy in plaats van rechtstreeks naar de app.

Aan de gebruiker binnen de sessie, de Proxy vervangt de relevante URL's, Java-scripts en cookies in de app aan gedupliceerd in de Proxy's houden. Bijvoorbeeld: als de app een pagina met koppelingen die eindigen geeft met *myapp.com*, de Proxy wordt vervangen door de pagina's die met ongeveer eindigen *myapp.com.cas.ms*.

Wanneer een sessie via de Proxy wordt geleid, kan de Proxy het verkeer inspecteren, de gebeurtenissen die het identificeert weergegeven in de Cloud App Proxy-portal en beleidsregels worden toegepast op de sessie.

## <a name="how-identifying-managed-devices-works"></a>Hoe werkt apparaten te identificeren beheerd

Beheerde om apparaten te identificeren, gebruikt de Proxy het mechanisme van clientcertificaten. Het mechanisme voor werkt als volgt:

-   Als de gebruiker beschikt over een clientcertificaat op haar apparaat geïnstalleerd en er is een relevante beleid waarmee wordt gecontroleerd of beheerde of onbeheerde apparaten.

    -   Wanneer de gebruiker op de pagina Proxy tijdens de fase aanmelden aankomt, vraagt de Proxy een clientcertificaat van het apparaat van de gebruiker.

    -   Het apparaat van de gebruiker wordt gevraagd om het clientcertificaat en als ze goedkeurt, wordt het certificaat verzonden naar de Proxy.

    -   De Proxy verifieert vervolgens het clientcertificaat op basis van het basiscertificaat dat is opgegeven door de beheerder.

    -   Als het clientcertificaat dat is geleverd door het apparaat is geverifieerd met het basiscertificaat wordt het apparaat wordt beschouwd als beheerd.

-   Als een van de vorige fasen is niet voltooid, het apparaat wordt beschouwd als niet-beheerd.



## <a name="see-also"></a>Zie ook  
[Proxy-implementatie](proxy-deployment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  