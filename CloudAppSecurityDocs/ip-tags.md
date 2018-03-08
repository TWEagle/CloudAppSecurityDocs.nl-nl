---
title: IP-bereiken en -tags instellen | Microsoft Docs
description: "Dit onderwerp bevat instructies voor het werken met IP-tags en IP-categorieën."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/7/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: bbf54f66-4ce2-428c-afc8-b5a64277014f
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d05b1151383526ff37821c7d15abbd9b0f4f4f41
ms.sourcegitcommit: 9de7ed2224aeed049fc2a87e52307988f8837eeb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/08/2018
---
#  <a name="IPtagsandRanges"></a>Werken met IP-bereiken en -tags

Eenvoudig kunt herkennen bekende IP-adressen, zoals uw fysieke office IP-adressen, moet u IP-adresbereiken, waarmee u kunt taggen en indelen op de juiste wijze instellen en aanpassen van de manier waarop Logboeken en waarschuwingen worden weergegeven en worden onderzocht. <br></br>  
Elke groep met IP-adresbereiken kan worden ingedeeld op basis van een vooraf gedefinieerde lijst met IP-categorieën of worden getagd met zelfgemaakte IP-tags. Met deze instelling kunt u openbare gegevens over de geografische locatie overschrijven op basis van uw interne netwerkkennis.  
  
IPv4 en IPv6 worden ondersteund.  
  
Cloud App Security is vooraf geconfigureerd met ingebouwde tags voor de volgende IP-adressen: 
- Native client
- Verouderd besturingssysteem
- Beheerde apparaten
- Anonieme proxy
- Botnet (wanneer een activiteit is uitgevoerd door een botnet, ontvangt u een koppeling voor meer informatie over de specifieke botnet)
- Tor
- Compatibel apparaat
- Geverifieerd apparaat
- Imiteren

Raadpleeg de ID in de Cloud App Security API-documentatie voor het gebruik van deze ingebouwde tags als onderdeel van een zoekopdracht. 

> [!NOTE]
> U kunt IP-adresbereiken bulksgewijs toevoegen door het maken van een script met de **IP-adresbereiken API**, die kan worden gevonden in de Cloud App Security-portalmenubalk door te klikken op het vraagteken en vervolgens **API-documentatie**.


Ingebouwde IP-Adreslabels en aangepaste IP-tags worden beschouwd als hiërarchisch met aangepaste IP-tags voorrang heeft op de ingebouwde IP-tags. Bijvoorbeeld, als een IP-adres wordt gemarkeerd als **riskant** op basis van dreigingen, maar er is een aangepaste IP-code die wordt geïdentificeerd als **zakelijk** aangepaste categorie en labels voorrang.

Klik in de menubalk op het Instellingenpictogram ![het Instellingenpictogram](./media/settings-icon.png "Instellingenpictogram") en selecteer **IP-adresbereiken**. Klik op het plusteken om IP-adresbereiken toevoegen en instellen van de volgende velden:  
  
> [!NOTE]  
> - De locatie en de geregistreerde provider overschrijven de standaardinstellingen.   
> - IP-tags worden echter toegevoegd aan de activiteit zonder gegevens te overschrijven.  
  
1.  Geef uw IP-adresbereik een **naam**. De naam niet wordt weergegeven in het activiteitenlogboek, deze wordt alleen gebruikt voor het beheren van uw IP-adresbereik.  
  
     Als u het IP-adresbereik wilt opnemen in een IP-categorie, selecteert u een categorie in de vervolgkeuzelijst.  
  
2.  Voer het **IP-adresbereik** in dat u wilt configureren en klik vervolgens op de knop met het plusteken (+). U kunt zoveel IP-adressen en subnetten toevoegen als u wilt met behulp van de notatie voor netwerkvoorvoegsels (ook wel CIDR-notatie genoemd), bijvoorbeeld 192.168.1.0/32.  
  
3.  **Categorieën** gemakkelijk herkennen activiteiten uit interessante IP-adressen worden gebruikt. De categorieën zijn beschikbaar in de portal vereisen nog wel Gebruikersconfiguratie om te bepalen welke IP-adressen zijn opgenomen in elke categorie, met uitzondering van de categorie "Riskant", waaronder twee IP-tags - anonieme proxy en Tor.  
  
     De volgende IP-categorieën zijn beschikbaar:  
  
    -   **Beheer**: dit moeten alle IP-adressen van uw beheerders zijn.  
  
    -  **Cloudprovider**: dit moeten de IP-adressen die worden gebruikt door de cloudprovider.
  
    -   **Zakelijke**: dit moeten alle IP-adressen van uw interne netwerk, uw filialen en uw zwervende Wi-Fi-adressen.  
  
    -   **Riskant**: dit moeten alle IP-adressen zijn die u beschouwt als riskant. Dit kunnen verdachte IP-adressen zijn die u in het verleden hebt bekeken, IP-adressen in de netwerken van uw concurrenten enzovoort.  
  
    -   **VPN**: dit moeten alle IP-adressen zijn die u voor externe werknemers gebruikt.  
4.  Om de activiteiten van deze IP-adressen te **taggen**, voert u een tag in. Als u een woord in het vak invoert, wordt de tag gemaakt. Nadat u al een geconfigureerde tag hebt, kunt u eenvoudig deze toevoegen aan extra IP-adresbereiken door deze te kiezen uit de lijst. U kunt zoveel IP-tags toevoegen als u wilt voor elk bereik. IP-tags kunnen worden gebruikt tijdens het samenstellen van beleid.  Naast de IP-tags die u configureert, heeft Cloud App Security ingebouwde tags die u niet kunt configureren. Onder [IP tags filter](activity-filters.md) (Filter voor IP-tags) wordt de lijst met tags weergegeven.  
  
5.  Als u de (ISP-) velden van de **locatie** of organisatie voor deze adressen wilt overschrijven, voert u een nieuwe waarde in. Als u bijvoorbeeld een IP-adres hebt dat wordt beschouwd als Iers, maar u weet dat het adres zich in de Verenigde Staten bevindt, dan kunt u deze instelling overschrijven.  
  
6.  Voer een **geregistreerde provider** in. Overschrijft dit de gegevens in uw activiteiten  
 
7.   Wanneer u klaar bent, klikt u op **Maken**.  
  
     ![newipaddress-bereik](./media/newipaddress-range.png "newipaddress-bereik")  
  
  
    
## <a name="see-also"></a>Zie ook  
[Cloud Discovery instellen](set-up-cloud-discovery.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  