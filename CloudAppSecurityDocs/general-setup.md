---
title: Geef de instellingen van uw organisatie op in de Cloud App Security-portal voor de beste resultaten | Microsoft Docs
description: In dit artikel wordt uitgelegd hoe u informatie over uw organisatie opgeeft in Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/3/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2e7e57b0-db54-4d75-896c-4700dd9abe48
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: ff8f123a1bab8831071865422f8afa34e20e416b
ms.sourcegitcommit: c47fd92c71028ede8840e0766f20eb0ad2898e70
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="basic-setup"></a>Basisconfiguratie
De volgende procedure bevat instructies voor het aanpassen van de Cloud App Security-portal.

## <a name="prerequisites"></a>Vereisten 
Voor toegang tot portal is het nodig zijn voor de volgende IP-adressen toevoegen aan uw Firewall goedgekeurde IP-adressen voor toegang tot de Cloud App Security-portal:  
  
- 104.42.231.28  
  
> [!NOTE]  
>  Om updates te krijgen wanneer URL's en IP-adressen zijn gewijzigd moet u zich abonneren op RSS zoals uitgelegd in: [Office 365-URL's en IP-adresbereiken](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).  
  
## <a name="set-up-the-portal"></a>De portal instellen  
  
1.  Klik in de Cloud App Security-portal in de menubalk op het instellingentandwiel ![Instellingenpictogram](./media/settings-icon.png "Instellingenpictogram") en selecteer **instellingen** om gegevens van uw organisatie te configureren.     

3.  Bij **Organisatiegegevens** is het van belang dat u een **Weergavenaam organisatie** opgeeft voor uw organisatie. Deze wordt weergegeven op het e-mailberichten en webpagina's die uit het systeem worden verzonden.  
  
4. Geef een **omgevingsnaam** (tenant) op. Dit is vooral belangrijk als u meerdere tenants beheert.  
  
4. Het is ook mogelijk om een **Logo** die wordt weergegeven in e-mailmeldingen verzonden uit het systeem en de webpagina's die uit het systeem worden verzonden. Het logo moet een PNG-bestand zijn met een maximale grootte van 150 x 50 pixels op een transparante achtergrond.  

4.  Denk eraan om een lijst met uw **Beheerde domeinen** toe te voegen. Deze stap is cruciaal omdat in Cloud App Security door middel van de beheerde domeinen wordt bepaald welke gebruikers intern en extern zijn en welke bestanden al dan niet mogen worden gedeeld. Dit wordt gebruikt voor rapporten en waarschuwingen.  
> [!NOTE] 
> - Gebruikers in domeinen die niet zijn geconfigureerd als interne zijn gemarkeerd als extern en niet voor activiteiten en bestanden worden gescand.

5. Zie [Integratie van Azure Information Protection](azip-integration.md) voor informatie als u integreert met behulp van Azure Information Protection-integratie. 

 >[!NOTE]
 > Met Azure Information Protection-integratie wilt werken, moet u inschakelen de [App-connector voor Office 365](connect-office-365-to-microsoft-cloud-app-security.md).
  
6.  Als u op enig moment een back-up wilt maken van uw portal-instellingen, biedt dit scherm hiervoor de mogelijkheid. Klik op **portal-instellingen exporteren** voor het maken van een json-bestand van alle uw portal-instellingen, met inbegrip van beleid regels, gebruikersgroepen en IP-adresbereiken.  
  
   
> [!NOTE] 
> Als u ExpressRoute gebruikt, is Cloud App Security geïmplementeerd in Azure en volledig geïntegreerd met [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Alle interacties met de Cloud App Security-apps en het verkeer dat wordt verzonden naar de Cloud App Security, waaronder het uploaden van detectielogboeken, verloopt via ExpressRoute **openbare peering** voor verbeterde latentie, prestaties en beveiliging. Er zijn geen configuratiestappen vereist door de klant. <br></br>Zie voor meer informatie over openbare peering [ExpressRoute-circuits en routeringsdomeinen](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/).  
    
## <a name="see-also"></a>Zie ook  
[Cloud Discovery instellen](set-up-cloud-discovery.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  