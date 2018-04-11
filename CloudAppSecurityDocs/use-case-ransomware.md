---
title: Overzicht van scenario voor beveiliging tegen bedreigingen | Microsoft Docs
description: In dit onderwerp wordt een scenario beschreven voor beveiliging van uw organisatie tegen bedreigingen in uw cloudomgeving.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 7a06a243-9ec2-4a11-8db2-bc065cdfef64
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: da7db14dc4ae7df175bb6bf3db05d29d0d29d6b0
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="protecting-your-organization-from-ransomware"></a>Uw organisatie beschermen tegen ransomware

In de meest recente enorme ransomware-aanval druk WannaCry op de hele wereld cyberbeveiliging hard, een geschatte 200.000 computers te infecteren tussen de 150 landen. Met de toename van ransomware aanvallen in de afgelopen jaren, een gemiddelde 25.000 aanvallen per maand in 2015 en 56,000 2016, steeds noodzakelijk cybersecurity actie moet ondernemen over ervoor te zorgen dat uw netwerk en de cloud zijn niet op risico. Dit artikel wordt uitgelegd hoe u Cloud App Security kunt gebruiken voor het bewaken van uw cloud, detecteren en bedreigingen te verhelpen en aanbevolen procedures voor het beveiligen van uw omgeving tegen ransomware toepassen.

## <a name="what-is-ransomware"></a>Wat is ransomware?
Ransomware is een cyberbeveiliging aanval waarbij de aanvaller verzendt u een bestand dat kan verhinderen dat toegang tot uw computer en uw eigen bestanden te versleutelen. De bestanden worden soms vastgehouden voor ransom en niet worden ontsleuteld totdat u betaalt de aanvaller toegang herstellen naar uw computer, bestanden of kritieke LOB-apps. Ransomware aanvallen kunnen van invloed op een computer, thuis, office, netwerk of de server. In feite omdat grote organisaties bestaan uit een groot aantal gebruikers die mogelijk per ongeluk een bestand opent dat ransomware Tools in uw netwerk, zijn organisaties nog meer risico wordt gedwongen de aanvaller de ransomware stoppen en computers of bestanden herstellen toegang betalen.

>[!NOTE]
> Deze gebruiksvoorbeeld geldt voor Office 365, G Suite, vak en Dropbox.

## <a name="the-threat"></a>DE BEDREIGING
Een gebruiker in uw organisatie is het doel van een aanval ransomware. De gebruiker mogelijk een e-mailbericht geïnfecteerd en voer ransomware die de alle bestanden, met inbegrip van de bestanden die zijn gesynchroniseerd met de cloud infecteert onbewust openen.

## <a name="the-solution"></a>DE OPLOSSING
Mogelijke ransomware in uw cloudomgeving detecteren door het maken van een beleid voor het bijwerken van u wanneer er verdachte activiteit wordt gedetecteerd en automatische acties instellen om te voorkomen dat ransomware bestanden naar uw cloud worden opgeslagen.

## <a name="prerequisites"></a>Vereisten

[Verbinding maken met](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) ten minste één cloud-app (Office 365, G Suite, vak en Dropbox) en Cloud App Security.

## <a name="setting-up-monitoring"></a>Controle instellen

1.  Standaard scant Cloud App Security uw netwerk om een basislijn in te stellen, waarbij patronen worden vastgesteld van wat uw gebruikers gewoonlijk in de cloud doen, wanneer ze dat doen en wat ze meestal doen. 

2. Bovendien is het belangrijk uw cloud-apps door het instellen van een beleid dat wordt gecontroleerd op uw cloud-apps voor het downloaden van grootschalige bewaking te starten en de waarschuwing die u als iets extra zaken gebeurt:

    1. Op de **besturingselement** tabblad [ **sjablonen**](policy-template-reference.md). 
   
    2. Van de [ **beleidssjabloon** ](policy-template-reference.md) Kies **potentiële ransomware activiteit**. 
       ![sjabloon ransomware](./media/ransomware-template.png)
    3. Deze sjabloon is ontworpen out-of-the-box om te zoeken naar typische van ransomware-aanvallen, bestanden en mappen die zijn gekoppeld aan een bekende ransomware activiteit. Desgewenst kunt u het type melding ontvangen van (e-mail en SMS-bericht) instellen wanneer het beleid wordt vergeleken.
        ![sjabloon ransomware](./media/ransomware-template-fields.png)
    4. Klik op **Maken**. 
   
     
2. Uw overeenkomsten onderzoeken
    
    1. Klik in de pagina **Beleid** op de naam van het beleid om naar het **Beleidsrapport** te gaan en bekijk de resultaten die zijn geactiveerd door het beleid.

    2. U kunt de overeenkomende reeks onderzoeken door te klikken op een specifieke overeenkomst om de activiteitslade te openen. In de lade kunt u de andere beleidsregels zien die aan deze activiteit zijn gekoppeld. 
     
## <a name="validating-your-policy"></a>Uw beleid valideren

1. Om te simuleren een waarschuwing, wijzigt u de extensie van 30 bestanden in .wncry en te uploaden naar de SharePoint-site.
3. Ga naar het beleidsrapport. Binnen enkele ogenblikken zou een activiteitsbeleidovereenkomst moeten worden weergegeven. 
4. U kunt op de overeenkomst klikken om te zien welke bestanden zijn gedownload. De overeenkomst zelf wordt gemaskeerd ter bescherming van gevoelige gegevens. 

## <a name="remediating-attacks-and-preventing-risk"></a>Automatisch doorvoeren aanvallen en te voorkomen dat risico

Nadat u het hebt gevalideerd en het beleid op uw wensen hebt afgestemd, verwijdert u mogelijke valse positieven die overeenkomen met uw beleid. Ga als volgt verder: 
1. Wanneer een beleid ransomware wordt gevonden, kunt u het herstellen door het instellen van geautomatiseerde [beheeracties](governance-actions.md).

2. Om te voorkomen dat toekomstige aanvallen, instellen van het beleid automatische beheeracties uitvoeren. Bijvoorbeeld in SharePoint en OneDrive u kunt het beleid instellen op automatisch **onderbreken gebruiker**.

   ## <a name="see-also"></a>Zie ook  
   [Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  