---
title: Hoe Cloud App Security inhoudsinspectie uitvoert | Microsoft Docs
description: In dit artikel wordt het proces beschreven dat in Cloud App Security wordt gevolgd wanneer DLP-inhoudsinspectie op gegevens in de cloud wordt uitgevoerd.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/23/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2401adbc-0011-4938-9e3a-a4c719a2f619
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 1083a743f2602bab6e55e96e1e7f7dd4c0b77bce
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2017
---
# <a name="content-inspection"></a>Inhoudsinspectie
In dit artikel wordt het proces beschreven dat in Cloud App Security wordt gevolgd wanneer DLP-inhoudsinspectie op gegevens in de cloud wordt uitgevoerd. 


Inhoudsinspectie werkt als volgt in Cloud App Security:
1. Ten eerste wordt er in Cloud App Security een NRT-scan (Near Real-Time) uitgevoerd op de stations en gebeurtenissen die zijn gedetecteerd als nieuw of gewijzigd.
2. Nadat deze scan is voltooid, worden in Cloud App Security alle relevante bestanden in alle stations doorlopend gescand.  

Zowel de bestanden in de NRT-scan als de doorlopende scan worden toegevoegd aan de inspectiewachtrij. De volgorde van de bestanden in de scanwachtrij wordt ingesteld op basis van de activiteit in bestanden en de scan van uw stations. Bestanden worden alleen gescand als in de metagegevens van het bestand wordt aangegeven dat het bestand van een ondersteund MIME-type is. Deze scan is van toepassing op bestanden die relevant zijn voor een gegevensscan (documenten, afbeeldingen, presentaties, spreadsheets, tekst- en ZIP-bestanden).  

Nadat een bestand is gescand, gebeurt het volgende:

1. In Cloud App Security worden alle aangepaste beleidsregels toegepast die betrekking hebben op de metagegevens en niet op de inhoud zelf. Bijvoorbeeld een beleid waarmee u wordt gewaarschuwd wanneer bestanden groter zijn dan 20 MB, of een beleid waarmee u wordt gewaarschuwd wanneer DOCX-bestanden worden opgeslagen in OneDrive. 

2. Als er een beleid is waarvoor inhoudsinspectie moet worden uitgevoerd en het bestand in aanmerking komt voor inspectie, wordt de inhoud in de inspectiewachtrij geplaatst. De lengte van de wachtrij is afhankelijk van de grootte van de tenant en het aantal bestanden dat moet worden gescand. 

3. Op dit moment kunt u de status van de inhoudsinspectie bekijken door **Onderzoeken** > **Bestanden** te kiezen en vervolgens op een bestand te klikken. In de bestandslade die wordt geopend met de details van het bestand, geeft de **Status van inhoudsinspectie** de status **Voltooid**, **In behandeling** of **Niet van toepassing** aan (als het bestandstype niet wordt ondersteund), of wordt een foutbericht weergegeven. Zie [Problemen oplossen met inhoudsinspectie](troubleshooting-content-inspection.md) voor meer informatie over foutberichten van inhoudsinspectie.

> [!NOTE]
> Als er een streepje wordt weergegeven bij de scanstatus, betekent dit dat het bestand niet in de wachtrij staat om te worden gescand. Zie [Beleidsregels voor bestanden](data-protection-policies.md) voor informatie over het instellen van beleid voor inhoudsinspectie.

De ingebouwde beleidsregels voor inhoudsinspectie kunnen zoeken naar het volgende:

- E-mailadressen 
- Creditcardnummers 
  - Alle creditcardbedrijven (Visa, MasterCard, American Express, Diners Club, Discover, JCB, Dankort, UnionPay) 
  - Scheidingstekens (spatie, punt of streepje)
  - Deze scan omvat ook de Luhn-validatie
- SWIFT-codes
- Internationale paspoortnummers
- Rijbewijsnummers
- Datums
- ABA-transitrouteringsnummers van banken
- Bankidentificatiecodes
- HIPAA HICN-gezondheidszorgclaimnummers
- HIPAA NPI nationale provider-id’s
- PHI Volledige namen en geboortedatums
- Californische identificatie- of rijbewijsnummers
- Rijbewijsnummers
- Huisadressen
- Id-kaarten
- Sofinummers

## <a name="supported-languages"></a>Ondersteunde talen

De Cloud App Security-inhoudsinspectie-engine:
-   ondersteunt alle Unicode-tekens
-   bevat informatie over meer dan 1.000 bestandstypen
-   Meerdere talen worden ondersteund, met name de bestanden die gebruikmaken van Unicode-tekensets. Zorg ervoor dat uw beleid is gedefinieerd voor de desbetreffende talen. Als u bijvoorbeeld op zoek bent naar trefwoorden, moet u de trefwoorden invoeren in de talen die u wilt gebruiken.
-   In tekstbestandstypen die gebruikmaken van niet-Unicode-codering, bijvoorbeeld Chinees GB2312, werkt het vergelijken met Unicode Chinese trefwoorden niet zoals verwacht.
-   Voor bestandstypen die afhankelijk zijn van bibliotheken van derden werken overeenkomende tekenreeksen en woorden niet altijd als verwacht. Dit gebeurt meestal bij bestanden (zoals binaire bestandstypen) waarin de inhoudsinspectie afhankelijk is van bibliotheken van derden die Java-tekenreeksen voor de taal- en tekensets retourneren.



## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  