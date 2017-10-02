---
title: Beleidsregels voor anomaliedetectie maken in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u een beschrijving van beleidsregels voor anomaliedetectie en naslaginformatie over de bouwstenen van een beleid voor anomaliedetectie.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/24/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: ab9bc377-d2f5-4f4c-a419-f1728a15d1c7
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 5ffc6d748e8a4050a40cfadc81d5b2267eae934d
ms.sourcegitcommit: 8759541301241e03784c5ac87b56986f22bd0561
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2017
---
# <a name="anomaly-detection-policy"></a>Beleid voor afwijkingsdetectie
Dit artikel bevat een verwijzing naar meer informatie over beleidsregels en geeft uitleg over elk beleidstype en de velden die kunnen worden geconfigureerd voor elk beleid.  

Als uw organisatie wordt beveiligd door Cloud App Security, worden alle cloudactiviteiten beoordeeld volgens verschillende vooraf ingestelde risicofactoren. Cloud App Security analyseert elke gebruikerssessie in uw cloud en vergelijkt deze vervolgens met de risicofactoren die u hier instelt om u op de hoogte te stellen als er een activiteit plaatsvindt die afwijkt van de gebruikelijke activiteiten voor uw organisatie of van de gangbare gebruikersactiviteiten. De beleidspagina afwijkingsdetectie kunt u configureren en aanpassen welke families risicofactor worden meegenomen in het risicoanalyseproces. Het beleid kan anders worden afgedwongen voor verschillende gebruikers, locaties en organisatiesectoren. U kunt bijvoorbeeld een beleid instellen waarbij u geïnformeerd wordt als leden van uw IT-team buiten kantoor actief zijn.   

Cloud App Security heeft een initiële learning periode van zeven dagen waarover deze niet alle nieuwe gebruikers, de activiteit, de apparaten of de locaties als afwijkend markeren komt. Na deze periode wordt elke sessie vergeleken met de activiteiten, de tijd dat gebruikers actief waren, de IP-adressen, de apparaten, enzovoort die de afgelopen maand zijn gedetecteerd en wordt naar de risicoscore van deze activiteiten gekeken. Gebruik de schuifregelaar voor gevoeligheid in het beleid in te stellen van de minimale risicoscore waaruit worden waarschuwingen gegenereerd. Het wordt aanbevolen wanneer u een beleid voor afwijkingsdetectie maakt, gebruikt u de gevoeligheidsdrempelwaarde standaard voor een week, voordat u deze in overeenstemming met het aantal waarschuwingen die u hebt ontvangen, Cloud App Security verzendt u meer of minder waarschuwingen voor verschillende risico wanneer scores wijzigen u de gevoeligheid wijzigen.
  
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
  
    -   **Locatie**: Is er activiteit in een ongebruikelijke, verdachte of nieuwe locatie?  
  
    -   **Onmogelijke reis**: Is een gebruiker aangemeld vanuit Denver en 10 minuten later vanuit Parijs?  
  
    -   **Apparaat en gebruikersagent**: Is er activiteit vanuit een niet-herkend of niet-beheerd apparaat?  

    -   **Activiteitensnelheid**: Is er plotseling sprake van veel activiteiten in een specifieke app? Is er sprake van grote downloads of verwijderingen, of worden grote aantallen bestanden gedeeld of doen zich veel onverwachte beheeractiviteiten voor?
  
     U kunt deze parameters gebruiken voor het definiëren van complexe scenario's, bijvoorbeeld om het IP-adresbereik van uw kantoor uit te sluiten van de risicofactoren voor afwijkingsdetectie, om een 'kantoor-IP'-tag te maken en het bereik uit te sluiten van de ingestelde parameters. Het bereik dat u hebt gemaakt van de afwijkingsdectectie voor beheerdersaccounts vervolgens uitsluiten:  
  
    -   Onder **Risicotype** gaat u naar **Admin-activiteit**.  
  
    -   Wijzig **Van toepassing op** naar **Specifieke activiteiten**.  
  
    -   Onder **Activiteitfilters** stelt u **Van toepassing op** in op **Specifieke activiteiten** en onder **Activiteiten die overeenkomen met al het onderstaande** kiest u **Administratieve activiteiten** is **True**.  
  
    -   Klik op de **+** pictogram en selecteer **IP-tag is niet gelijk aan** en selecteer de kantoor-IP-tag.  
  
7.  Onder **Gevoeligheid**, selecteert u hoe vaak u waarschuwingen wilt ontvangen.  
  
     De gevoeligheidswaarde bepaalt hoeveel wekelijkse waarschuwingen gemiddeld per 1000 gebruikers worden geactiveerd.  
  
     ![anomaliedetectie-IP's](./media/anomaly-detection-ips.png "anomaliedetectie-IP's")  
  
8.  Klik op **Maken**.  
 

## <a name="anomaly-detection-policy-reference"></a>Beleidsverwijzing afwijkingsdetectie  
Een beleidsverwijzing afwijkingsdetectie kunt u instellen en configureren van doorlopende bewaking van Gebruikersactiviteit voor gedragsafwijkingen. Als u de gebruikersactiviteit scant, worden afwijkingen gedetecteerd. Het risico wordt geëvalueerd door meer dan 30 verschillende risico indicatoren, gegroepeerd in 6 risicofactoren te bekijken. Beveiligingswaarschuwingen worden op basis van de beleidsresultaten geactiveerd.   
Elk beleid bestaat uit de volgende onderdelen:  
  
-   Activiteitfilters – Hiermee kunt u uitsluitend gefilterde gebruikersactiviteit selectief op afwijkingen scannen.  
  
-   Risicofactoren – Hiermee kunt u kiezen welke risicofactoren u op wilt nemen in de risico-evaluatie.  
  
-   Gevoeligheid – Hiermee kunt u instellen hoeveel waarschuwingen het beleid moet activeren.  
  
### <a name="activity-filters"></a>Activiteitfilters  
Zie [hier beschrijving van koppeling invoeren](activity-filters.md) voor een lijst met activiteitfilters.  
  
### <a name="risk-factors"></a>Risicofactoren  
Hieronder volgt een lijst met de risicofactoren die bij het evalueren van het risico van gebruikersactiviteit worden beschouwd. Elke risicofactor kan aan of uit worden gezet. Voor elke risicofactor zijn er twee opties onder het **Toepassen op**-veld, die bepalen of deze in de risico-evaluatie van de gebruikersactiviteit worden opgenomen:  
  
-   Alle gecontroleerde activiteit – risicofactor opnemen voor alle gebruikersactiviteit die het beleidsactiviteitfilter wordt doorgegeven.  
  
-   Geselecteerde activiteit – risicofactor opnemen voor gebruikersactiviteit die zowel de beleidsfilters activiteit en de activiteitfilters die onder deze risicofactor verschijnen doorgegeven. Wanneer deze optie is geselecteerd wordt er een activiteitsfilterkiezer onder de risicofactor weergegeven, die precies hetzelfde werkt als het beleidsactiviteitfilter.  
  
Elke risicofactor die in de risico-evaluatie is opgenomen heeft zijn eigen triggers, die een toename in het geëvalueerde risico van gebruikersactiviteit veroorzaken.  
  
-   Aanmeldingsfouten – een groot aantal mislukte aanmeldingen of activiteiten die geheel bestaan uit aanmeldingsfouten.  
  
-   Beheerdersactiviteit - administratieve activiteit uitgevoerd door een onverwachte gebruiker of uitgevoerd vanuit een IP, ISP of locatie die nieuw zijn of niet gebruikt door een andere gebruiker in de organisatie.  
  
-   Inactieve accounts - activiteit uitgevoerd door een gebruiker die gedurende een lange periode niet actief was.  
  
-   Locatie - activiteit uitgevoerd vanuit een IP, ISP of locatie die zijn nooit gebruikt door een andere gebruiker, nooit door deze bepaalde gebruiker gebruikt, nooit gebruikt, of uitsluitend voor aanmeldingsfouten in het verleden is gebruikt.  
  
-   Onmogelijk traject - activiteit vanaf externe locaties binnen een korte periode.  
  
-   Apparaat en gebruikersagent - activiteit uitgevoerd door een gebruiker met behulp van een gebruikersagent of apparaat dat is nooit door een andere gebruiker gebruikt, nooit door deze bepaalde gebruiker worden gebruikt, of helemaal nooit is gebruikt.  
  
-   Frequentie van activiteit - herhaalde activiteiten uitgevoerd door een gebruiker binnen een korte periode. 

### <a name="sensitivity"></a>Gevoeligheid  
Er zijn twee manieren om het aantal waarschuwingen dat door het beleid is geactiveerd te bepalen:  
  
-   Schuifregelaar voor gevoeligheid: kies hoeveel waarschuwingen per 1000 gebruikers per week geactiveerd moeten worden. De waarschuwingen worden van de activiteiten met het hoogste risico geactiveerd.  
  
-   Dagelijks waarschuwingslimiet: beperk het aantal waarschuwingen dat op één dag worden gegeven.  
  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  
