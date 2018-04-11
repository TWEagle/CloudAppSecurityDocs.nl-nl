---
title: Verwijzing naar beleidssjabloon in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u informatie over hoe beleidsregels worden gebruikt en ingesteld om het gebruik van cloud-apps te beheren.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: a6658937-57a2-484a-85cb-5a4cdbeeb002
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: e18f4e2601008ed42f8889822d1bc1fd31896dbc
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="policy-templates"></a>Beleidssjablonen

Hier volgt een lijst met alle beleidssjablonen die zijn opgenomen in Cloud App Security. Voor het gebruiksgemak raden wij u aan bij het maken van beleid zoveel mogelijk gebruik te maken van een bestaande sjabloon.

|Risicocategorie|Naam van sjabloon|Description|
|-----|----|----|
|Cloud Discovery|Afwijkend gedrag in gedetecteerde gebruikers|Ontvang een waarschuwing wanneer afwijkend gedrag wordt vastgesteld bij gedetecteerde gebruikers en apps, zoals: grote hoeveelheden geüploade gegevens in vergelijking met andere gebruikers, grote gebruikerstransacties vergeleken met de geschiedenis van de gebruiker.|
|Cloud Discovery|Afwijkend gedrag van gedetecteerde IP-adressen|Ontvang een waarschuwing wanneer in gevonden IP-adressen en apps afwijkend gedrag wordt gedetecteerd, zoals grote hoeveelheden geüploade gegevens in vergelijking met andere IP-adressen, grote app-transacties in vergelijking met de geschiedenis van het IP-adres.|
|Cloud Discovery|Compatibiliteitscontrole van samenwerkingsapp|Ontvang een waarschuwing wanneer er nieuwe samenwerkingsapp worden gedetecteerd die niet compatibel zijn met SOC2 en SSAE 16, en worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Cloud Discovery|Compatibiliteitscontrole van apps voor cloudopslag|Ontvang een waarschuwing wanneer er nieuwe apps voor cloudopslag worden gedetecteerd die niet compatibel zijn met SOC2, SSAE 16, ISAE 3402 en PCI DSS, en worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Cloud Discovery|Compatibiliteitscontrole van CRM-app|Ontvang een waarschuwing wanneer er nieuwe CRM-apps worden gedetecteerd die niet compatibel zijn met SOC2, SSAE 16 ISAE 3402, ISO 27001 en HIPAA, en worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Cloud Discovery|Nieuwe app voor cloudopslag|Ontvang een waarschuwing wanneer er nieuwe apps voor cloudopslag worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Cloud Discovery|Nieuwe app voor het hosten van code|Ontvang een waarschuwing wanneer er nieuwe apps voor het hosten van code worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Cloud Discovery|Nieuwe samenwerkingsapp|Ontvang een waarschuwing wanneer er nieuwe samenwerkingsapps worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Cloud Discovery|Nieuwe CRM-app|Ontvang een waarschuwing wanneer er nieuwe CRM-apps worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Cloud Discovery|Nieuwe app met hoge verkeervolumes|Ontvang een waarschuwing wanneer er nieuwe apps worden gedetecteerd waarvan het totale dagelijks verkeer van meer dan 500 MB bedraagt.|
|Cloud Discovery|Nieuwe app met hoog uploadvolume|Ontvang een waarschuwing wanneer er nieuwe apps worden gedetecteerd waarvan het totale dagelijks uploadverkeer meer dan 500 MB bedraagt.|
|Cloud Discovery|Nieuwe HRM-app|Ontvang een waarschuwing wanneer er nieuwe HRM-apps worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Cloud Discovery|Nieuwe app voor online vergaderen|Ontvang een waarschuwing wanneer er nieuwe apps voor online vergaderen worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Cloud Discovery|Nieuwe populaire app|Ontvang een waarschuwing wanneer er nieuwe apps worden gedetecteerd die door meer dan 500 gebruikers worden gebruikt.|
|Cloud Discovery|Nieuwe riskante app|Ontvang een waarschuwing wanneer er nieuwe apps worden gedetecteerd met een risicoscore lager dan 6 en die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Cloud Discovery|Nieuwe verkoopapp|Ontvang een waarschuwing wanneer er nieuwe verkoopapps worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Cloud Discovery|Nieuwe VMS-apps|Ontvang een waarschuwing wanneer er nieuwe VMS-apps (Vendor Management System) worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|DLP|Extern gedeelde broncode|Ontvang een waarschuwing wanneer een bestand met broncode wordt gedeeld buiten uw organisatie.|
|DLP|Bestand met betaalkaartgegevens gedetecteerd in de cloud (ingebouwde DLP-engine)|Ontvang een waarschuwing wanneer een bestand met betaalkaartgegevens wordt gedetecteerd door onze ingebouwde DLP-engine (voor preventie van gegevensverlies) in een goedgekeurde cloud-app.|
|DLP|Bestand met beveiligde gezondheidsinformatie gedetecteerd in de cloud (ingebouwde DLP-engine)|Ontvang een waarschuwing wanneer een bestand met beveiligde gezondheidsinformatie wordt gedetecteerd door onze ingebouwde DLP-engine (voor preventie van gegevensverlies) in een goedgekeurde cloud-app.|
|DLP|Bestand met persoonsgegevens gedetecteerd in de cloud (ingebouwde DLP-engine)|Ontvang een waarschuwing wanneer een bestand met persoonsgegevens wordt gedetecteerd door onze ingebouwde DLP-engine (voor preventie van gegevensverlies) in een goedgekeurde cloud-app.|
|Detectie van dreigingen|Beheeractiviteiten vanaf een niet-zakelijk IP-adres|Ontvang een waarschuwing wanneer een gebruiker beheeractiviteiten uitvoert vanaf een IP-adres dat niet is opgenomen in de categorie zakelijke IP-adresbereiken. U moet eerst uw zakelijke IP-adressen configureren door naar de pagina Instellingen te gaan en **IP-adresbereiken** in te stellen.|
|Detectie van dreigingen|Detectie van algemene afwijkingen|Ontvang een waarschuwing wanneer een afwijkende sessie in een van de goedgekeurde apps wordt gedetecteerd, zoals: onmogelijke reis, aanmeldingspatroon, inactief account.|
|Detectie van dreigingen|Aanmelding vanaf een riskant IP-adres|Ontvang een waarschuwing wanneer een gebruiker zich aanmeldt bij uw goedgekeurde apps vanaf een riskant IP-adres. Standaard bevat de categorie riskante IP-adressen adressen met IP-adreslabels van een anonieme proxy, TOR of Botnet. U kunt meer IP-adressen aan deze categorie toevoegen op de pagina met instellingen voor IP-adresbereiken.|
|Detectie van dreigingen|Groot aantal downloads door één gebruiker|Waarschuwing tijdens het uitvoeren van een enkele gebruiker meer dan 50 downloads binnen 1 minuut.|
|Detectie van dreigingen|Meerdere mislukte aanmeldingen van een gebruiker bij een app|Ontvang een waarschuwing wanneer één specifieke gebruiker zich bij een bepaalde app probeert aan te melden en hem of haar dat na meer dan 10 keer binnen 5 minuten niet lukt.|
|Detectie van dreigingen|Mogelijke ransomware activiteit|Een waarschuwing wanneer een gebruiker bestanden uploadt naar de cloud mogelijk besmet met ransomware.|
|Detectie van dreigingen|Aanmelding van een gebruiker vanaf een niet-gecategoriseerd IP-adres|Ontvang een waarschuwing wanneer een gebruiker zich aanmeldt vanaf een IP-adres dat niet is opgenomen in een specifieke categorie IP-bereiken. U kunt IP-adressen categoriseren door IP-adresbereiken te selecteren op de pagina Instellingen.|
|Delen beheren|Bestand met persoonlijke e-mailadressen gedeeld|Ontvang een waarschuwing wanneer een bestand met het persoonlijke e-mailadres van een gebruiker wordt gedeeld.|
|Delen beheren|Bestand gedeeld met niet-geautoriseerd domein|Ontvang een waarschuwing wanneer een bestand wordt gedeeld met een niet-geautoriseerd domein (zoals uw concurrent).|
|Delen beheren|Gedeelde digitale certificaten (bestandsextensies)|Ontvang een waarschuwing wanneer een bestand met digitale certificaten openbaar wordt gedeeld.|
|Delen beheren|Verouderde extern gedeelde bestanden|Zoek extern gedeelde bestanden die 6 maanden lang niet zijn geopend of gewijzigd en verwijder deze van uw station.|



## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  