---
title: Verbinding maken tussen Okta en Microsoft Cloud App Security | Microsoft Docs
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
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a413236b04726dddc69068e39967f6ad17218719
ms.openlocfilehash: c11e133f78c3973006c3e70dd1ccd719f7b639aa


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
  
3.  Klik in de Cloud App Security-console op **Onderzoeken** en vervolgens op **Goedgekeurde apps**.  
  
4.  Klik in de rij Okta op **Verbinden** in de kolom **App Connector-status**, of klik op de knop **Verbinding maken met een app** en vervolgens op **Okta**.  
  
     ![Verbinden maken met Okta](./media/connect-okta.png "connect okta")  
  
5.  Voer op API-pagina in het veld **Domein** uw Okta-domein in en plak uw token in het veld **Token**.  
  
6.  Klik op **Verbinden** om het token voor Okta te maken in Cloud App Security.  
  
7.  Controleer of de verbinding tot stand is gekomen door op **Test API** te klikken.  
  
     Het testen kan enkele minuten duren. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Sluiten**.  
  
Nadat u verbinding hebt gemaakt met Okta, ontvangt u gebeurtenissen tot 60 dagen voorafgaand aan de verbinding.
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO5-->


