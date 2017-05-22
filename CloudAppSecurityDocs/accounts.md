---
title: Inzicht in accounts van cloud-apps | Microsoft Docs
description: In dit onderwerp.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/16/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 7811f23b-6100-427f-93b1-44f5f81f6c76
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 5033a66c976775c512c0f5f0d3ebd3d9aee89b5a
ms.sourcegitcommit: cb8238610222953751ff714b346a0b4cf73ac40c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/16/2017
---
# <a name="accounts"></a>Accounts
Cloud App Security maakt de accounts van uw verbonden apps voor u zichtbaar. Nadat u Cloud App Security hebt verbonden met een app met behulp van de App-connector, leest Cloud App Security gegevens van accounts die gekoppeld zijn aan verbonden apps. Op de pagina Accounts kunt u die accounts en machtigingen onderzoeken, evenals de groepen waartoe de accounts behoren, plus hun aliassen en de apps die ze gebruiken. Wanneer Cloud App Security een nieuw account detecteert dat niet eerder aan een van de verbonden apps was gekoppeld, bijvoorbeeld in activiteiten of in het delen van bestanden, wordt het account bovendien toegevoegd aan de lijst met accounts van die app. Hiermee krijgt u inzicht in de activiteit van externe gebruikers die met uw cloud-apps werken.


De pagina **Accounts** kan worden gefilterd, zodat u specifieke accounts kunt vinden en verschillende soorten accounts nauwkeuriger kunt onderzoeken. U kunt bijvoorbeeld filteren op alle externe accounts die sinds vorig jaar niet meer zijn gebruikt. 

Op de pagina **Accounts** kunt u uw accounts gemakkelijk op problemen onderzoeken, waaronder het volgende:  

-   U kunt controleren of er accounts zijn die gedurende een lange periode niet actief zijn geweest in een bepaalde service (misschien moet u de licentie van die service voor die gebruiker intrekken)  
-   U kunt filteren op de lijst met gebruikers met beheerdersmachtigingen  

-   U kunt zoeken naar gebruikers die niet langer deel uitmaken van uw organisatie, maar wel nog steeds actieve accounts hebben  

-   U kunt beheeracties voor de accounts ondernemen, zoals een app onderbreken of naar de instellingenpagina van een account gaan. Zie het [Beheerlogboek](governance-actions.md) voor een volledige lijst met beheeracties.
    
-   U kunt zien welke accounts in elke gebruikersgroep zijn opgenomen  

-   U kunt zien welke apps zijn geopend door elk account en welke apps zijn verwijderd voor specifieke accounts
    

![scherm Accounts](./media/accounts-page.png)

## <a name="account-filters"></a>Accountfilters
Hieronder volgt een lijst met de accountfilters die kunnen worden toegepast. De meeste filters bieden ondersteuning voor meerdere waarden en voor NOT (niet), zodat u over een zeer krachtig hulpprogramma beschikt voor het maken van een beleid.  
  
- **Accountnaam**: De accountnaam is de primaire alias van de gebruiker, maar andere id’s uit andere Microsoft-accounts (Office 365 en Azure Active Directory) zoals proxyadressen, aliassen en beveiligings-id’s worden ook ondersteund en worden geconsolideerd onder de primaire alias.

- **Relatie**: De relatie is ofwel **Intern** ofwel **Extern**. Als u wilt instellen welke gebruikers en accounts intern zijn, stelt u onder **Instellingen** het **IP-adresbereik** van uw interne organisatie in. Als het account beheerdersmachtigingen heeft, wordt het pictogram in de tabel Accounts weergegeven met het ![accountbeheerderspictogram](./media/accounts-admin-icon.png) (een rode stropdas).

- **App**: Hiermee kunt u filteren op elke API-verbonden app die wordt gebruikt door accounts in uw organisatie.

- **Domein**: Hiermee kunt u filteren op gebruikers in specifieke domeinen.

- **Laatst gezien**: Met het filter **Laatst gezien** kunt u accounts vinden die inactief zijn en waarvan de gebruikers al een tijdje geen activiteiten hebben uitgevoerd.

- **Organisatie/afdeling**: Hiermee kunt u filteren op leden van specifieke organisatiegroepen die in uw verbonden apps zijn gedefinieerd.

- **Gebruikersgroep**: Hiermee kunt u filteren op leden van gebruikersgroepen in Cloud App Security; zowel ingebouwde gebruikersgroepen als geïmporteerde gebruikersgroepen.


## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  