---
title: Cloud App Security netwerkvereisten | Microsoft Docs
description: Dit onderwerp beschrijft de IP-adressen en poorten die u wilt openen om te werken met Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/19/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4de606f2-a09e-4e48-a578-e223de8b5e69
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: bb6fab3aeb7e9f758ecc63969c05ab4137e378e7
ms.sourcegitcommit: 8132433d8a4bd15571ef76752c28de136ec95bd0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/19/2017
---
# <a name="network-requirements"></a>Netwerkvereisten

Dit onderwerp bevat een lijst met poorten en IP-adressen die u wilt toestaan en witte lijst om te kunnen werken met Cloud App Security. 


## <a name="view-your-data-center"></a>Weergeven van uw datacenter

Sommige van de onderstaande vereisten zijn afhankelijk van op welke Datacenter u met verbonden bent. 

Als u wilt zien welke datacentrum u een verbinding met:

1. Klik in de Cloud App Security-portal op de **?** in de menubalk en selecteer **over**. 

    ![Klik op over](./media/about-menu.png)

2. In het scherm van de versie van Cloud App Security ziet u de regio en het datacenter.

    ![Weergeven van uw datacenter](./media/data-center.png)

## <a name="portal-access"></a>Toegang tot portal

Voor toegang tot de Cloud App Security-portal, voegt u **uitgaande poort 443** voor de volgende IP-adressen en DNS-namen van uw firewall witte lijst:  


> [!div class="mx-tableFixed"]
|Datacenter|IP-adressen|DNS-naam|
|----|----|----|
|ONS|13.80.125.22<br></br>52.183.75.62<br></br>13.91.91.243|Portal.cloudappsecurity.com<br></br>\*. portal.cloudappsecurity.com <br></br>\*. us.portal.cloudappsecurity.com|
|US2|13.80.125.22<br></br>52.183.75.62<br></br>52.184.165.82|Portal.cloudappsecurity.com<br></br>\*. portal.cloudappsecurity.com <br></br>\*. us2.portal.cloudappsecurity.com|
|EU|13.80.125.22<br></br>52.183.75.62<br></br>52.174.56.180|Portal.cloudappsecurity.com<br></br>\*. portal.cloudappsecurity.com <br></br>\*. eu.portal.cloudappsecurity.com|


>[!NOTE]
>In plaats van een jokerteken (\*) kunt u de URL van uw specifieke tenant openen, bijvoorbeeld op basis van de bovenstaande schermafbeelding kunt u openen: mod244533.us.portal.cloudappsecurity.com

## <a name="siem-agent-connection"></a>Verbinding van SIEM-agent

Toevoegen zodat Cloud App Security verbinding maken met uw SIEM **uitgaande poort 443** van de volgende IP-adressen van uw firewall witte lijst:  


> [!div class="mx-tableFixed"]
|Datacenter|IP-adressen|  
|----|----|
|ONS|13.91.91.243|
|US2|52.184.165.82|
|EU|52.174.56.180|

## <a name="app-connector-access-and-external-dlp-integration"></a>Toegang tot de App-connector en externe DLP-integratie

Als u wilt verbinding maken met apps van derden en integreren met externe DLP-oplossingen, inschakelen Cloud App Security verbinding worden gemaakt vanaf deze IP-adressen:


> [!div class="mx-tableFixed"]
|Datacenter|IP-adressen|  
|----|----|
|ONS|13.91.91.243 <br></br> 104.209.35.177 <br></br> 13.91.98.185 <br></br> 40.118.211.172 <br></br> 13.93.216.68 <br></br> 13.91.61.249 <br></br> 13.93.233.42 <br></br> 13.64.196.27 <br></br> 13.64.198.97 <br></br> 13.64.199.41 <br></br> 13.64.198.19|
|US2|52.184.165.82<br></br> 40.84.4.93 <br></br> 40.84.4.119 <br></br> 40.84.2.83 |
|EU|52.174.56.180<br></br>13.80.22.71<br></br>13.95.29.177<br></br>13.95.30.46|


### <a name="app-connector"></a>App-connector
Voor sommige apps van derden worden geopend door Cloud App Security, kunnen deze IP-adressen worden gebruikt om in te schakelen van Cloud App Security voor het verzamelen van Logboeken en toegang verlenen voor de Cloud App Security-console. 

> [!NOTE]
>Mogelijk ziet u deze IP-adressen in de activiteitenlogboeken van de leverancier omdat Cloud App Security beheeracties uitvoert en van deze IP-adressen scant. 
  

### <a name="dlp-integration"></a>DLP-integratie

Open uw firewall DMZ kan deze IP-adressen met een dynamische bronpoortnummer of bereik in de volgorde voor Cloud App Security gegevens via uw stunnel verzenden naar uw server ICAP. 

1.  Adressen van bron: dit moeten wit weergegeven als hierboven vermeld voor apps voor API-connector van derden
2.  TCP-bronpoort: dynamische
3.  Bestemming adres(sen): één of twee IP-adres van de stunnel verbonden met de externe ICAP-server
4.  Doel-TCP-poort: zoals gedefinieerd in uw netwerk

> [!NOTE] 
> Het poortnummer stunnel is standaard ingesteld op 11344. U kunt dit wijzigen in een andere poort, indien nodig, maar zorg ervoor dat Noteer het nieuwe poortnummer.

## <a name="email-server"></a>E-mailserver

Het IP-adres van de Cloud App Security-specifieke e-mailadres is: 

198.2.134.139 (mail1.cloudappsecurity.com)

Zorg ervoor dat aan de lijst met geaccepteerde dit IP-adres met uw service tegen ongewenste e-mail waarmee meldingen worden verzonden.
    
## <a name="log-collector"></a>Logboekverzamelaar 

Cloud Discovery-functies met een logboekverzamelaar inschakelen en de Shadow IT detecteren in uw organisatie, is het nodig zijn voor het openen van het volgende:

- Toestaan dat de logboekverzamelaar binnenkomend FTP- en Syslog-verkeer ontvangen.
- De logboekverzamelaar initiëren uitgaand verkeer naar de portal (bijvoorbeeld contoso.cloudappsecurity.com) op poort 443 toestaan.
- De logboekverzamelaar initiëren uitgaand verkeer naar Azure blob storage op poort 80 en 443 toestaan:
   
    |Datacenter|URL|
    |----|----|
    |ONS|https://adaprodconsole.BLOB.Core.Windows.NET/|
    |US2|https://prod03use2console1.BLOB.Core.Windows.NET/|
    |EU|https://prod02euwconsole1.BLOB.Core.Windows.NET/|

> [!NOTE]
> Als uw firewall vereist dat een lijst met statische IP-adressen toegang en biedt geen ondersteuning voor whitelisting op basis van de URL, staan de logboekverzamelaar initiëren uitgaand verkeer naar de [Microsoft Azure datacenter IP-adresbereiken](https://www.microsoft.com/download/details.aspx?id=41653) op poort 443.




## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  

   