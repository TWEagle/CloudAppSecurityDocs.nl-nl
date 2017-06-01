---
title: Geef de instellingen van uw organisatie op in de Cloud App Security-portal voor de beste resultaten | Microsoft Docs
description: In dit artikel wordt uitgelegd hoe u informatie over uw organisatie opgeeft in Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2e7e57b0-db54-4d75-896c-4700dd9abe48
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: cb2b4b26ee9a5f0340409090318fcbe1421b90d5
ms.sourcegitcommit: 50fac1cec86dfb8170ba9c63a8f58a4bf24e3c5b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2017
---
# <a name="basic-set-up"></a>Basisinstellingen
De volgende procedure bevat instructies voor het aanpassen van de Cloud App Security-portal.
  
## <a name="set-up-the-portal"></a>De portal instellen  
  
1.  In de Cloud App Security-portal klikt u op het pictogram Instellingen ![pictogram instellingen](./media/settings-icon.png "pictogram instellingen") in de menubalk en selecteert u **Algemene instellingen** om het volgende te configureren:  
     
     ![algemene instellingen](./media/general-settings.png "algemene instellingen")  
  
3.  Bij **Organisatiegegevens** is het van belang dat u een **Weergavenaam organisatie** opgeeft voor uw organisatie. Deze wordt weergegeven op de e-mailberichten en webpagina's die vanuit het systeem worden verzonden.  
  
4. Geef een **omgevingsnaam** (tenant) op. Dit is vooral belangrijk als u meerdere tenants beheert.  
  
4. Het is ook mogelijk om een **Logo** op te geven dat wordt weergegeven in e-mailmeldingen en webpagina’s die vanuit het systeem worden verzonden. Het logo moet een PNG-bestand zijn met een maximale grootte van 150 x 50 pixels op een transparante achtergrond.  

4.  Denk eraan om een lijst met uw **Beheerde domeinen** toe te voegen. Deze stap is cruciaal omdat in Cloud App Security door middel van de beheerde domeinen wordt bepaald welke gebruikers intern en extern zijn en welke bestanden al dan niet mogen worden gedeeld. Dit wordt gebruikt voor rapporten en waarschuwingen.  
> [!NOTE] 
> - Gebruikers in domeinen die niet zijn geconfigureerd als interne gebruikers, worden gemarkeerd als externe gebruikers en voor deze gebruikers worden de activiteiten of bestanden niet gescand.

5. Zie [Integratie van Azure Information Protection](azip-integration.md) voor informatie als u integreert met behulp van Azure Information Protection-integratie. 
  
  
6.  Als u op enig moment een back-up wilt maken van uw portal-instellingen, biedt dit scherm hiervoor de mogelijkheid. Klik op **Portal-instellingen exporteren** om een json-bestand te maken van al uw portal-instellingen, zoals beleidsregels, gebruikersgroepen en IP-adresbereiken.  
  
       



> [!NOTE] 
> Als u ExpressRoute gebruikt, is Cloud App Security geïmplementeerd in Azure en volledig geïntegreerd met [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Alle interacties met de Cloud App Security-apps en het verkeer dat wordt verzonden naar Cloud App Security, met inbegrip van het uploaden van detectielogboeken, verlopen via **openbare peering** van ExpressRoute voor verbeterde latentie, prestaties en beveiliging. Er zijn geen configuratiestappen vereist door de klant.  
    Zie voor meer informatie over openbare peering [ExpressRoute-circuits en routeringsdomeinen](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/).  
    
## <a name="see-also"></a>Zie ook  
[Cloud Discovery instellen](set-up-cloud-discovery.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  