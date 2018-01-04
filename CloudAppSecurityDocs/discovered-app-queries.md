---
title: Werken met Cloud App Security gedetecteerde app-filters en query's | Microsoft Docs
description: Dit onderwerp bevat een lijst met Cloud App Security gedetecteerde app-filters en query's en wordt uitgelegd hoe u ermee.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/3/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 1a2d3aeb-4e28-4c73-804b-95e862b08e43
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: ea1b0b150f1028e8a8d4edac32aa6d8a4f59b564
ms.sourcegitcommit: bbf4a2715d1ea3fd21c1a1b87c7f5a2947d2ca68
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/04/2018
---
# <a name="discovered-app-filters-and-queries"></a>Gedetecteerde app-filters en query 's

## <a name="discovered-app-filters"></a>Gedetecteerde app-filters

Er zijn basiseigenschappen en geavanceerde doorzochte app-filters. Gebruiken om te creëren van een complexe filter (zoals in het bovenstaande voorbeeld) de optie voor Geavanceerd waarin alle van de volgende opties:

![Gedetecteerde apps](./media/discovered-apps.png)  


- **App-tag**: Selecteer of de app is erkende of niet-toegestane of niet is gemarkeerd. Bovendien kunt u een aangepast label maken voor uw app en vervolgens worden gebruikt om te filteren op specifieke typen apps. 
- **Apps en domeinen**: Hiermee kunt u zoeken naar specifieke apps of apps die worden gebruikt in een specifieke domeinen. 
- **Categorieën**: het filter categorieën, dat aan de linkerkant van de pagina bevindt zich, kunt u zoeken naar typen apps volgens app-categorieën, bijvoorbeeld apps sociale netwerken, opslag-Cloud-apps, enzovoort. U kunt meerdere categorieën tegelijk of één categorie selecteren en vervolgens de basiseigenschappen en geavanceerde filters boven deze op toepassen.
- **Naleving risicofactor**: Hiermee kunt u naar een specifieke normen gehanteerd zoeken, certificering en conformiteit die de app kan voldoen aan de (HIPAA, ISO 27001, SOC 2, PCI-DSS, enz.).
- **Algemene risicofactor**: Hiermee kunt u naar algemene risicofactoren zoals Consumer populariteit, Data zoeken center landinstellingen, enzovoort.
- **Risicoscore**: Hiermee kunt u filteren op apps met risico score zodat u zich richten kunt op, bijvoorbeeld alleen zeer risicovolle apps controleren. U kunt ook de risicoscore ingesteld door Cloud App Security overschrijven. Zie voor meer informatie [werken met de risicoscore](risk-score.md).
- **Beveiliging risicofactor**: kunt u filteren op basis van specifieke veiligheidsmaatregelen (zoals versleuteling op rest, meervoudige verificatie, enz.).
- **Gebruik**: Hiermee kunt u filteren op basis van de gebruiksstatistieken van deze app, zoals apps met minder dan of meer dan een opgegeven hoeveelheid **gegevens uploads**, apps met meer dan of kleiner dan een opgegeven aantal **gebruikers**.

### <a name="creating-and-managing-custom-app-tags"></a>Maken en beheren van aangepaste app labels

U kunt een aangepaste app-code kunt maken. Deze tags kunnen vervolgens worden gebruikt als filters voor dieper verdiepen specifieke typen apps die u wilt onderzoeken. Bijvoorbeeld, aangepaste controleoverzicht, toewijzing aan een bepaalde bedrijfseenheid of aangepaste goedkeuringen, zoals 'goedgekeurd door juridische'.

Een aangepaste app-label maken:

1. Van de **instellingen** tandwiel, selecteer **Cloud Discovery** en in de **beheren van app-tags** en klik op het pictogram ![plus pictogram](./media/plus-icon.png). 

![aangepaste app label maken](./media/create-app-tag.png)

2. U kunt de **app-codes beheren** tabel om weer te geven welke apps op dit moment zijn gemarkeerd met elke tag app en u ongebruikte app labels kunt verwijderen.

3. Toepassen van een app-tag in het **gedetecteerde apps** tabblad, klik op de drie punten aan de rechterkant van de tabel en selecteer de app-tag toe te passen. 

> [!NOTE]
>U kunt ook maken een nieuwe app-code rechtstreeks in de **gedetecteerde apps** tabel door te klikken op **maakt app label** na het selecteren van de drie punten rechts van alle geselecteerde app. U kunt ook toegang tot de **app-codes beheren** scherm door te klikken op de koppeling in de hoek voor de **maakt app label** pop.

## <a name="discovered-app-queries"></a>Gedetecteerde app-query 's

Een eenvoudiger onderzoek zelfs kunt u nu aangepaste query's maken en opslaan voor later gebruik. 

1. In de **gedetecteerde apps** pagina, gebruikt u de filters zoals hierboven wordt beschreven om Inzoomen op uw apps indien nodig. 

2. Nadat u de gewenste resultaten hebben bereikt, klikt u op de **opslaan als** knop in de rechterbovenhoek van de filters. 

3. In de **opslaan query** pop-up naam van uw query.

 ![Nieuwe query](./media/new-query.png)

4. Gebruik deze query opnieuw in de toekomst onder **query's**, schuif omlaag naar **opgeslagen query's** en selecteert u uw query. 

 ![query openen](./media/open-query.png)


Cloud App Security kunt u met **voorgestelde query's** en kunt u aangepaste query's die u vaak gebruikt opslaan. Voorgestelde query's bieden u aanbevolen mogelijkheden van onderzoek die uw gedetecteerde apps filteren met behulp van de volgende optionele voorgestelde query's:

 - Cloud-apps waarmee anonieme gebruik - filtert alle gedetecteerde apps om weer te geven alleen de apps die beveiligingsrisico's zijn omdat ze geen gebruikersverificatie vereisen en toestaan dat gebruikers om gegevens te uploaden.

 - Cloud-apps die zijn gecertificeerd - CSA-STER filtert alle gedetecteerde apps om weer te geven alleen apps waarvoor CSA STER certificeringsinstantie door zelf assessment, certificering, attestation of doorlopende bewaking.

 - Cloud-apps die voldoen aan het beleid - FedRAMP filtert alle gedetecteerde apps om weer te geven alleen apps waarvan risicofactor FedRAMP-compatibiliteit hoog, Gemiddeld of laag is. 

 - Cloud-opslag- en samenwerking apps waarvan gegevens-filters van de gebruiker eigenaar uw gedetecteerde apps om weer te geven alleen de apps die riskant zijn omdat ze u eigenaar hebben over de gegevens niet toestaan, maar ze uw gegevens behouden.

 - Cloud-opslag-apps die zijn riskant en niet-compatibele - filtert alle gedetecteerde apps om alleen apps waarin ze niet zijn SOC 2 of PCI DSS-versie niet wordt ondersteund en ze hebben een risicoscore van 5 of minder compatibel met HIPAA weer te geven.

 - Enterprise cloud-apps waarvoor zwakke verificatie - filtert alle gedetecteerde apps om weer te geven alleen de apps die niet, SAML ondersteunen, hebben geen wachtwoordbeleid en MFA niet inschakelt.

 - Enterprise cloud-apps waarvoor zwakke versleuteling - filtert alle gedetecteerde apps om weer te geven alleen de apps die riskant zijn omdat ze geen gegevens in rust versleutelen en elk versleutelingsprotocol voor de niet ondersteunen.

![query gedetecteerde apps](./media/queries-discovered-apps.png)

 
Bovendien kunt u de voorgestelde query's als uitgangspunt voor een nieuwe query. Selecteer eerst een van de voorgestelde query's. Vervolgens wijzigingen aanbrengen en klik tot slot **opslaan als** Maak een nieuwe **query opgeslagen**.


## <a name="see-also"></a>Zie ook
 
[Momentopnamerapporten maken van Cloud Discovery](create-snapshot-cloud-discovery-reports.md)

[Automatisch uploaden van logboeken configureren voor doorlopende rapporten](configure-automatic-log-upload-for-continuous-reports.md)

[Werken met Cloud Discovery-gegevens](working-with-cloud-discovery-data.md)

