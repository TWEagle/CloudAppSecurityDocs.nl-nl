---
title: Problemen met inhoudsinspectie oplossen in Cloud App Security | Microsoft Docs
description: Dit onderwerp bevat een lijst met statussen van inhoudsinspectie en hun betekenis.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/10/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 359eb77f-e719-4c50-9b62-6ef64149a5a5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 40f759d58fe26776c0738271c0112d00bb52bf5a
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2017
---
# <a name="troubleshooting-content-inspection"></a>Problemen oplossen met inhoudsinspectie
|Status van inhoudsinspectie|Beschrijving|
|----|----|
|Voltooid|De inhoudsinspectie is voltooid.|
|Niet van toepassing|De inhoudsinspectie is niet van toepassing op dit bestand. Dit komt mogelijk doordat inhoudsinspectie van dit bestand niet is vereist door een beleid of doordat het bestandstype niet wordt ondersteund.|
|In behandeling|Het bestand bevindt zich momenteel in de inhoudsinspectiewachtrij.|
|Mislukt: downloadfout|Het bestand kan met Cloud App Security niet worden gedownload voor inspectie.|
|Mislukt: het bestand is versleuteld|Het bestand kan niet worden ontsleuteld.|
|Mislukt: het bestand is beschadigd|Het bestand is op de een of andere manier beschadigd en kan niet worden geïnspecteerd.|
|Mislukt: interne fout|Tijdens het inspecteren van het bestand is een fout opgetreden die niet nader kan worden bepaald.|
|Mislukt: externe DLP-fout|Er is iets fout gegaan in de externe DLP waardoor de inhoudsinspectie is mislukt in Cloud App Security.|
|Mislukt: bestandsgrootte overschreden|De bestandslimiet varieert al naar gelang de bestandsgrootte en het aantal tekens.|
|Mislukt: toegang tot bestand geweigerd|Het bestand bevindt zich buiten de cloud en kan niet worden geopend met Cloud App Security.|
|Mislukt: bestand is verwijderd|Het bestand bestaat niet meer in de cloud en kan niet worden geïnspecteerd.|
|Mislukt: niet-ondersteund bestandstype|De inhoudsinspectie kan in Cloud App Security niet worden uitgevoerd voor dit bestandstype. Dit kan komen doordat het bestandstype niet wordt ondersteund of omdat het bestand niet daadwerkelijk is opgeslagen in de indeling van het verwachte bestandstype.|

> [!NOTE]
> Als er een streepje wordt weergegeven bij de scanstatus, betekent dit dat het bestand niet in de wachtrij staat om te worden gescand. Zie [Beleidsregels voor bestanden](data-protection-policies.md) voor informatie over het instellen van beleid voor inhoudsinspectie.

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  