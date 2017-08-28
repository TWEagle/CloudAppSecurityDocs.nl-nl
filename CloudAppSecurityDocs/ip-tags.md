---
title: IP-bereiken en -tags instellen | Microsoft Docs
description: "Dit onderwerp bevat instructies voor het werken met IP-tags en IP-categorieën."
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: bbf54f66-4ce2-428c-afc8-b5a64277014f
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: edf852bf90a0d4b9345f1beb675ef5ee3c4f941d
ms.sourcegitcommit: c3fda43ef6fe0d15f0eb9ea23a6f245bad8c371b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2017
---
#  <a name="IPtagsandRanges"></a>Werken met IP-bereiken en -tags

Om bekende IP-adressen, zoals uw fysieke IP-adressen van kantoor, eenvoudig te kunnen herkennen, moet u IP-adresbereiken instellen waarmee u ze op de juiste wijze kunt taggen en indelen en de manier waarop logboeken en waarschuwingen worden weergegeven, kunt aanpassen.   
Elke groep met IP-adresbereiken kan worden ingedeeld op basis van een vooraf gedefinieerde lijst met IP-categorieën of worden getagd met zelfgemaakte IP-tags. Met deze instelling kunt u openbare gegevens over de geografische locatie overschrijven op basis van uw interne netwerkkennis.  
  
IPv4 en IPv6 worden ondersteund.  
  
Cloud App Security is vooraf geconfigureerd met ingebouwde tags voor de volgende IP-adressen: 
- Native client
- Verouderd besturingssysteem
- Beheerde apparaten
- Anonieme proxy
- Botnet (als een activiteit is uitgevoerd door een botnet, ontvangt u een koppeling voor meer informatie over de specifieke botnet)
- Tor
- Compatibel apparaat
- Geverifieerd apparaat
- Imiteren

Raadpleeg de ID in de Cloud App Security API-documentatie voor het gebruik van deze ingebouwde tags als onderdeel van een zoekopdracht. 

> [!NOTE]
> U kunt IP-adresbereiken bulksgewijs toevoegen door het maken van een script met de [IP-adresbereiken API](https://portal.cloudappsecurity.com/api-docs/)


Ingebouwde IP-Adreslabels en aangepaste IP-tags worden beschouwd als hiërarchisch met aangepaste IP-tags voorrang heeft op de ingebouwde IP-tags. Bijvoorbeeld, als een IP-adres wordt het gelabeld als **riskant** op basis van dreigingen, maar er is een aangepaste IP-code die wordt geïdentificeerd als **zakelijk** aangepaste categorie en labels voorrang.

Klik in de menubalk op het pictogram Instellingen ![pictogram instellingen](./media/settings-icon.png "pictogram instellingen") en selecteer **IP-adresbereiken**. Klik op **+IP-adresbereik toevoegen** en stel het volgende in:  
  
> [!NOTE]  
>  De locatie en de geregistreerde provider overschrijven de standaardinstellingen.   
> IP-tags worden echter toegevoegd aan de activiteit zonder gegevens te overschrijven.  
  
1.  Geef uw IP-adresbereik een **naam**. De naam wordt niet weergegeven in het activiteitenlogboek, maar wordt alleen gebruikt voor het beheren van uw IP-adresbereik.  
  
     Als u het IP-adresbereik wilt opnemen in een IP-categorie, selecteert u een categorie in de vervolgkeuzelijst.  
  
2.  Voer het **IP-adresbereik** in dat u wilt configureren en klik vervolgens op de knop met het plusteken (+). U kunt zoveel IP-adressen en subnetten toevoegen als u wilt met behulp van de notatie voor netwerkvoorvoegsels (ook wel CIDR-notatie genoemd), bijvoorbeeld 192.168.1.0/32.  
  
3.  Als u de (ISP-) velden van de **locatie** of organisatie voor deze adressen wilt overschrijven, voert u een nieuwe waarde in. Als u bijvoorbeeld een IP-adres hebt dat wordt beschouwd als Iers, maar u weet dat het adres zich in de Verenigde Staten bevindt, dan kunt u deze instelling overschrijven.  
  
4.  Voer een **geregistreerde provider** in. Hierdoor worden de gegevens in uw activiteiten overschreven.  
  
5.  Om de activiteiten van deze IP-adressen te **taggen**, voert u een tag in. Als u een woord in het vak invoert, wordt de tag gemaakt. Als u al een geconfigureerde tag hebt, kunt u deze eenvoudig toevoegen aan extra IP-adresbereiken door de tag te kiezen uit de lijst. U kunt zoveel IP-tags toevoegen als u wilt voor elk bereik. IP-tags kunnen worden gebruikt tijdens het samenstellen van beleid.  Naast de IP-tags die u configureert, heeft Cloud App Security ingebouwde tags die u niet kunt configureren. Onder [IP tags filter](activity-filters.md) (Filter voor IP-tags) wordt de lijst met tags weergegeven.  
  
6.  **IP-categorieën** worden gebruikt om activiteiten uit interessante IP-adressen eenvoudig te herkennen. De categorieën die beschikbaar zijn in de portal vereisen nog wel gebruikersconfiguratie om te bepalen welke IP-adressen worden opgenomen in elke categorie, met uitzondering van de categorie Riskant, die twee IP-tags (Anonieme proxy en Tor) omvat.  
  
     De volgende IP-categorieën zijn beschikbaar:  
  
    -   **Beheer**: dit moeten alle IP-adressen van uw beheerders zijn.  
  
    -   **Intern**: dit moeten alle IP-adressen van uw interne netwerk, uw filialen en uw Wifi-roamingadressen zijn.  
  
    -   **Riskant**: dit moeten alle IP-adressen zijn die u beschouwt als riskant. Dit kunnen verdachte IP-adressen zijn die u in het verleden hebt bekeken, IP-adressen in de netwerken van uw concurrenten enzovoort.  
  
    -   **VPN**: dit moeten alle IP-adressen zijn die u voor externe werknemers gebruikt.  
  
    -   **Cloudproxy**: dit moet het IP-adres zijn van uw proxyserver in de cloud.  
  
7.  Wanneer u klaar bent, klikt u op **Maken**.  
  
     ![newipaddress-bereik](./media/newipaddress-range.png "newipaddress-bereik")  
  
  
    
## <a name="see-also"></a>Zie ook  
[Cloud Discovery instellen](set-up-cloud-discovery.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  