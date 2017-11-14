---
title: Het blokkeren van gevoelige gegevens voor niet-beheerde apparaten met behulp van Cloud App Security proxy worden gedownload | Microsoft Docs
description: Dit onderwerp beschrijft het scenario voor het beveiligen van uw organisatie tegen downloads van gevoelige gegevens door niet-beheerde devicesusing Azure AD-proxymogelijkheden.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/13/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 06238ebc-2088-4372-9412-96cceaf3b145
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 5d49c04f6ddfda778bc3775805a42383a41f88c4
ms.sourcegitcommit: eb4e70b6fa15cfff01932a711cecee38f67bc058
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2017
---
# <a name="blocking-downloads-of-sensitive-information-using-the-microsoft-cloud-app-security-proxy"></a>Downloads van gevoelige gegevens via de Microsoft Cloud App Security-proxy worden geblokkeerd


De hedendaagse IT-beheerder is vastgelopen tussen een steen en vaste place: U wilt uw werknemers productief inschakelen. Dit betekent dat werknemers toegang tot apps om te op elk gewenst moment, vanaf elk apparaat werken kunnen toestaan. Aan de andere kant u wilt beveiligen van het bedrijf en die bedrijfseigen en bevoorrechte informatie bevat. Hoe kunt u uw werknemers toegang hebben tot uw cloud-apps en bescherming van uw gegevens inschakelen? **U kunt deze gebruiksvoorbeeld naar blok downloads door gebruikers die toegang tot uw vertrouwelijke gegevens in de enterprise cloud-apps van niet-beheerde apparaten of locaties buiten-bedrijfsnetwerk hebben.**


## <a name="the-threat"></a>De bedreiging
Een accountmanager in uw organisatie wil iets in Salesforce thuis tijdens het weekend, op hun persoonlijke laptop te controleren. De Salesforce-gegevens kan client creditcard of persoonlijke gegevens bevatten. De PC zonder begeleiding is, betekent dat als ze documenten van Salesforce op deze downloaden, deze kan worden geïnfecteerd met kwaadaardige software of als dit is zoekgeraakt of gestolen, niet zijn kan beveiligd met een wachtwoord en iedereen die het vindt home heeft toegang tot gevoelige informatie. 

## <a name="the-solution"></a>De oplossing
Beveiligen van uw organisatie door te controleren en beheren van cloud-app gebruikt met voorwaardelijke toegang van Azure AD en de Cloud App Security-proxy.  

## <a name="prerequisites"></a>Vereisten

- Een geldige licentie voor Azure AD Premium-P2
- Een cloud-app configureren voor eenmalige aanmelding in Azure AD  
- Zorg ervoor dat de [app wordt geïmplementeerd en Cloud App Security](proxy-deployment-aad.md)

## <a name="create-a-block-download-policy-for-unmanaged-devices"></a>Maak een beleid voor het downloaden van blok voor onbeheerde apparaten  

Cloud App Security sessie beleidsregels kunt u de sessie op basis van apparaatstatus verder te beperken. Wanneer u een sessie met behulp van het apparaat als een voorwaarde beheren wilt, moet u zowel een beleid voor voorwaardelijke toegang maken en als het beleid voor sessies om dit te bereiken.  

### <a name="step-1-create-an-azure-ad-conditional-access-policy"></a>Stap 1: Maak een beleid voor voorwaardelijke toegang van Azure AD

1. Maak een Azure AD-beleid voor voorwaardelijke toegang met toegewezen gebruikers- en app.
2. Selecteer **beperkingen afgedwongen proxy gebruiken** onder sessie besturingselementen in het beleid voor voorwaardelijke toegang.   

 ![Voorwaardelijke toegang van Azure AD](./media/proxy-deploy-restrictions-aad.png)

Na het voltooien van deze taak gaat u verder met de Cloud App Security-portal en maak een beleid voor sessies kunt bewaken en beheren van downloaden van bestanden in de sessie.

### <a name="step-2-create-a-session-policy"></a>Stap 2: Een sessie-beleid maken

1. Selecteer in de Cloud App Security-portal **besturingselement** gevolgd door **beleid**. 

2. In de **beleid** pagina, klikt u op **beleid maken** gevolgd door **sessie beleid**.
 
 ![Sessie-beleid maken](./media/create-session-policy.png)

2. In de **sessie beleid maken** pagina, Geef uw beleid een naam en beschrijving. Bijvoorbeeld: **blok downloadt van Salesforce voor onbeheerde apparaten**.

3. Wijs een **beleid ernst** en **categorie**.

 ![Beleid voor nieuwe sessie](./media/new-session-policy.png)

4. Onder **sessie besturingselementtype**, selecteer **alle activiteiten bewaken en beheren van het downloaden van bestand**. Dit biedt u de mogelijkheid voor het bewaken van alles wat die gebruikers doen binnen een Salesforce-sessie en geeft u tot blok beheren en beveiligen van downloads in realtime.

 ![sessie-beleidstype besturingselement](./media/session-policy-control-type.png)

5.  onder **activiteitbron** in de **activiteiten die overeenkomen met alle van de volgende** sectie, selecteer het filter: 
    
    - **Apparaat-tag**: Selecteer **is niet gelijk aan** en selecteer vervolgens **compatibele**, **verbonden met het domein**, of **geldig clientcertificaat**, afhankelijk van de methode voor het identificeren van beheerde apparaten in uw organisatie gebruikt. 
    
    - **App**: Selecteer de app die u beheren wilt.  

    - **Gebruikers**: Selecteer de gebruikers die u wilt bewaken.  
    
7. U kunt ook als u wilt blokkeren de downloads voor de locaties die geen deel uitmaken van uw bedrijfsnetwerk onder **activiteitbron** in de **activiteiten die overeenkomen met alle van de volgende** sectie, stelt u de de volgende filters: 

  - **IP-adres** of **locatie**: U kunt een van deze twee parameters niet-zakelijk of onbekende locaties, waaruit een gebruiker probeert te krijgen tot gevoelige gegevens te identificeren.

     > [!NOTE]
     > Als u wilt blokkeren downloads van zowel onbeheerde apparaten en niet-zakelijk locaties, hebt u twee sessie beleidsregels, die ingesteld maken de **activiteitbron** met behulp van de locatie en een stelt de **activiteit bron** op niet-beheerde apparaten.
 
   - **App**: Selecteer de app die u beheren wilt.    
   
   - **Gebruikers**: Selecteer de gebruikers die u wilt bewaken.  

6. Onder **activiteitbron** in de **bestanden die overeenkomen met alle van de volgende** sectie, stelt u de volgende filters: 
   
    - **Classificatielabels**: als u classificatielabels voor Azure Information Protection en de bestanden op basis van een specifiek label van de Azure Information Protection-classificatie wilt filteren.
   
    - Selecteer **bestandsnaam** of **bestandstype** om toe te passen op basis van deze beperkingen.
 
     ![sessie beleid bestandsfilters](./media/session-policy-file-filters.png)

7. Schakel **inhoudscontrole** inschakelen van de interne DLP om te scannen bestanden voor een gevoelige inhoud. 

 ![sessie beleid inhoudscontrole](./media/session-policy-content-inspection.png)

8. Onder **acties**, selecteer **blok**. De blokkeringsbericht die uw gebruikers krijgen wanneer ze worden niet downloaden van bestanden aanpassen.  

 ![acties voor sessie-beleid](./media/session-policy-actions.png)

9. Stel de waarschuwingen die u wilt ontvangen wanneer het beleid wordt vergeleken. U kunt een limiet kunt instellen, zodat u niet te veel waarschuwingen ontvangt, en u kunt aangeven of de waarschuwingen krijgt als een e-mailbericht of SMS-bericht.

 ![sessie beleid waarschuwingen](./media/session-policy-alert.png)


10. Klik op **Maken**  
 

## <a name="validate-your-policy"></a>Valideren van het beleid 

1. Om te simuleren geblokkeerd bestand downloaden van een onbeheerd apparaat of een niet-zakelijk netwerklocatie aanmelden bij de app en probeert een bestand te downloaden. 

2. Het bestand moet worden geblokkeerd en u ontvangt het bericht dat u onder ingesteld **aanpassen blok berichten**. 

  ![blok downloadbericht](./media/block-download-message.png)

3. Klik in de Cloud App Security-portal op **besturingselement** gevolgd door **beleid**, en klik vervolgens op het beleid dat u hebt gemaakt om het rapport beleid weer te geven. Een sessie beleid overeenkomst moet binnenkort worden weergegeven. 
 
  ![rapport van beleid](./media/session-policy-report.png)

4. In het rapport beleid kunt u zien welke aanmeldingen indien omgeleid naar de proxy voor het beheer van sessies en welke bestanden zijn gedownload of worden geblokkeerd van de bewaakte sessies.




## <a name="see-also"></a>Zie ook  
[Een sessie-beleid maken](session-policy-aad.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  