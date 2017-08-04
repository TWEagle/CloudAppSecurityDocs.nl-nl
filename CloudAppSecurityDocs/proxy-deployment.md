---
title: De Cloud App Security-Proxy implementeren | Microsoft Docs
description: Dit onderwerp bevat informatie over het implementeren van de Cloud App Security-Proxy.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/31/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 75094bde-e135-47fb-b5c6-7e1168919771
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 245e44cdf56b15795f67340442babcb0f688ea9d
ms.sourcegitcommit: c5a0d07af558239976ce144c14ae56c81642191b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/03/2017
---
# <a name="deploying-the-cloud-app-security-proxy"></a>De Cloud App Security-Proxy implementeren

> [!NOTE]
> Het is raadzaam om te proberen de installatie in een sandbox- of testomgeving voordat u deze installeert in een productieomgeving.

De stappen die hieronder worden beschreven moeten worden genomen om de Cloud App Security-Proxy implementeren en zowel toegangsbeheer als Sessiecontrole inschakelen.

## <a name="prerequisites"></a>Vereisten

-   Een werkomgeving waarin uw cloud-app is geconfigureerd met een id-provider. Het installatieproces omvat configuratiewijzigingen in zowel de app en de id-provider.
- Zorg ervoor dat u toegang hebt tot de instellingen voor eenmalige aanmelding in de id-provider en de app.

## <a name="deploy-the-proxy"></a>De Proxy implementeren

Als u de Proxy in een productieomgeving installeert, raden wij aan zoeken naar een tijd wanneer de meeste van de gebruikers de app niet gebruikt meestal laat nachts of tijdens het weekend en aan uw gebruikers communiceren dat er mogelijk een korte app uitvaltijd.

Voordat u begint met configuratiewijzigingen aanbrengen, Controleer of uw huidige configuratie werkt. Nadat dit is geverifieerd, kunt u de volgende stappen uitvoeren.

1.  In de Cloud App Security-portal, gaat u naar het instellingentandwiel en kies **Proxy**.

2. Klik in de rechterbovenhoek op het plusteken.

3. In **app toevoegen aan Proxy** venster, selecteer de app die u wilt toevoegen en klik vervolgens op **wizard starten**. 

 ![app toevoegen aan de Cloud App Security-Proxy](./media/proxy-add-app.png)

4. Upload het metagegevensbestand voor eenmalige aanmelding van uw app eenmalige aanmelding-instellingen. Als u een bestand met metagegevens geen hebt, klikt u op **gegevens handmatig invoeren** en geef de aangevraagde gegevens op basis van de wizard. 

 ![bestand met metagegevens voor eenmalige aanmelding toevoegen aan Cloud App Security-Proxy](./media/proxy-w-add-app.png)


5. In de portal van de identiteitsprovider, moet u de volgende stappen uitvoeren. In de meeste identiteit provider-portals wordt uitgevoerd onder **toepassingen**:

    1. Maak een nieuwe aangepaste SAML-app. Dit is vereist voor een nieuwe aangepaste app te maken, omdat er voor het wijzigen van URL's en SAML kenmerken toevoegen die mogelijk niet in de galerie met apps.
    
    2. Kopieer de configuratie voor eenmalige aanmelding van de bestaande app in de lijst met de id-provider in de nieuwe aangepaste app. Zorg ervoor dat de **id** (ook wel bekend als doelgroep of entiteit-ID) in de aangepaste app komt overeen met de **id** van de instellingen voor eenmalige aanmelding van de werkelijke app. Als uw id-provider niet u kunt met dezelfde **id** voor twee verschillende apps, na het kopiëren, het wijzigen van de id van de oorspronkelijke app.
    
    3. Alle gebruikers die momenteel zijn toegewezen aan de oorspronkelijke app om de nieuwe aangepaste app toewijzen.
    
    ![bestand met metagegevens voor eenmalige aanmelding toevoegen aan Cloud App Security-Proxy](./media/proxy-w-add-external-config.png)

5. Upload het metagegevensbestand voor eenmalige aanmelding van de id-provider. Als u een bestand met metagegevens geen hebt, klikt u op **gegevens handmatig invoeren** en geef de aangevraagde gegevens op basis van de wizard.  

 ![bestand met metagegevens voor eenmalige aanmelding toevoegen aan Cloud App Security-Proxy](./media/proxy-w-identity-provider.png)

6. Voer de volgende externe configuratiewijzigingen in de portal van de identiteitsprovider en klik vervolgens in de nieuwe aangepaste app die u hebt gemaakt:

    1. Kopieer de URL die is opgegeven in de Wizard. Vervolgens gaat u naar de portal van de identiteitsprovider en plak deze in de nieuwe aangepaste SAML app die u hebt gemaakt als het enkelvoudige aanmeldings-URL (of antwoord-URL).
    
    2. Kopieer de kenmerken en waarden die zijn opgegeven in de wizard Proxy en toe te voegen als SAML aangepaste kenmerken.
    
    3. Zorg ervoor dat de naam-id's die worden gebruikt door uw app in de e-mailadres zijn: dit nodig is om het inschakelen van de Cloud App Security Proxy beleidsregels worden toegepast op gebruikers.
    
    4. De instellingen voor uw nieuwe aangepaste app opslaan en klik op **volgende** in de Proxy-wizard.
 ![instellingen van de identiteit in de Cloud App Security Proxy bijwerken](./media/proxy-w-ip-external2.png)

4.  In de pagina van de app-instellingen voor eenmalige aanmelding, doet u het volgende:
    1. Back-up van uw huidige appinstellingen voor de.
    
    2. Kopieer de URL van de Proxy-wizard in de app SAML één aanmeldings-URL.
    
    3. Download het SAML voor Cloud App Security-certificaat voor de app.
    
    4. Uploaden van dit certificaat SAML in plaats van de oorspronkelijke map in de aangepaste app die u hebt gemaakt, en uw instellingen opslaan.
   
    5. Klik in de wizard Proxy **voltooien**.


Alle logboekbestanden in hun aanvragen aan uw app wordt binnen een paar minuten gerouteerd via de Cloud App Security-Proxy. 



### <a name="test-the-configuration"></a>Test de configuratie

1.  Probeer aan te melden bij de app. Als de aanmelding is mislukt, zorg er dan voor dat u de stappen voor de wizard Proxy correct voltooid. 

2.  In de Cloud App Security-portal onder **onderzoeken**, selecteer **activiteitenlogboek** en zorg ervoor dat er **logboek voor eenmalige aanmelding op** gebeurtenissen vastgelegd door de Proxy.



## <a name="see-also"></a>Zie ook  
[Werken met de Cloud App Security-Proxy](proxy-intro.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  