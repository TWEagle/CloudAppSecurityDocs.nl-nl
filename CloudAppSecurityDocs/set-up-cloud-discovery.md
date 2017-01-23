---
title: Cloud Discovery implementeren | Microsoft Docs
description: Dit onderwerp wordt de instellingsprocedure voor Cloud Discovery beschreven.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/26/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a9b5bd8d-305b-4e93-9a4c-a4683ea09080
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 98b16c96c31039248bdfbe57f980b3ae6a26a7de
ms.openlocfilehash: 3c722ac79fa124193655ca053c713f3d6edc7017


---

# <a name="set-up-cloud-discovery"></a>Cloud Discovery instellen
In Cloud Discovery worden uw verkeerslogboeken geanalyseerd op basis van de catalogus met cloud-apps van Cloud App Security. Deze catalogus bevat meer dan 13.000 cloud-apps die op basis van meer dan 50 kenmerken worden geclassificeerd en beoordeeld, zodat u altijd inzicht hebt in het cloudgebruik, de Shadow IT en het risico dat Shadow IT vormt in uw organisatie.
Met de **catalogus met cloud-apps** wordt het risico voor uw cloud-apps beoordeeld op basis van regelgevingscertificeringen, industrienormen en best practices. In de catalogus met cloud-apps worden vier aanvullende processen uitgevoerd om de catalogus up-to-date te houden:
1.  Geautomatiseerde gegevensextractie rechtstreeks vanuit de cloud-app (voor kenmerken zoals SOC 2-naleving).
2.  Geautomatiseerde geavanceerde gegevensextractie voor gegevens met Cloud App Security-algoritmen (voor kenmerken zoals HTTP-beveiligingsheaders).
3.  Continue analyses door het analistenteam van Cloud App Security (voor kenmerken zoals versleuteling van inactieve gegevens).
4.  Klantgebaseerde revisieaanvragen, gebaseerd op klantaanvragen voor wijzigingen in de catalogus met cloud-apps. Alle aanvragen worden bekeken door ons cloudanalistenteam en bijgewerkt op basis van hun bevindingen.
  
## <a name="cloud-discovery-data-anonymization"></a>Cloud Discovery-gegevens anoniem maken

U kunt door Cloud Discovery-gegevens anoniem te maken de privacy van gebruikers beveiligen. Nadat het gegevenslogboek naar de Cloud App Security-portal is geüpload, wordt het logboek opgeschoond en wordt alle informatie over gebruikersnamen vervangen door versleutelde gebruikersnamen. Op deze manier blijven alle cloudactiviteiten anoniem. Zie [Cloud Discovery anoniem maken](cloud-discovery-anonymizer.md) voor meer informatie.

## <a name="snapshot-and-continuous-risk-assessment-reports"></a>Momentopname- en doorlopende risicoanalyserapporten 

Er zijn twee typen rapporten die u kunt genereren: 
- **Momentopnamerapporten** bieden ad-hocinzicht in een set verkeerslogboeken die u handmatig hebt geüpload vanuit uw firewalls en proxy's.
 
- Met **doorlopende rapporten** worden alle logboeken geanalyseerd die vanuit uw netwerk worden doorgestuurd met Cloud App Security. Deze rapporten bieden betere zichtbaarheid over alle gegevens en met de rapporten wordt afwijkend gebruik automatisch geïdentificeerd met de Machine Learning-anomaliedetectie of via aangepaste beleidsregels die u definieert.
 
## <a name="log-process-flow-from-raw-data-to-risk-assessment"></a>Logboekprocesstroom: van ruwe gegevens naar risicoanalyse  
Het proces voor het genereren van een risicoanalyse bestaat uit de volgende stappen en duurt enkele minuten tot enkele uren, afhankelijk van de hoeveelheid gegevens die moet worden verwerkt.  
  
-   **Uploaden** – De logboeken over webverkeer van het netwerk worden naar de portal geüpload.  
  
-   **Parseren** – Cloud App Security parseert en extraheert met een specifieke parser voor elke gegevensbron verkeersgegevens uit de verkeerslogboeken.  
  
-   **Analyseren** – De verkeersgegevens worden vergeleken met de catalogus met cloud-apps om meer dan 13.000 cloud-apps te identificeren en hun risicoscore vast te stellen. Tijdens de analyse worden actieve gebruikers en IP-adressen ook geïdentificeerd.  
  
-   **Rapport genereren** - Hiermee wordt een risicoanalyserapport gegenereerd met gegevens die worden geëxtraheerd uit logboekbestanden.   
 
 
>[!NOTE]
>De gegevens voor het doorlopende rapport worden twee keer per dag geanalyseerd.
 
## <a name="using-traffic-logs-for--cloud-discovery"></a>Verkeerslogboeken gebruiken voor Cloud Discovery
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
Daarom worden deze kenmerken in Cloud Discovery-gegevens voor deze logboeken weergegeven en hebt u slechts beperkt inzicht in de cloud-apps. Voor Cisco ASA-firewalls moet u het gegevensniveau instellen op 6. 
 

Als u zonder problemen een Cloud Discovery-rapport wilt genereren, moeten uw verkeerslogboeken aan de volgende voorwaarden voldoen:
1.  De gegevensbron wordt ondersteund (zie de onderstaande lijst).
2.  De logboekindeling komt overeen met de verwachte standaardindeling (deze wordt tijdens het uploaden gecontroleerd met het hulpprogramma Logboek).
3.  Gebeurtenissen zijn niet ouder dan 90 dagen.
4.  Het logboekbestand is geldig en bevat gegevens over uitgaand verkeer.
 
## <a name="supported-firewalls-and-proxies"></a>Ondersteunde firewalls en proxy's
- Blue Coat Proxy SG - toegangslogboek (W3C)
- Controlepunt
- Cisco ASA-firewalls (voor deze firewalls moet u het gegevensniveau instellen op 6)
- Cisco IronPort WSA
- Cisco ScanSafe
- Merkai - URL-logboek
- Dell Sonicwall
- Fortiner Fortigate
- Juniper SRX
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


Als uw logboek niet wordt ondersteund, selecteert u **Overige** in het veld **Gegevensbron**, geeft u het apparaat op en voert u het logboek in dat u wilt uploaden. Uw logboek wordt bekeken door het cloudanalistenteam van Cloud App Security en u ontvangt een melding als ondersteuning voor het logboektype is toegevoegd. 


De gegevenskenmerken (volgens de documentatie van de leverancier):

|Gegevensbron|URL van de doel-app|IP-adres van de doel-app|Gebruikersnaam|IP-adres van bron|Totaal verkeer|Geüploade bytes|
|----|----|----|-----|----|----|----|
|Blue Coat|**Ja**|Nee|**Ja**|**Ja**|**Ja**|**Ja**|
|Controlepunt|Nee|**Ja**|Nee|**Ja**|Nee|Nee|
|Cisco ASA|Nee|**Ja**|Nee|**Ja**|**Ja**|Nee|
|Cisco FWSM|Nee|**Ja**|Nee|**Ja**|**Ja**|Nee|
|Cisco Ironport WSA|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|
|Cisco ScanSafe|**Ja**|Nee|**Ja**|**Ja**|**Ja**|**Ja**|
|Dell Sonicwall|**Ja**|**Ja**|Nee|**Ja**|**Ja**|**Ja**|
|FortiGate|Nee|**Ja**|Nee|**Ja**|**Ja**|**Ja**|
|Juniper SRX|Nee|**Ja**|Nee|**Ja**\*|**Ja**|**Ja**|
|McAfee SWG|**Ja**|Nee|Nee|**Ja**|**Ja**|**Ja**|
|Meraki|**Ja**|**Ja**|Nee|**Ja**|Nee|Nee|
|MS TMG|**Ja**|Nee|**Ja**|**Ja**|**Ja**|**Ja**|
|Palo Alto Networks|**Ja**|**Ja**|**Ja**|**Ja**\*|**Ja**|**Ja**|
|Sophos|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|Nee|
|Websense - gedetailleerd onderzoeksrapport (CSV)|**Ja**|Nee|Nee|**Ja**|Nee|Nee|
|Websense - internetactiviteitenlogboek (CEF)|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|**Ja**|
|Zscaler|**Ja**|Nee|**Ja**|Nee|**Ja**|Nee|

\*Cloud Discovery biedt ondersteuning voor IPv6.

## <a name="see-also"></a>Zie ook
 
[Momentopnamerapporten maken van Cloud Discovery](create-snapshot-cloud-discovery-reports.md)

[Automatisch uploaden van logboeken configureren voor doorlopende rapporten](configure-automatic-log-upload-for-continuous-reports.md)

[Werken met Cloud Discovery-gegevens](working-with-cloud-discovery-data.md)
  
  


<!--HONumber=Jan17_HO2-->


