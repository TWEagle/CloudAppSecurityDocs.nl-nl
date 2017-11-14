---
title: De Proxy Cloud App Security voor Azure AD-apps implementeren | Microsoft Docs
description: Dit onderwerp bevat informatie over het implementeren van de Microsoft Cloud App Security-Proxy voor Azure AD-apps.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/13/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2490c5e5-e723-4fc2-a5e0-d0a3a7d01fc2
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 3717d7358b3b869dca918fcaa60a2b2b465df367
ms.sourcegitcommit: eb4e70b6fa15cfff01932a711cecee38f67bc058
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2017
---
# <a name="deploy-proxy-for-azure-ad-apps"></a>Proxy voor Azure AD-apps implementeren

> [!NOTE]
> Dit is een preview-functie.

Volg deze stappen voor het configureren van Azure AD-apps worden beheerd door de Cloud App Security-proxy.

> [!NOTE]
> Als u wilt de proxy Cloud App Security voor Azure AD-apps implementeert, moet u een geldige [licentie voor Azure AD Premium-P2](https://docs.microsoft.com/azure/active-directory/license-users-groups).

## <a name="step-1-add-azure-ad-apps-in-cloud-app-security"></a>Stap 1: Azure AD-apps toevoegen in de Cloud App Security  

1. Maak een Azure AD testbeleid voor voorwaardelijke toegang.

    1. In Azure Active Directory, onder **beveiliging**, klikt u op **voorwaardelijke toegang**.

     ![Voorwaardelijke toegang van Azure AD](./media/aad-conditional-access.png)

    2. Klik op **nieuw beleid** en maak een nieuw beleid om ervoor te zorgen dat onder **sessie** u **beperkingen afgedwongen proxy gebruiken**.

     ![Voorwaardelijke toegang van Azure AD](./media/proxy-deploy-restrictions-aad.png)

    3. In het beleid testen onder **gebruikers**, een testgebruiker of de gebruiker die kan worden gebruikt voor een eerste aanmelding toewijzen.
    
    4. In het beleid testen onder **Cloud-app**, de apps die u wilt toewijzen aan besturingselement met de proxy. 

     > [!NOTE]
     >Zorg ervoor dat apps die worden ondersteund door de proxy te kiezen. De proxy ondersteunt apps die zijn geconfigureerd met SAML eenmalige aanmelding in Azure AD. Office 365-toepassingen zijn bijvoorbeeld niet geconfigureerd met SAML zodat ze worden momenteel niet ondersteund.


2.  Nadat u het beleid hebt gemaakt, moet u zich aanmelden bij elke app die is geconfigureerd in het beleid aan een gebruiker die is geconfigureerd in het beleid. Zorg ervoor dat eerst afmelding van bestaande sessies.

3.  In de Cloud App Security-portal, gaat u naar het instellingentandwiel en kies **Proxy**. 
    
      ![proxy-menu](./media/proxy-menu.png)

4.  U ziet een bericht laten weten dat nieuwe Azure AD-apps zijn gedetecteerd door de proxy. Klik op de **weergeven van nieuwe apps** koppeling.

 ![proxy weergave nieuwe apps](./media/proxy-view-new-apps.png)

5.  In het dialoogvenster dat wordt geopend, ziet u alle apps die u in de vorige stap hebt aangemeld. Voor elke app klikt u op de + Meld u aan en klik vervolgens op **toevoegen**.

 ![nieuwe proxy-apps](./media/proxy-new-app.png)

 > [!NOTE]
 > Als een app niet wordt weergegeven in de catalogus met Cloud App Security-Apps, verschijnt in het dialoogvenster onder onbekend apps samen met de aanmeldings-URL. Wanneer te klikken op het plusteken om deze apps is het mogelijk om aan te raden de app toe te voegen aan de catalogus. Nadat de app in de catalogus is, voert u de stappen voor het implementeren van de app. 

6.  Bekijk in de tabel proxy-apps de **beschikbare besturingselementen** kolom en controleer of zowel de voorwaardelijke toegang van Azure AD als de sessie-besturingselement worden weergegeven. <br></br>Als Sessiecontrole niet voor een app wordt weergegeven, betekent dit dat het is nog niet beschikbaar voor die specifieke app en u ziet de **aanvragen Sessiecontrole** in plaats daarvan koppelt. Klik op het in een dialoogvenster te openen en aanvragen van het voorbereiden van de app om te bepalen van de sessie. Tijdens de periode van de openbare preview Proxy worden het voorbereidingsproces samen met u uitgevoerd door het team van Cloud App Security.
  
 ![beheer van de aanvraag-sessies](./media/request-session-control.png)

7. Optionele - apparaten met behulp van clientcertificaten identificeren:

      1. Ga naar het instellingentandwiel en kies **apparaat identificatie**.

      2. Een basiscertificaat uploaden.

        ![Apparaat-id](./media/device-identification.png)
 
       Nadat het certificaat is geüpload, kunt u sessie beleid op basis van **apparaat tag** gelijk is aan of niet gelijk aan **geldig clientcertificaat**.
 
      > [!NOTE]
      >Een certificaat wordt alleen worden aangevraagd van een gebruiker als de sessie overeenkomt met een beleid dat het certificaat geldig client filter gebruikt. 

## <a name="step-2-test-the-deployment"></a>Stap 2: De implementatie testen

1. Eerste logboek buiten eventuele bestaande sessies. Vervolgens probeert aan te melden elke app die is geïmplementeerd, gebruik van een gebruiker die overeenkomt met het beleid dat is geconfigureerd in Azure AD. 

2.  In de Cloud App Security-portal onder **onderzoeken**, selecteer **activiteitenlogboek**, en zorg ervoor dat de aanmeldings-activiteiten zijn vastgelegd voor elke app.

3.  U kunt filteren door te klikken op **Geavanceerd**, en vervolgens filteren met behulp van **bron gelijk is aan voorwaardelijke toegang van Azure Active Directory**.

     ![Filteren met behulp van voorwaardelijke toegang van Azure AD](./media/sso-logon.png)

3. Het is raadzaam dat u zich bij de mobiele en bureaublad-apps op beheerde en onbeheerde apparaten aanmeldt om ervoor te zorgen dat de activiteiten goed worden vastgelegd in het gebeurtenissenlogboek.<br></br>
Om te bevestigen dat de activiteit goed wordt vastgelegd, klikt u op een logboekbestand voor eenmalige aanmelding op activiteit zodat Hiermee opent u de sectie van de activiteit en zorg ervoor dat de **label van de gebruikersagent** correct weergeeft of het apparaat een native client is (wat betekent dat ofwel een mobiele of bureaubladtoepassingen app) of het apparaat is een beheerd apparaat (compatibel zijn, domein lid of een geldig clientcertificaat).
 
 ![label van de gebruikersagent testen](./media/domain-joined.png)


U bent nu klaar om te maken [sessie beleid](session-policy-aad.md) om uw proxy-apps te beheren.



## <a name="see-also"></a>Zie ook  
[Werken met de Cloud App Security-proxy](proxy-intro-aad.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  