---
title: De RegEx-engine gebruiken voor beleidsregels voor inhoudscontrole | Microsoft Docs
description: In dit onderwerp vindt u instructies voor het gebruik van RegEx voor jokertekens in de beleidsregels van Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/12/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: dc8b87e5-e6c1-4a65-ab8c-067fb527fce4
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c386cbbdadaf97297e6d876cdac9f7d3e2142b73
ms.sourcegitcommit: b840b945b270e616560f565bcc6590dd68ad5ebd
translationtype: HT
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
  
||||  
|-|-|-|  
|**Reguliere expressie**|**Gegevens**|**Overeenkomsten**|  
|Colou?r (?:black&#124;blue&#124;white)|Color black<br /><br /> Color white<br /><br /> Color red|Ja<br /><br /> Ja<br /><br /> Nee|  
|[a-z0-9]{1,9}@[a-z0-9]{1,9}\\.[a-z]{2,3}|Some1@abc.com<br /><br /> user@host.org<br /><br /> @bad.com|Ja<br /><br /> Ja<br /><br /> Nee|  
|20\d{2}-(?:0[1-9]&#124;1[0-2])-(?:[0-2][0-9]&#124;30&#124;31)|2015-12-31<br /><br /> 2015-01-09<br /><br /> 1999-12-31|Ja<br /><br /> Ja<br /><br /> Nee|  
|d.n't\s{0,10}c.r.|Don't     care<br /><br /> D!n'tcor0<br /><br /> Doesn't care|Ja<br /><br /> Ja<br /><br /> Nee|  
 

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  