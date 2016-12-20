---
title: Verbinding maken met ServiceNow | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen de ServiceNow-app en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c626d94d-2ffd-4daf-8fa4-4b6d308cf012
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6beb9041b338406fb5b16f4bd045dbdc4592c6d9
ms.openlocfilehash: 7935006b6b28ed93601ca60adf3c1a408440eae7


---

# <a name="connect-servicenow-to-microsoft-cloud-app-security"></a>Verbinding maken tussen ServiceNow en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande ServiceNow-account met behulp van de connector-API voor de app.  
  
## <a name="how-to-connect-servicenow-to-cloud-app-security"></a>De verbinding maken tussen ServiceNow en Cloud App Security  
  
> [!NOTE]  
>  Cloud App Security ondersteunt ServiceNow-versies van Eureka en Fiji. Als u verbinding wilt maken tussen ServiceNow en Cloud App Security, moet u machtigingen hebben op beheerdersniveau en er zeker van zijn dat het ServiceNow-exemplaar API-toegang ondersteunt.  
  
1.  Meld u met een beheerdersaccount aan bij uw ServiceNow-account.  
  
2.  Maak een nieuw serviceaccount voor Cloud App Security en wijs de beheerdersrol aan het nieuwe account toe.  
  
3.  Zorg ervoor dat de REST API-plugin is ingeschakeld.  
  
     ![ServiceNow-account](./media/servicenow-account.png "servicenow account")  
  
4.  Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
5.  Klik op de pagina **App-connectors** op de knop met het plusteken en vervolgens op **ServiceNow**.  
  
     ![Verbinding maken met ServiceNow](./media/connect-servicenow.png "connect servicenow")  
  
6.  Voeg in het pop-upvenster in de bijbehorende vakken uw ServiceNow-gebruikersnaam, -wachtwoord en de URL van het exemplaar in.  
  
7.  Klik op **Verbinden**.  
  
     ![ServiceNow-wachtwoord bijwerken](./media/servicenow-update-password.png "servicenow update password")  
  
8.  Controleer of de verbinding tot stand is gekomen door op **Test API** te klikken.  
  
     Het testen kan enkele minuten duren. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Sluiten**.  
  
Nadat u verbinding hebt gemaakt met ServiceNow, ontvangt u gebeurtenissen tot 60 dagen voorafgaand aan de verbinding.
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO5-->


