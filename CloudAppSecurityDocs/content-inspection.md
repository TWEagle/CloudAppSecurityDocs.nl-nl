---
title: Inhoudsinspectie | Microsoft Docs
description: In dit artikel wordt het proces beschreven dat in Cloud App Security wordt gevolgd wanneer DLP-inhoudsinspectie op gegevens in de cloud wordt uitgevoerd.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2401adbc-0011-4938-9e3a-a4c719a2f619
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: ea1854d6bf32e01afe6183409b68ded32ee37dd1


---

# <a name="content-inspection"></a>Inhoudsinspectie
In dit artikel wordt het proces beschreven dat in Cloud App Security wordt gevolgd wanneer DLP-inhoudsinspectie op gegevens in de cloud wordt uitgevoerd. 


Inhoudsinspectie werkt als volgt in Cloud App Security:
1. In Cloud App Security worden alle relevante bestanden in alle stations doorlopend gescand. 
2. In Cloud App Security wordt een NRT-scan (Near Real-Time) uitgevoerd op de stations en gebeurtenissen die zijn gedetecteerd als nieuw of gewijzigd. 

Zowel de bestanden in de doorlopende scan als de bestanden in de NRT-scan worden aan de inspectiewachtrij toegevoegd. De volgorde van de bestanden in de scanwachtrij wordt ingesteld op basis van de activiteit in bestanden en de scan van uw stations. Bestanden worden alleen gescand als in de metagegevens van het bestand wordt aangegeven dat het bestand van een ondersteund MIME-type is. Deze scan is van toepassing op bestanden die relevant zijn voor een gegevensscan (documenten, afbeeldingen, presentaties, spreadsheets, tekst- en ZIP-bestanden).  

Nadat een bestand is gescand, gebeurt het volgende:

1. In Cloud App Security worden alle aangepaste beleidsregels toegepast die betrekking hebben op de metagegevens en niet op de inhoud zelf. Bijvoorbeeld een beleid waarmee u wordt gewaarschuwd wanneer bestanden groter zijn dan 20 MB, of een beleid waarmee u wordt gewaarschuwd wanneer DOCX-bestanden worden opgeslagen in OneDrive. 

2. Als er een beleid is waarvoor inhoudsinspectie moet worden uitgevoerd en het bestand in aanmerking komt voor inspectie, wordt de inhoud in de inspectiewachtrij geplaatst. De lengte van de wachtrij is afhankelijk van de grootte van de tenant en het aantal bestanden dat moet worden gescand. 

3. Op dit moment kunt u de status van de inhoudsinspectie bekijken door **Onderzoeken** > **Bestanden** te kiezen en vervolgens op een bestand te klikken. In **Status van inhoudsinspectie** in de bestandslade die wordt geopend met de details van het bestand, wordt een van de volgende statuswaarden weergegeven: 

|Status van inhoudsinspectie|Beschrijving|
|----|----|
|Voltooid|De inhoudsinspectie is voltooid.|
|Niet van toepassing|De inhoudsinspectie is niet van toepassing op dit bestand. Dit kan komen doordat inhoudsinspectie van dit bestand niet is vereist door een beleid of omdat het bestandstype niet wordt ondersteund.|
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

## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  


<!--HONumber=Oct16_HO4-->


