---
title: Beveiligen van uw organisatie tegen bedreigingen | Microsoft Docs
description: In dit onderwerp wordt een scenario beschreven voor beveiliging van uw organisatie tegen bedreigingen in uw cloudomgeving.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/27/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 0017be99-29c3-468e-a181-255e343ed4f5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 7bad1e1ae6196b684ac35d063558fad22bc3689f
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2017
---
# <a name="protecting-your-organization-against-threats"></a>Beveiligen van uw organisatie tegen bedreigingen  

Met een hoog risico gebruiks- en cloud beveiligingsproblemen identificeren, abnormaal gebruikersgedrag detecteren en te voorkomen dat bedreigingen in uw verbonden cloud-apps. Krijg inzicht in activiteiten van gebruikers en beheerders en definieer beleid voor het genereren van automatische waarschuwingen bij verdacht gedrag of als er in uw goedgekeurde omgevingen specifieke activiteiten plaatsvinden die u als riskant beschouwt. Maak gebruik van de enorme hoeveelheid gegevens die Microsoft te bieden heeft op het gebied van bedreigingsinformatie en beveiligingsonderzoek. Met beleid voor bedreigingsdetectie kunt u ervoor zorgen dat uw goedgekeurde apps over alle beveiligingsmaatregelen beschikken en dat u alle controle over de apps houdt.
 
## <a name="mass-download-by-a-single-user-data-exfiltration-by-an-insider"></a>Massaopslag downloaden door één gebruiker (exfiltration gegevens door een insider)

Deze gebruiksvoorbeeld geldt voor Office 365, G Suite, Box, Dropbox, Salesforce.

### <a name="the-threat"></a>DE BEDREIGING
Een kwaadwillende insider kunt exfiltrate gegevens van Office 365 of andere cloud-apps downloaden of toegang krijgen tot meerdere bestanden gedurende een korte periode.

### <a name="the-solution"></a>DE OPLOSSING
Detecteer wanneer een gebruiker in korte tijd een groot aantal bestanden downloadt of opent.

#### <a name="prerequisites"></a>Vereisten

[Verbind](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) ten minste een cloud-app met de Cloud App Security.

#### <a name="setting-up-monitoring"></a>Controle instellen

1.  Standaard scant Cloud App Security uw netwerk om een basislijn in te stellen, waarbij patronen worden vastgesteld van wat uw gebruikers gewoonlijk in de cloud doen, wanneer ze dat doen en wat ze meestal doen. 

2. Stel een beleid dat wordt gecontroleerd op uw cloud-apps voor grootschalige downloaden en de waarschuwing die u als iets extra zaken gebeurt:

    1. Op de pagina **Beleid** klikt u op [**Activiteitenbeleid maken**](user-activity-policies.md). 
   

    2. In het veld [**Beleidssjabloon**](policy-template-reference.md) kiest u **Massale downloads door één gebruiker**.
    
    3. Desgewenst kunt u het activiteitfilter herhaalde te stellen.
    
    4. Klik op **Maken**. 
   
     
2. Uw overeenkomsten onderzoeken
    
    1. Klik in de pagina **Beleid** op de naam van het beleid om naar het **Beleidsrapport** te gaan en bekijk de resultaten die zijn geactiveerd door het beleid.

    2. U kunt de overeenkomende reeks onderzoeken door te klikken op een specifieke overeenkomst om de activiteitslade te openen. In de lade kunt u de andere beleidsregels zien die aan deze activiteit zijn gekoppeld. 
    
    3. U kunt de bestanden die zijn gedownload door de gebruiker door te klikken op de activiteit bjecten in controleren de **activiteit lade** en vervolgens op de naam van het bestand, wordt dit u leiden tot het bestand in de tabel bestanden. Er kunt u zien als de bestanden zijn eigendom van de gebruiker die ze worden gedeeld met en kunt u bepalen of deze zijn bestanden die ze meestal werkt of dat ze intern IP-adres dat niet moet worden gedownload.
     


#### <a name="validating-your-policy"></a>Uw beleid valideren

1. Om te simuleren een waarschuwing, download u een aantal documenten, die groter is dan de drempelwaarde die u instelt, van de gekoppelde cloud-apps binnen een korte periode, afhankelijk van de periode die u in het beleid (bijvoorbeeld: 30 downloads in minder dan 5 minuten) instellen.
3. Ga naar het beleidsrapport. Binnen enkele ogenblikken zou een activiteitsbeleidovereenkomst moeten worden weergegeven. 
4. U kunt op de overeenkomst klikken om te zien welke bestanden zijn gedownload.  

#### <a name="removing-the-risk"></a>Het risico verwijderen

Nadat u hebt deze gevalideerd en het beleid voor de besturing, verwijder mogelijke valse positieven die mogelijk overeen met het beleid, zoals serviceaccounts die zijn gesynchroniseerd bestanden, mappen van afbeeldingen van bedrijfsgebeurtenissen, enzovoort. Ga als volgt verder: 
  1. U kunt ondernemen [beheeracties](governance-actions.md) openen van de activiteit in de sectie van de activiteit en klik op de naam van het bestand onder **activiteit objecten**.

  2. Neem contact op met de gebruikers om te zien waarom ze moeten kopieën van zoveel zakelijke bestanden op hun computers.

 
## <a name="admin-activity-from-outside-your-organizations-network"></a>Beheerdersactiviteit van buiten het netwerk van uw organisatie

Deze gebruiksvoorbeeld geldt voor Office 365, G Suite vak, Dropbox, Salesforce en Okta.

### <a name="the-threat"></a>DE BEDREIGING
Een beheerdersaccount er inbreuk is gemaakt door een externe aanvaller. Beheerdersaccounts zijn de meest gevoelige accounts in uw organisatie, omdat het de hoogste bevoegdheden en toegang tot alle informatie hebt in uw organisatie. Meestal moet administratieve activiteit worden uitgevoerd vanaf kantoor als onderdeel van de beheerder werk en niet vanaf externe locaties of niet-herkende apparaten.

### <a name="the-solution"></a>DE OPLOSSING
Detecteren wanneer mensen die als beheerders zijn verbonden met uw cloudtoepassing van het externe IP-adressen en het uitvoeren van een admin-activiteit.

#### <a name="prerequisites"></a>Vereisten

- [Verbind](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) ten minste één cloud-app met Cloud App Security.

- Ga naar **instellingen** > **IP-adresbereiken** en IP-adresbereiken voor zowel interne subnetten toe te voegen en hun uitgaande openbare IP-adressen en ze als labelen **zakelijk**.

#### <a name="setting-up-monitoring"></a>Controle instellen

1.  Starten van de controle van uw cloud-apps door het instellen van een beleid dat wordt gecontroleerd op uw cloud-apps voor de activiteit van Administrators buiten uw netwerk en de waarschuwing die u als iets extra zaken gebeurt:

    1. Op de pagina **Beleid** klikt u op [**Activiteitenbeleid maken**](user-activity-policies.md). 
   

    2. In de [ **beleidssjabloon** ](policy-template-reference.md) Kies **administratieve activiteiten van een niet-zakelijk IP-adres** en stelt u de **activiteitstype** naar **aanmelden** en selecteer **gebruiker** en vervolgens **uit groep** en selecteer de groep uw beheerders tot behoren.
    
    3. U kunt het beleid voor het instellen van het aantal herhaalde activiteiten die u moet overwegen verdachte wilt aanpassen.
    
    4. Klik op **Maken**. 
   
     
2. Uw overeenkomsten onderzoeken
    
    1. Klik in de pagina **Beleid** op de naam van het beleid om naar het **Beleidsrapport** te gaan en bekijk de resultaten die zijn geactiveerd door het beleid.

    2. U kunt de overeenkomende reeks onderzoeken door te klikken op een specifieke overeenkomst om de activiteitslade te openen. In de lade kunt u de andere beleidsregels zien die aan deze activiteit zijn gekoppeld. 
     
#### <a name="validating-your-policy"></a>Uw beleid valideren

1. Om te simuleren van een waarschuwing, van een computer met een IP-adres die geen deel uitmaakt van uw bedrijfsnetwerk admin activiteiten uitvoeren, om ervoor te zorgen dat het aantal activiteiten die worden uitgevoerd groter dan de drempelwaarde die u instelt is, binnen een korte periode, afhankelijk van de periode die u in het beleid (bijvoorbeeld 1 activiteiten in minder dan 5 minuten) instellen.
3. Ga naar het beleidsrapport. Binnen enkele ogenblikken zou een activiteitsbeleidovereenkomst moeten worden weergegeven. 
4. U kunt klikken op de overeenkomst om te zien welke activiteiten zijn uitgevoerd. 

#### <a name="removing-the-risk"></a>Het risico verwijderen

Nadat u het hebt gevalideerd en het beleid op uw wensen hebt afgestemd, verwijdert u mogelijke valse positieven die overeenkomen met uw beleid. Ga als volgt verder: 
  1. U kunt ondernemen [beheeracties](governance-actions.md) openen van de activiteit in de sectie van de activiteit en klik op de naam van de **gebruiker**.

  2. In de gebruikerspagina dat wordt geopend, ziet u een grafiek van de activiteit van de gebruiker over de afgelopen maand en de locaties waar de gebruiker al is gezien active gedurende de afgelopen maand, evenals groepslidmaatschappen, app-activiteit en accounts. 
  
  3. Indien nodig, kunt u klikken op **Neem contact op met** een e-mailbericht verzenden naar de gebruiker om te waarschuwen dat hun account al helemaal wordt geschonden.

 ![auto gov extern](./media/auto-gov-external.png)

   2. Nadat deze volledig is gevalideerd, kunt u deze automatische bestuursacties uit laten voeren. U kunt bijvoorbeeld **onderbreken gebruiker** of **samenwerkingen van gebruiker verwijderen**.


## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  