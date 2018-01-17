---
title: Inzicht in accounts van cloud-apps | Microsoft Docs
description: In dit onderwerp.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 7811f23b-6100-427f-93b1-44f5f81f6c76
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: e710418938af85a8a16a866dcbae43ac612f090a
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2018
---
# <a name="accounts"></a>Accounts
Cloud App Security maakt de accounts van uw verbonden apps voor u zichtbaar. Nadat u Cloud App Security hebt verbonden met een app met behulp van de App-connector, leest Cloud App Security gegevens van accounts die gekoppeld zijn aan verbonden apps. Op de pagina Accounts kunt u die accounts en machtigingen onderzoeken, evenals de groepen waartoe de accounts behoren, plus hun aliassen en de apps die ze gebruiken. Bovendien – wanneer Cloud App Security een nieuw account die niet eerder is zichtbaar detecteert in een van de verbonden apps - bijvoorbeeld in activiteiten of in het delen van bestanden - is het account toegevoegd aan de lijst met accounts van deze app. Hiermee krijgt u inzicht in de activiteit van externe gebruikers die met uw cloud-apps werken.


De pagina **Accounts** kan worden gefilterd, zodat u specifieke accounts kunt vinden en verschillende soorten accounts nauwkeuriger kunt onderzoeken. U kunt bijvoorbeeld filteren op alle externe accounts die sinds vorig jaar niet meer zijn gebruikt. 

De **Accounts** pagina kunt u eenvoudig uw accounts, met inbegrip van de volgende problemen te onderzoeken:  

-   U kunt controleren of er accounts zijn die gedurende een lange periode niet actief zijn geweest in een bepaalde service (misschien moet u de licentie van die service voor die gebruiker intrekken)  
-   U kunt filteren op de lijst met gebruikers met beheerdersmachtigingen  

-   U kunt zoeken naar gebruikers die niet langer deel uitmaken van uw organisatie, maar wel nog steeds actieve accounts hebben  

-   U kunt beheeracties voor de accounts ondernemen, zoals een app onderbreken of naar de instellingenpagina van een account gaan. Zie het [Beheerlogboek](governance-actions.md) voor een volledige lijst met beheeracties.
    
-   U kunt zien welke accounts in elke gebruikersgroep zijn opgenomen  

-   U kunt zien welke apps zijn geopend door elk account en welke apps zijn verwijderd voor specifieke accounts
    

![scherm Accounts](./media/accounts-page.png)

## <a name="account-filters"></a>Accountfilters
Hier volgt een lijst van de account-filters die kunnen worden toegepast. De meeste filters bieden ondersteuning voor meerdere waarden en niet, zodat u over een krachtig hulpprogramma voor het maken van beleid.  
  
- **Accountnaam**: De accountnaam is de primaire alias van de gebruiker, maar andere id’s uit andere Microsoft-accounts (Office 365 en Azure Active Directory) zoals proxyadressen, aliassen en beveiligings-id’s worden ook ondersteund en worden geconsolideerd onder de primaire alias.

- **Lidmaatschap van de**: de relatie is **intern** of **externe**. Als u wilt instellen welke gebruikers en accounts intern zijn, stelt u onder **Instellingen** het **IP-adresbereik** van uw interne organisatie in. In het geval dat het account beheerdersmachtigingen het pictogram in de tabel Accounts heeft wordt weergegeven door het toevoegen van de rode tie ![pictogram voor gebruikeraccounts admin](./media/accounts-admin-icon.png).

- **App**: Hiermee kunt u filteren op elke API-verbonden app die wordt gebruikt door accounts in uw organisatie.

- **Domein**: Hiermee kunt u filteren op gebruikers in specifieke domeinen.

- **Laatst gezien**: Met het filter **Laatst gezien** kunt u accounts vinden die inactief zijn en waarvan de gebruikers al een tijdje geen activiteiten hebben uitgevoerd.

- **Organisatie/afdeling**: Hiermee kunt u filteren op leden van specifieke organisatiegroepen die in uw verbonden apps zijn gedefinieerd.

- **Gebruikersgroep**: Hiermee kunt u filteren op leden van gebruikersgroepen in Cloud App Security; zowel ingebouwde gebruikersgroepen als geïmporteerde gebruikersgroepen.


## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  