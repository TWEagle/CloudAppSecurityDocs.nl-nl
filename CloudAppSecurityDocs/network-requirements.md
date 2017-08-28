---
title: Cloud App Security netwerkvereisten | Microsoft Docs
description: Dit onderwerp beschrijft de IP-adressen en poorten die u wilt openen om te werken met Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4de606f2-a09e-4e48-a578-e223de8b5e69
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: dac230e191c7c2d8159a2f373e6ef939fdd841a4
ms.sourcegitcommit: c3fda43ef6fe0d15f0eb9ea23a6f245bad8c371b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2017
---
# <a name="network-requirements"></a>Netwerkvereisten

Dit onderwerp bevat een lijst met poorten en IP-adressen die u wilt toestaan en geaccepteerde om te kunnen werken met Cloud App Security. 


## <a name="portal-access"></a>Toegang tot portal

Voor toegang tot portal is het nodig zijn voor de volgende IP-adressen toevoegen aan uw firewall goedgekeurde IP-adressen voor toegang tot de Cloud App Security-portal:  
  
104.42.231.28  


## <a name="app-connector-access"></a>Toegang tot de App-connector

Voor sommige apps van derden worden geopend door Cloud App Security, is het mogelijk nodig zijn de volgende IP-adressen toevoegen aan de lijst met geaccepteerde Cloud App Security voor het verzamelen van Logboeken en toegang verlenen voor de Cloud App Security-console:  
  
104.209.35.177  
13.91.98.185 40.118.211.172 13.93.216.68 13.91.61.249 13.93.233.42 13.64.196.27 13.64.198.97 13.64.199.41 13.64.198.19

> [!NOTE]
>Mogelijk ziet u deze IP-adressen in de activiteitenlogboeken van de leverancier omdat Cloud App Security beheeracties uitvoert en van deze IP-adressen scant. 
  

## <a name="siem-agent-and-log-collector"></a>SIEM-agent en de logboekverzamelaar

Om in te schakelen Cloud App Security verbinding maken met uw SIEM en kunt u de logboekverzamelaar Cloud App Security om uit te voeren, is het nodig zijn om te openen:

- Uitgaande poort 443-104.42.231.28

## <a name="external-dlp-integration"></a>Externe DLP-integratie

Open in de volgorde voor Cloud App Security gegevens via uw stunnel verzenden naar uw server ICAP uw firewall DMZ kan het externe IP-adressen die door Cloud App Security gebruikt met een dynamische bronpoortnummer of bereik. 

1.  Adressen van bron: dit moeten goedgekeurde lijst zoals hierboven vermeld voor apps voor API-connector van derden
2.  TCP-bronpoort: dynamische
3.  Bestemming adres(sen): één of twee IP-adres van de stunnel verbonden met de externe ICAP-server
4.  Doel-TCP-poort: zoals gedefinieerd in uw netwerk

> [!NOTE] 
> Het poortnummer stunnel is standaard ingesteld op 11344. U kunt dit wijzigen in een andere poort, indien nodig, maar zorg ervoor dat Noteer het nieuwe poortnummer.



  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  

   