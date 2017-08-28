---
title: Uw gegevens beschermen met Cloud App Security en Azure Information Protection | Microsoft Docs
description: In dit onderwerp beschrijft het proces voor het instellen van bijna realtime gegevensbeveiliging voor gevoelige gegevens in uw organisatie.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/22/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: f3d01d43-0018-40e5-b7c7-8384d37bad52
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 59d8bb7e1d06cf0d5158f75e86f6bb9eff14c7de
ms.sourcegitcommit: c3fda43ef6fe0d15f0eb9ea23a6f245bad8c371b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/27/2017
---
# <a name="protecting-your-organizations-data"></a>Beveiligen van gegevens van uw organisatie

Uw werknemers in gegevensbeveiliging goed training zijn dure en soms onmogelijk. Voor de bedrijven die veel leveranciers en partners met toegang tot de SharePoint-sites en Dropbox locaties hebben, is het moeilijk zijn om ervoor te zorgen dat uw gegevens altijd beveiligd is. Dat is waar Cloud App Security-integratie met Azure Information Protection wordt geleverd. Dit beter samen cloud app super team kunt u uw gegevens in bijna realtime beveiligen. Niet alleen kunt die gevaarlijk zijn voor de klanten kan worden tegen PII-voorschriften in veel landen, waardoor potentiële juridische problemen voor uw organisatie.

## <a name="the-threat"></a>DE BEDREIGING
Een gebruiker in uw organisatie slaat klant vertrouwelijke informatiebestanden aan vak. De gebruiker niet Houd er rekening mee dat naast hun directe team de hele ondersteuningsmedewerkers toegang tot die Box-account heeft, inclusief leveranciers, partners en bezoekers die af en toe in de office stoppen. Iedere persoon met toegang tot de Box-account van uw organisatie heeft nu toegang tot die informatie.

## <a name="the-solution"></a>DE OPLOSSING
Uw gegevens beschermen in bijna realtime door het instellen van een beleid dat automatisch toepassing Azure Information Protection-versleuteling op vertrouwelijke bestanden.
## <a name="prerequisites"></a>Vereisten

[Verbinding maken tussen Box](connect-box-to-microsoft-cloud-app-security.md) met Cloud App Security.

## <a name="setting-up-data-protection"></a>Configureren van gegevensbeveiliging

1. Beginnen met het beveiligen van de gegevens die u opslaan in het vak door het instellen van een beleid dat wordt opgeslagen in het vak gevoelige gegevens versleutelen:

    1. Op de **besturingselement** tabblad [ **beleid**](control-cloud-apps-with-policies.md). 
   
    2. Klik op **beleid maken** en selecteer **Bestandsbeleid**.
    3. Aanroepen van het beleid voor gegevensbeveiliging vak en klikt u onder **maken van een filter voor de bestanden die dit beleid wordt toegepast op**, gericht op uw vertrouwelijke of gevoelige gegevens.<br></br>
    Selecteer bijvoorbeeld **bovenliggende map** gelijk is aan **klantgegevens** en selecteer **eigenaar** gelijk is aan en selecteer het financiële team.
    4. Onder **Governance**, open de **vak** sectie en selecteer **beveiligen**.
    5. Omdat [Cloud App Security is geïntegreerd met Azure Information Protection](azip-integration.md), kunt u in uw bestaande lijst van de classificatielabels moet worden gebruikt om de gegevens te beveiligen.
    4. Klik op **Maken**. 
   
     
2. Uw overeenkomsten onderzoeken
    
    1. Klik in de pagina **Beleid** op de naam van het beleid om naar het **Beleidsrapport** te gaan en bekijk de resultaten die zijn geactiveerd door het beleid.

    2. U kunt de overeenkomende reeks onderzoeken door te klikken op een specifieke overeenkomst om de bestandslade te openen. In de lade ziet u de beleidsregels die van dit bestand overeenkomt. 
     
## <a name="validating-your-policy"></a>Uw beleid valideren

1. Om te simuleren een waarschuwing, gaat u naar uw account vak en proberen te krijgen tot een bestand in de map **klantgegevens**.
3. Ga naar het beleidsrapport. Binnen enkele ogenblikken zou een bestandsbeleidovereenkomst moeten worden weergegeven. 
4. U kunt klikken op de overeenkomst om te zien welke bestanden zijn beveiligd. De overeenkomst zelf wordt gemaskeerd ter bescherming van gevoelige gegevens. 



 ## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  