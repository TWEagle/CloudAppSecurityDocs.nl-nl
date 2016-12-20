---
title: Verbinding maken met Google Apps | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen Google Apps en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/23/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b938e1e0-356d-4cc6-ba4a-862c0c59d709
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 6beb9041b338406fb5b16f4bd045dbdc4592c6d9
ms.openlocfilehash: b28eaa521980cb7ec8eee94f0168ca07286533e7


---

# <a name="connect-google-apps-to-microsoft-cloud-app-security"></a>Verbinding maken tussen Google Apps en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande Google Apps-account met behulp van de connector-API's voor de app.

  
  
## <a name="configure-google-apps"></a>Google Apps configureren  
  
1.  Als Google Apps Super Admin meldt u zich aan bij [https://cloud.google.com/console/project](https://cloud.google.com/console/project).  
  
2.  Klik op **Create an empty project** (Een leeg project maken) om een nieuw project te starten.  
  
     ![Google1](./media/google1.png "google1")  
  
3.  In het scherm **New project** (Nieuw project):  
  
    1.  Geef uw project de naam **Cloud App Security for Google**.  
  
    2.  Selecteer of u zich wilt abonneren op updates.  
  
    3.  Controleer en ga akkoord met de gebruiksrechtovereenkomst.  
  
    4.  Klik op **Maken**.  
  
         ![Google2](./media/google2.png "google2")  
  
4.  Nadat het project is gemaakt, klikt u op **Enable and manage APIs** (API’s inschakelen en beheren).  
  
     ![Google3](./media/google3.png "google3")  
  
5.  Klik op het tabblad **Enabled APIs** (Ingeschakelde API’s) en schakel alle vermelde API's uit.  
  
     ![Google5](./media/google5.png "google5")  
  
6.  Klik op het tabblad **Google APIs** (API's van Google) en schakel de volgende API's in (gebruik de zoekbalk als de API niet wordt vermeld in de lijst **Popular APIs** (Populaire API's)):  
  
     ![Google8](./media/google8.png "google8")  
  
    > [!NOTE]  
    >  Negeer de waarschuwing over **Credentials** (Referenties) voor nu.  
  
    -   Admin SDK  
  
    -   Audit API  
  
    -   Drive API  
  
    -   Google Apps Marketplace SDK  
  
    -   Gmail API  
  
         ![Google11-waarschuwing](./media/google11-warning.png "google11 warning")  
  
7.  U moet 5 **Enabled APIs** (Ingeschakelde API’s) hebben:  
  
     ![Google15](./media/google15.png "google15")  
  
8.  Klik op **Credentials** (Referenties) gevolgd door **OAuth consent** (Toestemming OAuth)  
  
    -   In **Product name shown to users** (Productnaam weergegeven voor gebruikers) typt u **Cloud App Security for Google**.  
  
    -   Alle andere velden zijn optioneel.  
  
    -   Klik op **Opslaan**.  
  
     ![Google16](./media/google16.png "google16")  
  
9. Op het tabblad **Credentials** (Referenties) klikt u op de pijl naast **Create credentials** (Referenties maken) en selecteert u **Service account key** (Sleutel serviceaccount).  
  
     ![Google17](./media/google17.png "google17")  
  
10. In **Service account** kiest u **New service account** (Nieuw serviceaccount) en typt u een naam, bijvoorbeeld **Serviceaccount 1**.  
  
     ![Google19](./media/google19.png "google19")  
  
     Onder **Key type** (Type sleutel) kiest u **P12** en klikt u op **Create** (Maken).  
  
     Er wordt een P12-certificaatbestand gedownload. Sla het certificaat op voor later gebruik.  
  
     ![Google20](./media/google20.png "google20")  
  
11. Op het tabblad **Credentials** (Referenties) klikt u aan de rechterkant op **Manage service accounts** (Serviceaccounts beheren).  
  
     ![Google Apps-referenties serviceaccount](./media/google-apps-credentials-service-account.png "google apps credentials service account")  
  
12. Klik op de 3 punten rechts van het serviceaccount dat u hebt gemaakt en selecteer **Edit** (Bewerken).  
  
     ![Google22](./media/google22.png "google22")  
  
13. Schakel het selectievakje **Enable Google Apps Domain-wide Delegation** (Domeinbrede delegatie voor Google Apps inschakelen) in en klik op **Save** (Opslaan).  
  
     ![Google24](./media/google24.png "google24")  
  
14. Kopieer het **e-mailadres** dat is toegewezen aan uw service, u hebt dit later nodig.  
  
     ![Google25](./media/google25.png "google25")  
  
15. Open het Google-menu door op de drie horizontale lijnen naast Google Cloud Platform te klikken en selecteer **API manager**.  
  
     ![Google-menu](./media/google-menu.png "google menu")  
  
     Selecteer **Enabled APIs** (Ingeschakelde API’s).  
  
     ![Google27](./media/google27.png "google27")  
  
16. Klik op het tandwiel voor de instellingen naast **Drive API** (API station) en vul onder **Drive UI Integration** (Integratie met API station) het volgende in:  
  
    -   **Application Name** (Naam toepassing): Cloud App Security for Google.  
  
    -   **Short Description & Long Description** (Korte beschrijving en lange beschrijving): Met Microsoft Cloud App Security kunt u inzicht krijgen in cloudtoepassingen, zodat u het gebruik van cloudtoepassingen kunt sturen, onderzoeken en beheren; bedrijfsgegevens kunt beveiligen; en verdachte activiteiten kunt detecteren voor alle cloudtoepassingen.  
  
    -   Upload onder **Application icon** (Pictogram voor toepassing) de afbeeldingen van 128x128 en 32x32 pixels.  
  
         U kunt de afbeeldingen vinden op: [https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip](https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip)  
  
    -   Typ het volgende onder **Open URL** (URL openen):  
  
         https://portal.cloudappsecurity.com/#/services/11770?tab=files  
  
    -   Klik op **Save Changes** (Wijzigingen opslaan).  
  
         ![Google29](./media/google29.png "google29")  
  
17. In de lijst **Enabled APIs** (Ingeschakelde API’s) klikt u op het tandwiel voor instellingen naast **Google Apps Marketplace SDK** en selecteert u het tabblad **Configuration** (Configuratie).  
  
    -   Kopieer het **projectnummer (app-id)** dat bovenaan wordt weergegeven voor later gebruik.  
  
    -   **Application Name** (Naam toepassing): Cloud App Security for Google.  
  
         Vul bij **Application description** (Beschrijving toepassing) het volgende in: "Met Microsoft Cloud App Security kunt u inzicht krijgen in cloud-apps, zodat u het gebruik van cloud-apps kunt sturen, onderzoeken en beheren; bedrijfsgegevens kunt beveiligen; en verdachte activiteiten kunt detecteren voor alle cloud-apps."  
  
    -   Schakel het vakje **Enable individual install** (Afzonderlijke installatie inschakelen) uit.  
  
    -   Configureer de 4 vereiste afbeeldingen onder **Application icons** (Pictogrammen voor toepassingen).  
  
         U kunt de afbeeldingen vinden op: [https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip](https://portal.cloudappsecurity.com/cas/static/files/MSLogos.zip)  
  
         ![Google31](./media/google31.png "google31")  
  
    -   Vul de volgende **Support URLs** (URL’s voor ondersteuning) in:  
  
        -   **URL gebruiksrechtovereenkomst**: http://go.microsoft.com/fwlink/?LinkID=733268  
  
        -   **URL privacybeleid**: http://go.microsoft.com/fwlink/?LinkId=512132  
  
    -   Onder **OAuth 2.0 scopes** (Bereik OAuth 2.0) typt u het volgende (1 per regel. Druk op Enter om te bevestigen):  
  
        -   https://www.googleapis.com/auth/admin.reports.audit.readonly  
  
        -   https://www.googleapis.com/auth/admin.reports.usage.readonly  
  
        -   https://www.googleapis.com/auth/drive  
  
        -   https://www.googleapis.com/auth/drive.appdata  
  
        -   https://www.googleapis.com/auth/drive.apps.readonly  
  
        -   https://www.googleapis.com/auth/drive.file  
  
        -   https://www.googleapis.com/auth/drive.metadata.readonly  
  
        -   https://www.googleapis.com/auth/drive.readonly  
  
        -   https://www.googleapis.com/auth/drive.scripts  
  
        -   https://www.googleapis.com/auth/admin.directory.user.readonly  
  
        -   https://www.googleapis.com/auth/admin.directory.user.security  
  
        -   https://www.googleapis.com/auth/admin.directory.user.alias  
  
        -   https://www.googleapis.com/auth/admin.directory.orgunit  
  
        -   https://www.googleapis.com/auth/admin.directory.notifications  
  
        -   https://www.googleapis.com/auth/admin.directory.group.member  
  
        -   https://www.googleapis.com/auth/admin.directory.group  
  
        -   https://www.googleapis.com/auth/admin.directory.device.mobile.action  
  
        -   https://www.googleapis.com/auth/admin.directory.device.mobile  
  
        -   https://www.googleapis.com/auth/admin.directory.user  
  
    -   Klik op **Save Changes** (Wijzigingen opslaan).  
  
18. Selecteer **Security** (Beveiliging) in de lijst met besturingselementen. Als u deze optie niet ziet, selecteert u More controls (Meer besturingselementen) in de grijze balk aan de onderkant van de pagina en selecteert u vervolgens **Security** (Beveiliging).  
  
     ![Google Apps-beveiliging](./media/google-apps-security.png "google apps security")  
  
19. Kies **API reference** (API-verwijzing).  
  
     ![Google API-verwijzing](./media/google-api-ref.png "google api ref")  
  
20. Selecteer **Enable API Access** (API-toegang inschakelen) en klik op **Save changes** (Wijzigingen opslaan).  
  
     ![Google API-toegang](./media/google-api-access.png "google api access")  
  
## <a name="configure-cloud-app-security"></a>Cloud App Security configureren  
  
1.  Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
2.  Klik op de pagina **Verbonden apps** op de knop met het plusteken en selecteer **Google Apps**.  
  
     ![Verbinding maken met Google Apps](./media/connect-google-apps.png "connect google apps")  
  
3.  Vul het volgende in het pop-upvenster in:  
  
     ![Configuratie van Google Apps in Cloud App Security](./media/google-apps-configuration-in-cloud-app-security.png "Google Apps Configuration in Cloud App Security")  
  
    1.  **Het e-mailadres van het Google serviceaccount** dat u hebt genoteerd in stap 14.  
  
    2.  **Het Google-projectnummer (app-id)** dat u hebt genoteerd in stap 17.  
  
    3.  Upload het **Google-certificaat** P12 dat u hebt opgeslagen in stap 10.  
  
    4.  Voer één **e-mailadres voor beheer** in van uw Google Apps-beheerder.  
  
    5.  Als u een onbeperkt account van Google Apps hebt, schakelt u dit selectievakje in. Zie [Enable instant visibility, protection and governance actions for your apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) (Directe zichtbaarheid, bescherming en beheeracties voor uw apps inschakelen) voor informatie over welke functies beschikbaar zijn in Cloud App Security voor een onbeperkt account van Google Apps.  
  
    6.  Klik op **Instellingen opslaan**.  
  
    7.  **Volg de link** om verbinding te maken met Google Apps. Google Apps wordt geopend en u wordt gevraagd de toegang voor Cloud App Security te autoriseren.  
  
         ![Google Apps-autorisatieaanvraag](./media/google-apps-authorization-request.png "Google Apps authorization request")  
  
    8.  Controleer of de verbinding tot stand is gekomen door op **Test API** te klikken.  
  
         Het testen kan enkele minuten duren.  
  
         Nadat u de melding hebt gekregen dat de test is geslaagd, klikt u op **Done** (Klaar) en sluit u de pagina van Google Apps.  
  
  
Nadat u verbinding hebt gemaakt met Google Apps, ontvangt u gebeurtenissen tot 60 dagen voorafgaand aan de verbinding.
  
Na de verbinding met Google Apps wordt in Cloud App Security een volledige scan uitgevoerd. Afhankelijk van hoeveel bestanden en gebruikers u hebt, kan het voltooien van de volledige scan even duren. Als u NRT-scans (Near Real-Time) wilt inschakelen, worden de bestanden waarvoor activiteit is gedetecteerd naar het begin van de scanwachtrij verplaatst. Een bestand dat wordt bewerkt, bijgewerkt of gedeeld, wordt bijvoorbeeld direct gescand en voor een dergelijk bestand wordt niet op het reguliere scanproces gewacht. Dit geldt niet voor bestanden die niet inherent zijn gewijzigd, bijvoorbeeld bestanden die zijn weergegeven, afgedrukt, geëxporteerd of waarvan een voorbeeld is bekeken.
  
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Nov16_HO5-->


