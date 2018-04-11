---
title: De RegEx-engine gebruiken voor beleidsregels voor inhoudscontrole | Microsoft Docs
description: In dit onderwerp vindt u instructies voor het gebruik van RegEx voor jokertekens in de beleidsregels van Cloud App Security.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: dc8b87e5-e6c1-4a65-ab8c-067fb527fce4
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 91326c6153d9d400236816b6a86b128ae3cafc18
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="working-with-the-regex-engine"></a>Bij het werken met de beleidsregels voor inhoudscontrole
 
In de beleidsregels voor inhoudsinspectie in Cloud App Security wordt voor jokertekens gebruikgemaakt van RegEx. Inhoudscontrole kan worden toegepast als onderdeel van beleidsregels voor bestanden. Als u reguliere expressies wilt testen, kunt u de volgende websites gebruiken:  
  
-   [http://regexpal.com/](http://regexpal.com/)  
  
     (Zorg ervoor dat u **Niet hoofdlettergevoelig** selecteert.)  
  
-   [https://regex101.com/](https://regex101.com/)  
  
     Bevat een gedetailleerde analyse van de RegEx.  
  
De volgende beperkingen worden opgelegd voor aangepaste reguliere expressies:  
  
-   De zoekopdracht is altijd niet hoofdlettergevoelig  
   
-   Toegestane kwantiteitsmeters: {n, m} waarbij n, m < 10  
  
-   Alle groepen moeten ‘non-capturing’ zijn, bijvoorbeeld: (?:xxx)  
  
     In plaats van (groep) gebruikt u (?:groep)  
  
-   Niet-toegestane kwantiteitsmeters: *, +, {n,}  
  
     In plaats van * gebruikt u {0,9}  
  
     In plaats van + gebruikt u {1,9}  
  
-   Niet-toegestane terugverwijzingen: \\<getal\> of \k\<naam>  
  
Voorbeelden van expressies  
  

|                                                               |                                                               |                                    |
|---------------------------------------------------------------|---------------------------------------------------------------|------------------------------------|
|              <strong>Reguliere expressie</strong>              |                     <strong>Gegevens</strong>                     |      <strong>Overeenkomsten</strong>      |
|            Colou?r (?:black&#124;blue&#124;white)             |   Color black<br /><br /> Color white<br /><br /> Color red   | Ja<br /><br /> Ja<br /><br /> Nee |
|           [a-z0-9]{1,9}@[a-z0-9]{1,9}\\.[a-z]{2,3}            | Some1@abc.com<br /><br /> user@host.org<br /><br /> @bad.com  | Ja<br /><br /> Ja<br /><br /> Nee |
| 20\d{2}-(?:0[1-9]&#124;1[0-2])-(?:[0-2][0-9]&#124;30&#124;31) |   2015-12-31<br /><br /> 2015-01-09<br /><br /> 1999-12-31    | Ja<br /><br /> Ja<br /><br /> Nee |
|                       d.n't\s{0,10}c.r.                       | Don't     care<br /><br /> D!n'tcor0<br /><br /> Doesn't care | Ja<br /><br /> Ja<br /><br /> Nee |

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  

## <a name="check-out-this-video"></a>Bekijk deze video.
[Werken met de Regex-Engine](https://channel9.msdn.com/Shows/Microsoft-Security/Microsoft-Cloud-App-Security-Working-with-the-Regex-Engine)    