---
title: Verbinding maken tussen Dropbox en Microsoft Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen de Dropbox-app en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4acd93f4-b885-4e1f-a385-43b5db02a3ee
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 105003dfbd8afbb10cdb2058e2da180d4b49e294


---

# <a name="connect-dropbox-to-microsoft-cloud-app-security"></a>Verbinding maken tussen Dropbox en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande Dropbox-account met behulp van de connector-API's voor de app.  
 
 
Omdat met Dropbox toegang tot bestanden via gedeelde koppelingen zonder aanmelden wordt ingeschakeld, worden deze gebruikers in Cloud App Security geregistreerd als niet-geverifieerde gebruikers. Als u niet-geverifieerde Dropbox-gebruikers ziet, kan dit wijzen op gebruikers die niet afkomstig zijn van uw organisatie of herkende gebruikers vanuit uw organisatie die zich niet hebben aangemeld.

## <a name="how-to-connect-dropbox-to-cloud-app-security"></a>Verbinding maken tussen Dropbox en Microsoft Cloud App Security  
  
1.  Klik in de Cloud App Security-console op **Onderzoeken** en vervolgens op **Goedgekeurde apps**.  
  
2.  Klik in de rij Dropbox op **Verbinden** in de kolom **App Connector-status**, of klik op de knop **Verbinding maken met een app** en vervolgens op **Dropbox**.  
  
     ![Verbinding maken met Dropbox](./media/connect-dropbox.png "connect dropbox")  
  
3.  Voer het e-mailadres van het beheeraccount in op het tabblad API van de pagina Dropbox-instellingen.  
  
4.  Klik op **Genereer link**.  
  
5.  Klik op **Volg deze link**.  
  
     Hiermee opent u de aanmeldingspagina Dropbox. Voer uw referenties in om Cloud App Security toegang te geven tot het Dropbox-exemplaar van uw team.  
  
6.  Dropbox geeft een melding weer om u te vragen of u Cloud App Security toegang wilt geven tot de gegevens van uw team en het activiteitenlogboek en toestemming wilt geven om willekeurige activiteiten uit te voeren als een willekeurig teamlid. Klik op **Toestaan** om door te gaan.  
  
7.  In de Cloud App Security-console zou u nu een bericht moeten ontvangen waarin staat vermeld dat er verbinding is gemaakt met Dropbox.  
  
8.  Controleer of de verbinding tot stand is gekomen door op **Test API** te klikken.  
  
     Het testen kan enkele minuten duren. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Sluiten**.  
  
Nadat u verbinding hebt gemaakt met Dropbox, ontvangt u gebeurtenissen tot 60 dagen voorafgaand aan de verbinding.

> [!NOTE] 
> Alle Dropbox-gebeurtenissen voor het toevoegen van bestanden worden in Cloud App Security weergegeven als de gebeurtenis Bestand uploaden. Dit gebeurt om te zorgen dat deze gebeurtenis in overeenstemming is met alle andere apps die zijn verbonden met Cloud App Security. 
 
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


