---
title: Inzicht in accounts van cloud-apps | Microsoft Docs
description: In dit onderwerp.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/23/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 7811f23b-6100-427f-93b1-44f5f81f6c76
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 5d5ccc55fe0d9c3fea93446daebfcbd5bbed8c8d
ms.sourcegitcommit: fd3b6c04cec30f7c9300cc02d29d562d17bf43ea
translationtype: HT
---
# <a name="accounts"></a>Accounts
Cloud App Security maakt alle accounts van uw verbonden apps voor u zichtbaar. Nadat u Cloud App Security hebt verbonden met een app met behulp van de App-connector, scant Cloud App Security alle accounts die zijn verbonden met de apps. Op de pagina Accounts kunt u die accounts onderzoeken, evenals de groepen waartoe ze behoren, hun aliassen en de apps die ze gebruiken. 


Het logboek **Accounts** kan worden gefilterd, zodat u specifieke accounts kunt vinden en verschillende soorten accounts nauwkeuriger kunt onderzoeken. U kunt bijvoorbeeld filteren op alle externe accounts die sinds vorig jaar niet meer zijn gebruikt. U kunt beleidsregels maken op basis van de accounts en vervolgens aangeven waarvoor u waarschuwingen wilt ontvangen en actie wilt ondernemen. 

Op de pagina **Accounts** kunt u uw accounts gemakkelijk op problemen onderzoeken, waaronder het volgende:  

-   U kunt controleren of er accounts zijn die gedurende een lange periode niet actief zijn geweest in een bepaalde service (misschien moet u de licentie van die service voor die gebruiker intrekken)  
-   U kunt filteren op de lijst met gebruikers met beheerdersmachtigingen  

-   U kunt bekijken welke accounts actief zijn maar tot gebruikers behoren die niet meer bij uw organisatie werken  

-   U kunt de machtigingen van een gebruiker voor een specifieke app intrekken (afhankelijk van de app) of vereisen dat een specifieke gebruiker meervoudige verificatie uitvoert
    
-   U kunt zien welke accounts in elke gebruikersgroep zijn opgenomen  

-   U kunt zien welke apps zijn geopend door elk account en welke apps zijn verwijderd voor specifieke accounts
    
-   U kunt ook inzoomen op het account van een gebruiker en relevante beheeracties selecteren, zoals **De gebruiker blokkeren** of **Samenwerkingen van gebruiker verwijderen**. Als de gebruiker is geïmporteerd uit Azure Active Directory, kunt u ook klikken op **Azure AD-accountinstellingen** voor eenvoudige toegang tot geavanceerde gebruikersbeheerfuncties, bijvoorbeeld voor groepsbeheer, meervoudige verificatie, details over de aanmeldingen van de gebruiker en het blokkeren van aanmeldingen.

![scherm Accounts](./media/accounts-page.png)

## <a name="account-filters"></a>Accountfilters
Hieronder volgt een lijst met de accountfilters die kunnen worden toegepast. De meeste filters bieden ondersteuning voor meerdere waarden en voor NOT (niet), zodat u over een zeer krachtig hulpprogramma beschikt voor het maken van een beleid.  
  
- **Accountnaam**: De accountnaam is de primaire alias van de gebruiker, maar andere id’s uit andere Microsoft-accounts (Office 365 en Azure Active Directory) zoals proxyadressen, aliassen en beveiligings-id’s worden ook ondersteund en worden geconsolideerd onder de primaire alias.

- **Relatie**: De relatie is ofwel **Intern** ofwel **Extern**. Als u wilt instellen welke gebruikers en accounts intern zijn, stelt u onder **Instellingen** het **IP-adresbereik** van uw interne organisatie in. Als het account beheerdersmachtigingen heeft, wordt het pictogram in de tabel Accounts weergegeven met het ![accountbeheerderspictogram](./media/accounts-admin-icon.png) (een rode stropdas).

- **App**: Hiermee kunt u filteren op elke API-verbonden app die wordt gebruikt door accounts in uw organisatie.

- **Domein**: Hiermee kunt u filteren op gebruikers in specifieke domeinen.

- **Laatst gezien**: Met het filter **Laatst gezien** kunt u accounts vinden die inactief zijn en waarvan de gebruikers al een tijdje geen activiteiten hebben uitgevoerd.

- **Organisatie/afdeling**: Hiermee kunt u filteren op leden van specifieke Azure Active Directory- of Office 365-organisatiegroepen.

- **Gebruikersgroep**: Hiermee kunt u filteren op leden van gebruikersgroepen in Cloud App Security; zowel ingebouwde gebruikersgroepen als geïmporteerde gebruikersgroepen.


## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  