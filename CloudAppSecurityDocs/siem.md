---
title: Integratie van SIEM met Cloud App Security | Microsoft Docs
description: Dit onderwerp bevat informatie over de integratie van uw SIEM met Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/14/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4649423b-9289-49b7-8b60-04b61eca1364
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 292b4c6408aa526184aefb57ee594b72b3262ce7
ms.sourcegitcommit: cb8238610222953751ff714b346a0b4cf73ac40c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/16/2017
---
# <a name="siem-integration"></a>Integratie van SIEM
    
U kunt Cloud App Security nu met uw SIEM-server integreren om gecentraliseerde bewaking van waarschuwingen en activiteiten in te schakelen. Door de integratie met een SIEM-service kunt u uw cloudtoepassingen beter beveiligen terwijl uw gebruikelijke beveiligingswerkstroom blijft behouden, beveiligingsprocedures worden geautomatiseerd en gebeurtenissen in de cloud en on-premises aan elkaar worden gekoppeld. De Cloud App Security SIEM-agent wordt uitgevoerd op uw server. De agent haalt waarschuwingen en activiteiten op uit Cloud App Security en verzendt deze naar de SIEM-server.

Wanneer u uw SIEM voor het eerst integreert met Cloud App Security, worden activiteiten en waarschuwingen van de laatste twee dagen doorgestuurd naar de SIEM, plus alle activiteiten en waarschuwingen (op basis van het filter dat u selecteert) die daarna volgen. Als u deze functie voor een langere periode uitschakelt en de functie vervolgens weer inschakelt, worden bovendien waarschuwingen en activiteiten van de laatste twee dagen doorgestuurd en vervolgens alle waarschuwingen en activiteiten die daarna volgen.

## <a name="siem-integration-architecture"></a>Architectuur van SIEM-integratie

De SIEM-agent wordt geïmplementeerd in het netwerk van uw organisatie. Wanneer de agent is geïmplementeerd en geconfigureerd, pollt deze de gegevenstypen die zijn geconfigureerd (waarschuwingen en activiteiten) met Cloud App Security RESTful-API's.
Het verkeer wordt verzonden via een gecodeerd HTTPS-kanaal op poort 443.

Wanneer de SIEM-agent de gegevens van Cloud App Security ophaalt, stuurt de Syslog berichten naar uw lokale SIEM met behulp van de netwerkconfiguraties die u hebt opgegeven tijdens de installatie (TCP of UDP met een aangepaste poort). 

![Architectuur van SIEM-integratie](./media/siem-architecture.png)

## <a name="sample-siem-logs"></a>Voorbeelden van SIEM-logboeken

De logboeken die zijn opgegeven voor uw SIEM van Cloud App Security zijn CEF over Syslog. In de volgende voorbeeldlogboeken kunt u het type gebeurtenis zien dat meestal wordt verzonden door Cloud App Security naar uw SIEM-server. Hierin kunt u zien wanneer de waarschuwing is geactiveerd, het **type gebeurtenis**het **beleid** dat is geschonden, de **gebruiker** die de gebeurtenis heeft geactiveerd, de **app** de gebruiker heeft gebruikt voor het maken van de schending en de **URL** waarvan de waarschuwing afkomstig is:

Voorbeeld van activiteitenlogboek: 
  
2017-05-12T13:15:32.131Z CEF:0|MCAS|SIEM_Agent|0.97.33|EVENT_CATEGORY_UPLOAD_FILE|**Bestand uploaden**|0|externalId=AVv8zNojeXPEqTlM-j6M start=1494594932131 end=1494594932131 msg=**Bestand uploaden: passwords.txt** **suser=admin@contoso.com** doel**ServiceName=Jive Software** dvc= requestClientApplication= cs1Label=**portalURL cs1=https://contoso.cloudappsecurity.com**/#/audits?activity.id\=eq(AVv8zNojeXPEqTlM-j6M,) cs2Label=uniqueServiceAppIds cs2=APPID_JIVE cs3Label=targetObjects cs3=test.txt c6a1Label="Device IPv6 Address" c6a1=



Voorbeeld van waarschuwingenlogboek: 

2017-05-12T13:25:57.640Z CEF:0|MCAS|SIEM_Agent|0.97.33|ALERT_CABINET_EVENT_MATCH_AUDIT|asddsddas|3|externalId=5915b7e50d5d72daaf394da9 start=1494595557640 end=1494595557640 msg=**Activiteitsbeleid aanmeldingen bij Jive** is geactiveerd door admin@contoso.com **suser=admin@contoso.com** doel**ServiceName=Jive Software** cn1Label=riskScore cn1= cs1Label=portal**URL cs1=https://contoso.cloudappsecurity.com**/#/alerts/5915b7e50d5d72daaf394da9 cs2Label=uniqueServiceAppIds cs2=APPID_JIVE cs3Label=relatedAudits cs3=AVv81ljWeXPEqTlM-j-j


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

1. Klik in de Cloud App Security-portal onder het tandwiel Instellingen op **SIEM-agents**.

2. Klik op SIEM-agent toevoegen om de wizard te starten.
3. Klik in de wizard op **SIEM-agent toevoegen**.    
4. Vul in de wizard een naam in, **selecteer uw SIEM-indeling** en stel **geavanceerde instellingen** in die relevant zijn voor deze indeling. Klik op **Volgende**.

   ![Algemene SIEM-instellingen](./media/siem1.png)

5. Typ het IP-adres of de hostnaam van de **externe Syslog-host** en het **Syslog-poortnummer**. Selecteer TCP of UDP als het externe Syslog-protocol.
Vraag indien nodig uw beveiligingsbeheerder om deze informatie.
Klik op **Volgende**.
  ![Externe Syslog-instellingen](./media/siem2.png)

6. Selecteer welke gegevenstypen, **waarschuwingen** en **activiteiten** u wilt exporteren naar uw SIEM-server. Gebruik de schuifregelaar om deze in en uit te schakelen. Standaard is alles geselecteerd. U kunt de vervolgkeuzelijst **Toepassen op** gebruiken om filters zo in te stellen dat alleen bepaalde waarschuwingen en activiteiten naar uw SIEM-server worden verzonden.
U kunt op **Resultaten bewerken en bekijken** klikken om te controleren of het filter goed werkt. Klik op **Volgende**. 

  ![Instellingen voor gegevenstypen](./media/siem3.png)

7. Kopieer het token en bewaar het voor later. Nadat u op Voltooien hebt geklikt en de wizard hebt afgesloten, wordt de SIEM-pagina opnieuw weergegeven en ziet u in de tabel de SIEM-agent die u hebt toegevoegd. Er wordt nu weergegeven dat deze is **gemaakt** totdat deze later wordt verbonden.

### <a name="step-2-download-the-jar-file-and-run-it-on-your-server"></a>Stap 2: Het JAR-bestand downloaden en uitvoeren op uw server

1. [Download het ZIP-bestand vanuit het Microsoft Downloadcentrum](https://go.microsoft.com/fwlink/?linkid=838596) en pak het uit.

2. Pak het JAR-bestand van het ZIP-bestand uit en voer het uit op uw server.
 Nadat u het bestand hebt uitgevoerd, voert u het volgende uit:
    
      java -jar mcas-siemagent-0.87.20-signed.jar [--logsDirectory MAPNAAM] [--proxy ADRES[:POORT]] --token TOKEN
> [!NOTE]
> - De bestandsnaam kan verschillen afhankelijk van de versie van de SIEM-agent.
> - Parameters tussen vierkante haken [] zijn optioneel en moeten alleen worden gebruikt als dat relevant is.

Hierbij worden de volgende variabelen gebruikt:
- MAPNAAM is het pad naar de map die u wilt gebruiken voor lokale agent-logboeken voor foutopsporing.
- ADRES[: POORT] is het proxyserveradres en de poort die door de server wordt gebruikt om verbinding met internet te maken.
- TOKEN is het SIEM-agenttoken dat u in de vorige stap hebt gekopieerd.

U kunt op elk gewenst moment -h typen om hulp te krijgen.



### <a name="step-3-validate-that-the-siem-agent-is-working"></a>Stap 3: Valideren dat de SIEM-agent werkt

1. Controleer of de SIEM-agent in de Cloud App Security-portal niet de status **Verbindingsfout** of **Verbroken** heeft en of er geen agentmeldingen zijn. Deze wordt weergegeven als **Verbindingsfout** als de verbinding meer dan twee uur niet beschikbaar is en als **Verbroken** als de verbinding gedurende meer dan 12 uur niet beschikbaar is.
 ![SIEM verbroken](./media/siem-not-connected.png)
 
   In plaats daarvan moet de status Verbonden zijn, zoals hier wordt weergegeven:  ![SIEM verbonden](./media/siem-connected.png)

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

## <a name="see-also"></a>Zie ook  
[Problemen met SIEM-integratie oplossen](troubleshooting-siem.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  