---
title: Cloud App Security Discovery-gegevens met Azure AD-gebruikersnamen verrijken | Microsoft Docs
description: Dit artikel bevat informatie over het aanvullen van Cloud App Security Discovery-gegevens met Azure AD-gebruikersnamen.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/24/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 45295c2c-3e4d-4482-bf95-2e47072f9236
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 897211ce4e43a65d2c4783f1e5ca22ba80662731
ms.sourcegitcommit: 8759541301241e03784c5ac87b56986f22bd0561
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2017
---
# <a name="cloud-discovery-enrichment"></a>Cloud Discovery verrijking

Cloud Discovery-gegevens kunnen nu worden uitgebreid met gegevens van Azure Active Directory-gebruikersnaam. Wanneer u deze functie inschakelt, wordt de gebruikersnaam in de logboeken van de discovery-verkeer ontvangen overeenkomt en vervangen door de Azure AD-gebruikersnaam de volgende nieuwe functies ingeschakeld:
-   Shadow IT-gebruik door Azure Active Directory-gebruiker, kunt u onderzoeken.
-   U kunt het gebruik van doorzochte wolk app correleren met de activiteiten API verzameld.
-   Vervolgens kunt u aangepaste logboeken op basis van Azure AD-gebruikersgroepen maken. Bijvoorbeeld, een rapport Shadow IT voor een specifieke marketingafdeling.


## <a name="prerequisites"></a>Vereisten:
- Gegevensbron moet gebruikersnaam gegevens opgeven
- Office 365 app connector verbonden

## <a name="enabling-user-data-enrichment"></a>Gebruiker gegevens verrijking inschakelen 
    
1. Selecteer **Instellingen voor Cloud Discovery** onder het tandwiel Instellingen.
     
2. In de **gebruiker verrijking** tabblad om in te schakelen van Cloud App Security voor Azure Active Directory-gegevens worden gebruikt voor het aanvullen van gebruikersnamen standaard **toegang bieden gedetecteerde gebruiker-id's met Azure Active Directory-gebruikersnamen**.

3. Klik op **Opslaan**.
 
![Cloud App Security Discovery aanvullen met Azure AD-gebruikersnamen](./media/discovery-enrichment.png)
  

  
      
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
    
      
  