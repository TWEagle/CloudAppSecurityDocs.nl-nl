---
title: Automatisch toegepast classificatielabels voor Azure Information Protection | Microsoft Docs
description: Dit onderwerp beschrijft het proces voor het automatisch toepassen van de classificatielabels Azure Information Protection in Microsoft Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/24/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: eac0b192-98d7-4939-9a07-1d4a7f8c39c3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 6ef94215cbb07dd35e9353e3a63b9e575905b16b
ms.sourcegitcommit: c0c0612cdf6805c8e92d7929be0f12f33660b2d2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/25/2017
---
# <a name="automatically-apply-azure-information-protection-classification-labels"></a>Azure Information Protection classificatielabels automatisch worden toegepast  

In een ideale situatie inzicht in al uw werknemers het belang van gegevensbeveiliging en werken binnen uw beleid. Maar in een werkelijkheid is het waarschijnlijk dat een partner die met accounting werkt een document naar uw opslagplaats vak met de juiste machtigingen uploadt en later een week zult u ontdekken dat vertrouwelijke informatie van uw bedrijf naar de concurrentie is gelekt. 

Microsoft Cloud App Security kunt u voorkomen dat dit soort na noodgevallen voordat dit gebeurt.

Cloud App Security identificeert die er openbare machtigingen voor een document dat is opgeslagen in uw account vak en gebruikt een classificatie-engine dat er vertrouwelijke informatie in het document openbaar gedeeld is. Cloud App Security verzendt u een waarschuwing waarmee u dit probleem is opgetreden, en daarnaast het past u uw Azure Information Protection **vertrouwelijk** classificatie label versleutelingsfunctie toegevoegd aan het bestand. 

>[!NOTE]
> - Toepassen van een Azure Information Protection-label is een van een lange lijst met beschikbare [beheeracties](governance-actions.md).
> - Deze functie is beschikbaar voor Box, SharePoint en OneDrive voor bedrijven.

### <a name="enhanced-data-level-encryption-protection"></a>Verbeterde versleuteling van gegevens op beveiliging

Cloud App Security-integratie met Azure Information Protection kunt een extra beveiligingsniveau door bestanden automatisch te versleutelen. Bijvoorbeeld, terwijl Azure Information Protection het bestand versleutelt, weten toepassingen die ondersteuning bieden voor Azure Information Protection (zoals Office 365) hoe de bestanden openen en de machtigingen in de classificatielabels geacht. Labels kunt u specifieke bescherming regels toepassen. Bijvoorbeeld, kunt u instellen een bestand zodanig dat deze kan worden geopend, maar kan niet worden gedeeld, afgedrukt, doorgestuurd of bewerkt). 

Deze hoog beveiligingsniveau verplaatst met het bestand - als u het bestand verzendt, kopiëren, opslaan in uw app onlineopslag nog steeds het bestand is beveiligd. Als een van uw werknemers een station met het bestand op het niet langer, het bestand wordt vergrendeld en als iemand probeert te openen, de bestandseigenaar een waarschuwing ontvangt. U kunt beveiliging automatisch toepassen met Cloud App Security. Bijvoorbeeld alle bestanden die creditcardnummers of zijn geüpload door de afdeling Financiën en extern worden gedeeld, kunnen worden ingesteld voor het automatisch worden beveiligd met een classificatie-label. 

## <a name="the-threat"></a>De bedreiging 
Een gebruiker in uw organisatie informatiebestanden worden opgeslagen klant vertrouwelijke aan vak en deze kan worden gedeeld met iedereen in de organisatie. De gebruiker niet Houd er rekening mee dat naast hun directe team de hele ondersteuningsmedewerkers toegang tot die Box-account heeft, inclusief leveranciers, partners en bezoekers die af en toe in de office stoppen. Iedere persoon met toegang tot de Box-account van uw organisatie heeft nu toegang tot die informatie. Niet alleen kunt die gevaarlijk zijn voor uw organisatie, kan het zijn tegen PII-voorschriften in veel landen mogelijke juridische problemen veroorzaakt.

## <a name="the-solution"></a>De oplossing
Cloud App Security met Azure Information Protection te gebruiken voor het insluiten van classificatie en beveiliging van informatie voor permanente beveiliging die volgt op uw gegevens, zodat deze blijft beveiligd, ongeacht waar deze wordt opgeslagen of dat ze worden gedeeld met. Hiermee kunt u ook gegevens veilig delen met collega's, evenals uw klanten en partners. Definieer wie toegang heeft tot gegevens en wat ze ermee kunnen doen--zoals zodat gebruikers kunnen weergeven en bewerken van bestanden, maar niet afdrukken of doorsturen--naast andere [beheeracties](governance-actions.md) ondersteund door Cloud App Security, zoals deelnemers verwijderen en mogelijkheden voor het delen verwijderen.

## <a name="prerequisites"></a>Vereisten

- [Cloud App Security en Azure Information Protection inschakelen](azip-integration.md) voor uw tenant.
- [Verbinding maken tussen Box](connect-box-to-microsoft-cloud-app-security.md) met Cloud App Security.

## <a name="setting-up-data-protection"></a>Configureren van gegevensbeveiliging

Stel een beleid dat u in de bestanden die zijn opgeslagen in uw account vak creditcardnummers zoekt instellen en wanneer ze niet zijn gevonden, automatisch een Azure Information Protection-label worden toegepast en vervolgens bepalen wat er gebeurt met alle bestanden met dat label.

1. Beginnen met het beveiligen van de gegevens die u opslaan in het vak door het instellen van een beleid dat wordt opgeslagen in het vak gevoelige gegevens versleutelen:

    1. Op de **besturingselement** tabblad [ **beleid**](control-cloud-apps-with-policies.md). 
    
    2. Klik op **beleid maken** en selecteer **Bestandsbeleid**.
    
    3. Aanroepen van het beleid *gegevensbeveiliging vak*.
    
    4. Onder **maken van een filter voor de bestanden die dit beleid wordt toegepast op**, gericht op uw vertrouwelijke of gevoelige gegevens.<br></br>
    Selecteer bijvoorbeeld **bovenliggende map** gelijk is aan **klantgegevens** in het vak en selecteer **eigenaar** gelijk is aan en selecteer het financiële team.
    
    4. In deze map, zoeken naar bestanden creditcardgegevens als volgt bevatten: onder **methode voor inhoudscontrole** Selecteer **ingebouwde DLP** en selecteer vervolgens **Include-bestanden die overeenkomen met een voorinstelling expressie** en selecteer **alle landen: Finance: tegoed creditcardnummer**.
    
    5. Onder **Governance**, open de **vak** sectie en selecteer **toepassen classificatie label** en selecteert u het label dat u wilt toepassen.
    
    6. Omdat [Cloud App Security is geïntegreerd met Azure Information Protection](azip-integration.md), kunt u in uw bestaande lijst van de classificatielabels moet worden gebruikt om de gegevens te beveiligen.
 
    7. Klik op **Maken**. 
   
   ![Classificatie label toevoegen aan het beleid](./media/aip-auto-policy.png)
     
2. Uw overeenkomsten onderzoeken
    
    1. Klik in de pagina **Beleid** op de naam van het beleid om naar het **Beleidsrapport** te gaan en bekijk de resultaten die zijn geactiveerd door het beleid.

    2. U kunt de overeenkomende reeks onderzoeken door te klikken op een specifieke overeenkomst om de bestandslade te openen. In de lade ziet u de beleidsregels die van dit bestand overeenkomt. 
     
## <a name="validating-your-policy"></a>Uw beleid valideren

1. Om te simuleren een waarschuwing, gaat u naar uw account vak en proberen te krijgen tot een bestand in de map **klantgegevens**.
3. Ga naar het beleidsrapport. Binnen enkele ogenblikken zou een bestandsbeleidovereenkomst moeten worden weergegeven. 
4. U kunt klikken op de overeenkomst om te zien welke bestanden zijn beveiligd. De overeenkomst zelf wordt gemaskeerd ter bescherming van gevoelige gegevens. 

>[!NOTE]
>Cloud App Security ondersteunt momenteel automatische toepassing van Azure Information Protection labels op de Box, SharePoint en OneDrive voor bedrijven.


 ## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  