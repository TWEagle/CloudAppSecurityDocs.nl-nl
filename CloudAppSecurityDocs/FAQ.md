---
title: Veelgestelde vragen over Cloud App Security | Microsoft Docs
description: Dit artikel bevat veelgestelde vragen over Cloud App Security en de bijbehorende antwoorden.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/10/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 081c2cf4-2750-4546-9490-4b65e87ae48c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 3e0c14d142f9154b5e986105899c9445667518c6
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2017
---
# <a name="frequently-asked-questions"></a>Veelgestelde vragen

## <a name="what-kind-of-permissions-do-i-need-to-have-in-order-to-access-cloud-app-security"></a>Wat voor soort machtigingen heb ik nodig voor toegang tot Cloud App Security?

U moet een globale beheerder, compliancebeheerder of beveiligingsbeheerder in Azure Active Directory zijn. Het is niet voldoende om deze rollen te hebben in het beveiligings- en compliancecentrum van Office 365.
Als u een gebruiker wilt instellen als een globale beheerder, compliancebeheerder of beveiligingsbeheerder in Azure Active Directory, voert u de volgende opdracht uit in Windows PowerShell:

        $cred = Get-Credential
        Connect-MsolService -credential $cred
        Add-MsolRoleMember -RoleName "Compliance Administrator" -RoleMemberEmailAddress "XX@XX.XX"
 OR Add-MsolRoleMember - RoleName "beveiligingsbeheerder" -RoleMemberEmailAddress "XX@XX.XX"

## <a name="see-also"></a>Zie ook  
Zie [Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md) voor informatie over het gebruiken en instellen van het gebruik van cloud-apps.   
Ga naar de [ondersteuningspagina van Cloud App Security](http://support.microsoft.com/oas/default.aspx?prid=16031) voor technische ondersteuning.   
Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit [Premier Portal](https://premier.microsoft.com/) kiezen.  
