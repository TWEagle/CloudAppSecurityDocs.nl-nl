---
title: Verbinding maken tussen Salesforce en Microsoft Cloud App Security voor zichtbaarheid en gebruikscontrole | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen Salesforce en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 776d7589-acdb-4cb6-99a0-3be2f7b6aab2
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d50f77f5b19f9d965209639861a5672d2bcfc730
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2017
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
  
         ![salesforce, gebruikers beheren, profielen](./media/salesforce-manageusers-profiles.png "salesforce, gebruikers beheren, profielen")  
  
    -   Kies het profiel dat u gebruikt voor het implementeren van Cloud App Security en klik op **Bewerken**. Dit is het profiel dat voor het serviceaccount van Cloud App Security moet worden gebruikt om de app-connector in te stellen.  
  
         ![salesforce, profiel bewerken](./media/salesforce-edit-profile.png "salesforce, profiel bewerken")  
  
    -   Zorg ervoor dat u hebt de volgende selectievakjes ingeschakeld:   
        - **API ingeschakeld**
        - **Alle gegevens weergeven** 
        - **Salesforce CRM-inhoud beheren**
        - **Gebruikers beheren**
        
        Als deze niet zijn geselecteerd, moet u mogelijk contact opnemen met Salesforce wilt toevoegen aan uw account.  
             
3.  Als **Salesforce CRM-inhoud** is ingeschakeld voor uw organisatie, zorg er dan voor dat dit ook is ingeschakeld voor het huidige beheerdersaccount.  
  
    1.  Ga naar uw Salesforce-instellingspagina.  
  
         ![salesforce, instellingen](./media/salesforce-setup.png "salesforce, instellingen")  
  
    2.  Selecteer in het menu aan de zijkant **Gebruikers beheren** en klik vervolgens op **Gebruikers**.  
  
         ![salesforce-menu, gebruikers](./media/salesforce-menu-users.png "salesforce-menu, gebruikers")  
  
    3.  Selecteer de huidige gebruiker met beheerdersrechten voor uw specifieke Cloud App Security-gebruiker.  
  
    4.  Zorg ervoor dat het selectievakje **Salesforce CRM-inhoud gebruiker** is geselecteerd.  
  
         Als dit niet is geselecteerd, klikt u op **Bewerken** en selecteert u vervolgens het selectievakje.  
  
         ![salesforce, crm-inhoud gebruiker](./media/salesforce-crm-content-user.png "salesforce, crm-inhoud gebruiker")  
  
    5.  Klik op **Opslaan**.  
  
4.  Klik in de Cloud App Security-console op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
5.  Klik op de pagina **App-connectors** op de knop met het plusteken en vervolgens op **Salesforce**.  
  
     ![verbinding maken met salesforce](./media/connect-salesforce.png "verbinding maken met salesforce")  
  
6.  Klik op de instellingspagina van Salesforce op het tabblad API en klik vervolgens op **Deze link volgen**, afhankelijk van welk exemplaar u wilt installeren.  
  
7.  Hiermee wordt de aanmeldingspagina van Salesforce geopend. Voer uw referenties in om Cloud App Security toegang te geven tot de Salesforce-app van uw team.  
  
     ![salesforce aanmelding](./media/salesforce-logon.png "salesforce aanmelding")  
  
8.  Salesforce geeft een melding weer om u te vragen of u Cloud App Security toegang wilt geven tot de gegevens van uw team en het activiteitenlogboek en toestemming wilt geven om willekeurige activiteiten uit te voeren als een willekeurig teamlid. Klik op **Toestaan** om door te gaan.  
  
9. Op dit moment ontvangt u een melding dat de implementatie is gelukt of mislukt. Cloud App Security is nu gemachtigd in Salesforce.com.  
  
10. In de Cloud App Security-console zou u moeten zien dat er verbinding is gemaakt met Salesforce.  
  
11. Controleer of de verbinding tot stand is gekomen door op **Test API** te klikken.  
  
     Het testen kan enkele minuten duren. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Gereed**.  
  
  
Nadat u verbinding hebt gemaakt met Salesforce, ontvangt u gebeurtenissen als volgt: triggers vanaf het moment van de verbinding, aanmeldingsgebeurtenissen en instellen van audittrail tot 60 dagen voorafgaand aan de verbinding, gebeurtenisbewaking tot 30 dagen of 1 dag terug (afhankelijk van uw licentie voor Salesforce EventMonitoring). De Cloud App Security API communiceert rechtstreeks met de beschikbare API's van Salesforce. Omdat Salesforce het aantal API-aanroepen die het kan ontvangen beperkt, wordt er door Cloud App Security rekening gehouden met de beperking. Salesforce-API's verzenden elk antwoord met een veld voor de API-tellers, waaronder het totaal aantal beschikbare en resterende. Cloud App Security rekent dit om naar een percentage en zorgt ervoor dat er altijd 10% van de beschikbare API-aanroepen overblijven. 

> [!NOTE]
> De beperking van Cloud App Security wordt uitsluitend berekend op de eigen API-aanroepen met Salesforce, niet met die van andere toepassingen die API-aanroepen met Salesforce gebruiken.
> Het beperken van API-aanroepen vanwege de beperking kan de snelheid vertragen waarmee gegevens in de Cloud App Security worden opgenomen, maar dit wordt gewoonlijk ‘s nachts hersteld.


SalesForce-gebeurtenissen worden door de Cloud App Security als volgt verwerkt: 
  
- Aanmeldgebeurtenissen om de 15 minuten
- Audittrail-instellingen om de 15 minuten
- Het gebeurtenislogboek word door Salesforce elke 24 uur geëxporteerd (12:00 UTC) 


## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  