---
title: Verbinding maken tussen Office 365 en Cloud App Security voor zichtbaarheid en gebruikscontrole | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen Office 365 en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a79bf393-0d2c-44b6-8dab-86c740fd7333
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f5dfdcb0d420434a66b73098d546e4de4a36f60e
ms.sourcegitcommit: 355226ee21981563066d637e7db0bff0d53c2da6
translationtype: HT
---
# <a name="connect-office-365-to-microsoft-cloud-app-security"></a>Verbinding maken tussen Office 365 en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van verbinding tussen Cloud App Security en uw bestaande Microsoft 365-account met behulp van de connector-API voor de app.  
  
  

## <a name="how-to-connect-office-365-to-cloud-app-security"></a>Verbinding maken tussen Office 365 en Cloud App Security  
  
> [!NOTE]
>- U moet ten minste één toegewezen Office 365-licentie hebben om verbinding te kunnen maken tussen Office 365 en Cloud App Security.
>-  Met controlelogboekregistratie voor Exchange-beheerders, standaard ingeschakeld in Office 365, wordt een gebeurtenis in het Office 365-controlelogboek geregistreerd wanneer een beheerder (of een gebruiker aan wie beheerdersrechten zijn toegewezen) een wijziging aanbrengt in uw Exchange Online-organisatie. Wijzigingen die zijn aangebracht via het Exchange-beheercentrum of door een cmdlet uit te voeren in Windows PowerShell, worden geregistreerd in het auditlogboek in het Exchange-beheercentrum. Zie het Engelstalige artikel [Administrator audit logging](http://go.microsoft.com/fwlink/p/?LinkID=619225) (Controlelogboekregistratie voor administrator) voor meer informatie over controlelogboekregistratie voor administrators in Exchange.
>- Het vastleggen van controlegebeurtenissen voor postvakken in Exchange moet voor elk gebruikerspostvak zijn ingeschakeld voordat de gebruikersactiviteiten in Exchange Online kunnen worden geregistreerd. Zie [Activiteiten in verband met Exchange-postvakken](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) voor meer informatie.
>- Als Office-apps zijn ingeschakeld, worden groepen die deel uitmaken van Office 365 ook in de specifieke Office-apps gemaakt. Als SharePoint bijvoorbeeld is ingeschakeld, worden Office 365-groepen in SharePoint gemaakt.
 
1.  Klik op de pagina **Verbonden apps** op de knop met het plusteken en selecteer **Office 365**.  

2.  Klik in het pop-upvenster van Office 365 op Verbinding maken met Office 365.

      ![Verbinding maken met 0365](./media/connect-0365.png) 
 
3.  Klik op Nu testen om de verbinding met Office 365 te testen. Het testen kan enkele minuten duren.
  
    ![Verbinding met O365 testen](./media/o365-test-connection.png) 
 
4.   Klik op **Sluiten** nadat is aangegeven dat een verbinding met Office 365 is gemaakt.
  
     ![Verbonden met O365](./media/o365-connected.png) 

> [!NOTE] 
> Nadat u verbinding hebt gemaakt met Office 365, ziet u gegevens tot een week geleden, waaronder toepassingen van derden die zijn verbonden met Office 365 en pull-API's zijn. Voor apps van derden die vóór de verbinding geen pull-API's waren, ziet u gebeurtenissen vanaf het moment dat u verbinding maakt met Office 365, omdat Cloud App Security API's inschakelt die standaard waren uitgeschakeld.

## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  