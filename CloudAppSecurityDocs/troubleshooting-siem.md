---
title: Problemen met integratie van SIEM met Cloud App Security oplossen | Microsoft Docs
description: In dit onderwerp vindt u een lijst van mogelijke problemen bij het verbinden van de SIEM met Cloud App Security en bijbehorende oplossingen daarvoor.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: de64d9ca-eaed-4243-bcf7-adca5aff18c8
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 5b801b889abdac386cba5cb850dc5d38bbba205c
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2018
---
# <a name="troubleshooting-the-siem-agent"></a>Problemen met de SIEM-agent oplossen

Controleer of de SIEM-agent in de Cloud App Security-portal niet de status **Verbindingsfout** of **Verbroken** heeft en of er geen agentmeldingen zijn. Deze wordt weergegeven als **Verbindingsfout** als de verbinding meer dan twee uur niet beschikbaar is en als **Verbroken** als de verbinding gedurende meer dan 12 uur niet beschikbaar is.

Als u tijdens het uitvoeren van de agent een van de volgende fouten in de opdrachtprompt ziet, gebruikt u de volgende stappen om het probleem te verhelpen:

|Fout|Description|Oplossing|
|----|----|----|
|Algemene fout tijdens bootstrap|Onverwachte fout tijdens agent-bootstrap.|Neem contact op met ondersteuning.|
|Te veel kritieke fouten|Er zijn te veel kritieke fouten opgetreden bij het verbinden van de console. Wordt afgesloten.|Neem contact op met ondersteuning.|
|Ongeldig token|Het opgegeven token is ongeldig.|Controleer of u het juiste token hebt gekopieerd. U kunt de bovenstaande procedure gebruiken om het token opnieuw te genereren.|
|Ongeldig proxyadres|Het opgegeven proxyadres is ongeldig.|Zorg ervoor dat u de juiste proxy en poort opgeeft.|


Als u na het maken van de agent een van de volgende **agent-meldingen** in de Cloud App Security-portal op de pagina SIEM-agent ziet, gebruikt u de volgende stappen om het probleem te verhelpen:

|Fout|Description|Oplossing|
|----|----|----|
|**Interne fout**|Er is een onbekende fout opgetreden bij uw SIEM-agent.|Neem contact op met ondersteuning.|
|**Verzendfout bij gegevensserver**|U kunt deze foutmelding krijgen als u met een Syslog-server via TCP werkt. De SIEM-agent kan geen verbinding maken met de Syslog-server.  Als deze foutmelding wordt weergegeven, haalt de agent pas weer nieuwe activiteiten op als het probleem is opgelost. Voer daarom de herstelstappen uit tot er geen fouten meer worden weergegeven.|1. Controleer of u uw Syslog-server correct hebt gedefinieerd: bewerk in de Cloud App Security-gebruikersinterface uw SIEM-agent zoals hierboven wordt beschreven, zorg ervoor dat de naam van de server goed is geschreven en stel de juiste poort in. </br>2. Controleer de verbinding met de Syslog-server: zorg ervoor dat de communicatie niet wordt geblokkeerd door uw firewall.| 
|**Fout bij gegevensserververbinding**| U kunt deze foutmelding krijgen als u met een Syslog-server via TCP werkt. De SIEM-agent kan geen verbinding maken met de Syslog-server.  Als deze foutmelding wordt weergegeven, haalt de agent pas weer nieuwe activiteiten op als het probleem is opgelost. Voer daarom de herstelstappen uit tot er geen fouten meer worden weergegeven.|1. Controleer of u uw Syslog-server correct hebt gedefinieerd: bewerk in de Cloud App Security-gebruikersinterface uw SIEM-agent zoals hierboven wordt beschreven, zorg ervoor dat de naam van de server goed is geschreven en stel de juiste poort in. </br>2. Controleer de verbinding met de Syslog-server: zorg ervoor dat de communicatie niet wordt geblokkeerd door uw firewall.|
|**SIEM-agentfout**|De SIEM-agent is meer dan X uur verbroken|Controleer of u de SIEM-configuratie in de Cloud App Security-portal niet hebt gewijzigd. Dit kan anders duiden op problemen met de verbinding tussen Cloud App Security en de computer waarop u de SIEM-agent uitvoert.|
|**Meldingsfout SIEM-agent**|Er werden van een SIEM-agent doorstuurfouten ontvangen van meldingen van een SIEM-agent.|Dit geeft aan dat u fouten hebt ontvangen met betrekking tot de verbinding tussen de SIEM-agent en uw SIEM-server. Zorg ervoor dat er geen firewall is die uw SIEM-server blokkeert of de computer waarop de SIEM-agent wordt uitgevoerd. Controleer ook of het IP-adres van de SIEM-server niet is gewijzigd.|



## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  