---
title: Beheeracties gebruiken om het gebruik van cloud-apps te beheren | Microsoft Docs
description: In dit artikel vindt u informatie over de beheeracties die u in Cloud App Security kunt uitvoeren om het gebruik van de cloud-apps in uw organisatie te beheren.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: bc11bbfe-ec6c-458c-8302-8112c383199d
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d312cca320a230323a29e3f98c38c3f694449590
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="control"></a>Beheer
U kunt beheeracties toepassen op gebruikersbestanden in uw cloudomgeving. Nadat u grondig onderzoek hebt gedaan en alles weet over uw cloud, kunt u beheeracties gebruiken om uw organisatie te beschermen.  

## <a name="use-policies-to-assess-risk"></a>Beleid gebruiken voor het beoordelen van risico  
Ga, nadat u uw openstaande waarschuwingen hebt bekeken, naar het Beleidscentrum om beleidsschendingen te bekijken waarvoor geen waarschuwing is geactiveerd.  

-   Klik in het Cloud App Security-dashboard op **Controle** en vervolgens op **Beleidsregels**.  

-   Selecteer een specifiek beleid om de lijst **Nu in overtreding** te zien met overeenkomsten met het beleid waarvoor geen waarschuwing is geactiveerd.  

-   Klik één voor één op de schendingen en bepaal bij elke schending wat u moet doen. Zie de onderstaande afbeeldingen voor meer informatie over beheeracties.  

     Als uw beleid is ingesteld op het vinden van nalevingsproblemen en iemand slaat creditcardnummers op in bestanden in OneDrive, dan hebt u een overeenkomst met het beleid.  

     ![PCI-overeenkomsten](./media/pci-matches.png "PCI-overeenkomsten")  

-   Selecteer de overeenkomst om de bestanden te zien die het beleid schenden.  

     ![PCI-inhoudsovereenkomsten](./media/pci-content-matches.png "PCI-inhoudsovereenkomsten")  

     U kunt het bestand zelf selecteren voor informatie over de bestanden.  

     U kunt op **Deelnemers** klikken om te zien wie toegang tot dit bestand heeft.  

     U kunt op **Overeenkomsten** klikken om de creditcardnummers zelf te zien.  

     ![Inhoudsovereenkomsten creditcardnummers](./media/content-matches-ccn.png "Inhoudsovereenkomsten creditcardnummers")  

## <a name="apply-governance-actions"></a>Beheeracties toepassen  
U kunt beheeracties toepassen vanuit beleidsregels, vanuit waarschuwingen en vanuit het **bestand**slogboek.  

U kunt op elk gewenst moment de status van alle eerder toegepaste beheeracties controleren en bekijken door naar het tandwiel **Instellingen** ![pictogram Instellingen](./media/settings-icon.png "pictogram Instellingen") te gaan en vervolgens **Beheerlogboek** te kiezen.  

Voor iedere mislukte beheeractie kiest u het pictogram **Opnieuw proberen** ![pictogram Opnieuw proberen](./media/retry-icon.png "pictogram Opnieuw proberen") om de actie opnieuw toe te passen.  

Er zijn verschillende beheeracties beschikbaar, afhankelijk van het soort beleid, overtreding of app.  

## <a name="move-from-detection-to-automatic-remediation"></a>Van detectie naar automatisch herstel  
Nadat u uw beleidsfilters hebt gedefinieerd en aangepast, kunt u geautomatiseerde beheeracties selecteren die worden uitgevoerd bij iedere schending van uw beleid.  
Aangezien herstelacties gebruikmaken van de API's van de cloudprovider, kunnen acties per app verschillen.  

> [!NOTE]  
>  Let goed op bij het instellen van beheeracties. Deze acties kunnen leiden tot onherstelbaar verlies van toegangsmachtigingen tot uw bestanden.  
> U wordt aangeraden de filters te verfijnen tot de precieze bestanden waarvoor u actie wilt ondernemen. Gebruik hiervoor meerdere zoekvelden. Hoe fijner de filters, hoe beter.  
>   
>  Als hulp kunt u de knop **Bewerken en voorbeeld van resultaten bekijken** in de sectie **Filters** gebruiken.  

![Bestandsbeleid bewerken en voorbeeld van resultaten](./media/file-policy-edit-and-preview-results.png "bestandsbeleid bewerken en voorbeeld van resultaten")  

## <a name="migration"></a>Migratie  
Cloud App Security helpt u bij de implementatie van uw migraties door u te laten weten wie welke apps gebruikt in uw organisatie en geeft u de hulpmiddelen om het gebruik van nieuwe apps te controleren. Zo kunt u achterhalen welke typen apps u moet aanbieden in uw organisatie, omdat u kunt zien wat iedereen al gebruikt.  

### <a name="migrate-your-users-to-a-new-app"></a>Uw gebruikers migreren naar een nieuwe app  
Stelt u zich eens voor: u hebt recentelijk Office 365 gekocht en uw wilt dat alle gebruikers in uw organisatie alleen OneDrive gebruiken voor cloudopslag. Dit is wat u mogelijk wilt doen:  

1. Ga naar uw **Clouddetectiedashboard** en filter onder **Categorieën** uw apps op **Cloudopslag**. Sorteer de resultaten op **gebruikers** of **IP-adressen**, en controleer welke app het meest wordt gebruikt.  

2. U kunt zien welke gebruikers andere apps gebruiken. U kunt ook op app-niveau kijken en gebruikers waarschuwen dat u ze wilt migreren naar OneDrive. Dit doet u als volgt:

   1.  Kies **Dropbox** in uw **Clouddetectiedashboard** en kies vervolgens het tabblad **IP-adres** of **Gebruikers**.  

   2.  Kies de pijl ![Pijlpictogram](./media/arrow-icon.png "pijlpictogram") en selecteer **Exporteren**.  

### <a name="find-more-secure-alternatives"></a>Veiligere alternatieven vinden  
In de servicecatalogus van Cloud App Security kunt u alternatieven vinden die veilig werken in uw organisatie in plaats van risicovolle apps die uw gebruikers mogelijk gebruiken.  

Stelt u zich eens voor: u wilt een productiviteitshulpprogramma aanschaffen maar weet niet zeker of uw gebruikers dit wel zouden gebruiken.  

1.   Ga naar uw **Clouddetectiedashboard**.  

2.   Filter onder **Categorieën** uw apps op **Productiviteit**.  

3.   Voor elke app die wordt gebruikt, bekijkt u de **score** om te zien of deze app veilig is en als dat niet het geval is, waarom niet.  

4.   Als u beslist dat u voor de hele organisatie een Enterprise-licentie wilt aanschaffen, kunt u ook naar de kolom **Gebruikers** kijken. Hier ziet u welke apps al populair zijn bij uw gebruikers, of deze apps worden vertrouwd en welke beveiligingsfuncties aanwezig zijn voordat u uw eigen beslissing neemt.  

## <a name="see-also"></a>Zie ook  
Zie [Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md) voor informatie over het gebruiken en instellen van het gebruik van cloud-apps.   

Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit [Premier Portal](https://premier.microsoft.com/) kiezen.  
