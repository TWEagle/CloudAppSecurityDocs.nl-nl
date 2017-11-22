---
title: Sessie beleidsregels maken om te diep meer inzicht verkrijgen in sessie gebruikersactiviteiten en blokkeren downloads | Microsoft Docs
description: Dit onderwerp beschrijft de procedure voor het instellen van een beleid voor Cloud App Security Proxy sessies grondige meer inzicht verkrijgen in sessie gebruikersactiviteiten en het blok downloadt.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/13/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 745df28a-654c-4abf-9c90-203841169f90
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c955e20b4abd506f5e44659fbdd921bb54def131
ms.sourcegitcommit: eb4e70b6fa15cfff01932a711cecee38f67bc058
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2017
---
# <a name="session-policies"></a>Sessie-beleid 

> [!NOTE]
> Dit is een preview-functie.

Beleidsregels voor cloud App Security sessie realtime niveau van de sessie-bewaking inschakelen, u gedetailleerde inzicht in de cloud-apps en de mogelijkheid om verschillende acties, afhankelijk van het beleid dat u voor een gebruikerssessie instelt uitvoeren op het netwerk. In plaats van toe te staan of volledig toegang blokkeert, kunt Sessiecontrole u toegang toestaan bij de bewaking van de sessie en/of de limiet voor bepaalde sessie-activiteiten. 

Bijvoorbeeld, kunt u die bepalen van niet-beheerde apparaten of voor sessies die afkomstig zijn van specifieke locaties, die u wilt toestaan dat de gebruiker toegang tot de app, maar ook het downloaden van gevoelige bestanden beperken of vereisen dat bepaalde documenten worden beveiligd op downloaden. Sessie-beleid kunnen u deze besturingselementen gebruikerssessie instellen. 

## <a name="prerequisites-to-using-session-policies"></a>Vereisten voor het gebruik van sessie-beleid

- Azure AD Premium P2-licentie
- De relevante apps moeten de [geïmplementeerd met de proxy](proxy-deployment-aad.md)
- Een [beleid voor voorwaardelijke toegang van Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) moet worden voldaan waarmee gebruikers worden omgeleid naar de Cloud App Security-proxy, zoals hieronder wordt beschreven.


## <a name="create-an-azure-ad-conditional-access-policy"></a>Een beleid voor voorwaardelijke toegang van Azure AD maken

Azure Active Directory-beleid voor voorwaardelijke toegang en Cloud App Security sessie beleidsregels werken in combinatie te bekijken van elke gebruikerssessie en beslissingen met beleid voor elke app. Als u een beleid voor voorwaardelijke toegang instelt in Azure AD, als volgt:

1. Configureer een [beleid voor voorwaardelijke toegang van Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal) met toewijzingen voor de gebruiker of groep van gebruikers en de SAML-app die u wilt beheren in met de Cloud App Security-proxy. 

  > [!NOTE]
  > Alleen apps die waren [geïmplementeerd met proxy](proxy-deployment-aad.md) worden beïnvloed door dit beleid.

2. Gebruikers naar de Cloud App Security-proxy te routeren door het selecteren van de **beperkingen afgedwongen proxy gebruiken** in de **sessie** blade.

 ![Voorwaardelijke toegang voor proxy-beperkingen voor Azure AD](./media/proxy-deploy-restrictions-aad.png)

## <a name="create-a-cloud-app-security-session-policy"></a>Maak een beleid van de sessie Cloud App Security 

Volg deze procedure voor het maken van een nieuwe sessie beleid:

1. Selecteer in de portal **besturingselement** gevolgd door **beleid**.
3. In de **beleid** pagina, klikt u op **beleid maken** en selecteer **sessie beleid**.  

 ![Sessie-beleid maken](./media/create-session-policy.png)

4. In de **sessie beleid** venster Wijs een naam voor het beleid, zoals *blok downloaden van gevoelige documenten in het vak voor Marketing gebruikers*.

 ![Beleid voor nieuwe sessie](./media/new-session-policy.png)

5. In de **sessie besturingselementtype** veld: 

    1. Selecteer **bewaken van alle activiteiten** als u alleen wilt bewaken van activiteiten door gebruikers.

    2. Selecteer **bewaken van alle activiteiten & downloaden van bestanden beheren** als u wilt controleren van gebruikersactiviteiten en extra acties zoals blok uitvoeren of downloads mogelijk voor gebruikers te beveiligen.

    ![sessie-beleidstype besturingselement](./media/session-policy-control-type.png)

6. Onder **activiteitbron** in de **activiteiten die overeenkomen met alle van de volgende** sectie, selecteert u extra activiteitfilters om toe te passen aan het beleid. Waaronder de volgende opties: 

     - **Apparaat labels**: dit filter gebruiken om niet-beheerde apparaten te identificeren.

     - **Locatie**: dit filter gebruiken om te identificeren onbekende (en dus risicovolle)-locaties. 

     - **IP-adres**: Gebruik dit om te filteren per IP-adressen of gebruik eerder toegewezen IP-Adreslabels. 

     - **Label van de gebruikersagent**: dit filter gebruiken om in te schakelen de heuristiek mobiele en bureaublad-apps identificeren. Dit filter kan worden ingesteld op gelijk is aan of is niet gelijk aan **Native client** en vergelijken met uw mobiele en bureaublad-apps voor elke cloud-app moet worden getest.
         
         ![ondersteuning voor native client](./media/user-agent-tag.png)

       >[!NOTE]
       >Sessie-beleid ondersteunt niet mobiele en bureaublad-apps. Zorg ervoor dat sessie-beleidsregels om te zien dat ze geen invloed op mobiele en bureaublad-app-functionaliteit testen. Indien nodig, sluit u mobiele en bureaublad-apps uit de sessie beleidsregels.

     ![sessie-beleidsbron activiteit](./media/session-policy-activity-filters.png)

7. Als u de optie voor het geselecteerd **bewaken van alle activiteiten & downloaden van bestanden beheren**:

    1. Onder **activiteitbron** in de **bestanden die overeenkomen met alle van de volgende** sectie, selecteert u extra bestandsfilters toepassen op het beleid. Waaronder de volgende opties:

        - **Classificatie label** -dit filter gebruiken als uw organisatie Azure Information Protection gebruikt en uw gegevens beveiligd is door de classificatielabels. Hier vervolgens mogelijk voor het filteren van bestanden op basis van de classificatie-label die u toegepast. Zie voor meer informatie over integratie tussen Cloud App Security en Azure Information Protection [integratie van Azure Information Protection](azip-integration.md).

        - **Bestandsnaam** -dit filter gebruiken voor het beleid toepassen op specifieke bestanden.

        - **Bestandstype** -dit filter gebruiken voor het beleid toepassen op specifieke bestandstypen, bijvoorbeeld blok downloaden voor alle xls-bestanden.

         ![sessie beleid bestandsfilters](./media/session-policy-file-filters.png)

        
    2. In de **inhoudscontrole** sectie instellen of u wilt de DLP-engine documenten scannen en bestandsservers inhoud inschakelen.
 
     ![sessie beleid inhoudscontrole](./media/session-policy-content-inspection.png)

    3. Onder **acties**, selecteer een van de volgende: 

        - **Toestaan dat**: Stel deze actie voor toestaan van expliciet downloaden volgens de door u ingestelde beleidsfilters.

        - **Blok**: Stel deze actie om te downloaden volgens de door u ingestelde beleidsfilters expliciet te blokkeren. Zie voor meer informatie [de werking van blok downloaden](#block-download).

        - **Beveiligen**: als uw organisatie Azure Information Protection gebruikt, kunt u instellen een **actie** toepassen van een label classificatie instellen in Azure Information Protection op het bestand. Zie voor meer informatie [hoe beveiligen downloaden works](#protect-download).

         ![acties voor sessie-beleid](./media/session-policy-actions.png)

10. U kunt **maken van een waarschuwing voor elke overeenkomende gebeurtenis met de ernst van het beleid** en stel een limiet voor de waarschuwing en selecteer of u wilt dat de waarschuwing als een e-mailbericht, een SMS-bericht of beide.

    ![Waarschuwing voor sessie-beleid](./media/session-policy-alert.png)


## <a name="how-session-monitoring-works"></a>Hoe sessiebewaking werkt

Wanneer u een beleid sessie maakt, wordt elke gebruikerssessie die overeenkomt met het beleid omgeleid naar de proxy-Sessiecontrole in plaats van de app rechtstreeks. De gebruiker ziet een melding controle wilt laten weten dat hun sessies worden bewaakt.

   ![sessie bewaking van de kennisgeving](./media/session-monitoring-notice.png)

Als u niet de gebruiker waarschuwen wilt dat ze worden bewaakt, kunt u het meldingsbericht uitschakelen.

1. Selecteer onder het instellingentandwiel **algemene instellingen**. 

2. Vervolgens onder de proxy-instellingen voor Cloud App Security, schakel de **gebruikers waarschuwen** selectievakje.

    ![sessie kennisgeving bewaking uitschakelen](./media/disable-session-monitoring-notice.png)

Aan de gebruiker binnen de sessie, de proxy vervangt de relevante URL's, Java-scripts en cookies behouden in de app-sessie met de proxy-URL's. Bijvoorbeeld: als de app een pagina met koppelingen waarvan domeinen eindigt op myapp.com retourneert, de proxy wordt vervangen door de koppelingen met domeinen die eindigt met ongeveer: myapp.com.us.cas.ms. Op deze manier wordt de hele sessie bewaakt door de proxy.

De proxy registreert de logboeken over webverkeer van elke gebruikerssessie die ermee wordt doorgestuurd. De verkeerslogboeken bevatten de gebruikersagent van de tijd, IP-adres, URL's bezocht en het aantal bytes geüpload en gedownload. Deze logboeken zijn geanalyseerd en de naam van een doorlopende rapport **Cloud App Security Proxy** wordt toegevoegd aan de lijst met Cloud Discovery-rapporten in de Cloud Discovery-dashboard.

![proxy-rapport](./media/proxy-report.png)


Deze logboeken exporteren:

1. Ga naar het instellingentandwiel en klik **Proxy**.
2. Aan de rechterkant van de tabel, klikt u op de knop exporteren ![knop exporteren](./media/export-button.png). 
3. Selecteer het bereik van het rapport en klikt u op **exporteren**. Dit proces kan enige tijd duren.

Voor het downloaden van het geëxporteerde logboek:

1. Nadat het rapport klaar is, gaat u naar **onderzoeken** en vervolgens **aangepaste rapporten**.
2. Selecteer in de tabel het relevante rapport uit de lijst met **Proxy verkeerslogboeken** en klik op downloaden ![knop downloaden](./media/download-button.png). 


## Hoe blok works downloaden<a name="block-download"></a>

Wanneer **blok** is ingesteld als de **actie** u wilt uitvoeren in de Cloud App Security proxy sessie beleid, de proxy voorkomen dat een gebruiker een bestand in overeenstemming met filters voor bestanden met het beleid downloaden. Een gebeurtenis downloaden wordt herkend door de proxy voor elke SAML-app en wanneer een gebruiker deze gebeurtenis begint, de proxy is opgetreden in realtime te voorkomen dat het wordt uitgevoerd. Wanneer het signaal ontvangen dat een gebruiker een download heeft gestart, de proxy retourneert een **downloaden beperkt** bericht aan de gebruiker en het gedownloade bestand met een tekstbestand met een aangepast bericht voor de gebruiker die kan worden vervangen geconfigureerd via beleid voor de proxy-sessies.  

## Het beveiligen van downloaden werkt<a name="protect-download"></a>

Wanneer **beveiligen** is ingesteld als de **actie** om te worden uitgevoerd in de Cloud App Security proxy sessie beleid, de proxy wordt afgedwongen de labels en volgende beveiliging van een bestand in overeenstemming met het beleid bestand filters. Labels zijn geconfigureerd in de Azure Information Protection-console in Azure en **beveiligen** moet worden geselecteerd in het label voor het label als een optie in de Cloud App Security-beleid wordt weergegeven. Als een label is ingeschakeld en een bestand wordt gedownload, die voldoet aan de criteria van de Cloud App Security-beleid, wordt de naam en de bijbehorende beveiliging (met machtigingen) toegepast op het bestand tijdens het downloaden. Het oorspronkelijke bestand blijft-is in de cloud-app wanneer het gedownloade bestand is nu worden beveiligd. Gebruikers die proberen toegang tot het bestand moeten voldoen aan de machtigingsvereisten bepaald door de beveiliging kan worden toegepast.  
 
 
## <a name="see-also"></a>Zie ook  
[Downloads op niet-beheerde apparaten met behulp van Azure AD-proxy-mogelijkheden worden geblokkeerd](use-case-proxy-block-session-aad.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  