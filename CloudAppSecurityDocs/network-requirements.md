---
title: Cloud App Security netwerkvereisten | Microsoft Docs
description: Dit onderwerp beschrijft de IP-adressen en poorten die u wilt openen om te werken met Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/17/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4de606f2-a09e-4e48-a578-e223de8b5e69
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 82bdda2ab26fa1c954edb5186eeb37d909d65e64
ms.sourcegitcommit: d012fc1a099773bd9e9dc61906faab68dae0e996
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2017
---
# <a name="network-requirements"></a>Netwerkvereisten

Dit onderwerp bevat een lijst met poorten en IP-adressen die u wilt toestaan en witte lijst om te kunnen werken met Cloud App Security. 

Voor meer informatie over om te zien welke gegevens Cloud App Security center u bent verbonden, Zie [API-tokens](api-tokens.md)



## <a name="portal-access-siem-agent-authentication-gateway-and-log-collector"></a>Toegang tot portal, SIEM-agent, verificatie-gateway en logboekverzamelaar

Voor toegang tot portal en verificatie gateway en voor het inschakelen van Cloud App Security verbinding maken met uw SIEM, evenals de Cloud App Security inschakelen logboekverzamelaar uit te voeren is nodig om toe te voegen **uitgaande poort 443** voor het volgende IP-adres adressen van uw firewall witte lijst:  


> [!div class="mx-tableFixed"]
|Datacenter|IP-adressen|  
|----|----|
|US1|13.91.91.243<br></br>52.183.75.62|
|EU1|52.174.56.180<br></br>13.80.125.22|

## <a name="app-connector-access-and-external-dlp-integration"></a>Toegang tot de App-connector en externe DLP-integratie

Verbinding maken met apps van derden en integreren met externe DLP-oplossingen, Cloud App Security van verbinding maken met deze IP-adressen inschakelen:


> [!div class="mx-tableFixed"]
|Datacenter|IP-adressen|  
|----|----|
|US1|104.209.35.177<br></br>13.91.98.185<br></br>40.118.211.172<br></br>13.93.216.68<br></br>13.91.61.249<br></br>13.93.233.42<br></br>13.64.196.27<br></br>13.64.198.97<br></br>13.64.199.41<br></br>13.64.198.19|
|EU1|13.80.22.71<br></br>13.95.29.177<br></br>13.95.30.46|


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


    



  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  

   