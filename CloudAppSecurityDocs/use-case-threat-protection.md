---
title: Overzicht van scenario voor beveiliging tegen bedreigingen | Microsoft Docs
description: In dit onderwerp wordt een scenario beschreven voor beveiliging van uw organisatie tegen bedreigingen in uw cloudomgeving.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/30/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 0017be99-29c3-468e-a181-255e343ed4f5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: fcc793f0fea71ef0666a7c99034185c5cd5fd894
ms.sourcegitcommit: 7e9ae94cb4f90fbccaa84f19bdebb4652a425e45
translationtype: HT
---
# <a name="controlling-and-protecting-your-files"></a>Uw bestanden beheren en beveiligen  

Identificeer gebruik met een hoog risico en problemen met cloudbeveiliging, detecteer abnormaal gebruikersgedrag en voorkom bedreigingen in uw goedgekeurde cloud-apps. Krijg inzicht in activiteiten van gebruikers en beheerders en definieer beleid voor het genereren van automatische waarschuwingen bij verdacht gedrag of als er in uw goedgekeurde omgevingen specifieke activiteiten plaatsvinden die u als riskant beschouwt. Maak gebruik van de enorme hoeveelheid gegevens die Microsoft te bieden heeft op het gebied van bedreigingsinformatie en beveiligingsonderzoek. Met beleid voor bedreigingsdetectie kunt u ervoor zorgen dat uw goedgekeurde apps over alle beveiligingsmaatregelen beschikken en dat u alle controle over de apps houdt.
 
## <a name="massive-quantities-of-files-are-being-downloaded-insider-data-exfiltration"></a>Grote hoeveelheden bestanden worden gedownload (exfiltratie van insider-gegevens)

Deze use case is van toepassing op Office 365, G Suite, Box, Dropbox en Salesforce.

### <a name="the-threat"></a>DE BEDREIGING
Een aanvaller met een verdacht account kan gegevens uit Office 365 of andere cloud-apps exfiltreren door meerdere bestanden te downloaden of te openen.

### <a name="the-solution"></a>DE OPLOSSING
Detecteer wanneer een gebruiker in korte tijd een groot aantal bestanden downloadt of opent.

#### <a name="prerequisites"></a>Vereisten

[Verbind](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) ten minste een cloud-app met de Cloud App Security.

#### <a name="setting-up-monitoring"></a>Controle instellen

1.    Standaard scant Cloud App Security uw netwerk om een basislijn in te stellen, waarbij patronen worden vastgesteld van wat uw gebruikers gewoonlijk in de cloud doen, wanneer ze dat doen en wat ze meestal doen. 

2. Bovendien is het belangrijk om te beginnen met de bewaking van uw cloud-apps door een beleid in te stellen dat let op grote downloads in uw cloud-apps en u waarschuwt als er iets ongewoons gebeurt:

    1. Op de pagina **Beleid** klikt u op [**Activiteitenbeleid maken**](user-activity-policies.md). 
    ![activiteitenbeleid maken](./media/create-activity-policy.png)

    2. In het veld [**Beleidssjabloon**](policy-template-reference.md) kiest u **Massale downloads door één gebruiker**.
    
    3. U kunt ook het filter voor herhaalde activiteit verfijnen.
    
    4. Klik op **Sjabloon toepassen**. 
    ![sjabloon activiteitenbeleid](./media/activity-policy-template.png)
     
2. Uw overeenkomsten onderzoeken
    
    1. Klik in de pagina **Beleid** op de naam van het beleid om naar het **Beleidsrapport** te gaan en bekijk de resultaten die zijn geactiveerd door het beleid.

    2. U kunt de overeenkomende reeks onderzoeken door te klikken op een specifieke overeenkomst om de activiteitslade te openen. In de lade kunt u de andere beleidsregels zien die aan deze activiteit zijn gekoppeld. 
     


#### <a name="validating-your-policy"></a>Uw beleid valideren

1. U kunt een waarschuwing simuleren door vanuit uw verbonden cloud-apps meerdere keren in korte tijd verschillende documenten te downloaden, zoals gedefinieerd in uw beleidsconfiguratie (bijvoorbeeld 10 keer in minder dan 30 minuten).
3. Ga naar het beleidsrapport. Binnen enkele ogenblikken zou een activiteitsbeleidovereenkomst moeten worden weergegeven. 
4. U kunt op de overeenkomst klikken om te zien welke bestanden zijn gedownload. De overeenkomst zelf wordt gemaskeerd ter bescherming van gevoelige gegevens. 

#### <a name="removing-the-risk"></a>Het risico verwijderen

Nadat u het hebt gevalideerd en het beleid op uw wensen hebt afgestemd, verwijdert u mogelijke valse positieven die overeenkomen met uw beleid. Ga als volgt verder: 
  1. U kunt onmiddellijk [bestuursacties](governance-actions.md) ondernemen door op de drie puntjes aan het einde van de rij te klikken en de relevante bestuursactie te selecteren, bijvoorbeeld **Gebruiker in quarantaine plaatsen**.

 ![auto gov extern](./media/auto-gov-external.png)

   2. Nadat deze volledig is gevalideerd, kunt u deze automatische bestuursacties uit laten voeren. In SharePoint en OneDrive kunt u bijvoorbeeld **Externe gebruikers verwijderen** of **Gebruiker in quarantaine plaatsen** en voor G Suite en Box kunt u **Externe gebruikers verwijderen** en **Publieke toegang verwijderen**.

  ![automatische bestuursacties toepassen](./media/apply-automatic-gov-actions.png)



## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  