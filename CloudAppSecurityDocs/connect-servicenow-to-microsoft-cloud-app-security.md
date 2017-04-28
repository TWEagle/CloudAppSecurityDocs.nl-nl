---
title: Verbinding maken tussen ServiceNow en Cloud App Security voor zichtbaarheid en gebruikscontrole | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen de ServiceNow-app en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c626d94d-2ffd-4daf-8fa4-4b6d308cf012
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 1f4fd428f762bcbe1fb2a26bf44268cf985fbd4f
ms.sourcegitcommit: c79c405a1277c5fcebbc245fa12ff8feb53248d5
translationtype: HT
---
# <a name="connect-servicenow-to-microsoft-cloud-app-security"></a>Verbinding maken tussen ServiceNow en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande ServiceNow-account met behulp van de connector-API voor de app.  
  
## <a name="how-to-connect-servicenow-to-cloud-app-security"></a>De verbinding maken tussen ServiceNow en Cloud App Security  
  
> [!NOTE]  
>  Cloud App Security ondersteunt ServiceNow-versies van Eureka, Fiji, Genève, Helsinki en Istanboel. Als u verbinding wilt maken tussen ServiceNow en Cloud App Security, moet u de rol **Beheerder** hebben en er zeker van zijn dat het ServiceNow-exemplaar API-toegang ondersteunt.  Raadpleeg voor meer informatie de [ServiceNow-productdocumentatie](http://wiki.servicenow.com/index.php?title=Base_System_Roles#gsc.tab=0).
  
1.  Meld u met een beheerdersaccount aan bij uw ServiceNow-account.  
  
2.  In de zoekbalk **Filter navigator** typt u **OAuth** en selecteert u **Toepassingsregister**.

3. In de menubalk **Toepassingsregisters** klikt u op **Nieuw** om een nieuw OAuth-profiel te maken.

   ![ServiceNow new OAuth profile](./media/servicenow-app-registry.png)

4. Onder **Wat voor soort OAuth-toepassing?**, klikt u op **Een OAuth-API-eindpunt maken voor externe clients**.

   ![ServiceNow OAuth type](./media/servicenow-oauth-app-type.png)

5. Onder **Nieuw record toepassingsregisters** vult u het volgende in:
    
    - **Naam**-veld, de naam van het nieuwe OAuth-profiel, bijvoorbeeld CloudAppSecurity. 
    
    - De **Client-ID** wordt automatisch gegenereerd. Kopieer deze ID; u moet deze in de Cloud App Security plakken om de verbinding te voltooien.
    
    - In het veld **Clientgeheim** voert u een tekenreeks in. Als u dit leeg blijft, wordt automatisch een willekeurige geheim gegenereerd. Kopieer en bewaar het voor later. 
    
    - Verleng de **Levensduur van het toegangstoken** tot ten minste 3600.
    
    - Klik op **Indienen**.

   ![ServiceNow profile IDs](./media/servicenow-profile-ids.png)

6.  Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
7.  Klik op de pagina **App-connectors** op de knop met het plusteken en vervolgens op **ServiceNow**.  
  
     ![connect servicenow](./media/connect-servicenow.png "connect servicenow")  
  
8.  Voeg in het pop-upvenster in de bijbehorende vakken uw ServiceNow-gebruikersnaam, -wachtwoord, de URL van het exemplaar, Client-ID en Clientgeheim in.  
  
9.  Klik op **Verbinden**.  
  
     ![servicenow connect to CAS](./media/servicenow-portal-connect.png "servicenow connect in portal")  
  
10.  Controleer of de verbinding tot stand is gekomen door op **Test now** (Nu testen) te klikken.  
  
     Het testen kan enkele minuten duren. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Sluiten**.  
  
Nadat u verbinding hebt gemaakt met ServiceNow, ontvangt u gebeurtenissen tot 60 dagen voorafgaand aan de verbinding.
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
