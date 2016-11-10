---
title: Problemen met Cloud Discovery oplossen | Microsoft Docs
description: In dit onderwerp vindt u een lijst met veelvoorkomende fouten in Cloud Discovery en de aanbevolen oplossingen voor deze fouten.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 76dfaebb-d477-4bdb-b3d7-04cc3fe6431d
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 2d0b2cebdfa15cccc5888660da498446d620b64f


---

# <a name="troubleshooting-cloud-discovery"></a>Problemen met Cloud Discovery oplossen
## <a name="log-parsing-errors"></a>Fouten bij het parseren van logboeken

U kunt de verwerking van Cloud Discovery-logboeken bijhouden met behulp van het beheerlogboek. In deze handleiding vindt u oplossingsacties die u moet uitvoeren voor elke fout die hier kan worden weergegeven.

### <a name="governance-log-errors"></a>Fouten in het beheerlogboek
|FOUT|BESCHRIJVING|OPLOSSING|
|----|----|----|
|Niet-ondersteund bestandstype|Het geüploade bestand is geen geldig logboekbestand (bijvoorbeeld een afbeeldingsbestand).|Upload een **tekst**-, **zip**- of **gzip**-bestand dat rechtstreeks vanuit uw firewall of proxyserver is geëxporteerd.|
|Interne fout|Er is een interne bronfout gedetecteerd|Klik op **Opnieuw** om de taak opnieuw uit te voeren.|
|De logboekindeling komt niet overeen|De logboekindeling die u hebt geüpload, komt niet overeen met de verwachte indeling voor deze gegevensbron.|1. Controleer of het logboek niet is beschadigd. <br /> 2. U moet het logboek vergelijken en afstemmen met de voorbeeldindeling die op de uploadpagina wordt weergegeven.|
|Transacties zijn meer dan negentig dagen oud|Alle transacties zijn meer dan negentig dagen oud en worden daarom genegeerd.|Exporteer een nieuw logboek met recente gebeurtenissen en upload het logboek opnieuw.|
|Er zijn geen transacties voor gecatalogiseerde cloud-apps|Er zijn geen transacties voor herkende cloud-apps in het logboek gevonden.|Controleer of het logboek gegevens over uitgaand verkeer bevat.|
|Niet-ondersteunde logboektype|Wanneer u **Gegevensbron = Overige (niet ondersteund)** selecteert, wordt het logboek niet geparseerd. In plaats daarvan wordt het logboek verzonden naar het technische team van Cloud App Security.|Het technische team van Cloud App Security bouwt voor elke gegevensbron een specifieke parser. De meeste populaire gegevensbronnen worden [al ondersteund](set-up-cloud-discovery.md). Elke niet-ondersteunde gegevensbron die wordt geüpload, wordt beoordeeld en toegevoegd aan de pijplijn voor nieuwe gegevensbronparsers. Nieuwe parsermeldingen worden gepubliceerd als onderdeel van de opmerkingen bij de release voor Cloud App Security.|
## <a name="log-collector-errors"></a>Fouten in de logboekverzamelaar

|PROBLEEM|OPLOSSING|
|----|----|
|Kan geen verbinding maken met de logboekverzamelaar via FTP|1. Controleer of u FTP-referenties en geen SSH-referenties gebruikt. <br />2. Controleer of de FTP-client niet is ingesteld op SFTP.|
|Het bijwerken van de configuratie van de verzamelaar is mislukt|1. Controleer of u het meest recente toegangstoken hebt ingevoerd. <br />2. Controleer in de firewall of de logboekverzamelaar uitgaand verkeer mag starten op poort 443.|
|De logboeken die naar de verzamelaar worden verzonden, worden niet in de portal weergegeven|1.  Controleer of er mislukte parseertaken in het beheerlogboek worden weergegeven.  <br />  &nbsp;&nbsp;&nbsp;&nbsp;Als dit het geval is, lost u de fout op met behulp van de bovenstaande tabel Fouten bij het parseren van logboeken.<br /> 2. Als dit niet het geval is, controleert u de configuratie van de gegevensbronnen en de logboekverzamelaar in de portal. <br /> &nbsp;&nbsp;&nbsp;&nbsp;a. Controleer op de pagina Gegevensbron of de gegevensbron die u gebruikt, op de juiste manier is geconfigureerd. <br />&nbsp;&nbsp;&nbsp;&nbsp;b. Controleer op de pagina Logboekverzamelaars of de gegevensbron aan de juiste logboekverzamelaar is gekoppeld. <br /> 3. Controleer de lokale configuratie van de on-premises computer van de logboekverzamelaar.  <br />&nbsp;&nbsp;&nbsp;&nbsp;a. Meld u via SSH aan bij de logboekverzamelaar en voer het hulpprogramma collector_config uit.<br/>&nbsp;&nbsp;&nbsp;&nbsp;b. Bevestig dat uw firewall of proxy logboeken naar de logboekverzamelaar verzendt met het protocol dat u hebt gedefinieerd (Syslog/TCP, Syslog/UDP of FTP) en dat deze naar de juiste poort en map worden verzonden.<br /> &nbsp;&nbsp;&nbsp;&nbsp;c. Voer netstat uit op de computer en controleer of de computer inkomende verbindingen van uw firewall of proxyserver ontvangt. <br /> 4.   Controleer of de logboekverzamelaar uitgaand verkeer mag starten op poort 443.|

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->

