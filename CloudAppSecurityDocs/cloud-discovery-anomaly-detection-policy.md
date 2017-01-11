---
title: Beleid voor anomaliedetectie voor Cloud Discovery | Microsoft Docs
description: In dit onderwerp vindt u informatie over hoe u in Cloud Discovery met beleidsregels voor anomaliedetectie kunt werken.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 12/21/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: eaf73af0-7610-4903-b656-8d90b1d2b18c
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3c78f9b9eca0c88256951ba5e58b656b6d5b14ab
ms.openlocfilehash: 1bbf3b0b6c36cb7b29826efc598a66a41a53b3e2


---

# <a name="cloud-discovery-anomaly-detection-policy"></a>Beleid voor afwijkingsdetectie voor Cloud Discovery
Dit artikel bevat een verwijzing naar meer informatie over beleidsregels en geeft uitleg over elk beleidstype en de velden die kunnen worden geconfigureerd voor elk beleid.  
  
## <a name="cloud-discovery-anomaly-detection-policy-reference"></a>Beleidsverwijzing afwijkingsdetectie van de cloud  
Met een beleidsregel van de afwijkingsdetectie van de cloud kunt u continue monitoring van ongebruikelijke stijgingen in het gebruik van cloudtoepassingen instellen en configureren. Voor elke cloudtoepassing wordt de toename in gedownloade data, geüploade data, het aantal transacties en het aantal gebruikers in beschouwing genomen. Elke toename wordt vergeleken met het normale gebruikspatroon van de toepassing, zoals vastgesteld op basis van eerder gebruik. Bij zeer sterke toenamen wordt er een beveiligingswaarschuwing geactiveerd.  
  
U kunt voor elk beleid filters instellen die u de mogelijkheid bieden om het gebruik van toepassingen selectief te bewaken, gebaseerd op een toepassingsfilter, geselecteerde gegevensweergaven en een geselecteerde begindatum. U kunt ook de gevoeligheid instellen om op te geven hoeveel waarschuwingen het beleid moet activeren.  

Stel voor elk beleid het volgende in:

1. Beslis of u het beleid wilt baseren op een sjabloon. Een relevante beleidssjabloon is de sjabloon **Afwijkend gedrag in gedetecteerde gebruikers** die waarschuwt als afwijkend gedrag wordt gedetecteerd in gevonden gebruikers en apps, zoals grote hoeveelheden geüploade gegevens in vergelijking met andere gebruikers of grote gebruikerstransacties vergeleken met de geschiedenis van de gebruiker. U kunt ook de sjabloon **Afwijkend gedrag van gedetecteerde IP-adressen** selecteren. Met deze sjabloon wordt gewaarschuwd als afwijkend gedrag wordt gedetecteerd in gevonden IP-adressen en apps, zoals grote hoeveelheden geüploade gegevens in vergelijking met andere IP-adressen, grote app-transacties in vergelijking met de geschiedenis van het IP-adres. 
 
2. Geef een **beleidsnaam** en **beschrijving** op.  

3. Maak een filter voor de apps die u wilt controleren, door op **Filter toevoegen** te klikken. U kunt een specifieke app of een **categorie** apps selecteren of u kunt filteren op een **naam**, **domein** en **risicofactor** en op **Opslaan** klikken.

4. Stel onder **Toepassen op** in hoe het gebruik moet worden gefilterd. Het gebruik dat wordt bewaakt kan op twee manieren worden gefilterd:  
  
    -   Doorlopende rapporten: geef aan of u **alle doorlopende rapporten** (standaard) of **specifieke doorlopende rapporten** wilt controleren.  
  
        -   Als u voor **alle doorlopende rapporten** kiest, wordt elke gebruikstoename vergeleken met het normale gebruikspatroon zoals vastgesteld uit alle gegevensweergaven.  
  
        -   Als u voor **specifieke doorlopende rapporten** kiest,wordt elke gebruikstoename vergeleken met het normale gebruikspatroon zoals vastgesteld uit dezelfde gegevensweergave als waarin deze toename is geobserveerd.  
  
    -   **Gebruikers en IP-adressen**: elk toepassingsgebruik van de cloud is gekoppeld aan een gebruiker, een IP-adres of beide.  
  
        -   Door **Gebruikers** te selecteren, wordt koppeling van toepassingsgebruik met IP-adressen genegeerd, indien deze aanwezig is.  
  
        -   Door **IP-adressen** te selecteren, wordt koppeling van toepassingsgebruik met gebruikers genegeerd, indien deze aanwezig is.  
  
        -   Door **Gebruikers en IP-adressen** (standaard) te selecteren, worden beide koppelingen in beschouwing genomen, maar kunnen er dubbele waarschuwingen worden gegeven indien er een sterke overeenkomst is tussen gebruikers en IP-adressen.
    -   Alleen waarschuwingen activeren voor verdachte activiteiten die zich voordoen na een bepaalde datum: een toename van het toepassingsgebruik voor de geselecteerde datum wordt genegeerd. Activiteiten voor de geselecteerde datum worden echter gebruikt om het normale gebruikspatroon vast te stellen.  
  
5. U kunt onder **Waarschuwingen** de gevoeligheid van waarschuwingen instellen. U kunt het aantal waarschuwingen dat door het beleid wordt geactiveerd, op enkele manieren bepalen:  
  
    -   De schuifregelaar **Select anomaly detection sensitivity** (Gevoeligheid voor anomaliedetectie selecteren) waarschuwt voor de belangrijkste X afwijkende activiteiten per 1000 gebruikers per week. De waarschuwingen worden geactiveerd voor de activiteiten met het hoogste risico.  
  
    -   **Dagelijkse waarschuwingslimiet**: beperk het aantal waarschuwingen dat op één dag wordt gegeven. U kunt ervoor kiezen **waarschuwingen te verzenden als e-mail**, **waarschuwingen te verzenden als sms-bericht, of beide**. Sms-berichten worden beperkt tot tien per dag voor de UTC-tijdzone, wat betekent dat de limiet van tien berichten opnieuw wordt ingesteld om 12 uur 's nachts in de UTC-tijdzone.

    - U kunt er ook voor kiezen de **standaardinstellingen van uw organisatie te gebruiken**. Dan worden de **daglimiet voor waarschuwingen** en de e-mail- en sms-instellingen ingevuld vanuit de standaardinstellingen van uw organisatie. Geef de standaardinstellingen op door de instellingen voor **Alert configuration** (Waarschuwingsconfiguratie) in te vullen en vervolgens op **Save these alert settings as the default for your organization** (Deze waarschuwingsinstellingen als standaard voor uw organisatie opslaan) te klikken.

6. Klik op **Maken**.

7. Net als bij elk ander beleid kunt u het beleid **bewerken**, **uitschakelen** en **inschakelen** door op de drie punten aan het einde van de rij op de pagina **Beleid** te klikken. Nadat u een nieuw beleid hebt gemaakt, is dat standaard ingeschakeld.

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Dec16_HO4-->


