---
title: Verbinding maken tussen G Suite en Cloud App Security voor zichtbaarheid en gebruikscontrole | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen G Suite en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 1b33f8bcb27cc303463ac83b46098bf82d66d25c
ms.sourcegitcommit: 8759541301241e03784c5ac87b56986f22bd0561
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2017
---
# <a name="connect-g-suite-to-microsoft-cloud-app-security"></a>Verbinding maken tussen G Suite en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande G Suite-account met behulp van de connector-API's.

  
  
## <a name="configure-g-suite"></a>G Suite configureren  
  
1.  Als een G Suite Super Admin, meld u aan bij [https://cloud.google.com/console/project](https://cloud.google.com/console/project).  
  
2.  Klik op **Create project** (Een project maken) om een nieuw project te starten.  
  
     ![google1](./media/google1.png "google1")  
  
3.  In de **nieuw project** scherm, Geef uw project als volgt:</br>
    **Microsoft Cloud App Security** en klik op **maken**.  
           ![google2](./media/google2.png "google2")  
  
4.  Nadat het project is gemaakt, selecteert u in de werkbalk naast Google Cloud Platform, het project en klikt vervolgens onder **API** op **Go to APIs overview**(Naar API's-overzicht gaan).  
  
     ![google3](./media/google3.png "google3")  
  
5.  Schakel onder **API** alle vermelde API's uit.  
      
6.  Klik op **Library** (Bibliotheek) en schakel de volgende API's in (gebruik de zoekbalk als de API niet wordt vermeld in de lijst **Popular APIs** (Populaire API's)):  
  
     ![google apis](./media/google4.png "google4")  
  
    > [!NOTE]  
    >  Negeer de waarschuwing over **Credentials** (Referenties) voor nu.  
  
    -   Admin SDK  
  
    -   Audit API  
  
    -   Google Drive API  
  
    -   Google Apps Marketplace SDK  
  
    -   Gmail API  
            
7.  U moet 5 **Enabled APIs** (Ingeschakelde API’s) hebben:  
  
     ![google enabled apis](./media/google5.png "google5")  
  
8.  Klik op **Credentials** (Referenties) gevolgd door **OAuth consent screen** (Scherm toestemming OAuth)  
  
    -   In **productnaam weergegeven voor gebruikers**, type **Microsoft Cloud App Security**.  
  
    -   Alle andere velden zijn optioneel.  
  
    -   Klik op **Opslaan**.  
  
     ![Google-Productnaam](./media/google6.png "google6")  
  
9. In het scherm **API Credentials** (API-referenties), klikt u op de pijl naast **Create credentials** (Referenties maken).  
  
     ![Google-referenties](./media/google7.png "google7")  

10. Selecteer **Service account key** (Serviceaccountsleutel).

     ![Google-account servicesleutel](./media/google8.png "google8")  
  
11. Onder **maken service account key**, kies **nieuwe serviceaccount**, en typ een naam, bijvoorbeeld **serviceaccount 1**. Onder **rol**, kies **Project** en vervolgens **Editor**. Onder **sleuteltype**, kies **P12** en klik op **maken**. Schakel het selectievakje **Enable G Suite Domain-wide Delegation** (Domeinbrede delegatie voor Google Apps inschakelen) in en klik op **Save** (Opslaan).  
  
     ![Sleutel voor service-account maken in Google](./media/google9.png "google9")  
  
12.  Een P12-certificaatbestand wordt opgeslagen op uw computer.  
        
12. In het scherm **Credentials** (Referenties) klikt u aan de rechterkant op **Manage service accounts** (Serviceaccounts beheren).  
       ![Referenties G Suite-serviceaccount](./media/google10.png "G Suite referenties-serviceaccount")  
  
13. Klik op de drie punten rechts van het serviceaccount dat u hebt gemaakt en selecteer **bewerken**.  
  
     ![google edit](./media/google11.png "google edit")  
  
15. Kopieer de **Service-account-ID** toegewezen aan uw service - u hebt dit later nodig.  
  
     ![google service account ID](./media/google13.png "google13")  
  
16. Open het Google-menu door te klikken op de drie horizontale lijnen naast Google Cloud Platform in de titelbalk. Selecteer **API manager** gevolgd door **Dashboard**.  
    
17. Blader omlaag naar de lijst met ingeschakelde API's en klik op het instellingentandwiel naast **Google Drive API**.   
       ![Selecteer Google Drive](./media/google14.png "google14")  

18. Vul in de volgende informatie:

    -   **Toepassingsnaam**: Microsoft Cloud App Security.  
  
    -   **Korte beschrijving en lange beschrijving** (optioneel): Microsoft Cloud App Security kunt u inzicht krijgen in cloudtoepassingen, zodat u kunt beheren, onderzoeken en beheren gebruik van cloudtoepassingen; bedrijfsgegevens kunt beveiligen; en detecteren verdachte activiteiten voor alle cloudtoepassingen.  
  
    -   Google vereist dat u ten minste één toepassingspictogram uploadt. Ga naar [https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip](https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip) voor het downloaden van een zip-bestand met Cloud App Security-pictogrammen. Vervolgens sleept u onder **Application icon** (Pictogram voor toepassing) de afbeeldingen van 128x128 en 32x32 pixels en zet u die neer.  
  
    -   Onder **station integratie** Typ de volgende URL onder **URL openen:**  
  
         https://portal.cloudappsecurity.com/#/services/11770?tab=files  
     
         ![Google station config](./media/google15.png "Google Drive-configuratie")  
  
19. In de lijst **Enabled APIs** (Ingeschakelde API’s) klikt u op het tandwiel voor instellingen naast **Google Apps Marketplace SDK** . 
         ![Google marketplace SDK config](./media/google16.png "Google Drive-configuratie")  

       >[!NOTE]
       > Als het tandwiel is uitgeschakeld, kunt u klikken op **Google Apps Marketplace SDK** in plaats daarvan. 
20. Selecteer het tabblad **Configuration** (Configuratie). 
  
    -   Kopieer het **projectnummer (app-id)** dat bovenaan wordt weergegeven voor later gebruik.  
  
    -   De **toepassingsnaam** melding **Microsoft Cloud App Security**.
  
         Vul de **toepassingsbeschrijving** veld met het 'Microsoft Cloud App Security kunt u inzicht krijgen in de cloud-apps beter kunt beheren, te onderzoeken en te bepalen van cloud-app-gebruik; bedrijfsgegevens kunt beveiligen; en het detecteren van verdachte activiteiten voor alle cloud-Apps."  
  
    -   Schakel het vakje **Enable individual install** (Afzonderlijke installatie inschakelen) uit.  
  
    -   Configureren van de vier vereiste afbeeldingen onder **toepassingspictogrammen**.  
  
         U kunt de afbeeldingen vinden op: [https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip](https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip)  
  
         ![Google marketplace sdk config](./media/google17.png "google17")  
  
    -   Vul de volgende **Support URLs** (URL’s voor ondersteuning) in:  
  
        -   **URL gebruiksrechtovereenkomst**: http://go.microsoft.com/fwlink/?LinkID=733268  
  
        -   **URL privacybeleid**: http://go.microsoft.com/fwlink/?LinkId=512132  
  
    -   Onder **OAuth 2.0 scopes**, kopiëren en plakken van de volgende URL's (kopiëren ze op een tijd en druk op Enter na elke opdracht):  
  
           https://www.googleapis.com/auth/admin.reports.audit.readonly  
  
           https://www.googleapis.com/auth/admin.reports.usage.readonly  
  
           https://www.googleapis.com/auth/drive  
  
           https://www.googleapis.com/auth/drive.appdata  
  
           https://www.googleapis.com/auth/drive.apps.readonly  
  
           https://www.googleapis.com/auth/drive.file  
  
           https://www.googleapis.com/auth/drive.metadata.readonly  
  
           https://www.googleapis.com/auth/drive.readonly  
  
           https://www.googleapis.com/auth/drive.scripts  
  
           https://www.googleapis.com/auth/admin.directory.user.readonly  
  
           https://www.googleapis.com/auth/admin.directory.user.security  
  
           https://www.googleapis.com/auth/admin.directory.user.alias  
  
           https://www.googleapis.com/auth/admin.directory.orgunit  
  
           https://www.googleapis.com/auth/admin.directory.notifications  
  
           https://www.googleapis.com/auth/admin.directory.group.member  
  
           https://www.googleapis.com/auth/admin.directory.group  
  
           https://www.googleapis.com/auth/admin.directory.device.mobile.action  
  
           https://www.googleapis.com/auth/admin.directory.device.mobile  
  
           https://www.googleapis.com/auth/admin.directory.user  
  
    -   Klik op **Save Changes** (Wijzigingen opslaan).  
  
18. Ga naar [admin.google.com](https://admin.google.com/) en kies vervolgens **Security** (beveiliging). 
       ![google security](./media/googlesecurity.png "google8")  
 
19. Kies **API reference** (API-verwijzing).  
       ![Google api inschakelen](./media/googleapi.png "google8")  
      
20. Selecteer **Enable API Access** (API-toegang inschakelen) en klik op **Save changes** (Wijzigingen opslaan).  
  
    ![google api reference](./media/googleapiref.png "google8")  

  
## <a name="configure-cloud-app-security"></a>Cloud App Security configureren  
  
1.  Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
2.  Klik op de pagina **Connected apps** (Verbonden apps) op de knop met het plusteken en selecteer **G Suite**.  
       
  
3.  Vul in het pop-upvenster in de volgende informatie:  
  
     ![Configuratie van G Suite in Cloud App Security](./media/gsuite-config-cas.png "Configuratie van G Suite in Cloud App Security")  
  
    1.  **Het e-mailadres van het serviceaccount** dat u hebt gekopieerd in stap 16.  
  
    2.  **Het projectnummer (app-id)** dat u hebt gekopieerd in stap 21.  
  
    3.  Upload het P12-**certificaat** dat u hebt opgeslagen in stap 12. U moet het wachtwoord die u hebt opgeslagen om dit te doen.  
  
    4.  Voer een **admin account email** in van uw G Suite-beheerder.  
  
    5.  Als u een onbeperkt account van G Suite hebt, schakelt u dit selectievakje in. Zie voor informatie over welke functies beschikbaar in de Cloud App Security voor G Suite onbeperkte zijn [Schakel directe zichtbaarheid, bescherming en beheeracties voor uw apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).  
  
    6.  Klik op **Instellingen opslaan**.  
  
    7.  **Klik op de koppeling** om verbinding te maken met G Suite. Hiermee opent u G Suite en u wordt gevraagd om toegang te verlenen voor Cloud App Security.  
         
    8.  Controleer of de verbinding tot stand is gekomen door op **Test now** (Nu testen) te klikken.  
  
         Het testen kan enkele minuten duren.  
  
         Nadat u de melding hebt gekregen dat de test is geslaagd, klikt u op **Done** (Klaar) en sluit u de pagina van G Suite.  
  
  
Nadat u verbinding hebt gemaakt met G Suite, ontvangt u gebeurtenissen tot 60 dagen voorafgaand aan de verbinding.
  
Na de verbinding met G Suite wordt in Cloud App Security een volledige scan uitgevoerd. Afhankelijk van hoeveel bestanden en gebruikers u hebt, kan het voltooien van de volledige scan even duren. Zodat bijna de real-timescans worden waarop de activiteit wordt gedetecteerd verplaatst naar het begin van de wachtrij scan. Bijvoorbeeld, wordt een bestand dat wordt bewerkt, bijgewerkt of gedeeld meteen gescand. Dit geldt niet voor bestanden die inherent niet zijn gewijzigd. Bijvoorbeeld worden bestanden die worden weergegeven, bekeken, afgedrukt of geëxporteerd gescand tijdens de reguliere scan.
  
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  