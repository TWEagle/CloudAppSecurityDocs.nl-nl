---
title: Beleid voor anomaliedetectie | Microsoft Docs
description: In dit onderwerp vindt u een beschrijving van beleidsregels voor anomaliedetectie en naslaginformatie over de bouwstenen van een beleid voor anomaliedetectie.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/8/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: ab9bc377-d2f5-4f4c-a419-f1728a15d1c7
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 98b16c96c31039248bdfbe57f980b3ae6a26a7de
ms.openlocfilehash: a0d8975ae20830fe1b9d4ce3c1a54858038eebd3


---

# <a name="anomaly-detection-policy"></a>Beleid voor afwijkingsdetectie
Dit artikel bevat een verwijzing naar meer informatie over beleidsregels en geeft uitleg over elk beleidstype en de velden die kunnen worden geconfigureerd voor elk beleid.  
 
Cloud App Security heeft een initiële leerperiode van zeven dagen. Gedurende deze periode worden nieuwe gebruikers, activiteiten, apparaten of locaties niet als afwijkend gemarkeerd. Na deze periode wordt elke sessie vergeleken met de activiteiten, de tijd dat gebruikers actief waren, de IP-adressen, de apparaten, enzovoort die de afgelopen maand zijn gedetecteerd en wordt naar de risicoscore van deze activiteiten gekeken. U kunt de schuifregelaar voor gevoeligheid in het beleid gebruiken om de minimumrisicoscore in te stellen op basis waarvan waarschuwingen worden geactiveerd. U wordt aangeraden tijdens het maken van een anomaliebeleid gedurende een week de standaardgevoeligheidsdrempelwaarde te gebruiken voordat u de deze waarde wijzigt overeenkomstig het aantal waarschuwingen dat u hebt ontvangen. Wanneer u de gevoeligheid wijzigt, verzendt Cloud App Security meer of minder waarschuwingen voor verschillende risicoscores.
  
![Schuifregelaar voor gevoeligheid](./media/sensitivity-slider.png)
## <a name="anomaly-detection-policy-reference"></a>Beleidsverwijzing afwijkingsdetectie  
Met een beleidsverwijzing afwijkingsdetectie kunt u doorlopende controle van gebruikersactiviteit voor gedragsafwijkingen installeren en configureren.  Als u de gebruikersactiviteit scant, worden afwijkingen gedetecteerd. Het risico wordt geëvalueerd door meer dan 30 verschillende risico indicatoren, gegroepeerd in 6 risicofactoren te bekijken. Beveiligingswaarschuwingen worden op basis van de beleidsresultaten geactiveerd.   
Elk beleid bestaat uit de volgende onderdelen:  
  
-   Activiteitfilters – Hiermee kunt u uitsluitend gefilterde gebruikersactiviteit selectief op afwijkingen scannen.  
  
-   Risicofactoren – Hiermee kunt u kiezen welke risicofactoren u op wilt nemen in de risico-evaluatie.  
  
-   Gevoeligheid – Hiermee kunt u instellen hoeveel waarschuwingen het beleid moet activeren.  
  
### <a name="activity-filters"></a>Activiteitfilters  
Zie [hier beschrijving van koppeling invoeren](activity-filters.md) voor een lijst met activiteitfilters.  
  
### <a name="risk-factors"></a>Risicofactoren  
Hieronder ziet u een lijst met de risicofactoren die bij de risico-evaluatie van gebruikersactiviteit worden overwogen. Elke risicofactor kan aan of uit worden gezet. Voor elke risicofactor zijn er twee opties onder het **Toepassen op**-veld, die bepalen of deze in de risico-evaluatie van de gebruikersactiviteit worden opgenomen:  
  
-   Alle gecontroleerde activiteit – Risicofactor opnemen voor alle gebruikersactiviteit die het beleidsactiviteitfilter passeert.  
  
-   Geselecteerde activiteit – Risicofactor opnemen voor alle gebruikersactiviteit die zowel de beleidsactiviteitfilters als de activiteitfilters die onder deze risicofactor verschijnen passeert. Wanneer deze optie is geselecteerd wordt er een activiteitsfilterkiezer onder de risicofactor weergegeven, die precies hetzelfde werkt als het beleidsactiviteitfilter.  
  
Elke risicofactor die in de risico-evaluatie is opgenomen heeft zijn eigen triggers, die een toename in het geëvalueerde risico van gebruikersactiviteit veroorzaken.  
  
-   Aanmeldingsfouten – een groot aantal mislukte aanmeldingen of activiteiten die geheel bestaan uit aanmeldingsfouten.  
  
-   Beheerdersactiviteit - administratieve activiteit uitgevoerd door een onverwachte gebruiker of uitgevoerd vanaf een IP, ISP of een locatie die nieuw is, of niet gebruikt door een andere gebruiker in de organisatie.  
  
-   Inactieve accounts - activiteit uitgevoerd door een gebruiker die gedurende een lange periode niet actief was.  
  
-   Locatie - activiteit vanaf een IP, ISP of locatie die of nooit door een andere gebruiker is gebruikt, nooit door deze bepaalde gebruiker, helemaal nooit, of uitsluitend voor aanmeldingsfouten in het verleden is gebruikt.  
  
-   Onmogelijk traject - activiteit vanaf externe locaties binnen een korte periode.  
  
-   Apparaat en gebruikersagent - activiteit uitgevoerd door een gebruiker met behulp van een gebruikersagent of apparaat dat of nooit door een andere gebruiker is gebruikt, nooit door deze bepaalde gebruiker is gebruikt, of helemaal nooit is gebruikt.  
  
-   Frequentie van activiteit - herhaalde activiteiten uitgevoerd door een gebruiker binnen een korte periode. 

### <a name="sensitivity"></a>Gevoeligheid  
Er zijn twee manieren om het aantal waarschuwingen dat door het beleid is geactiveerd te bepalen:  
  
-   Schuifregelaar voor gevoeligheid: kies hoeveel waarschuwingen per 1000 gebruikers per week geactiveerd moeten worden. De waarschuwingen van de activiteiten met het hoogste risico worden verzonden.  
  
-   Dagelijks waarschuwingslimiet: beperk het aantal waarschuwingen dat op één dag worden gegeven.  
  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  



<!--HONumber=Jan17_HO2-->


