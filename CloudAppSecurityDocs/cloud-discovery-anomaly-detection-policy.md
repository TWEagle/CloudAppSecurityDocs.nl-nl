---
title: Beleid voor anomaliedetectie voor Cloud Discovery | Microsoft Docs
description: In dit onderwerp vindt u informatie over hoe u in Cloud Discovery met beleidsregels voor anomaliedetectie kunt werken.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: eaf73af0-7610-4903-b656-8d90b1d2b18c
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 481ca3d68e5e7aea006eeff443ec521a374e6e11


---

# <a name="cloud-discovery-anomaly-detection-policy"></a>Beleid voor afwijkingsdetectie voor Cloud Discovery
Dit artikel bevat een verwijzing naar meer informatie over beleidsregels en geeft uitleg over elk beleidstype en de velden die kunnen worden geconfigureerd voor elk beleid.  
  
## <a name="cloud-discovery-anomaly-detection-policy-reference"></a>Beleidsverwijzing afwijkingsdetectie van de cloud  
Met een beleidsregel van de afwijkingsdetectie van de cloud kunt u continue monitoring van ongebruikelijke stijgingen in het gebruik van cloudtoepassingen instellen en configureren. Voor elke cloudtoepassing wordt de toename in gedownloade data, geüploade data, het aantal transacties en het aantal gebruikers in beschouwing genomen. Elke toename wordt vergeleken met het normale gebruikspatroon van de toepassing, zoals vastgesteld op basis van eerder gebruik. Bij zeer sterke toenamen wordt er een beveiligingswaarschuwing geactiveerd.  
  
Elk beleid bestaat uit de volgende onderdelen:  
  
-   Filters: bieden u de mogelijkheid om het gebruik van toepassingen selectief te bewaken, gebaseerd op een toepassingenfilter, geselecteerde dataweergaven en een geselecteerde startdatum.  
  
-   Gevoeligheid: hiermee kunt u instellen hoeveel waarschuwingen het beleid moet activeren.  
  
### <a name="activity-filters"></a>Activiteitfilters  
Zie [activiteitfilters](activity-filters.md), voor een lijst van activiteitfilters.  
  
### <a name="apply-to"></a>Van toepassing op  
Het gebruik dat wordt bewaakt kan op twee manieren worden gefilterd:  
  
-   Dataweergaven: selecteer of u standaard alle dataweergaven wilt bewaken of kies specifieke dataweergaven om te bewaken.  
  
    -   Indien u **Alle dataweergaven** selecteert, wordt elke toename vergeleken met het normale gebruikspatroon zoals vastgesteld uit alle dataweergaven.  
  
    -   Indien u specifieke dataweergaven selecteert, wordt elke toename vergeleken met het normale gebruikspatroon zoals vastgesteld uit dezelfde dataweergaven als waarin deze geobserveerd was.  
  
-   Gebruikers en IP-adressen: elke toepassingsgebruik van de cloud is gekoppeld aan een gebruiker, een IP-adres of beide.  
  
    -   Door **Gebruikers** te selecteren, wordt koppeling van toepassingsgebruik met IP-adressen genegeerd, indien deze aanwezig is.  
  
    -   Door **IP-adressen** te selecteren, wordt koppeling van toepassingsgebruik met gebruikers genegeerd, indien deze aanwezig is.  
  
    -   Door **Gebruikers en IP-adressen** te selecteren, worden beide koppelingen in beschouwing genomen, maar kunnen er dubbele waarschuwingen worden gegeven indien er een sterke overeenkomst is tussen gebruikers en IP-adressen.  
  
De waarschuwing wordt alleen gegeven voor verdachte activiteiten die zich voordoen na de datum. Een toename van toepassingsgebruik voor de geselecteerde datum wordt genegeerd. Activiteiten voor de geselecteerde datum worden echter gebruikt om het normale gebruikspatroon vast te stellen.  
  
### <a name="sensitivity"></a>Gevoeligheid  
Er zijn twee manieren om het aantal waarschuwingen dat door het beleid is geactiveerd te bepalen:  
  
-   Schuifregelaar voor gevoeligheid: kies hoeveel waarschuwingen per 1000 gebruikers per week geactiveerd moeten worden. De waarschuwingen van de activiteiten met het hoogste risico worden verzonden.  
  
-   Dagelijks waarschuwingslimiet: beperk het aantal waarschuwingen dat op één dag worden gegeven.  
  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


