---
title: Maken van Cloud App Security-beleid voor het toestaan en blokkeren van toegang | Microsoft Docs
description: In dit onderwerp beschrijft de procedure voor het instellen van een Proxy voor Cloud App Security-beleid voor het toestaan en blokkeren van toegang tot apps die zijn verbonden via Azure AD.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/20/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 9095cff1-f8b0-44a7-b1df-a83e674abbc6
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b91c48262dbf85b133433b9d16615cab934dcddd
ms.sourcegitcommit: 3d943dbb0e0850af0dc390a78d8feca2f3fde61b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/20/2017
---
# <a name="access-policies"></a>Beleidsregels voor toegang 

> [!NOTE]
> Dit is een preview-functie.

Cloud App Security-beleid, schakel real-time bewaking en controle over toegang tot de cloud-apps op basis van gebruiker, locatie, apparaten en apps. U kunt beleidsregels voor toegang voor elk apparaat, met inbegrip van apparaten die niet domein toegevoegd en niet door Windows Intune worden beheerd door het implementeren van clientcertificaten op beheerde apparaten of door gebruik te maken van bestaande certificaten, zoals MDM-certificaten van derden maken. U kunt bijvoorbeeld clientcertificaten te implementeren op beheerde apparaten en vervolgens toegang van apparaten zonder een certificaat te blokkeren. 

> [!NOTE]
> In plaats van toe te staan of volledig, de toegang blokkeert met [sessie beleid](session-policy-aad.md) u toegang kunt toestaan bij de bewaking van de sessie en/of de limiet voor bepaalde sessie-activiteiten. 

## <a name="prerequisites-to-using-access-policies"></a>Vereisten voor het gebruik van beleidsregels voor toegang

- Azure AD Premium P2-licentie
- De relevante apps moeten de [geïmplementeerd met de proxy](proxy-deployment-aad.md)
- Een [beleid voor voorwaardelijke toegang van Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) moet worden voldaan waarmee gebruikers worden omgeleid naar de Cloud App Security-proxy, zoals hieronder wordt beschreven.

> [!NOTE]
> - Toegangsbeleid bieden ook ondersteuning voor apps die zijn geconfigureerd met identiteitsproviders dan Azure AD in Private Preview. Voor meer informatie over de Private Preview sturen een e-mail naar mcaspreview@microsoft.com.

## <a name="create-an-azure-ad-conditional-access-policy"></a>Een beleid voor voorwaardelijke toegang van Azure AD maken

Azure Active Directory-beleid voor voorwaardelijke toegang en Cloud App Security sessie beleidsregels werken in combinatie te bekijken van elke gebruikerssessie en beslissingen met beleid voor elke app. Als u een beleid voor voorwaardelijke toegang instelt in Azure AD, als volgt:

1. Configureer een [beleid voor voorwaardelijke toegang van Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) met toewijzingen voor de gebruiker of groep van gebruikers en de SAML-app die u wilt beheren in met de Cloud App Security-proxy. 

  > [!NOTE]
  > Alleen apps die waren [geïmplementeerd met proxy](proxy-deployment-aad.md) worden beïnvloed door dit beleid.

2. Gebruikers naar de Cloud App Security-proxy te routeren door het selecteren van de **beperkingen afgedwongen proxy gebruiken** in de **sessie** blade.

 ![Voorwaardelijke toegang voor proxy-beperkingen voor Azure AD](./media/proxy-deploy-restrictions-aad.png)

## <a name="create-a-cloud-app-security-access-policy"></a>Maak een Cloud App Security-beleid 

Volg deze procedure voor het maken van een nieuw beleid voor toegang:

1. Selecteer in de portal **besturingselement** gevolgd door **beleid**.
2. In de **beleid** pagina, klikt u op **beleid maken** en selecteer **toegangsbeleid**.  

 ![Toegangsbeleid maken](./media/access-policy-menu.png)

3. In de **toegangsbeleid** venster Wijs een naam voor het beleid, zoals *toegang tot niet-beheerde apparaten geblokkeerd voor*.

 ![Nieuw-beleid](./media/access-policy-screen.png)

4. Onder **activiteitbron** in de **activiteiten die overeenkomen met alle van de volgende** sectie, selecteert u extra activiteitfilters om toe te passen aan het beleid. Waaronder de volgende opties: 
     
   - **Apparaat labels**: dit filter gebruiken om niet-beheerde apparaten te identificeren.

   - **Locatie**: dit filter gebruiken om te identificeren onbekende (en dus risicovolle)-locaties. 

   - **IP-adres**: Gebruik dit om te filteren per IP-adressen of gebruik eerder toegewezen IP-Adreslabels. 

   - **Label van de gebruikersagent**: dit filter gebruiken om in te schakelen de heuristiek mobiele en bureaublad-apps identificeren. Dit filter kan worden ingesteld op gelijk is aan of is niet gelijk aan **Native client** en vergelijken met uw mobiele en bureaublad-apps voor elke cloud-app moet worden getest.
  
       ![ondersteuning voor native client](./media/user-agent-tag.png)

5. Onder **acties**, selecteer een van de volgende: 

    - **Toestaan dat**: Stel deze actie expliciet wilt toestaan toegang volgens de door u ingestelde beleidsfilters.

    - **Blok**: instellen van deze actie expliciet toegang volgens de door u ingestelde beleidsfilters wordt geblokkeerd. 

6. U kunt **maken van een waarschuwing voor elke overeenkomende gebeurtenis met de ernst van het beleid** en stel een limiet voor de waarschuwing en selecteer of u wilt dat de waarschuwing als een e-mailbericht, een SMS-bericht of beide.




 
## <a name="see-also"></a>Zie ook  
[Downloads op niet-beheerde apparaten met behulp van Azure AD-proxy-mogelijkheden worden geblokkeerd](use-case-proxy-block-session-aad.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  