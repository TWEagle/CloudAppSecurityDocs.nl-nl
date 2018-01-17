---
title: Cloud App Security Discovery-gegevens met Azure AD-gebruikersnamen verrijken | Microsoft Docs
description: Dit artikel bevat informatie over het aanvullen van Cloud App Security Discovery-gegevens met Azure AD-gebruikersnamen.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 45295c2c-3e4d-4482-bf95-2e47072f9236
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 0ba0dc559bd2d1e1c91ef44e9bcbec828dec6a9f
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2018
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

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
    
      
  