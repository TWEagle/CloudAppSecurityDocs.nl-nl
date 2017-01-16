---
title: Cloud-apps beheren met beleidsregels | Microsoft Docs
description: In dit onderwerp vindt u informatie over hoe beleidsregels worden gebruikt en ingesteld om het gebruik van cloud-apps te beheren.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/8/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a6658937-57a2-484a-85cb-5a4cdbeeb002
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 98b16c96c31039248bdfbe57f980b3ae6a26a7de
ms.openlocfilehash: 4d09fa2aa44634e9389baeef431e897c32f3a912


---
# <a name="policy-templates"></a>Beleidssjablonen

Hier volgt een lijst met alle beleidssjablonen die zijn opgenomen in Cloud App Security. Voor het gebruiksgemak raden wij u aan bij het maken van beleid zoveel mogelijk gebruik te maken van een bestaande sjabloon.

|Naam van sjabloon|Beschrijving|
|----|----|
|Nieuwe populaire app|Ontvang een waarschuwing wanneer er nieuwe apps worden gedetecteerd die door meer dan 500 gebruikers worden gebruikt.|
|Bestand gedeeld met niet-geautoriseerd domein|Ontvang een waarschuwing wanneer een bestand wordt gedeeld met een niet-geautoriseerd domein (zoals uw concurrent).|
|Meerdere mislukte aanmeldingen van een gebruiker bij een app|Ontvang een waarschuwing wanneer één specifieke gebruiker zich bij een bepaalde app probeert aan te melden en hem of haar dat na meer dan 10 keer binnen 5 minuten niet lukt.|
|Afwijkend gedrag in gedetecteerde gebruikers|Ontvang een waarschuwing wanneer afwijkend gedrag wordt vastgesteld bij gedetecteerde gebruikers en apps, zoals: grote hoeveelheden geüploade gegevens in vergelijking met andere gebruikers, grote gebruikerstransacties vergeleken met de geschiedenis van de gebruiker.|
|Compatibiliteitscontrole van CRM-app|Ontvang een waarschuwing wanneer er nieuwe CRM-apps worden gedetecteerd die niet compatibel zijn met SOC2, SSAE 16 ISAE 3402, ISO 27001 en HIPAA, en worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Detectie van algemene afwijkingen|Ontvang een waarschuwing wanneer een afwijkende sessie in een van de goedgekeurde apps wordt gedetecteerd, zoals: onmogelijke reis, aanmeldingspatroon, inactief account.|
|Nieuwe app met hoog uploadvolume|Ontvang een waarschuwing wanneer er nieuwe apps worden gedetecteerd waarvan het totale dagelijks uploadverkeer meer dan 500 MB bedraagt.|
|Groot aantal downloads door één gebruiker|Ontvang een waarschuwing wanneer één specifieke gebruiker meer dan 30 downloads binnen 5 minuten uitvoert.|
|Nieuwe app met hoge verkeervolumes|Ontvang een waarschuwing wanneer er nieuwe apps worden gedetecteerd waarvan het totale dagelijks verkeer van meer dan 500 MB bedraagt.|
|Compatibiliteitscontrole van apps voor cloudopslag|Ontvang een waarschuwing wanneer er nieuwe apps voor cloudopslag worden gedetecteerd die niet compatibel zijn met SOC2, SSAE 16, ISAE 3402 en PCI DSS, en worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Nieuwe riskante app|Ontvang een waarschuwing wanneer er nieuwe apps worden gedetecteerd met een risicoscore lager dan 6 en die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Compatibiliteitscontrole van samenwerkingsapp|Ontvang een waarschuwing wanneer er nieuwe samenwerkingsapp worden gedetecteerd die niet compatibel zijn met SOC2 en SSAE 16, en worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Aanmelding vanaf een riskant IP-adres|Ontvang een waarschuwing wanneer een gebruiker zich aanmeldt bij uw goedgekeurde apps vanaf een riskant IP-adres. Standaard bevat de categorie riskante IP-adressen adressen met IP-adreslabels van een anonieme proxy, TOR of Botnet. U kunt meer IP-adressen aan deze categorie toevoegen op de pagina met instellingen voor IP-adresbereiken.|
|Beheeractiviteiten vanaf een niet-beheerders-IP-adres|Ontvang een waarschuwing wanneer een gebruiker beheeractiviteiten uitvoert vanaf een IP-adres dat niet is opgenomen in een specifieke categorie IP-adresbereiken. U kunt meer riskante IP-adressen instellen door IP-adresbereiken te selecteren op de pagina Instellingen.|
|Aanmelding van een gebruiker vanaf een niet-gecategoriseerd IP-adres|Ontvang een waarschuwing wanneer een gebruiker zich aanmeldt vanaf een IP-adres dat niet is opgenomen in een specifieke categorie IP-bereiken. U kunt IP-adressen categoriseren door IP-adresbereiken te selecteren op de pagina Instellingen.|
|Bestand met persoonsgegevens gedetecteerd in de cloud (ingebouwde DLP-engine)|Ontvang een waarschuwing wanneer een bestand met persoonsgegevens wordt gedetecteerd door onze ingebouwde DLP-engine (voor preventie van gegevensverlies) in een goedgekeurde cloud-app.|
|Nieuwe HRM-app|Ontvang een waarschuwing wanneer er nieuwe HRM-apps worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Bestand met betaalkaartgegevens gedetecteerd in de cloud (ingebouwde DLP-engine)|Ontvang een waarschuwing wanneer een bestand met betaalkaartgegevens wordt gedetecteerd door onze ingebouwde DLP-engine (voor preventie van gegevensverlies) in een goedgekeurde cloud-app.|
|Nieuwe app voor het hosten van code|Ontvang een waarschuwing wanneer er nieuwe apps voor het hosten van code worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Nieuwe samenwerkingsapp|Ontvang een waarschuwing wanneer er nieuwe samenwerkingsapps worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Nieuwe VMS-apps|Ontvang een waarschuwing wanneer er nieuwe VMS-apps (Vendor Management System) worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Nieuwe app voor online vergaderen|Ontvang een waarschuwing wanneer er nieuwe apps voor online vergaderen worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Afwijkend gedrag van gedetecteerde IP-adressen|Ontvang een waarschuwing wanneer in gevonden IP-adressen en apps afwijkend gedrag wordt gedetecteerd, zoals grote hoeveelheden geüploade gegevens in vergelijking met andere IP-adressen, grote app-transacties in vergelijking met de geschiedenis van het IP-adres.|
|Nieuwe verkoopapp|Ontvang een waarschuwing wanneer er nieuwe verkoopapps worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Nieuwe app voor cloudopslag|Ontvang een waarschuwing wanneer er nieuwe apps voor cloudopslag worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Extern gedeelde broncode|Ontvang een waarschuwing wanneer een bestand met broncode wordt gedeeld buiten uw organisatie.|
|Nieuwe CRM-app|Ontvang een waarschuwing wanneer er nieuwe CRM-apps worden gedetecteerd die worden gebruikt door meer dan 50 gebruikers met een totaal dagelijks gebruik van meer dan 50 MB.|
|Bestand met beveiligde gezondheidsinformatie gedetecteerd in de cloud (ingebouwde DLP-engine)|Ontvang een waarschuwing wanneer een bestand met beveiligde gezondheidsinformatie wordt gedetecteerd door onze ingebouwde DLP-engine (voor preventie van gegevensverlies) in een goedgekeurde cloud-app.|
|Bestand met persoonlijke e-mailadressen gedeeld|Ontvang een waarschuwing wanneer een bestand met het persoonlijke e-mailadres van een gebruiker wordt gedeeld.|
|Gedeelde digitale certificaten (bestandsextensies)|Ontvang een waarschuwing wanneer een bestand met digitale certificaten openbaar wordt gedeeld.|
|Verouderde extern gedeelde bestanden|Zoek extern gedeelde bestanden die 6 maanden lang niet zijn geopend of gewijzigd en verwijder deze van uw station.|



## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  


<!--HONumber=Jan17_HO2-->


