---
title: Verbinding maken tussen Office 365 en Cloud App Security voor zichtbaarheid en gebruikscontrole | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen Office 365 en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/22/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a79bf393-0d2c-44b6-8dab-86c740fd7333
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: e568172068f5ec63a519c495f7e824bd49b03883
ms.sourcegitcommit: 6e4eac42e553fd288da7de9c67eb79f11a420245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/22/2017
---
# <a name="connect-office-365-to-microsoft-cloud-app-security"></a>Verbinding maken tussen Office 365 en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van verbinding tussen Cloud App Security en uw bestaande Microsoft 365-account met behulp van de connector-API voor de app.  
  
Cloud App Security ondersteunt zowel het verouderde Office 365 Dedicated Platform als de meest recente aanbiedingen van Office 365-services (ook wel de vNext release van Office 365 genoemd).  Cloud App Security biedt geen ondersteuning voor de verouderde Microsoft Business Productivity Online Standard Suite. 

> [!NOTE]
> In sommige gevallen verschilt een vNext-servicerelease enigszins van het standaard Office 365-aanbod op het niveau van beheertaken en beheer.

Cloud App Security ondersteunt de volgende Office 365-apps:

- Office 365
- SharePoint
- OneDrive
- Teams (alleen wordt weergegeven nadat de activiteiten van Teams worden gedetecteerd in de portal)
- Power BI (alleen wordt weergegeven nadat de activiteiten van Power BI worden gedetecteerd in de portal en moet u controlebeleid inschakelen)
- Exchange (alleen wordt weergegeven nadat de activiteiten in Exchange in de portal worden gedetecteerd en moet u controlebeleid inschakelen)

 
## <a name="how-to-connect-office-365-to-cloud-app-security"></a>Verbinding maken tussen Office 365 en Cloud App Security  
  
> [!NOTE]
>- U moet ten minste één toegewezen Office 365-licentie hebben om verbinding te kunnen maken tussen Office 365 en Cloud App Security.
>-  Met controlelogboekregistratie voor Exchange-beheerders, standaard ingeschakeld in Office 365, wordt een gebeurtenis in het Office 365-controlelogboek geregistreerd wanneer een beheerder (of een gebruiker aan wie beheerdersrechten zijn toegewezen) een wijziging aanbrengt in uw Exchange Online-organisatie. Wijzigingen die zijn aangebracht via het Exchange-beheercentrum of door een cmdlet uit te voeren in Windows PowerShell, worden geregistreerd in het auditlogboek in het Exchange-beheercentrum. Zie het Engelstalige artikel [Administrator audit logging](http://go.microsoft.com/fwlink/p/?LinkID=619225) (Controlelogboekregistratie voor administrator) voor meer informatie over controlelogboekregistratie voor administrators in Exchange.
>- Exchange-postvak logboekregistratie moet worden ingeschakeld voor elke gebruikerspostvak voordat gebruikersactiviteit in Exchange Online wordt vastgelegd, Zie [Exchange-postvak activiteiten](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c).
>- Als Office-apps zijn ingeschakeld, zijn groepen die deel van Office 365 uitmaken ook geïmporteerde en Cloud App Security van de specifieke Office-apps, bijvoorbeeld als SharePoint is ingeschakeld, Office 365-groepen worden geïmporteerd als SharePoint-groepen.
>- U moet [inschakelen in Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-auditing/) ophalen van de logboeken van daaruit. Zodra de controle is ingeschakeld, wordt door Cloud App Security gestart ophalen van de logboeken (met een vertraging van 24 72 uur).
> Als uw Azure Active Directory is ingesteld op automatisch synchroniseren met de gebruikers in uw on-premises Active Directory omgeving overschrijven de instellingen van de instellingen in de on-premises omgeving de Azure AD-instellingen en het gebruik van de **onderbreken gebruiker** beheeractie is hersteld. 
 
1.  Klik op de pagina **Verbonden apps** op de knop met het plusteken en selecteer **Office 365**.  

2.  Klik in het pop-upvenster van Office 365 op Verbinding maken met Office 365.

      ![Verbinding maken met 0365](./media/connect-0365.png) 
 
3.  Klik op Nu testen om de verbinding met Office 365 te testen. Het testen kan enkele minuten duren.
  
    ![Verbinding met O365 testen](./media/o365-test-connection.png) 
 
4.   Klik op **Sluiten** nadat is aangegeven dat een verbinding met Office 365 is gemaakt.
  
     ![Verbonden met O365](./media/o365-connected.png) 

> [!NOTE] 
> Nadat u verbinding hebt gemaakt met Office 365, ziet u gegevens tot een week geleden, waaronder toepassingen van derden die zijn verbonden met Office 365 en pull-API's zijn. Voor apps van derden die niet waren binnenhalen van API's voordat de verbinding is, ziet u gebeurtenissen vanaf het moment dat u verbinding maken met Office 365 omdat Cloud App Security Hiermee schakelt u een API's die standaard uitgeschakeld is.

## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  