---
title: Integratie van SIEM met Cloud App Security | Microsoft Docs
description: Dit onderwerp bevat informatie over de integratie van uw SIEM met Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/10/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4649423b-9289-49b7-8b60-04b61eca1364
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: beaf31d7c365f62fb9c9dc7b79b0d89f31ee694d
ms.sourcegitcommit: e547c4c91d8de9d4da376e4d4eebbe18c503b7ca
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/18/2017
---
# <a name="siem-integration"></a>Integratie van SIEM
    
Nu kunt u Cloud App Security integreren met uw SIEM-server om in te schakelen gecentraliseerde bewaking van waarschuwingen en activiteiten van verbonden apps. Als nieuwe activiteiten en gebeurtenissen worden ondersteund door verbonden apps, wordt inzicht in deze vervolgens in de Cloud App Security uitgerold. Door de integratie met een SIEM-service kunt u uw cloudtoepassingen beter beveiligen terwijl uw gebruikelijke beveiligingswerkstroom blijft behouden, beveiligingsprocedures worden geautomatiseerd en gebeurtenissen in de cloud en on-premises aan elkaar worden gekoppeld. De Cloud App Security SIEM-agent wordt uitgevoerd op uw server. De agent haalt waarschuwingen en activiteiten op uit Cloud App Security en verzendt deze naar de SIEM-server.

Wanneer u uw SIEM voor het eerst integreert met Cloud App Security, worden activiteiten en waarschuwingen van de laatste twee dagen doorgestuurd naar de SIEM, plus alle activiteiten en waarschuwingen (op basis van het filter dat u selecteert) die daarna volgen. Als u deze functie voor een langere periode uitschakelt en de functie vervolgens weer inschakelt, worden bovendien waarschuwingen en activiteiten van de laatste twee dagen doorgestuurd en vervolgens alle waarschuwingen en activiteiten die daarna volgen.

## <a name="siem-integration-architecture"></a>Architectuur van SIEM-integratie

De SIEM-agent wordt geïmplementeerd in het netwerk van uw organisatie. Wanneer geïmplementeerd en geconfigureerd, wordt de gegevens ophaalt typen die zijn geconfigureerd (waarschuwingen en activiteiten) met Cloud App Security RESTful-API's.
Het verkeer wordt verzonden via een gecodeerd HTTPS-kanaal op poort 443.

Wanneer de SIEM-agent de gegevens van Cloud App Security ophaalt, stuurt de Syslog berichten naar uw lokale SIEM met behulp van de netwerkconfiguraties die u hebt opgegeven tijdens de installatie (TCP of UDP met een aangepaste poort). 

![Architectuur van SIEM-integratie](./media/siem-architecture.png)

## <a name="supported-siems"></a>Ondersteunde siem 's

Cloud App Security ondersteunt momenteel Micro Focus ArcSight en algemene CEF.

## <a name="how-to-integrate"></a>Het integreren van

De integratie met uw SIEM vindt in drie stappen plaats:
1. De integratie instellen in de Cloud App Security-portal. 
2. Het JAR-bestand downloaden en uitvoeren op uw server.
3. Valideren of de SIEM-agent werkt.

### <a name="prerequisites"></a>Vereisten

- Een standaard-Windows- of -Linux-server (kan een virtuele machine zijn).
- Op de server moet Java 8 worden uitgevoerd; eerdere versies worden niet ondersteund.

## <a name="integrating-with-your-siem"></a>Integratie met uw SIEM

### <a name="step-1-set-it-up-in-the-cloud-app-security-portal"></a>Stap 1: De integratie instellen in de Cloud App Security-portal

1. Klik in de Cloud App Security-portal onder het instellingentandwiel **Security extensions** en klik vervolgens op de **SIEM agents** tabblad.

2. Klik op het plusteken om start de **toevoegen SIEM-agent** wizard.
3. Klik in de wizard op **Start Wizard**.   
4. Vul in de wizard een naam in, **selecteer uw SIEM-indeling** en stel **geavanceerde instellingen** in die relevant zijn voor deze indeling. Klik op **Volgende**.

   ![Algemene SIEM-instellingen](./media/siem1.png)

5. Typ het IP-adres of de hostnaam van de **externe Syslog-host** en het **Syslog-poortnummer**. Selecteer TCP of UDP als het externe Syslog-protocol.
Vraag indien nodig uw beveiligingsbeheerder om deze informatie.
Klik op **Volgende**.

  ![Instellingen van extern Syslog](./media/siem2.png)

6. Selecteer welke gegevenstypen, **waarschuwingen** en **activiteiten** u wilt exporteren naar uw SIEM-server. Gebruik de schuifregelaar om deze in en uit te schakelen. Standaard is alles geselecteerd. U kunt de vervolgkeuzelijst **Toepassen op** gebruiken om filters zo in te stellen dat alleen bepaalde waarschuwingen en activiteiten naar uw SIEM-server worden verzonden.
U kunt op **Resultaten bewerken en bekijken** klikken om te controleren of het filter goed werkt. Klik op **Volgende**. 

  ![Instellingen voor gegevenstypen](./media/siem3.png)

7. Kopieer het token en bewaar het voor later. Nadat u op Voltooien hebt geklikt en de wizard hebt afgesloten, wordt de SIEM-pagina opnieuw weergegeven en ziet u in de tabel de SIEM-agent die u hebt toegevoegd. Er wordt nu weergegeven dat deze is **gemaakt** totdat deze later wordt verbonden.

### <a name="step-2-download-the-jar-file-and-run-it-on-your-server"></a>Stap 2: Het JAR-bestand downloaden en uitvoeren op uw server

1. In de [Microsoft Download Center](https://go.microsoft.com/fwlink/?linkid=838596), na het accepteren van de [softwarelicentievoorwaarden](https://go.microsoft.com/fwlink/?linkid=862491), moet het ZIP-bestand downloaden en uitpakken van het.

2. Voer het uitgepakte bestand op uw server:
    
        java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN

> [!NOTE]
> - De bestandsnaam kan verschillen afhankelijk van de versie van de SIEM-agent.
> - Parameters vierkante haakjes [] zijn optioneel en moeten alleen worden gebruikt als relevant.
> - Het is raadzaam de JAR tijdens het opstarten van de server uitgevoerd.
>   - Windows: Als een geplande taak uitvoeren en zorg ervoor dat u configureert u de taak voor **uitvoeren of de gebruiker is aangemeld of niet** en of u schakelt de **de taak stoppen als deze wordt uitgevoerd logner dan** selectievakje.
>   - Linux: Voeg de opdracht uitvoeren met een  **&**  naar het bestand rc.local. Bijvoorbeeld: `java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory DIRNAME] [--proxy ADDRESS[:PORT]] --token TOKEN &`

Hierbij worden de volgende variabelen gebruikt:
- MAPNAAM is het pad naar de map die u wilt gebruiken voor lokale agent-logboeken voor foutopsporing.
- ADRES[: POORT] is het proxyserveradres en de poort die door de server wordt gebruikt om verbinding met internet te maken.
- TOKEN is het SIEM-agenttoken dat u in de vorige stap hebt gekopieerd.

U kunt op elk gewenst moment -h typen om hulp te krijgen.

Het volgende zijn voorbeeld activiteitenlogboeken verzonden naar uw SIEM:
```
2017-11-22T17:50:04.000Z CEF:0|MCAS|SIEM_Agent|0.111.85|EVENT_CATEGORY_LOGOUT|Log out|0|externalId=1511373015679_167ae3eb-ed33-454a-b548-c2ed6cea6ef0 rt=1511373004000 start=1511373004000 end=1511373004000 msg=Log out suser=admin@contoso.com destinationServiceName=ServiceNow dvc=13.82.149.151 requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511373015679_167ae3eb-ed33-454a-b548-c2ed6cea6ef0,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-28T19:40:15.000Z CEF:0|MCAS|SIEM_Agent|0.112.68|EVENT_CATEGORY_VIEW_REPORT|View report|0|externalId=1511898027370_e272cd5f-31a3-48e3-8a6a-0490c042950a rt=1511898015000 start=1511898015000 end=1511898015000 msg=View report: ServiceNow Report 23 suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511898027370_e272cd5f-31a3-48e3-8a6a-0490c042950a,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=23,sys_report,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-28T19:25:34.000Z CEF:0|MCAS|SIEM_Agent|0.112.68|EVENT_CATEGORY_DELETE_OBJECT|Delete object|0|externalId=1511897141625_7558b33f-218c-40ff-be5d-47d2bdd6b798 rt=1511897134000 start=1511897134000 end=1511897134000 msg=Delete object: ServiceNow Object f5122008db360300906ff34ebf96198a suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511897141625_7558b33f-218c-40ff-be5d-47d2bdd6b798,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=,,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-27T20:40:14.000Z CEF:0|MCAS|SIEM_Agent|0.112.49|EVENT_CATEGORY_CREATE_USER|Create user|0|externalId=1511815215873_824f8f8d-2ecd-439b-98b1-99a1adf7ba1c rt=1511815214000 start=1511815214000 end=1511815214000 msg=Create user: user 747518c0db360300906ff34ebf96197c suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511815215873_824f8f8d-2ecd-439b-98b1-99a1adf7ba1c,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=,747518c0db360300906ff34ebf96197c,sys_user,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-27T20:41:20.000Z CEF:0|MCAS|SIEM_Agent|0.112.49|EVENT_CATEGORY_DELETE_USER|Delete user|0|externalId=1511815287798_bcf60601-ecef-4207-beda-3d2b8d87d383 rt=1511815280000 start=1511815280000 end=1511815280000 msg=Delete user: user 233490c0db360300906ff34ebf9619ef suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511815287798_bcf60601-ecef-4207-beda-3d2b8d87d383,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=,233490c0db360300906ff34ebf9619ef,,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

2017-11-28T19:24:55.000Z LAB-EUW-ARCTEST CEF:0|MCAS|SIEM_Agent|0.112.68|EVENT_CATEGORY_DELETE_OBJECT|Delete object|0|externalId=1511897117617_5be018ee-f676-4473-a9b5-5982527409be rt=1511897095000 start=1511897095000 end=1511897095000 msg=Delete object: ServiceNow Object b1709c40db360300906ff34ebf961923 suser=admin@contoso.com destinationServiceName=ServiceNow dvc= requestClientApplication= cs1Label=portalURL cs1=https://contoso.portal.cloudappsecurity.com/#/audits?activity.id\=eq(1511897117617_5be018ee-f676-4473-a9b5-5982527409be,) cs2Label=uniqueServiceAppIds cs2=APPID_SERVICENOW cs3Label=targetObjects cs3=,,admin@contoso.com,admin@contoso.com,admin@contoso.com cs4Label=policyIDs cs4= c6a1Label="Device IPv6 Address" c6a1=

```
Evenals de volgende waarschuwingen logfile voorbeeld:
```
2017-07-15T20:42:30.531Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|myPolicy|3|externalId=596a7e360c204203a335a3fb start=1500151350531 end=1500151350531 msg=Activity policy ''myPolicy'' was triggered by ''admin@box-contoso.com'' suser=admin@box-contoso.com destinationServiceName=Box cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596a7e360c204203a335a3fb cs2Label=uniqueServiceAppIds cs2=APPID_BOX cs3Label=relatedAudits cs3=1500151288183_acc891bf-33e1-424b-a021-0d4370789660 cs4Label=policyIDs cs4=59f0ab82f797fa0681e9b1c7

2017-07-16T09:36:26.550Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b339b0c204203a33a51ae start=1500197786550 end=1500197786550 msg=Activity policy ''test-activity-policy'' was triggered by ''user@contoso.com'' suser=user@contoso.com destinationServiceName=Salesforce cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b339b0c204203a33a51ae cs2Label=uniqueServiceAppIds cs2=APPID_SALESFORCE cs3Label=relatedAudits cs3=1500197720691_b7f6317c-b8de-476a-bc8f-dfa570e00349 cs4Label=policyIDs cs4=

2017-07-16T09:17:03.361Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy3|3|externalId=596b2fd70c204203a33a3eeb start=1500196623361 end=1500196623361 msg=Activity policy ''test-activity-policy3'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Office 365 cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eeb cs2Label=uniqueServiceAppIds cs2=APPID_O365 cs3Label=relatedAudits cs3=1500196549157_a0e01f8a-e29a-43ae-8599-783c1c11597d cs4Label=policyIDs cs4=

2017-07-16T09:17:15.426Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy|3|externalId=596b2fd70c204203a33a3eec start=1500196635426 end=1500196635426 msg=Activity policy ''test-activity-policy'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Office 365 admin center cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b2fd70c204203a33a3eec cs2Label=uniqueServiceAppIds cs2=APPID_O365_PORTAL cs3Label=relatedAudits cs3=1500196557398_3e102b20-d9fa-4f66-b550-8c7a403bb4d8 cs4Label=policyIDs cs4=59f0ab35f797fa9811e9b1c7

2017-07-16T09:17:46.290Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy4|3|externalId=596b30200c204203a33a4765 start=1500196666290 end=1500196666290 msg=Activity policy ''test-activity-policy4'' was triggered by ''admin@contoso.com'' suser=admin@contoso.com destinationServiceName=Microsoft Exchange Online cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b30200c204203a33a4765 cs2Label=uniqueServiceAppIds cs2=APPID_OUTLOOK cs3Label=relatedAudits cs3=1500196587034_a8673602-7e95-46d6-a1fe-c156c4709c5d cs4Label=policyIDs cs4=

2017-07-16T09:41:04.369Z CEF:0|MCAS|SIEM_Agent|0.102.17|ALERT_CABINET_EVENT_MATCH_AUDIT|test-activity-policy2|3|externalId=596b34b10c204203a33a5240 start=1500198064369 end=1500198064369 msg=Activity policy ''test-activity-policy2'' was triggered by ''user2@test15-adallom.com'' suser=user2@test15-adallom.com destinationServiceName=Google cn1Label=riskScore cn1= cs1Label=portalURL cs1=https://cloud-app-security.com/#/alerts/596b34b10c204203a33a5240 cs2Label=uniqueServiceAppIds cs2=APPID_33626 cs3Label=relatedAudits cs3=1500197996117_fd71f265-1e46-4f04-b372-2e32ec874cd3 cs4Label=policyIDs cs4=

```
#### <a name="sample-cloud-app-security-alerts-in-cef-format"></a>Voorbeeld Cloud App Security waarschuwingen in CEF-indeling


|Van toepassing op|De naam van de CEF-veld|Description|
|----|-----|----|
|Activiteiten /-waarschuwingen|Start| Activiteit of waarschuwing tijdstempel|
|Activiteiten /-waarschuwingen|Einde|Activiteit of waarschuwing tijdstempel|
|Activiteiten /-waarschuwingen|RT|Activiteit of waarschuwing tijdstempel|
|Activiteiten /-waarschuwingen|bericht |Activiteit of waarschuwing beschrijving zoals weergegeven in de portal|
|Activiteiten /-waarschuwingen|suser| Activiteit of waarschuwing onderwerp gebruiker|
|Activiteiten /-waarschuwingen|destinationServiceName| Activiteit of waarschuwing app, bijvoorbeeld Office 365, Sharepoint, vak die afkomstig zijn.|
|Activiteiten /-waarschuwingen|CS<X>Label|Elk label moet een andere betekenis, maar deze bijvoorbeeld targetObjects in het label zelf wordt uitgelegd.|
|Activiteiten /-waarschuwingen|CS<X>|De informatie die overeenkomt met het label (de doelgebruiker van de activiteit of een waarschuwing aan de hand van het label voorbeeld).|
|Activiteiten|EVENT_CATEGORY_ * |Categorie op hoog niveau van de activiteit|
|Activiteiten|<ACTION> |Het activiteitstype, zoals weergegeven in de portal|
|Activiteiten|externalId| Gebeurtenis-id|
|Activiteiten|DVC| IP-adres van het clientapparaat.|
|Activiteiten|requestClientApplication|Gebruikersagent van het clientapparaat.|
|Waarschuwingen|<alert type>|Bijvoorbeeld 'ALERT_CABINET_EVENT_MATCH_AUDIT'|
|Waarschuwingen|<name>|De naam van de overeenkomende beleid|
|Waarschuwingen|externalId|Waarschuwing-ID|



### <a name="step-3-validate-that-the-siem-agent-is-working"></a>Stap 3: Valideren dat de SIEM-agent werkt

1. Controleer of de SIEM-agent in de Cloud App Security-portal niet de status **Verbindingsfout** of **Verbroken** heeft en of er geen agentmeldingen zijn. Deze wordt weergegeven als **Verbindingsfout** als de verbinding meer dan twee uur niet beschikbaar is en als **Verbroken** als de verbinding gedurende meer dan 12 uur niet beschikbaar is.
 ![SIEM verbroken](./media/siem-not-connected.png)
 
   In plaats daarvan de status moet worden verbonden, zoals hier: ![SIEM verbonden](./media/siem-connected.png)

2. Zorg ervoor dat u in uw Syslog/SIEM-server activiteiten en waarschuwingen ziet die afkomstig zijn van Cloud App Security.


## <a name="regenerating-your-token"></a>Uw token opnieuw genereren
Als u het token verliest, kunt u het altijd opnieuw genereren door in de tabel op de drie punten aan het einde van de rij voor de SIEM-agent te klikken en **Token opnieuw genereren** te selecteren.

 ![SIEM - token opnieuw genereren](./media/siem-regenerate-token.png)

## <a name="editing-your-siem-agent"></a>Uw SIEM-agent bewerken 
Als u de SIEM-agent op een later tijdstip moet bewerken, kunt u in de tabel op de drie punten aan het einde van de rij voor de SIEM-agent klikken en **Bewerken** selecteren. Als u de SIEM-agent bewerkt, hoeft u het JAR-bestand niet opnieuw uit te voeren, omdat het automatisch wordt bijgewerkt.

![SIEM - bewerken](./media/siem-edit.png)

## <a name="deleting-your-siem-agent"></a>Uw SIEM-agent verwijderen
Als u de SIEM-agent op een later tijdstip wilt verwijderen, kunt u in de tabel op de drie punten aan het einde van de rij voor de SIEM-agent klikken en **Verwijderen** selecteren.

![SIEM - verwijderen](./media/siem-delete.png)

> [!NOTE]
> Deze functie is beschikbaar voor openbare preview.

## <a name="high-availability-options"></a>Opties voor hoge beschikbaarheid

De SIEM-agent is één eindpunt die ondersteuning biedt voor herstel van maximaal twee dagen uitvaltijd. Extra beveiligingsmaatregel van maximale beschikbaarheid kan worden bereikt door een load balancer als het eindpunt van de klant.

## <a name="see-also"></a>Zie ook  
[Problemen met SIEM-integratie oplossen](troubleshooting-siem.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  