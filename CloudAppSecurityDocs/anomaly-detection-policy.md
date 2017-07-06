---
title: Beleidsregels voor anomaliedetectie maken in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u een beschrijving van beleidsregels voor anomaliedetectie en naslaginformatie over de bouwstenen van een beleid voor anomaliedetectie.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/19/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: ab9bc377-d2f5-4f4c-a419-f1728a15d1c7
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d6c1851b1903159d40c0daa256fbb28bdb1268bd
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2017
---
# <a name="anomaly-detection-policy"></a>Beleid voor afwijkingsdetectie
Dit artikel bevat een verwijzing naar meer informatie over beleidsregels en geeft uitleg over elk beleidstype en de velden die kunnen worden geconfigureerd voor elk beleid.  

Als uw organisatie wordt beveiligd door Cloud App Security, worden alle cloudactiviteiten beoordeeld volgens verschillende vooraf ingestelde risicofactoren. Cloud App Security analyseert elke gebruikerssessie in uw cloud en vergelijkt deze vervolgens met de risicofactoren die u hier instelt om u op de hoogte te stellen als er een activiteit plaatsvindt die afwijkt van de gebruikelijke activiteiten voor uw organisatie of van de gangbare gebruikersactiviteiten. De beleidspagina afwijkingsdetectie laat u de risicofactoren instellen en aanpassen die meegenomen worden in het risicoanalyseproces. Het beleid kan anders worden afgedwongen voor verschillende gebruikers, locaties en organisatiesectoren. U kunt bijvoorbeeld een beleid instellen waarbij u geïnformeerd wordt als leden van uw IT-team buiten kantoor actief zijn.   

Cloud App Security heeft een initiële leerperiode van zeven dagen. Gedurende deze periode worden nieuwe gebruikers, activiteiten, apparaten of locaties niet als afwijkend gemarkeerd. Na deze periode wordt elke sessie vergeleken met de activiteiten, de tijd dat gebruikers actief waren, de IP-adressen, de apparaten, enzovoort die de afgelopen maand zijn gedetecteerd en wordt naar de risicoscore van deze activiteiten gekeken. U kunt de schuifregelaar voor gevoeligheid in het beleid gebruiken om de minimumrisicoscore in te stellen op basis waarvan waarschuwingen worden geactiveerd. U wordt aangeraden tijdens het maken van een anomaliebeleid gedurende een week de standaardgevoeligheidsdrempelwaarde te gebruiken voordat u de deze waarde wijzigt overeenkomstig het aantal waarschuwingen dat u hebt ontvangen. Wanneer u de gevoeligheid wijzigt, verzendt Cloud App Security meer of minder waarschuwingen voor verschillende risicoscores.
  
![Schuifregelaar voor gevoeligheid](./media/sensitivity-slider.png)

Een afwijkingsdetectiebeleid configureren:  
  
1.  Klik in de console op **Beheer** gevolgd door **Beleidsregels**.  
  
2.  Klik op **Beleid maken** en selecteer **Afwijkingsdetectie**beleid.  
  
     ![menu voor beleid voor anomaliedetectie](./media/anomaly-detection-policy-menu.png "menu voor beleid voor anomaliedetectie")  
  
3.  Vul de naam en beschrijving van het beleid in en ga naar het veld **Activiteitfilters** om de activiteit te kiezen waarop het beleid van toepassing moet zijn.  
  
4.  Geef uw beleid een naam en beschrijving, wat u indien gewenst kunt baseren op een sjabloon. Voor meer informatie over beleidssjablonen, bekijk [Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md).  
  
5.  Om het beleid van toepassing te laten zijn op alle activiteiten in uw cloudomgeving, selecteert u **Alle gevolgde activiteiten**. Als u het beleid tot specifieke typen activiteit wilt beperken, kiest u **Specifieke activiteiten**. Klik op **Filters toevoegen** en stel de juiste parameters in waarmee u de activiteit wilt filteren. Bijvoorbeeld, als u het beleid alleen op de activiteiten uitgevoerd door Salesforce-beheerders wilt toepassen, kiest u deze gebruikerstag.  
  
6.  In dit veld stelt u de **Risicofactoren** in. U kunt kiezen welke risicogroepen u wilt meenemen in de berekening van de risicoscore. Aan de rechterkant van de rij kunt u de aan/uit-knop en de verschillende risico's uitschakelen. Daarnaast kunt u, voor een grotere mate van granulatie, de activiteit kiezen die voor elke specifieke risicogroep ingesteld moet worden.  
  
     We hanteren de volgende risicofactoren:  
  
    -   **Aanmeldfouten**: proberen gebruikers zich aan te melden en mislukt dit meerdere malen in een korte tijdsspanne?  
  
    -   **Beheerdersactiviteit**: Gebruiken beheerders hun beheerdersaccounts om in te loggen vanaf ongebruikelijke locaties of op vreemde tijden?  
  
    -   **Inactieve accounts**: Is er plotseling activiteit op een account dat al enige tijd niet meer in gebruik is?  
  
    -   **Locatie**: Is er activiteit afkomstig uit een ongebruikelijke, verdachte of nieuwe locatie?  
  
    -   **Onmogelijk traject**: Is een gebruiker aangemeld vanuit Denver en tien minuten later vanuit Parijs?  
  
    -   **Apparaat en gebruikersagent**: Is er activiteit vanuit een niet-herkend of niet-beheerd apparaat?  

    -   **Activiteitensnelheid**: Is er plotseling sprake van veel activiteiten in een specifieke app? Is er sprake van grote downloads of verwijderingen, of worden grote aantallen bestanden gedeeld of doen zich veel onverwachte beheeractiviteiten voor?
  
     U kunt deze parameters gebruiken voor het definiëren van complexe scenario's, bijvoorbeeld om het IP-adresbereik van uw kantoor uit te sluiten van de risicofactoren voor afwijkingsdetectie, om een 'kantoor-IP'-tag te maken en het bereik uit te sluiten van de ingestelde parameters. Om het bereik dat u hebt gemaakt uit te sluiten van de afwijkingsdectectie voor beheerdersaccounts:  
  
    -   Onder **Risicotype** gaat u naar **Admin-activiteit**.  
  
    -   Wijzig **Van toepassing op** naar **Specifieke activiteiten**.  
  
    -   Onder **Activiteitfilters** stelt u **Van toepassing op** in op **Specifieke activiteiten** en onder **Activiteiten die overeenkomen met al het onderstaande** kiest u **Administratieve activiteiten** is **True**.  
  
    -   Klik op de **+** pictogram en selecteer **IP-tag is niet gelijk aan** en selecteer de kantoor-IP-tag.  
  
7.  Onder **Gevoeligheid**, selecteert u hoe vaak u waarschuwingen wilt ontvangen.  
  
     De gevoeligheidswaarde bepaalt per 1000 gebruikers hoeveel waarschuwingen er wekelijks gemiddeld geactiveerd worden.  
  
     ![anomaliedetectie-IP's](./media/anomaly-detection-ips.png "anomaliedetectie-IP's")  
  
8.  Klik op **Maken**.  
 

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
  
  
