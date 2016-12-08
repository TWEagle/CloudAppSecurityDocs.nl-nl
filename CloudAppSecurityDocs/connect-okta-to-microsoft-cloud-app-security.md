---
title: Verbinding maken met Okta | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen Okta en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/26/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 9c3673b9-99bd-400c-9da1-5bf809ea5892
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6beb9041b338406fb5b16f4bd045dbdc4592c6d9
ms.openlocfilehash: 1e82f94cb8423bdaa3dcdc8d4a4f04179089546c


---

# <a name="connect-okta-to-microsoft-cloud-app-security"></a>Verbinding maken tussen Okta en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande Okta-account met behulp van de connector-API's voor de app.  
  
## <a name="how-to-connect-okta-to-cloud-app-security"></a>De verbinding maken tussen Okta en Microsoft Cloud App Security  
  
1.  U wordt aangeraden in Okta een beheerdersserviceaccount te maken voor Cloud App Security.  
  
     Zorg ervoor dat u een account gebruikt met superbeheerdersmachtigingen.  
  
     Zorg ervoor dat uw Okta-account is geverifieerd.  
  
2.  Klik in de Okta-console op **Beheerder**.  
  
    -   Klik op **Beveiliging** en vervolgens op **API**.  
  
         ![Okta-API](./media/okta-api.png "okta api")  
  
    -   Klik op **Token aanmaken**.  
  
         ![Okta-token maken](./media/okta-createtoken.jpg "okta createtoken")  
  
    -   Voer in het pop-upvenster **Token aanmaken** uw Cloud App Security-token in en klik op **Token aanmaken**.  
  
         ![Pop-upvenster Okta-token](./media/okta-token-popup.png "okta token popup")  
  
    -   In het **pop-upvenster Token aangemaakt**, kopieert u de**Tokenwaarde**.  
  
         ![Okta-tokenwaarde](./media/okta-token-value.png "okta token value")  
  
3.  Klik in de Cloud App Security-console op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
4.  Klik op de pagina **App-connectors** op de knop met het plusteken en vervolgens op **Okta**.  
  
     ![Verbinden maken met Okta](./media/connect-okta.png "connect okta")  
  
5.  Voer in het veld **Domein** van het pop-upvenster dat wordt geopend uw Okta-domein in en plak uw token in het veld **Token**.  
  
6.  Klik op **Verbinden** om het token voor Okta te maken in Cloud App Security.  
  
7.  Controleer of de verbinding tot stand is gekomen door op **Test API** te klikken.  
  
     Het testen kan enkele minuten duren. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Sluiten**.  
  
Nadat u verbinding hebt gemaakt met Okta, ontvangt u gebeurtenissen tot 60 dagen voorafgaand aan de verbinding.
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO5-->


