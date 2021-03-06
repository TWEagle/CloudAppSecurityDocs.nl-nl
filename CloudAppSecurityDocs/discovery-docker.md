---
title: Automatisch uploaden van logboeken configureren voor doorlopende rapporten | Microsoft Docs
description: In dit onderwerp beschrijft het proces voor het configureren van logboek automatisch uploaden voor continue rapporten in de Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c75ba963-ad5a-48e6-8d5d-610fc6e0b990
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f9af164385b74f9742581e9879424e02409af34d
ms.sourcegitcommit: 85d90d51e9e265d077f38b0188bcfdab2ce63ed1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2018
---
# <a name="configure-automatic-log-upload-for-continuous-reports"></a>Automatisch uploaden van logboeken configureren voor doorlopende rapporten


Met een logboekverzamelaar kunt u het uploaden van logboeken vanaf uw netwerk eenvoudig automatiseren. De logboekverzamelaar wordt uitgevoerd op uw netwerk en ontvangt logboeken via Syslog of FTP. Elk logboek wordt automatisch verwerkt, gecomprimeerd en naar de portal verzonden. FTP-logboeken worden geüpload naar de Cloud App Security nadat het bestand de FTP-overdracht naar de Logboekverzamelaar voltooid.  Voor Syslog, de Logboekverzamelaar schrijft de logboeken ontvangen op de schijf en het bestand uploadt en Cloud App Security wanneer de bestandsgrootte groter dan 40 KB is.

Nadat een logboek is geüpload naar de Cloud App Security, wordt deze verplaatst naar een back-map die de laatste 20 logboeken op elk gewenst moment worden opgeslagen. Wanneer nieuwe logboeken binnenkomen, worden de oude versie verwijderd. Wanneer de schijfruimte van logboek collector vol is, komt de logboekverzamelaar nieuwe logboeken totdat er meer schijfruimte vrij is. Dit gebeurt wanneer u ontvangt een waarschuwing op het **Logboekverzamelaars** tabblad van de **logboeken automatisch uploaden** instellingen.

Voordat u automatische logboekbestandsverzameling instelt, moet u controleren of uw logboek overeenkomt met het verwachte logboektype, zodat uw bestand kan worden geparseerd met Cloud App Security.

> [!NOTE]
>-  Cloud App Security biedt ondersteuning voor het doorsturen van logboeken vanaf uw SIEM-server naar de logboekverzamelaar, ervan uitgaande dat de logboeken worden doorgestuurd in hun oorspronkelijke indeling. Het is echter ten zeerste aanbevolen dat u de logboekverzamelaar rechtstreeks met uw firewall en/of de proxy integreren.
>- De logboekverzamelaar comprimeren gegevens voordat deze wordt geüpload. Het uitgaande verkeer op de logboekverzamelaar is 10% van de grootte van de verkeerslogboeken die het ontvangt. 

## <a name="deployment-modes"></a>Implementatiemodi

De Logboekverzamelaar ondersteunt twee implementatiemodi:

-   **Container**: wordt uitgevoerd als een Docker-installatiekopie op [Ubuntu on-premises](discovery-docker-ubuntu.md), [Ubuntu in Azure](discovery-docker-ubuntu-azure.md) of [RHEL on-premises](discovery-docker-ubuntu.md). 

-   **Virtueel apparaat**: [wordt uitgevoerd als een installatiekopie via Hyper-V- of VMware-hypervisor](configure-automatic-log-upload-for-continuous-reports.md)




## <a name="see-also"></a>Zie ook
 
[Momentopnamerapporten maken van Cloud Discovery](create-snapshot-cloud-discovery-reports.md)

[Werken met Cloud Discovery-gegevens](working-with-cloud-discovery-data.md)

