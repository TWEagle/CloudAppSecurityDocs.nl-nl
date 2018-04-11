---
title: Wat is er nieuw met Cloud App Security | Microsoft Docs
description: Dit onderwerp wordt regelmatig bijgewerkt, zodat u weet wat er nieuw is in de meest recente versie van Cloud App Security.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/7/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: d418ef3d-76ee-45d5-b5ae-21346e5239a3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: a6db87ce60e719886fcdb4f10b1308cc3d8f0423
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="whats-new-with-microsoft-cloud-app-security"></a>Wat is er nieuw is bij de Microsoft Cloud App Security

## <a name="cloud-app-security-release-119"></a>Cloud App Security-release 119
18 maart 2018 uitgebracht

-   De pagina bereiken van IP-adres bevat een ingebouwde IP-adressen die zijn gedetecteerd door Cloud App Security. Dit omvat IP-adressen voor geïdentificeerde cloudservices, zoals Azure en Office 365, evenals de feed dreigingen die automatisch verrijkt IP-adressen met informatie over bekende riskante IP-adressen. 
-   Wanneer de Cloud App Security probeert uit te voeren van een beheeractie op een bestand, maar mislukt omdat het bestand is vergrendeld, er wordt nu automatisch opnieuw geprobeerd de beheeractie. 

## <a name="cloud-app-security-release-118"></a>Cloud App Security-release 118
4 maart 2018 uitgebracht

- Nu kunt u profiteren van de Microsoft Cloud App Security van shadow IT detectie en mogelijkheden voor bewaking uitvoeren op uw eigen eigen aangepaste apps. De nieuwe mogelijkheid voor het toevoegen van aangepaste apps aan Cloud Discovery kunt u app-gebruik controleren en de hoogte worden gebracht van wijzigingen in het gebruikspatroon. Zie voor meer informatie [beveiligen van uw aangepaste apps](cloud-discovery-custom-apps.md). Deze functie wordt geleidelijk geïntroduceerd.

- De Cloud App Security-portal **instellingen** pagina's zijn ontworpen. Het nieuwe ontwerp consolideert alle pagina's van de instellingen, biedt functionaliteit voor het zoeken en een verbeterd ontwerp. 

- Cloud Discovery ondersteunt nu Barracuda F-serie Firewalls en Barracuda F-serie Firewall Web logboek Streaming.

- De zoekfunctie in de gebruikers- en IP-adres-pagina's worden nu automatisch aanvullen gemakkelijker te vinden wat u zoekt inschakelen.

- U kunt nu Bulksgewijze bewerkingen uitvoeren in de entiteiten uitsluiten en pagina's uitsluiten IP-adres-instellingen. Dit maakt het eenvoudiger voor u te selecteren van meerdere gebruikers en groepen of IP-adressen uitsluiten wordt bewaakt als onderdeel van de Cloud Discovery in uw organisatie. 

## <a name="cloud-app-security-release-117"></a>Cloud App Security-release 117
20 februari 2018 uitgebracht

-   Cloud App Security verdiept integratie met Azure Information Protection nu kunt u bestanden beveiligen in G Suite. Deze openbare preview-functie kunt u om te scannen en bestanden classificeren in G Suite en Azure Information protection labels voor beveiliging automatisch worden toegepast. Zie voor meer informatie [integratie van Azure Information Protection](azip-integration.md).

-   Cloud Discovery nu ondersteunt [digitaal werken i-FILTER](http://www.daj.jp/en/products/if/).

-   De tabel SIEM-agents biedt nu meer details voor eenvoudiger beheer.

## <a name="cloud-app-security-release-116"></a>Cloud App Security-release 116
4 februari 2018 uitgebracht
- Afwijkingsdetectiebeleid cloud App Security is uitgebreid met nieuwe **detecties scenario's gebaseerde** inclusief onmogelijke reis activiteit van een verdachte IP-adres en meld u aan meerdere mislukte pogingen. Het nieuwe beleid worden automatisch ingeschakeld, detectie van dreigingen out-of-the-box bieden in uw cloudomgeving. Het nieuwe beleid tonen bovendien meer gegevens uit de Cloud App Security-detectie-engine, kunt u het versnellen onderzoek en doorlopende bedreigingen kunnen bevatten. Zie voor meer informatie [ophalen onmiddellijk gebruikersgedrag analytics en afwijkingsdetectie detectie](https://docs.microsoft.com/en-us/cloud-app-security/anomaly-detection-policy).

- Gefaseerde implementatie: Cloud App Security correleert nu tussen gebruikers en hun accounts in de SaaS-apps. Hiermee kunt u eenvoudig onderzoeken alle activiteiten voor een gebruiker over alle hun verschillende gecorreleerde SaaS-apps, ongeacht welke app of het account gebruikt.  

-   Gefaseerde implementatie: Cloud App Security ondersteunt nu meerdere exemplaren van dezelfde verbonden app. Als er meerdere exemplaren van bijvoorbeeld Salesforce (één voor verkoop, één voor marketing) kunt u zich ze beide verbindt met Cloud App Security en ze te beheren vanuit dezelfde console om gedetailleerde beleidsregels en nadere analyse te maken. 

- De parsers voor Cloud Discovery ondersteunen nu twee extra controlepunt indelingen, XML en KPC.



## <a name="cloud-app-security-release-115"></a>Cloud App Security-release 115
21 januari 2018 uitgebracht

- Deze versie biedt een verbeterde ervaring bij het selecteren van specifieke mappen in de beleidsregels voor bestanden. U kunt nu eenvoudig weergeven en selecteren meerdere mappen in een beleid op te nemen. 
- In de **gedetecteerde apps** pagina: 
  - De functie Labels bulksgewijs kunt u aangepaste labels (in aanvulling op erkende en niet-toegestane tags) toepassen. 
  - Wanneer u **een IP-adressen genereren**, of **een gebruikers-rapport genereren** de geëxporteerde rapporten omvatten nu de informatie over het verkeer van erkende is of niet-toegestane apps. 
- U kunt nu een nieuwe API-App-connector van het team van Microsoft Cloud App Security rechtstreeks in de portal aanvragen bij de **verbinding maken met een app** pagina. 


## <a name="cloud-app-security-release-114"></a>Cloud App Security-release 114
7 januari 2018 uitgebracht

- Vanaf versie 114, zijn wij geleidelijk rolt de mogelijkheid om te maken en aangepaste query's opslaan in het activiteitenlogboek en doorzochte apps's. Aangepaste query's kunnen u filter sjablonen maakt die opnieuw kunnen worden gebruikt voor dieper onderzoek. Bovendien **query's voorgestelde** hebt onderzoek out-of-the-box-sjablonen om te filteren op uw activiteiten kunnen worden toegevoegd en apps gedetecteerd. De **query's voorgestelde** bevatten aangepaste filters om risico's zoals imitatie activiteiten, beheerder activiteiten, riskant niet-compatibele cloud-opslag-apps, zakelijke apps met zwakke versleuteling en beveiligingsrisico's te identificeren. U kunt de **query's voorgestelde** als uitgangspunt nemen ze wijzigen als u naar eigen inzicht en deze vervolgens opslaan als een nieuwe query. Zie voor meer informatie [activiteitfilters en query's](activity-filters-queries.md) en [gedetecteerde app-filters en query's](discovered-app-queries.md).
 
- U kunt nu de huidige status van de Cloud App Security-service controleren door te gaan [status.cloudappsecurity.com](https://status.cloudappsecurity.com) of rechtstreeks uit binnen de portal door te klikken op **Help**>**System status**. 
 


## <a name="see-also"></a>Zie ook  

Zie voor een beschrijving van versies voorafgaand aan de hier genoemde [vorige versies van Microsoft Cloud App Security](release-note-archive.md).

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  