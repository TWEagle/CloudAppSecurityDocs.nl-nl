---
title: Problemen met Cloud Discovery oplossen in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u een lijst met veelvoorkomende fouten in Cloud Discovery en de aanbevolen oplossingen voor deze fouten.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 76dfaebb-d477-4bdb-b3d7-04cc3fe6431d
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: ae08c4e39fa01b1007dc0e14d8235558d2180372
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2018
---
# <a name="troubleshooting-cloud-discovery"></a>Problemen met Cloud Discovery oplossen
## <a name="log-parsing-errors"></a>Fouten bij het parseren van logboeken

U kunt de verwerking van Cloud Discovery-logboeken bijhouden met behulp van het beheerlogboek. In dit artikel vindt u oplossingsacties die u moet uitvoeren voor elke fout die hier kan worden weergegeven.

### <a name="governance-log-errors"></a>Fouten in het beheerlogboek
|FOUT|BESCHRIJVING|OPLOSSING|
|----|----|----|
|Niet-ondersteund bestandstype|Het geüploade bestand is geen geldig logboekbestand (bijvoorbeeld een afbeeldingsbestand).|Upload een **tekst**-, **zip**- of **gzip**-bestand dat rechtstreeks vanuit uw firewall of proxyserver is geëxporteerd.|
|Interne fout|Er is een interne bronfout gedetecteerd|Klik op **Opnieuw** om de taak opnieuw uit te voeren.|
|De logboekindeling komt niet overeen|De logboekindeling die u hebt geüpload, komt niet overeen met de verwachte indeling voor deze gegevensbron.|1. Controleer of het logboek niet is beschadigd. <br /> 2. U moet het logboek vergelijken en afstemmen met de voorbeeldindeling die op de uploadpagina wordt weergegeven.|
|Transacties zijn meer dan negentig dagen oud|Alle transacties zijn meer dan negentig dagen oud en worden daarom genegeerd.|Exporteer een nieuw logboek met recente gebeurtenissen en upload het logboek opnieuw.|
|Er zijn geen transacties voor gecatalogiseerde cloud-apps|Er zijn geen transacties voor herkende cloud-apps in het logboek gevonden.|Controleer of het logboek gegevens over uitgaand verkeer bevat.|
|Niet-ondersteunde logboektype|Wanneer u **Gegevensbron = Overige (niet ondersteund)** selecteert, wordt het logboek niet geparseerd. In plaats daarvan wordt het logboek verzonden naar het technische team van Cloud App Security.|Het technische team van Cloud App Security bouwt voor elke gegevensbron een specifieke parser. De meeste populaire gegevensbronnen worden [al ondersteund](set-up-cloud-discovery.md). Elke niet-ondersteunde gegevensbron die wordt geüpload, wordt beoordeeld en toegevoegd aan de pijplijn voor nieuwe gegevensbronparsers. Nieuwe parsermeldingen worden gepubliceerd als onderdeel van de [opmerkingen bij de release](release-notes.md) voor Cloud App Security.|

## <a name="log-collector-errors"></a>Fouten in de logboekverzamelaar

|PROBLEEM|OPLOSSING|
|----|----|
|Kan geen verbinding maken met de logboekverzamelaar via FTP|1. Controleer of u FTP-referenties en geen SSH-referenties gebruikt. <br />2. Controleer of de FTP-client niet is ingesteld op SFTP.|
|Het bijwerken van de configuratie van de verzamelaar is mislukt|1. Controleer of u het meest recente toegangstoken hebt ingevoerd. <br />2. Controleer in de firewall of de logboekverzamelaar uitgaand verkeer mag starten op poort 443.|
|De logboeken die naar de verzamelaar worden verzonden, worden niet in de portal weergegeven|1.  Controleer of er mislukte parseertaken in het beheerlogboek worden weergegeven.  <br />  &nbsp;&nbsp;&nbsp;&nbsp;Als dit het geval is, lost u de fout op met behulp van de bovenstaande tabel Fouten bij het parseren van logboeken.<br /> 2. Als dit niet het geval is, controleert u de configuratie van de gegevensbronnen en de logboekverzamelaar in de portal. <br /> &nbsp;&nbsp;&nbsp;&nbsp;a. Controleer op de pagina Gegevensbron of de gegevensbron die u gebruikt, op de juiste manier is geconfigureerd. <br />&nbsp;&nbsp;&nbsp;&nbsp;b. Controleer op de pagina Logboekverzamelaars of de gegevensbron aan de juiste logboekverzamelaar is gekoppeld. <br /> 3. Controleer de lokale configuratie van de on-premises computer van de logboekverzamelaar.  <br />&nbsp;&nbsp;&nbsp;&nbsp;a. Meld u via SSH aan bij de logboekverzamelaar en voer het hulpprogramma collector_config uit.<br/>&nbsp;&nbsp;&nbsp;&nbsp;b. Bevestig dat uw firewall of proxy logboeken naar de logboekverzamelaar verzendt met het protocol dat u hebt gedefinieerd (Syslog/TCP, Syslog/UDP of FTP) en dat deze naar de juiste poort en map worden verzonden.<br /> &nbsp;&nbsp;&nbsp;&nbsp;c. Voer netstat uit op de computer en controleer of de computer inkomende verbindingen van uw firewall of proxyserver ontvangt. <br /> 4.   Controleer of de logboekverzamelaar uitgaand verkeer mag starten op poort 443.|
|Status van de collector wordt vastgelegd: gemaakt|De collector-implementatie van het logboek is niet voltooid. Voltooi de implementatiestappen van de on-premises volgens de Implementatiehandleiding.|
|Status van de collector wordt vastgelegd: verbroken|Er zijn geen gegevens ontvangen in de afgelopen 24 uur uit een van de gekoppelde gegevensbronnen.|De geëxporteerde activiteitenlogboeken instellen op uw toestel en controleer of dat ze juist zijn ingesteld.|



## <a name="discovery-dashboard-errors"></a>Detectie dashboard fouten

|PROBLEEM|OPLOSSING|
|----|----|
|Gegevens van de detectie is geüpload en geparseerd, maar de Cloud Discovery-dashboard ziet er leeg|Het Dashboard kan worden gefilterd op uw logboeken beschikt niet over gegevens en er zijn daarom geen gegevens om weer te geven. Wijzig de filters in de Cloud Discovery-dashboard om verschillende soorten gegevens om de resultaten weer te geven.|

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  