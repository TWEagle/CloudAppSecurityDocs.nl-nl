---
title: Verbinding maken tussen G Suite en Cloud App Security voor zichtbaarheid en gebruikscontrole | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen G Suite en Cloud App Security via de API-connector.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/10/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 9dba7289b83397ae68224b56332baf1a59abe704
ms.sourcegitcommit: d9b65152d06b9924231b296ffe565689b44ab93e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2018
---
# <a name="connect-g-suite-to-microsoft-cloud-app-security"></a>Verbinding maken tussen G Suite en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande G Suite-account met behulp van de connector-API's.
  
  
## <a name="configure-g-suite"></a>G Suite configureren  
  
1. Als een G Suite Super Admin, meld u aan bij <a href="https://cloud.google.com/console/project" target="_blank"> https://cloud.google.com/console/project </a>.  
  
2. Klik op **Create project** (Een project maken) om een nieuw project te starten.  
  
    ![google1](./media/google1.png "google1")  
  
3. In de **nieuw project** scherm, Geef uw project als volgt:</br>
   **Microsoft Cloud App Security** en klik op **maken**.  
          ![google2](./media/google2.png "google2")  
  
4. Nadat het project is gemaakt, in de werkbalk klikt u op **Google Cloud Platform** en zorg ervoor dat het juiste project is geselecteerd in de vervolgkeuzelijst omlaag aan de bovenkant.
       
      ![Google project](./media/googleverify-project.png "googleverify project")  

5. Onder **API's** klikt u op **gaat u naar de API's overzicht**.  
  
     ![google3](./media/google3.png "google3")  
  
6. Schakel onder **API** alle vermelde API's uit.  
      
7. Klik op **Library** (Bibliotheek) en schakel de volgende API's in (gebruik de zoekbalk als de API niet wordt vermeld in de lijst **Popular APIs** (Populaire API's)):  
     
   -   Admin SDK  
  
   -   Audit API  
  
   -   Google Drive API  
  
   -   Google Apps Marketplace API  
  
   -   Gmail API  
            
   ![google apis](./media/google4.png "google4")  
  
   > [!NOTE]  
   >  Negeer de waarschuwing over **Credentials** (Referenties) voor nu.  

8. Klik op inschakelen voor elke API.
     ![enable Google APPI](./media/google-api.png "google-api")  
9. U moet beschikken over 5 **ingeschakeld API's**, zorg ervoor dat u andere API's uitschakelen:
  
     ![google enabled apis](./media/google5.png "google5")  
  
10. Klik op **referenties** en selecteer vervolgens de **OAuth toestemming scherm** tabblad.
  
    - In **productnaam weergegeven voor gebruikers**, type **Microsoft Cloud App Security**.  
  
    - Alle andere velden zijn optioneel.  
  
    - Klik op **Opslaan**.  
  
      ![Google-Productnaam](./media/google6.png "google6")  
  
11. In de **referenties** tabblad, klik op de pijl naast **referenties maken**.  
  
     ![Google-referenties](./media/google7.png "google7")  

12. Selecteer **Service account key** (Serviceaccountsleutel).

     ![Google-account servicesleutel](./media/google8.png "google8")  
  
13. Onder **maken service account key**, kies **nieuwe serviceaccount**, en typ een naam, bijvoorbeeld **serviceaccount 1**. Onder **rol**, kies **Project** en vervolgens **Editor**. Onder **sleuteltype**, kies **P12** en klik op **maken**. Een P12-certificaatbestand wordt opgeslagen op uw computer.
 
     ![Sleutel voor service-account maken in Google](./media/google9.png "google9")  
  
14. Kopieer de **Service-account-ID** toegewezen aan uw service - u hebt dit later nodig.    
        
15. In het scherm **Credentials** (Referenties) klikt u aan de rechterkant op **Manage service accounts** (Serviceaccounts beheren).  
     
    ![Referenties G Suite-serviceaccount](./media/google10.png "G Suite referenties-serviceaccount")  
  
16. Klik op de drie punten rechts van het serviceaccount dat u hebt gemaakt en selecteer **bewerken**.  
  
     ![google edit](./media/google11.png "google edit")  
  
17. Schakel het selectievakje **Enable G Suite Domain-wide Delegation** (Domeinbrede delegatie voor Google Apps inschakelen) in en klik op **Save** (Opslaan).  
  
     ![Google-service-account-ID](./media/google12.png "google12")  
  
18. Open het Google-menu door te klikken op de drie horizontale lijnen naast Google Cloud Platform in de titelbalk. Klik op **Google Cloud Platform** en klik vervolgens op de **API's en services** tabblad in de links-menu.  
    
19. In het Dashboard dat wordt geopend, bladert u omlaag naar de lijst met ingeschakelde API's en klik op **Google Drive API**.   
       ![Selecteer Google Drive](./media/google14.png "google14")  

20. Klik op de **Drive UI Integration** tabblad en vult u de volgende informatie:

    - **Toepassingsnaam**: Microsoft Cloud App Security.  
  
    - **Korte beschrijving en lange beschrijving** (optioneel): Microsoft Cloud App Security kunt u inzicht krijgen in cloudtoepassingen, zodat u kunt beheren, onderzoeken en beheren gebruik van cloudtoepassingen; bedrijfsgegevens kunt beveiligen; en detecteren verdachte activiteiten voor alle cloudtoepassingen.  
  
    - Google vereist dat u ten minste één toepassingspictogram uploadt. Ga naar [ https://go.microsoft.com/fwlink/?linkid=862826 ](https://go.microsoft.com/fwlink/?linkid=862826) een zipbestand met Cloud App Security pictogrammen te downloaden. Klik vervolgens onder **toepassingspictogram**, klikt u op **Selecteer** naast de 128 x 128 installatiekopie en sleep deze naar het pop-scherm. Klik op **Selecteer** naast de 32 x 32 installatiekopie en sleep deze naar het pop-scherm.  
  
    - Schuif omlaag en in de **station integratie** sectie, typ de volgende URL onder **URL openen:**  
  
       https://portal.cloudappsecurity.com/#/services/11770?tab=files  
    
      ![Edit Google Drive](./media/google15.png "google15")  

21. Klik op **wijzigingen opslaan**.

22. Ga terug naar de **ingeschakeld API's** lijst. Klik op **Apps Marketplace SDK**. 
      
23. Selecteer het tabblad **Configuration** (Configuratie). 
  
    -   Kopieer het **projectnummer (app-id)** dat bovenaan wordt weergegeven voor later gebruik.  
  
    -   Onder **toepassingsnaam** type **Microsoft Cloud App Security**.
  
         In **toepassingsbeschrijving** Typ 'Microsoft Cloud App Security kunt u inzicht krijgen in de cloud-apps beter kunt beheren, te onderzoeken en te bepalen van cloud-app-gebruik; bedrijfsgegevens kunt beveiligen; en het detecteren van verdachte activiteiten voor alle cloud-Apps."  
  
    -   Schakel het vakje **Enable individual install** (Afzonderlijke installatie inschakelen) uit.  
  
    -   Configureren van de vier vereiste afbeeldingen onder **toepassingspictogrammen**.  
  
         De afbeeldingen kunnen worden gevonden op:  [https://go.microsoft.com/fwlink/?linkid=862826](https://go.microsoft.com/fwlink/?linkid=862826)  
  
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

    -   Onder **zichtbaarheid**, selecteer **mijn domein** (niet-openbare). 
    -   Klik op **Save Changes** (Wijzigingen opslaan).  
        ![Google zichtbaarheid](./media/google-visibility.png "google zichtbaarheid")  
24. Ga naar [admin.google.com](https://admin.google.com/) en kies vervolgens **Security** (beveiliging). 
   
      ![Google beveiliging](./media/googlesec.png "google-beveiliging")  
 
25. Kies **API reference** (API-verwijzing).  
       ![Google api inschakelen](./media/googleapi.png "google api")  
      
26. Selecteer **Enable API Access** (API-toegang inschakelen) en klik op **Save changes** (Wijzigingen opslaan).  
  
    ![google api reference](./media/googleapiref.png "google8")  

  
## <a name="configure-cloud-app-security"></a>Cloud App Security configureren  
  
1.  Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
2.  Klik op de pagina **Connected apps** (Verbonden apps) op de knop met het plusteken en selecteer **G Suite**.  
       
  
3.  Vul in het pop-upvenster in de volgende informatie:  
  
     ![Configuratie van G Suite in Cloud App Security](./media/gsuite-config-cas.png "Configuratie van G Suite in Cloud App Security")  
  
    1.  **Service-account-ID** die u in stap 13 gekopieerd.  
  
    2.  **Het projectnummer (app-id)** dat u hebt gekopieerd in stap 21.  
  
    3.  Upload het P12-**certificaat** dat u hebt opgeslagen in stap 12. U moet het wachtwoord die u hebt opgeslagen om dit te doen.  
  
    4.  Voer een **admin account email** in van uw G Suite-beheerder.  
  
    5.  Als u een G Suite bedrijven of Enterprise-account hebt, controleert u dit selectievakje in. Zie voor informatie over welke functies beschikbaar in de Cloud App Security for G Suite bedrijf of onderneming zijn [Schakel directe zichtbaarheid, bescherming en beheeracties voor uw apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).  
  
    6.  Klik op **Instellingen opslaan**.  
  
    7.  **Klik op de koppeling** om verbinding te maken met G Suite. Hiermee opent u G Suite en u wordt gevraagd om toegang te verlenen voor Cloud App Security.  
         
    8.  Controleer of de verbinding tot stand is gekomen door op **Test now** (Nu testen) te klikken.  
  
         Het testen kan enkele minuten duren.  
  
         Nadat u de melding hebt gekregen dat de test is geslaagd, klikt u op **Done** (Klaar) en sluit u de pagina van G Suite.  
  
  
Nadat u verbinding hebt gemaakt met G Suite, ontvangt u gebeurtenissen tot 60 dagen voorafgaand aan de verbinding.
  
Na de verbinding met G Suite wordt in Cloud App Security een volledige scan uitgevoerd. Afhankelijk van hoeveel bestanden en gebruikers u hebt, kan het voltooien van de volledige scan even duren. Zodat bijna de real-timescans worden waarop de activiteit wordt gedetecteerd verplaatst naar het begin van de wachtrij scan. Bijvoorbeeld, wordt een bestand dat wordt bewerkt, bijgewerkt of gedeeld meteen gescand. Dit geldt niet voor bestanden die inherent niet zijn gewijzigd. Bijvoorbeeld worden bestanden die worden weergegeven, bekeken, afgedrukt of geëxporteerd gescand tijdens de reguliere scan.
  
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  