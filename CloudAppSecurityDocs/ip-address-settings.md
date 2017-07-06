---
title: Apps verbinden om diepgaande zichtbaarheid en controle te krijgen met Cloud App Security | Microsoft Docs
description: In dit onderwerp wordt het proces beschreven voor het verbinden van apps met API-connectors met apps in de cloud van uw organisatie.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/3/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 7e718d77-aae7-4a3a-8421-5ba7cee7d67c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c8c9b63f4265876fc1de6a24c6576f917f9d2278
ms.sourcegitcommit: a0290ac2a662994f7771975ef6c20d0b47e9edd8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2017
---
Cloud App Security vereist toegang als volgt om te verbinden met uw netwerk. 

## <a name="cloud-app-security-system-ip-addresses"></a>Cloud App Security System IP-adressen

De volgende IP-adressen worden gebruikt door Cloud App Security verbinding maken met klantomgevingen. Dit is nodig om verbinding te maken met behulp van [ICAP](icap-stunnel.md) en verbinding te maken met App-connectors. Voor sommige apps, is het mogelijk nodig zijn de volgende IP-adressen toevoegen aan de lijst met geaccepteerde Cloud App Security voor het verzamelen van Logboeken en toegang verlenen voor de Cloud App Security-console. In sommige apps worden deze IP-adressen ook gebruikt voor het identificeren van Cloud App Security-activiteiten, zoals in de controlelogboeken van de service. 
  
-   Voor de logboeken:  
  
    104.209.35.177  
  
    13.91.98.185
 
    40.118.211.172

    13.93.216.68

    13.91.61.249

    13.93.233.42

    13.64.196.27

    13.64.198.97

    13.64.199.41

    13.64.198.19
  
  
## <a name="cas-portal-url-and-ip-addresses"></a>Portal URL's en IP-adressen van Certificeringsinstanties

De Cloud App Security-URL, poort 443 en IP-adressen worden gebruikt voor de klanttoegang tot portal, API-verbindingen wanneer u verbinding maakt to de APIs CAS logboekverzamelaar en SIEM-agent. 
  
     104.42.231.28  

 
  
> [!NOTE]  
>  Om updates te krijgen wanneer URL's en IP-adressen zijn gewijzigd moet u zich abonneren op RSS zoals uitgelegd in: [Office 365-URL's en IP-adresbereiken](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).  
  

  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  

   