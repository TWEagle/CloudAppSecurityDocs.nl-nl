---
title: Apps verbinden om diepgaande zichtbaarheid en controle te krijgen met Cloud App Security | Microsoft Docs
description: In dit onderwerp wordt het proces beschreven voor het verbinden van apps met API-connectors met apps in de cloud van uw organisatie.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/9/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 3b15ba46-ac9c-4b4f-aefc-137edc903bc1
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 437504a73f9b3ae4a8a21b379356934b76d2430b
ms.sourcegitcommit: 4daaec64c5a773cd092d94ee17ca05dfbd9e92c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/09/2017
---
# <a name="connect-apps"></a>Apps koppelen 
App-connectors maken gebruik van de API's van app-providers. Hierdoor zijn de apps waarmee u verbinding maakt, beter zichtbaar en controleerbaar voor Cloud App Security.  
  
Cloud App Security maakt gebruik van de API's die door de cloudprovider worden verstrekt; elke service heeft een eigen framework en API-beperkingen. Cloud App Security heeft de services gebruikt om het gebruik van de API's te optimaliseren en om de beste prestaties te leveren. Rekening houdend met de andere beperkingen die de services opleggen aan de API's (zoals beperking, API-limieten, dynamisch verschuiven van API-tijdsvensters, enzovoort), maken de Cloud App Security-engines gebruik van de toegestane capaciteit. Bepaalde bewerkingen, zoals het scannen van alle bestanden in de tenant vereisen een grote hoeveelheid API's en worden daarom verdeeld over een langere periode. Ga ervan uit dat sommige beleidsregels gedurende enkele uren tot dagen worden uitgevoerd.  
  
## <a name="how-it-works"></a>Hoe het werkt  
Cloud App Security wordt geïmplementeerd met systeembeheerdersbevoegdheden voor volledige toegang tot alle objecten in uw omgeving.  
  
De stroom voor App-connector is als volgt:
1. De verificatiemachtigingen worden gescand en opgeslagen met Cloud App Security.
2.  De gebruikerslijst wordt aangevraagd met Cloud App Security. Wanneer de scan voor de eerste keer wordt uitgevoerd, kan het enige tijd duren voordat de scan is voltooid. Nadat de gebruikersscan is voltooid, worden activiteiten en bestanden gescand met Cloud App Security. Zodra de scan wordt gestart, zijn sommige activiteiten beschikbaar in de Cloud App Security. 
4. Nadat de gebruikersaanvraag is voltooid, worden gebruikers, groepen, activiteiten en bestanden periodiek gescand met Cloud App Security. Na de eerste volledige scan zijn alle activiteiten beschikbaar. 
 
Dit kan enige tijd duren afhankelijk van de grootte van de tenant, het aantal gebruikers en de grootte en het aantal van de bestanden die moeten worden gescand. 
 
Afhankelijk van de app waarmee u verbinding maakt (zie de onderstaande tabel), maakt een API-verbinding het volgende mogelijk:  
  
-   **Accountgegevens**  
  
     Zichtbaarheid van gebruikers, accounts, profielinformatie, statusgroepen (Onderbroken, Actief, Uitgeschakeld) en bevoegdheden.  
  
-   **Audittrail**  
  
     Zichtbaarheid van de activiteiten van de gebruiker, de activiteiten van de beheerder, aanmeldactiviteit.  
  
-   **Gegevens scannen**  
  
     Scannen van niet-gestructureerde gegevens op twee manieren: - periodiek (elke 12 uur) en realtime (telkens wanneer een wijziging wordt gedetecteerd).  
  
-   **App-machtigingen**  
  
     Zichtbaarheid van gepubliceerde tokens en de bijbehorende machtigingen.  
  
-   **Accountbeheer**  
  
     De mogelijkheid om gebruikers te onderbreken, wachtwoorden in te trekken enz.  
  
-   **Gegevensbeheer**  
  
     De mogelijkheid om bestanden, inclusief bestanden in de prullenbak, in quarantaine plaatsen en bestanden te overschrijven.  
  
-   **Beheer van app-machtigingen**  
  
     Mogelijkheid om tokens te verwijderen.  
  
De volgende tabel geeft per cloud-app aan welke vaardigheden met App-connectors worden ondersteund:  

> [!div class="mx-tableFixed"]
||**Office 365**|**Box**|**Okta**|**G Suite**|**ServiceNow**|**Salesforce**|**Dropbox**|**AWS**|  
|-|-|-|-|-|-|-|-|-|  
|**Lijst van accounts**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**Groep**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**Bevoegdheden**|✔|✔|Niet ondersteund door provider|✔|✔|✔|✔||  
|**Gebruikersbeheer**|✔|✔||✔|Binnenkort beschikbaar|Binnenkort beschikbaar|Binnenkort beschikbaar||  
|**Aanmeldingsactiviteiten**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**Gebruikersactiviteiten**|✔*|✔|✔|✔ - Onbeperkte Google-licentie vereist|Gedeeltelijke|Ondersteund met Salesforce Shield|✔|Niet van toepassing|  
|**Beheeractiviteiten**|✔|✔|✔|✔|Gedeeltelijke|✔|✔|✔|  
|**Periodiek scannen van bestanden**|✔|✔|Niet van toepassing|✔|✔|✔|✔|Binnenkort beschikbaar|  
|**NRT-bestandsscan (Near-Realtime)**|✔|✔|Niet van toepassing|✔ - Onbeperkte Google-licentie vereist|||Binnenkort beschikbaar||  
|**Beheer van delen**|✔|✔|Niet van toepassing|✔|Niet van toepassing||✔||  
|**Quarantaine**|✔|✔|Niet van toepassing|Binnenkort beschikbaar|||Binnenkort beschikbaar||  
|**App-machtigingen weergeven**|✔|Niet ondersteund door provider|Niet van toepassing|✔||✔|Niet ondersteund door provider||  
|**App-machtigingen intrekken**|✔||Niet van toepassing|✔||✔|Niet van toepassing||  
  
  
## <a name="prerequisites"></a>Vereisten  

- Voor sommige apps, is het mogelijk nodig witte lijst IP-adressen inschakelen Cloud App Security voor het verzamelen van Logboeken en toegang verlenen voor de Cloud App Security-console. Zie voor meer informatie [vereisten](network-requirements.md).

- Voor elke app die u wilt verbinden met de Cloud App Security-API-integratie, kunt u het beste een beheerdersserviceaccount maken dat is toegewezen aan Cloud App Security.  
  
> [!NOTE]  
>  Om updates te krijgen wanneer URL's en IP-adressen zijn gewijzigd moet u zich abonneren op RSS zoals uitgelegd in: [Office 365-URL's en IP-adresbereiken](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).  
  
Om App-Connectors te gebruiken dient u ervoor te zorgen dat u over het volgende beschikt voor elke specifieke app:  
  
|App|Licentietype|Gebruiker|  
|---------|------------------|----------|  
|Box|Zakelijk|U wordt aangeraden verbinding met Box te maken als een beheerder. Als u verbinding maakt als een co-beheerder, zijn niet alle gegevens zichtbaar. Zorg ervoor dat u alle machtigingen selecteert als u verbinding maakt als een co-beheerder.|  
|G Suite|G Suite Unlimited gewenst<br /><br /> G Suite Enterprise (minimaal)|Superbeheerder|  
|Office 365||Globale beheerder|  
|AWS||Nieuw aangemaakte gebruiker|  
|Dropbox|Business/Enterprise|Beheer|  
|Okta|Enterprise (geen proefversie)|Beheer|  
|Exchange||Globale beheerder|  
|ServiceNow|Eureka en hoger|Beheer en RestAPI-rol|  
|SalesForce||Beheer|  
  

**ExpressRoute**  
  
Cloud App Security is geïmplementeerd in Azure en volledig geïntegreerd met [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Alle interacties met de Cloud App Security-apps en het verkeer dat wordt verzonden naar Cloud App Security, met inbegrip van het uploaden van detectielogboeken, verlopen via **openbare peering** van ExpressRoute voor verbeterde latentie, prestaties en beveiliging. Er zijn geen configuratiestappen vereist door de klant.  
Zie voor meer informatie over openbare peering [ExpressRoute-circuits en routeringsdomeinen](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/).  
  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  

## <a name="check-out-this-video"></a>Bekijk deze video.
[Microsoft Cloud App Security – REST-API en Tokens](https://channel9.msdn.com/Shows/Microsoft-Security/Microsoft-Cloud-App-Security--REST-APIs-and-Tokens)  
   