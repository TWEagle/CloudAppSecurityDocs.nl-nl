---
title: Verbinding maken tussen Salesforce en Microsoft Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen Salesforce en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/26/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 776d7589-acdb-4cb6-99a0-3be2f7b6aab2
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 759692e7b270d87dc1becf88453d095f2382c411
ms.openlocfilehash: 28ce67bd096d82e3775a281359fc100e2c214715


---


# <a name="connect-salesforce-to-microsoft-cloud-app-security"></a>Verbinding maken tussen Salesforce en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande Salesforce-account met behulp van de connector-API voor de app.  
  
## <a name="how-to-connect-salesforce-to-cloud-app-security"></a>Verbinding maken tussen Salesforce en Microsoft Cloud App Security  
  
1.  U wordt aangeraden een specifiek servicebeheerdersaccount te hebben voor Cloud App Security.  
  
2.  Valideer dat de REST API is ingeschakeld in Salesforce.  
  
     Uw Salesforce-account moet een van de volgende edities zijn met REST API-ondersteuning:  
  
     **Performance**, **Enterprise**, **Unlimited** of **Developer**.  
  
     De **Professional**-editie heeft standaards geen REST API, maar deze kan op aanvraag worden toegevoegd.  
  
     Controleer als volgt of REST API beschikbaar is op uw editie en is ingeschakeld:  
  
    -   Meld u aan bij uw SalesForce-account en ga naar de **instellingspagina**.  
  
    -   Ga onder **Gebruikers beheren** naar de pagina **Profielen**.  
  
         ![Salesforce-gebruikersprofielen beheren](./media/salesforce-manageusers-profiles.png "salesforce manageusers profiles")  
  
    -   Kies het profiel dat u gebruikt voor het implementeren van Cloud App Security en klik op **Bewerken**.  
  
         ![Salesforce-profiel bewerken](./media/salesforce-edit-profile.png "salesforce edit profile")  
  
    -   Zorg ervoor dat het selectievakje **API ingeschakeld** is geselecteerd. Als deze niet is geselecteerd, moet u mogelijk contact opnemen met Salesforce om deze toe voegen aan uw account.  
  
         ![Salesforce-API ingeschakeld](./media/salesforce-api-enabled.png "salesforce api enabled")  
  
3.  Als **Salesforce CRM-inhoud** is ingeschakeld voor uw organisatie, zorg er dan voor dat dit ook is ingeschakeld voor het huidige beheerdersaccount.  
  
    1.  Ga naar uw Salesforce-instellingspagina.  
  
         ![Salesforce-instellingen](./media/salesforce-setup.png "salesforce setup")  
  
    2.  Selecteer in het menu aan de zijkant **Gebruikers beheren** en klik vervolgens op **Gebruikers**.  
  
         ![Salesforce-menu Gebruikers](./media/salesforce-menu-users.png "salesforce menu users")  
  
    3.  Selecteer de huidige gebruiker met beheerdersrechten voor uw specifieke Cloud App Security-gebruiker.  
  
    4.  Zorg ervoor dat het selectievakje **Salesforce CRM-inhoud gebruiker** is geselecteerd.  
  
         Als dit niet is geselecteerd, klikt u op **Bewerken** en het selecteert u selectievakje.  
  
         ![Salesforce CRM-inhoud gebruiker](./media/salesforce-crm-content-user.png "salesforce crm content user")  
  
    5.  Klik op **Opslaan**.  
  
4.  Klik in de Cloud App Security-console op **Onderzoeken** en vervolgens op **Goedgekeurde apps**.  
  
5.  Klik in de rij Box op **Verbinden** in de kolom **App Connector-status**, of klik op de knop **Verbinding maken met een app** en vervolgens op **Salesforce**.  
  
     ![Verbinding maken met Salesforce](./media/connect-salesforce.png "connect salesforce")  
  
6.  Klik op de instellingspagina van Salesforce op het tabblad API en klik vervolgens op **Deze link volgen**, afhankelijk van welk exemplaar u wilt installeren.  
  
7.  Hiermee wordt de aanmeldingspagina van Salesforce geopend. Voer uw referenties in om Cloud App Security toegang te geven tot de Salesforce-app van uw team.  
  
     ![Aanmelden bij Salesforce](./media/salesforce-logon.png "salesforce logon")  
  
8.  Salesforce geeft een melding weer om u te vragen of u Cloud App Security toegang wilt geven tot de gegevens van uw team en het activiteitenlogboek en toestemming wilt geven om willekeurige activiteiten uit te voeren als een willekeurig teamlid. Klik op **Toestaan** om door te gaan.  
  
9. Op dit moment ontvangt u een melding dat de implementatie is gelukt of mislukt. Cloud App Security is nu gemachtigd in Salesforce.com.  
  
10. In de Cloud App Security-console zou u moeten zien dat er verbinding is gemaakt met Salesforce.  
  
11. Controleer of de verbinding tot stand is gekomen door op **Test API** te klikken.  
  
     Het testen kan enkele minuten duren. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Gereed**.  
  
  
Nadat u verbinding hebt gemaakt met SalesForce, ontvangt u gebeurtenissen als volgt: triggers vanaf het moment van de verbinding, aanmeldingsgebeurtenissen en instellen van audittrail tot 60 dagen voorafgaand aan de verbinding, gebeurtenisbewaking tot 30 dagen of 1 dag terug (afhankelijk van uw licentie voor SalesForce EventMonitoring).
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO3-->


