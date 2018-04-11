---
title: Cloud Discovery implementeren met Microsoft Cloud App Security | Microsoft Docs
description: Dit onderwerp wordt de instellingsprocedure voor Cloud Discovery beschreven.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/5/2017
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: a9b5bd8d-305b-4e93-9a4c-a4683ea09080
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 28cfc00573fa90c7e95ed00622cc67295e5de85b
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
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


|                 Gegevensbron                  |    URL van de doel-app    |    IP-adres van de doel-app     |       Gebruikersnaam       |      IP-adres van bron       |    Totaal verkeer     |    Geüploade bytes    |
|----------------------------------------------|----------------------|----------------------|----------------------|----------------------|----------------------|----------------------|
|                  Barracuda                   | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |          Nee          |          Nee          |
|                  Blue Coat                   | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|                  Controlepunt                  |          Nee          | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> |          Nee          |          Nee          |
|              Cisco ASA (Syslog)              |          Nee          | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> | <strong>Ja</strong> |          Nee          |
|           Cisco ASA van de vuurkracht           | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|                  Cisco FWSM                  |          Nee          | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> | <strong>Ja</strong> |          Nee          |
|              Cisco Ironport WSA              | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|                 Cisco Meraki                 | <strong>Ja</strong> | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> |          Nee          |          Nee          |
|           Clavister NGFW (Syslog)            | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|                Dell Sonicwall                | <strong>Ja</strong> | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|            Digitale Arts i-FILTER             | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|                  FortiGate                   |          Nee          | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|                 Juniper SRX                  |          Nee          | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|                 Juniper SSG                  |          Nee          | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|                  McAfee SWG                  | <strong>Ja</strong> |          Nee          |          Nee          | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|                    MS TMG                    | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|              Palo Alto Networks              |          Nee          | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|                    Sophos                    | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |          Nee          |
|                Squid (algemeen)                | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> |
|                Squid (systeemeigen)                | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> | <strong>Ja</strong> |          Nee          | <strong>Ja</strong> |
| Websense - gedetailleerd onderzoeksrapport (CSV) | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|    Websense - internetactiviteitenlogboek (CEF)    | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |
|                   Zscaler                    | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> | <strong>Ja</strong> |

## <a name="see-also"></a>Zie ook

[Momentopnamerapporten maken van Cloud Discovery](create-snapshot-cloud-discovery-reports.md)

[Automatisch uploaden van logboeken configureren voor doorlopende rapporten](configure-automatic-log-upload-for-continuous-reports.md)

[Werken met Cloud Discovery-gegevens](working-with-cloud-discovery-data.md)