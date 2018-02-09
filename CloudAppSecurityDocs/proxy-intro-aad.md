---
title: Beveiligen met Microsoft Cloud App Security proxyserver | Microsoft Docs
description: Dit onderwerp bevat informatie over de werking van de Cloud App Security-proxy.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/6/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 35a43120-bf67-4cf9-9b48-ebe157dbbd18
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 850436b8cb0c7a8e63a67a408ba51b6fecd9ac19
ms.sourcegitcommit: 8bfb8236b83f7423e73fe449d662935c084ff844
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2018
---
# <a name="protect-apps-with-microsoft-cloud-app-security-proxy"></a>Apps met Microsoft Cloud App Security proxy beveiligen

> [!NOTE]
> Dit is een preview-functie.


Vandaag de dag is het vaak niet genoeg om te weten wat er gebeurt in uw cloudomgeving achteraf, u wilt stoppen schendingen en lekken in realtime kunnen voordat werknemers opzettelijk of per ongeluk risico voor uw gegevens en uw organisatie. Het is belangrijk om in te schakelen voor gebruikers in uw organisatie wilt maken van de services en hulpprogramma's die voor hen beschikbaar in de cloud-apps en laat ze hun eigen apparaten meebrengen naar het werk. Op hetzelfde moment moet u de hulpprogramma's om u te helpen uw organisatie beschermen tegen gegevenslekken en diefstal van gegevens in realtime. Samen met Azure Active Directory biedt de Cloud App Security-proxy deze mogelijkheden in een holistische en geïntegreerde ervaring.

## <a name="how-it-works"></a>Hoe het werkt

De Cloud App Security-proxy is geïntegreerd met voorwaardelijke toegang van Azure AD. Voorwaardelijke toegang van Azure AD kunt u toegangsbeheer voor uw organisatie-apps op basis van bepaalde voorwaarden afdwingen. De voorwaarden definiëren *die* (bijvoorbeeld een gebruiker of groep gebruikers) en *wat* (die cloud-apps) en *waar* (welke locaties en netwerken) een beleid voor voorwaardelijke toegang is toegepast op. Nadat u de voorwaarden hebt vastgesteld, kunt u versturen gebruikers naar de Cloud App Security-proxy waar u toegangs- en -besturingselementen kunt toepassen.

Nadat een gebruiker wordt doorgestuurd naar de Cloud App Security-proxy, kunnen de toegang tot Apps en de sessies worden gecontroleerd en beheerd in realtime op basis van beleid voor toegang en -sessie. Beleid voor toegang en sessie worden gebruikt in de Cloud App Security-portal verder verfijnen filters en acties moeten worden uitgevoerd op een gebruiker ingesteld. U kunt met het beleid voor toegang en sessie:

-   **Blok bij het downloaden**: U kunt het downloaden van gevoelige documenten blokkeren. Bijvoorbeeld: op niet-beheerde apparaten.

-   **Bij het downloaden beveiligen**: in plaats van het downloaden van gevoelige documenten blokkeert, kunt u documenten kunnen worden beveiligd via versleuteling bij het downloaden vereisen. Dit zorgt ervoor dat het document is beveiligd en gebruikerstoegang is geverifieerd, als de gegevens op een niet-vertrouwd apparaat is gedownload. 

-   **Gebruikerssessies van niet-zakelijk netwerken beperken**: beperkte toegang door gebruikers toegang hebben tot een beveiligde app vanaf een locatie die geen deel uitmaakt van uw bedrijfsnetwerk, zijn toegestaan en het downloaden van gevoelige materialen is geblokkeerd of beveiligd.

-   **Laag-trust-gebruikerssessies bewaken**: riskant gebruikers wanneer ze zich in apps en hun acties worden vastgelegd uit in de sessie worden bewaakt. U kunt onderzoeken en analyseren van het gedrag van de gebruiker om te begrijpen wanneer en onder welke omstandigheden sessie beleid in de toekomst moeten worden toegepast. 

- **Toegang blokkeren**: U kunt volledig toegang tot bepaalde apps voor gebruikers die afkomstig zijn van niet-beheerde apparaten of van niet-zakelijk netwerken blokkeren.


### <a name="how-session-control-works"></a>De werking van Sessiecontrole

De proxy-Sessiecontrole is gebaseerd op voorwaardelijke toegang. Nadat u de toegang tot een app, kunt u de gebruikerssessies omleiden naar de proxy-Sessiecontrole in plaats van rechtstreeks naar de app. Daarna gaan aanvragen van gebruikers en -antwoorden via de proxy in plaats van rechtstreeks naar de app.

Aan de gebruiker binnen de sessie, de proxy vervangt de relevante URL's, Java-scripts en cookies behouden in de app-sessie met de proxy-URL's. Bijvoorbeeld: als de app een pagina met koppelingen waarvan domeinen met myapp.com retourneert eindigen, de proxy wordt vervangen door de koppelingen met domeinen die eindigt met ongeveer: myapp.com.us.cas.ms 

Deze methode hoeft u te installeren op het apparaat niet. Dit is ideaal bij de bewaking van sessies van niet-beheerde apparaten. 

Nadat een sessie via de proxy wordt geleid, kan de proxy het volgende doen:
1. Het verkeer voor de activiteiten van de gebruiker controleren
3. De geïdentificeerde activiteiten in de portal van de proxy Cloud-App weergeven
2. De verkeerslogboeken opslaan en analyseer ze
3. De beheerder om te exporteren van de verkeerslogboeken inschakelen
4. Beleid afdwingen op de sessie

## <a name="managed-device-identification"></a>Beheerd apparaat-id

De proxy kunt u beleid maken waarmee u rekening mee houden of een apparaat wordt beheerd of niet. Om te bepalen of een apparaat wordt beheerd of niet, de proxy maakt gebruik van:

-   Compatibele apparaten 
-   Apparaten die lid zijn van een domein 
-   Certificaten clientimplementatie
 
 
### <a name="compliant-and-domain-joined-devices"></a>Compatibele en het domein gekoppelde apparaten
Voorwaardelijke toegang van Azure AD kunt compatibele en domein apparaatgegevens rechtstreeks naar de Cloud App Security-proxy worden doorgegeven. Van daaruit kan een toegangsbeleid of een sessie-beleid worden ontwikkeld die gebruikmaakt van de status van het apparaat als een filter.
Zie voor meer informatie de [Inleiding tot beheer van apparaten in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction). 

### <a name="client-certificate-authenticated-devices"></a>Clientcertificaat geverifieerde apparaten

Het proxy-mechanisme voor apparaat-id aanvragen van relevante apparaten met behulp van clientcertificaten verificatie. Dit kunt u gebruikmaken van een bestaande clientcertificaten al is geïmplementeerd in uw organisatie of nieuwe clientcertificaten implementeert op beheerde apparaten en gebruik vervolgens de aanwezigheid van die certificaten toegangs- en beleidsregels. Zie voor meer informatie over het implementeren van clientcertificaten [proxy voor Azure AD-apps implementeren](proxy-deployment-aad.md).
 
## <a name="supported-apps-and-clients"></a>Ondersteunde apps en -clients

De proxy ondersteunt momenteel apps die zijn geconfigureerd met SAML voor eenmalige aanmelding in Azure AD. 

> [!NOTE]
> - De proxy biedt ook ondersteuning voor apps die zijn geconfigureerd met identiteitsproviders dan Azure AD in Private Preview. Voor meer informatie over de Private Preview sturen een e-mail naar mcaspreview@microsoft.com.
> - Office 365-toepassingen zijn niet geconfigureerd met SAML zodat ze worden momenteel niet ondersteund.

Sessiecontrole is beschikbaar voor elke browser op een primaire platform (mobiele apps en bureaublad-apps worden momenteel niet ondersteund). Door systeemeigen integreren met Azure AD, kunnen alle apps die zijn geconfigureerd met SAML eenmalige aanmelding in Azure AD worden ondersteund, waaronder de volgende apps:

-   SalesForce

-   Box

-   G Suite

-   Werkdag

-   Vertraging

-   Werkplek door Facebook

-   ServiceNow

-   JIRA/Confluence

-   AWS

-   Workiva

-   Basis op aanvraag

-   DocuSign

-   HighQ 

Aanvullende apps worden continu geïntegreerde om te bepalen van de sessie. Als u geïnteresseerd bent in een specifieke app die hier niet wordt vermeld [Stuur ons informatie over de app](mailto:casfeedback@microsoft.com) het gebruiksvoorbeeld u geïnteresseerd bent in en ingebouwde wordt deze.




## <a name="see-also"></a>Zie ook  
[De Cloud App Security-proxy implementeren](proxy-deployment-aad.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  


