---
title: Werken met de Cloud App Security Proxy | Microsoft Docs
description: Dit onderwerp bevat informatie over de werking van de Cloud App Security-Proxy.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/9/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 28317b70-1851-4610-b1d6-863bc5994bb6
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d4b01d92f705566bac36d764a7aede0eaa8defcc
ms.sourcegitcommit: 4cf65f627f2d370ee4a4decae1acbb9658874056
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2017
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

## <a name="access-control"></a>Toegangsbeheer
Toegangsbeheer biedt u de mogelijkheid om te bewaken, controleren en blokkeer de toegang - op basis van de app, apparaat, gebruiker en locatie. Op deze manier kunt u bepalen, in real-time, toegang tot uw cloud-apps.

Toegangsbeheer kunt u krachtige om beleid te maken, zoals:
 - toegang tot alle cloud-apps blokkeren vanaf niet-beheerde apparaten
 - toegang tot specifieke cloud-apps blokkeren voor specifieke gebruikers
 - Monitor voor toegang tot specifieke cloud-apps op een specifieke locatie
 - Beperk de toegang tot de cloud-apps naar specifieke gebruikersgroepen en -locaties

Toegangsbeheer gebruiken in de Cloud App Security, implementeert de Proxy door enkele wijzigingen aan uw bestaande configuratie van de id-provider en stel een beleid voor het beheren van uw cloud-apps. 

> [!NOTE]
> -  Er is niet nodig voor de identiteitsprovider bestaande beleidsregels wijzigen.

### <a name="how-access-control-works"></a>Hoe toegang tot werking van toegangsbeheer

Als onderdeel van de implementatie van de Proxy wijzigt u app- en identiteitsbeheer providerconfiguratie aanmeldingsaanvragen wilt omleiden naar de Proxy. 

Hierna moeten alle gebeurtenissen voor aanmelding, worden doorgestuurd via de Proxy- en de Proxy kunt bepalen of u wilt toestaan toegang tot de app, de toegang weigert of toegang bewaken.

### <a name="supported-apps-and-identity-providers"></a>Ondersteunde apps en id-providers

Toegangsbeheer ondersteunt elke app en een identiteitsprovider die SAML of WS-Federation-protocollen ondersteunt. Het team Cloud App Security getest de toonaangevende id-providers en de toonaangevende apps met de mogelijkheden voor het beheer van toegang. Aangezien er zijn echter veel id-providers en veel cloud-apps, het is raadzaam het proces voor één aanmelding met de id-provider en de app op een sandbox testdoeleinden of testomgeving voordat u deze implementeert in een productieomgeving.

## <a name="session-control"></a>Beheer van sessies

Sessiecontrole biedt een extra laag van besturingselement door te geven inzicht in elke activiteit in elke gebruikerssessie. Sessie-besturingselement kunnen diep sessie niveau bewaking, u gedetailleerde inzicht in de cloud-apps zoals die van een inline-proxy's voor on-premises apps het netwerk. Met beheer van sessies in plaats van toestaan en blokkeren van toegang volledig, kunt u bepaalde sessie activiteiten beperken. 

Bijvoorbeeld, kunt u die bepalen van niet-beheerde apparaten of voor sessies die afkomstig zijn van specifieke locaties, die u wilt toestaan dat de gebruiker toegang tot de toepassing, maar het downloaden van gevoelige bestanden beperken. 

### <a name="how-session-control-works"></a>De werking van Sessiecontrole

De Proxy-Sessiecontrole is ingebouwd in toegangsbeheer. Nadat u de toegang tot een app, kunt u de sessie-beleidsregels die worden gebruikerssessies omgeleid naar de Proxy-sessie besturingselement kunt instellen. Daarna gaan aanvragen van gebruikers en -antwoorden via de Proxy in plaats van rechtstreeks naar de app.

Aan de gebruiker binnen de sessie, de Proxy vervangt de relevante URL's, Java-scripts en cookies in de app aan gedupliceerd in de Proxy's houden. Bijvoorbeeld: als de app een pagina met koppelingen die eindigen geeft met *myapp.com*, de Proxy wordt vervangen door de pagina's die met ongeveer eindigen *myapp.com.cas.ms*.

Wanneer een sessie via de Proxy wordt geleid, kan de Proxy het verkeer inspecteren, de gebeurtenissen die het identificeert weergegeven in de Cloud App Proxy-portal en beleidsregels worden toegepast op de sessie.

## <a name="device-identification"></a>Apparaat-id

Cloud App Security kunt u om te bepalen en Proxy-beleid op basis van het apparaat houding maken. Om te bepalen of een apparaat of niet wordt beheerd, Cloud App Security maakt gebruik van:
 - Intune compatibele apparaten * 
 - Lid van een Azure AD-domein apparaten * 
 - Clientimplementatie-certificaten (voor alle apps)

* Alleen beschikbaar voor Azure AD-apps waar voorwaardelijke toegang beschikbaar is

## <a name="architecture"></a>Architectuur

Integratie met de Proxy-mogelijkheden voor wordt eenvoudige met Azure Active Directory uitgevoerd. U kunt ook gebruikmaken van Azure AD-domein zijn toegevoegd en compatibele apparaten van Intune om eenvoudig apparaat te identificeren bij het maken van beleid. 

Om in te stellen andere id-providers en apps werken met de Proxy, moeten beide worden geconfigureerd voor aanmeldingsaanvragen omleiden naar de Proxy.

Bovendien in volgorde van beheerde apparaten te identificeren, de Proxy clientcertificaten van beheerde apparaten kan aanvragen. Zodra een clientcertificaat is ontvangen door de Proxy, het apparaat wordt beschouwd als beheerd en beleid op beheerde en onbeheerde apparaten te laten treden.

Zie voor meer informatie over het implementatieproces [Proxy-implementatie](proxy-deployment.md).

![Cloud App Security Proxy-architectuur](./media/proxy-architecture.png)

## <a name="user-login-flow"></a>Aanmelding gebruikersstroom

1. Gebruiker verzendt een aanvraag naar de id-provider en referenties verstrekt.
2.  Als de toegang is toegestaan, wordt de gebruiker omgeleid naar de Cloud App Security-Proxy van de id-provider.
3.  Als de gebruiker een certificaat geïnstalleerd heeft en er is een relevante beleid waarmee wordt gecontroleerd of beheerd of onbeheerd apparaten, wordt de gebruiker gevraagd om clientcertificaten te verlenen. In beide gevallen moet wordt een toegangsbeleid geëvalueerd.
4.   Er zijn op dit moment 3 opties:
    -   De gebruiker is toegang tot de app toegestaan
    -   De gebruiker is toegang krijgen tot de app geblokkeerd
    -   De gebruiker toegang tot de app is toegestaan, maar in de bewaakte modus
        -   In dit geval wordt wordt de gebruiker opnieuw omgeleid naar de Cloud App Security Proxy, die de hele sessie tussen de gebruiker en de app wordt bewaakt. Bij de bewaking van, de Proxy evalueert het beleid van de sessie en blokkerende acties dienovereenkomstig kan uitvoeren.

>[!NOTE]
> Het bovenstaande diagram ziet u een *identiteitsprovider geïnitieerd aanmelding*. Als de gebruiker wordt gestart vanuit de app een *serviceprovider geïnitieerd aanmelding*, wordt hij omgeleid naar de Cloud App Security-Proxy en vervolgens met de id-provider voordat u voltooit de *identiteitsprovider geïnitieerd aanmelding* stroom.

## <a name="managed-devices-flow"></a>Beheerde apparaten stroom

De Proxy maakt gebruik van het mechanisme van clientcertificaten voor beheerde apparaten die niet worden beheerd door Azure AD. Het mechanisme voor werkt als volgt:

1 als de gebruiker beschikt over een clientcertificaat op haar apparaat geïnstalleerd en er is een relevante beleid waarmee wordt gecontroleerd of beheerde of onbeheerde apparaten.
   -   Wanneer de gebruiker op de pagina Proxy tijdens de fase aanmelden aankomt, vraagt de Proxy een clientcertificaat van het apparaat van de gebruiker.

   -   Het apparaat van de gebruiker wordt gevraagd om het clientcertificaat en als ze goedkeurt, wordt het certificaat verzonden naar de Proxy.

   -   De Proxy verifieert vervolgens het clientcertificaat op basis van het basiscertificaat dat is opgegeven door de beheerder.

   -   Als het clientcertificaat dat is geleverd door het apparaat is geverifieerd met het basiscertificaat wordt het apparaat wordt beschouwd als beheerd.

-   Als een van de vorige fasen is niet voltooid, het apparaat wordt beschouwd als niet-beheerd.



## <a name="see-also"></a>Zie ook  
[Proxy-implementatie](proxy-deployment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  