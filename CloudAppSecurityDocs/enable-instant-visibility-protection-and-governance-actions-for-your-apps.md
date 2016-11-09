---
title: Directe zichtbaarheid, bescherming en beheeracties voor uw apps inschakelen | Microsoft Docs
description: In dit onderwerp wordt het proces beschreven voor het inschakelen van API-connectors voor apps in de cloud van uw organisatie.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 3b15ba46-ac9c-4b4f-aefc-137edc903bc1
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: e74cd96f9bf8537f230dcb58715492bc6fccd2f0


---

# <a name="enable-instant-visibility-protection-and-governance-actions-for-your-apps"></a>Directe zichtbaarheid, bescherming en beheeracties voor uw apps inschakelen
App-connectors maken gebruik van de API's van app-providers. Hierdoor zijn de apps waarmee u verbinding maakt, beter zichtbaar en controleerbaar voor Cloud App Security.  
  
Cloud App Security maakt gebruik van de API's die door de cloudprovider worden verstrekt; elke service heeft een eigen framework en API-beperkingen. Cloud App Security heeft de services gebruikt om het gebruik van de API's te optimaliseren en om de beste prestaties te leveren. Rekening houdend met de andere beperkingen die de services opleggen aan de API's (zoals beperking, API-limieten, dynamisch verschuiven van API-tijdsvensters, enzovoort), maken de Cloud App Security-engines gebruik van de toegestane capaciteit. Bepaalde bewerkingen, zoals het scannen van alle bestanden in de tenant vereisen een grote hoeveelheid API's en worden daarom verdeeld over een langere periode. Ga ervan uit dat sommige beleidsregels gedurende enkele uren tot dagen worden uitgevoerd.  
  
**ExpressRoute**  
  
Cloud App Security is geïmplementeerd in Azure en volledig geïntegreerd met [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Alle interacties met de Cloud App Security-apps en het verkeer dat wordt verzonden naar Cloud App Security, met inbegrip van het uploaden van detectielogboeken, verlopen via **openbare peering** van ExpressRoute voor verbeterde latentie, prestaties en beveiliging. Er zijn geen configuratiestappen vereist door de klant.  
Zie voor meer informatie over openbare peering [ExpressRoute-circuits en routeringsdomeinen](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/).  
  
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
  
||||||||||  
|-|-|-|-|-|-|-|-|-|  
||**Office 365**|**Box**|**Okta**|**Google Apps**|**ServiceNow**|**Salesforce**|**Dropbox**|**AWS**|  
|**Lijst van accounts**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**Groep**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**Bevoegdheden**|✔|✔|Niet ondersteund door provider|✔|✔|✔|✔||  
|**Gebruikersbeheer**|✔|✔||✔|Binnenkort beschikbaar|Binnenkort beschikbaar|Binnenkort beschikbaar||  
|**Aanmeldingsactiviteiten**|✔|✔|✔|✔|✔|✔|✔|✔|  
|**Gebruikersactiviteiten**|✔*|✔|✔|✔ - Onbeperkte Google-licentie vereist|Gedeeltelijke|Ondersteund met Salesforce Shield|✔|Niet van toepassing|  
|**Beheeractiviteiten**|✔|✔|✔|✔|Gedeeltelijke|✔|✔|✔|  
|**Periodiek scannen van bestanden**|✔|✔|Niet van toepassing|✔|✔|✔|✔|Binnenkort beschikbaar|  
|**NRT-bestandsscan (Near-Realtime)**|Binnenkort beschikbaar|✔|Niet van toepassing|✔ - Onbeperkte Google-licentie vereist|||Binnenkort beschikbaar||  
|**Beheer van delen**|✔|✔|Niet van toepassing|✔|Niet van toepassing||✔||  
|**Quarantaine**|✔|✔|Niet van toepassing|Binnenkort beschikbaar|||Binnenkort beschikbaar||  
|**App-machtigingen weergeven**|✔|Niet ondersteund door provider|Niet van toepassing|✔||✔|Niet ondersteund door provider||  
|**App-machtigingen intrekken**|✔||Niet van toepassing|✔||✔|Niet van toepassing||  
  
\* App-connector voor Office 365 omvat beheeractiviteit voor Exchange Online. Als u gebruikersactiviteit wilt toevoegen voor Exchange Online, moet u de Exchange Online connector afzonderlijk implementeren.  
  
## <a name="prerequisites"></a>Vereisten  
Voor bepaalde apps kan het nodig zijn de volgende IP-adressen toe te voegen aan de lijst met geaccepteerde IP-adressen, zodat Cloud App Security de logboeken kan verzamelen en de Cloud App Security-console toegang kan krijgen:  
  
-   Voor de logboeken:  
  
     104.209.35.177  
  
     13.91.98.185  
  
-   Voor de console:  
  
     104.42.231.28  
  
> [!NOTE]  
>  Om updates te krijgen wanneer URL's en IP-adressen zijn gewijzigd moet u zich abonneren op RSS zoals uitgelegd in: [Office 365-URL's en IP-adresbereiken](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).  
  
Om App-Connectors te gebruiken dient u ervoor te zorgen dat u over het volgende beschikt voor elke specifieke app:  
  
|App|Licentietype|Gebruiker|  
|---------|------------------|----------|  
|Box|Zakelijk|U wordt aangeraden verbinding met Box te maken als een beheerder. Als u verbinding maakt als een co-beheerder, zijn niet alle gegevens zichtbaar. Zorg ervoor dat u alle machtigingen selecteert als u verbinding maakt als een co-beheerder.|  
|Google Apps|Google Apps Unlimited gewenst<br /><br /> Google Apps Enterprise (minimaal)|Superbeheerder|  
|Office 365||Globale beheerder|  
|AWS||Nieuw aangemaakte gebruiker|  
|Dropbox|Business/Enterprise|Beheer|  
|Okta|Enterprise (geen proefversie)|Beheer|  
|Exchange||Globale beheerder|  
|ServiceNow|Eureka en hoger|Beheer en RestAPI-rol|  
|SalesForce||Beheer|  
  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
   


<!--HONumber=Oct16_HO4-->


