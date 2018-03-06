---
title: Cloud Discovery implementeren met Microsoft Cloud App Security | Microsoft Docs
description: Dit onderwerp wordt de instellingsprocedure voor Cloud Discovery beschreven.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/5/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a9b5bd8d-305b-4e93-9a4c-a4683ea09080
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f8dabfd6a7e5d246c1c36dd29e023e294a266f5d
ms.sourcegitcommit: c47fd92c71028ede8840e0766f20eb0ad2898e70
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="set-up-cloud-discovery"></a>Cloud Discovery instellen
Cloud Discovery analyseert uw verkeerslogboeken op basis van de catalogus met Cloud App Security cloud-app van meer dan 15.000 cloud-apps die worden beoordeeld en gewaardeerd op basis van meer dan 60 risicofactoren u doorlopende inzicht in de cloud gebruikt, schaduw-IT, en het risico Shadow IT oplevert voor uw organisatie opgeven.
 
## <a name="snapshot-and-continuous-risk-assessment-reports"></a>Momentopname- en doorlopende risicoanalyserapporten 

Er zijn twee typen rapporten die u kunt genereren: 
- **Momentopnamerapporten** bieden ad-hocinzicht in een set verkeerslogboeken die u handmatig hebt geüpload vanuit uw firewalls en proxy's.
 
- Met **doorlopende rapporten** worden alle logboeken geanalyseerd die vanuit uw netwerk worden doorgestuurd met Cloud App Security. Deze rapporten bieden betere zichtbaarheid over alle gegevens en met de rapporten wordt afwijkend gebruik automatisch geïdentificeerd met de Machine Learning-anomaliedetectie of via aangepaste beleidsregels die u definieert.
 
## <a name="log-process-flow-from-raw-data-to-risk-assessment"></a>Logboekprocesstroom: van ruwe gegevens naar risicoanalyse  
Het proces voor het genereren van een risicoanalyse bestaat uit de volgende stappen en duurt enkele minuten tot enkele uren, afhankelijk van de hoeveelheid gegevens die moet worden verwerkt.  
  
-   **Uploaden** – De logboeken over webverkeer van het netwerk worden naar de portal geüpload.  
  
-   **Parseren** – Cloud App Security parseert en extraheert met een specifieke parser voor elke gegevensbron verkeersgegevens uit de verkeerslogboeken.  
  
-   **Analyseren** – verkeersgegevens worden vergeleken met de catalogus met Cloud-App op meer dan 15.000 cloud-apps identificeren en om hun risicoscore vast te stellen. Tijdens de analyse worden actieve gebruikers en IP-adressen ook geïdentificeerd.  
  
-   **Rapport genereren** - Hiermee wordt een risicoanalyserapport gegenereerd met gegevens die worden geëxtraheerd uit logboekbestanden.   
 
 
>[!NOTE]
>- De gegevens voor het doorlopende rapport worden twee keer per dag geanalyseerd.
>- De logboekverzamelaar comprimeren gegevens voordat deze wordt geüpload. Het uitgaande verkeer op de logboekverzamelaar is 10% van de grootte van de verkeerslogboeken die het ontvangt. 
 
## <a name="using-traffic-logs-for-cloud-discovery"></a>Met behulp van logboeken over webverkeer voor Cloud Discovery
In Cloud Discovery wordt gebruikgemaakt van de gegevens in uw verkeerslogboeken. Hoe gedetailleerder uw logboeken, hoe meer inzicht u krijgt. Voor Cloud Discovery zijn webverkeersgegevens met de volgende kenmerken vereist:
- Datum van de transactie
- Bron-IP
- Brongebruiker - sterk aanbevolen
- Doel-IP-adres
- Doel-URL **aanbevolen** (URL's bieden meer nauwkeurigheid voor de detectie van cloud-apps dan IP-adressen)
- Totale hoeveelheid gegevens (informatie over gegevens is zeer waardevol)
- Hoeveelheid geüploade of gedownloade gegevens (biedt inzicht in de gebruikspatronen van de cloud-apps)
- Ondernomen actie (toegestaan/geblokkeerd)
 
In Cloud Discovery kunnen geen kenmerken worden weergegeven of geanalyseerd die niet in uw logboeken zijn opgenomen.
De standaardlogboekindeling **Cisco ASA-firewall** bevat niet de **hoeveelheid geüploade bytes per transactie** en de **gebruikersnaam**, en bevat geen **doel-URL** (maar alleen het doel-IP-adres).
Daarom worden deze kenmerken niet weergegeven in Cloud Discovery-gegevens voor deze logboeken en hebt u slechts beperkt inzicht in de cloud-apps. Voor Cisco ASA-firewalls moet u het gegevensniveau instellen op 6. 
 

Als u zonder problemen een Cloud Discovery-rapport wilt genereren, moeten uw verkeerslogboeken aan de volgende voorwaarden voldoen:
1.  De gegevensbron wordt ondersteund (zie de onderstaande lijst).
2.  De logboekindeling komt overeen met de verwachte standaardindeling (deze wordt tijdens het uploaden gecontroleerd met het hulpprogramma Logboek).
3.  Gebeurtenissen zijn niet ouder dan 90 dagen.
4.  Het logboekbestand is geldig en bevat gegevens over uitgaand verkeer.
 


## Ondersteunde firewalls en proxy 's <a name="supported-firewalls-and-proxies"></a>

- Barracuda - Web App Firewall (W3C)
- Blue Coat Proxy SG - toegangslogboek (W3C)
- Controlepunt
- Cisco ASA-firewalls (voor deze firewalls moet u het gegevensniveau instellen op 6)
- Cisco ASA van de vuurkracht
- Cisco IronPort WSA
- Cisco ScanSafe
- Cisco Meraki - URL-logboek
- Clavister NGFW (Syslog)
- Dell Sonicwall
- Digitale Arts i-FILTER
- Fortinet Fortigate
- Juniper SRX
- Juniper SSG
- McAfee beveiligde webgateway
- Microsoft Forefront Threat Management Gateway (W3C)
- Firewall Palo Alto-reeks
- Sophos SG
- Sophos Cyberoam
- Squid (algemeen)
- Squid (systeemeigen)
- Websense - oplossingen voor webbeveiliging - gedetailleerd onderzoeksrapport (CSV)
- Websense - oplossingen voor webbeveiliging - activiteitenlogboek internet (CEF)
- Zscaler

> [!NOTE]
> Cloud Discovery ondersteunt zowel IPv4 als IPv6-adressen.

Als uw logboek niet wordt ondersteund, selecteert u **Overige** in het veld **Gegevensbron**, geeft u het apparaat op en voert u het logboek in dat u wilt uploaden. Uw logboek wordt bekeken door het cloudanalistenteam van Cloud App Security en u ontvangt een melding als ondersteuning voor het logboektype is toegevoegd. U kunt ook een aangepaste parser definiëren die overeenkomt met de indeling. Zie [Een aangepaste logboekparser gebruiken](custom-log-parser.md) voor meer informatie.


De gegevenskenmerken (volgens de documentatie van de leverancier):

|Gegevensbron|URL van de doel-app|IP-adres van de doel-app|Gebruikersnaam|IP-adres van bron|Totaal verkeer|Geüploade bytes|
|----|----|----|-----|----|----|----|
|Barracuda|**Ja**|**Ja**|**Ja**|**Ja**|Nee|Nee|
|Blue Coat|**Ja**|Nee|**Ja**|**Ja**|**Ja**|**Ja**|
|Controlepunt|Nee|**Ja**|Nee|**Ja**|Nee|Nee|
|Cisco ASA (Syslog)|Nee|**Ja**|Nee|**Ja**|**Ja**|Nee|
|Cisco ASA van de vuurkracht|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|
|Cisco FWSM|Nee|**Ja**|Nee|**Ja**|**Ja**|Nee|
|Cisco Ironport WSA|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|
|Cisco Meraki|**Ja**|**Ja**|Nee|**Ja**|Nee|Nee||Cisco ScanSafe|**Ja**|Nee|**Ja**|**Ja**|**Ja**|**Ja**|
|Clavister NGFW (Syslog)|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|
|Dell Sonicwall|**Ja**|**Ja**|Nee|**Ja**|**Ja**|**Ja**|
|Digitale Arts i-FILTER|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|
|FortiGate|Nee|**Ja**|Nee|**Ja**|**Ja**|**Ja**|
|Juniper SRX|Nee|**Ja**|Nee|**Ja**|**Ja**|**Ja**|
|Juniper SSG|Nee|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|
|McAfee SWG|**Ja**|Nee|Nee|**Ja**|**Ja**|**Ja**|
|MS TMG|**Ja**|Nee|**Ja**|**Ja**|**Ja**|**Ja**|
|Palo Alto Networks|Nee|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|
|Sophos|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|Nee|
|Squid (algemeen)|**Ja**|Nee|**Ja**|**Ja**|Nee|**Ja**|
|Squid (systeemeigen)|**Ja**|Nee|**Ja**|**Ja**|Nee|**Ja**|
|Websense - gedetailleerd onderzoeksrapport (CSV)|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|
|Websense - internetactiviteitenlogboek (CEF)|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|
|Zscaler|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|



## <a name="see-also"></a>Zie ook
 
[Momentopnamerapporten maken van Cloud Discovery](create-snapshot-cloud-discovery-reports.md)

[Automatisch uploaden van logboeken configureren voor doorlopende rapporten](configure-automatic-log-upload-for-continuous-reports.md)

[Werken met Cloud Discovery-gegevens](working-with-cloud-discovery-data.md)