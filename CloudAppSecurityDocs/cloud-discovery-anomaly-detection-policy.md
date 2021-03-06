---
title: Beleid voor anomaliedetectie voor Cloud Discovery maken in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u informatie over hoe u in Cloud Discovery met beleidsregels voor anomaliedetectie kunt werken.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: eaf73af0-7610-4903-b656-8d90b1d2b18c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 5491f56d8164cbd69b66a647016667739ad5cc06
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="cloud-discovery-anomaly-detection-policy"></a>Beleid voor afwijkingsdetectie voor Cloud Discovery
Dit artikel bevat een verwijzing naar meer informatie over beleidsregels en geeft uitleg over elk beleidstype en de velden die kunnen worden geconfigureerd voor elk beleid.  
  
## <a name="cloud-discovery-anomaly-detection-policy-reference"></a>Beleidsverwijzing afwijkingsdetectie van de cloud  
Een beleidsverwijzing afwijkingsdetectie voor Cloud discovery kunt u instellen en configureren met continue monitoring van ongebruikelijke stijgingen in het gebruik van cloud-toepassingen. Voor elke cloudtoepassing wordt de toename in gedownloade data, geüploade data, het aantal transacties en het aantal gebruikers in beschouwing genomen. Elke toename wordt vergeleken met het normale gebruikspatroon van de toepassing, zoals vastgesteld op basis van eerder gebruik. Bij zeer sterke toenamen wordt er een beveiligingswaarschuwing geactiveerd.  
  
U kunt voor elk beleid filters instellen die u de mogelijkheid bieden om het gebruik van toepassingen selectief te bewaken, gebaseerd op een toepassingsfilter, geselecteerde gegevensweergaven en een geselecteerde begindatum. U kunt ook de gevoeligheid instellen om op te geven hoeveel waarschuwingen het beleid moet activeren.  

Voor elk beleid moet u de volgende parameters instellen:

1. Bepaal of u het beleid te baseren op een sjabloon wilt, relevante beleidssjablonen zijn de **afwijkend gedrag in gedetecteerde gebruikers** sjabloon die u waarschuwt wanneer afwijkend gedrag is gedetecteerd in de gedetecteerde gebruikers en apps, zoals: groot hoeveelheid geüploade gegevens vergeleken met andere gebruikers, grote gebruikerstransacties vergeleken met de geschiedenis van de gebruiker. U kunt ook de sjabloon **Afwijkend gedrag van gedetecteerde IP-adressen** selecteren. Met deze sjabloon wordt gewaarschuwd als afwijkend gedrag wordt gedetecteerd in gevonden IP-adressen en apps, zoals grote hoeveelheden geüploade gegevens in vergelijking met andere IP-adressen, grote app-transacties in vergelijking met de geschiedenis van het IP-adres. 
 
2. Geef een **beleidsnaam** en **beschrijving** op.  

3. Maak een filter voor de apps die u wilt controleren, door op <strong>Filter toevoegen</strong> te klikken. 
   U kunt een specifieke app, een app selecteren <strong>categorie</strong>, of filteren op <strong>naam</strong>, <strong>domein, en ** risicofactor</strong>, en klik op <strong>opslaan</strong>.

4. Stel onder **Toepassen op** in hoe het gebruik moet worden gefilterd. Het gebruik dat wordt bewaakt kan op twee manieren worden gefilterd:  
  
    -   Doorlopende rapporten: geef aan of u **alle doorlopende rapporten** (standaard) of **specifieke doorlopende rapporten** wilt controleren.  
  
        -   Als u voor **alle doorlopende rapporten** kiest, wordt elke gebruikstoename vergeleken met het normale gebruikspatroon zoals vastgesteld uit alle gegevensweergaven.  
  
        -   Als u voor **specifieke doorlopende rapporten** kiest,wordt elke gebruikstoename vergeleken met het normale gebruikspatroon zoals vastgesteld uit dezelfde gegevensweergave als waarin deze toename is geobserveerd.  
  
    -   **Gebruikers en IP-adressen**: elk toepassingsgebruik van de cloud is gekoppeld aan een gebruiker, een IP-adres of beide.  
  
        -   Selecteren **gebruikers** worden de koppeling van toepassingsgebruik met IP-adressen genegeerd, indien deze aanwezig is.  
  
        -   Selecteren **IP-adressen** worden de koppeling van toepassingsgebruik met gebruikers genegeerd, indien deze aanwezig is.  
  
        -   Selecteren **gebruikers en IP-adressen** (standaard) beschouwt beide koppelingen, maar kunnen er dubbele waarschuwingen wanneer er een sterke overeenkomst is tussen gebruikers en IP-adressen.
    -   Activeren van waarschuwingen alleen voor verdachte activiteiten na datum – een toename van toepassingsgebruik voordat de geselecteerde datum wordt genegeerd. Activiteiten voor de geselecteerde datum is echter geleerd om het normale gebruikspatroon vast te stellen.  
  
5. Onder **waarschuwingen**, kunt u de waarschuwing gevoeligheid instellen. U kunt het aantal waarschuwingen dat door het beleid wordt geactiveerd, op enkele manieren bepalen:  
  
    -   De schuifregelaar **Select anomaly detection sensitivity** (Gevoeligheid voor anomaliedetectie selecteren) waarschuwt voor de belangrijkste X afwijkende activiteiten per 1000 gebruikers per week. De waarschuwingen worden gegenereerd voor de activiteiten met het hoogste risico.  
  
    -   **Dagelijkse waarschuwingslimiet**: beperk het aantal waarschuwingen dat op één dag wordt gegeven. U kunt ervoor kiezen **waarschuwingen te verzenden als e-mail**, **waarschuwingen te verzenden als sms-bericht, of beide**. Berichten die door de SMS-bericht verzonden zijn beperkt tot 10 per dag voor de UTC-tijdzone, wat betekent dat de limiet van 10 bericht wordt opnieuw ingesteld op middernacht in de UTC-tijdzone.

    - U kunt er ook voor kiezen de **standaardinstellingen van uw organisatie te gebruiken**. Dan worden de **daglimiet voor waarschuwingen** en de e-mail- en sms-instellingen ingevuld vanuit de standaardinstellingen van uw organisatie. Geef de standaardinstellingen op door de instellingen voor **Alert configuration** (Waarschuwingsconfiguratie) in te vullen en vervolgens op **Save these alert settings as the default for your organization** (Deze waarschuwingsinstellingen als standaard voor uw organisatie opslaan) te klikken.

6. Klik op **Maken**.

7. Zoals met alle beleidsregels, u kunt **bewerken**, **uitschakelen**, en **inschakelen** het beleid door te klikken op de drie punten aan het einde van de rij in de **beleid**pagina. Nadat u een nieuw beleid hebt gemaakt, is dat standaard ingeschakeld.

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  