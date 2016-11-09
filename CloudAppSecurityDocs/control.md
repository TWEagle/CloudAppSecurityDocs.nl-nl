---
title: Beheer | Microsoft Docs
description: In dit artikel vindt u informatie over de beheeracties die u in Cloud App Security kunt uitvoeren om het gebruik van de cloud-apps in uw organisatie te beheren.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: bc11bbfe-ec6c-458c-8302-8112c383199d
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 9dc74c35f32c9a3dff251d6e0ac6b35a3591f4b9


---

# <a name="control"></a>Beheer
Beheeracties kunnen worden toegepast op gebruikersbestanden in uw cloudomgeving. Nadat u grondig onderzoek hebt gedaan en alles weet over uw cloud, kunt u beheeracties gebruiken om uw organisatie te beschermen.  
  
## <a name="applying-governance-actions"></a>Beheeracties toepassen  
Beheeracties kunnen worden toegepast vanuit beleidsregels, vanuit waarschuwingen en vanuit het **bestand**slogboek.  
  
Op elk gewenst moment kunt u de status van alle eerder toegepaste beheeracties controleren en bekijken door naar het tandwiel **Instellingen** ![pictogram Instellingen](./media/settings-icon.png "settings icon") te gaan en vervolgens te klikken op **Beheerlogboek**.  
  
Voor iedere mislukte beheeractie klikt u op het pictogram Opnieuw ![Pictogram Opnieuw](./media/retry-icon.png "retry icon") om de actie opnieuw toe te passen.  
  
Er zijn verschillende beheeracties beschikbaar, afhankelijk van het soort beleid, overtreding of app.  
  
## <a name="moving-from-detection-to-automatic-remediation"></a>Van detectie naar automatisch herstel  
Na het definiëren en aanpassen van uw beleidsfilters, kunt u geautomatiseerde beheeracties selecteren die worden uitgevoerd bij iedere overtreding van uw beleid.  
Aangezien herstelacties gebruikmaken van de API’s van de cloudprovider, kunnen acties per app verschillen.  
  
> [!NOTE]  
>  Let goed op bij het instellen van beheeracties, want ze kunnen leiden tot onherstelbaar verlies van toegangsmachtigingen tot uw bestanden.  
> We bevelen aan om de filters te verfijnen tot de precieze bestanden waarbij actie moet worden ondernomen. Gebruik hiervoor meerdere zoekvelden. Hoe fijner de filters, hoe beter.  
>   
>  Als hulp kunt u de knop **Bewerken en voorbeeld van resultaten bekijken** in de sectie Filters gebruiken.  
  
![Bestandsbeleid bewerken en voorbeeld van de resultaten bekijken](./media/file-policy-edit-and-preview-results.png "file policy edit and preview results")  
  
## <a name="migration"></a>Migratie  
Cloud App Security helpt u bij de implementatie van uw migraties door u te laten weten wie welke apps gebruikt in uw organisatie en geeft u de hulpmiddelen om het gebruik van nieuwe apps te controleren. Zo kunt u achterhalen welke typen apps u moet aanbieden in uw organisatie, omdat u kunt zien wat iedereen al gebruikt.  
  
### <a name="how-to-migrate-your-users-to-a-new-app"></a>Uw gebruikers migreren naar een nieuwe app  
Stelt u zich eens voor: U hebt recentelijk Office 365 gekocht en uw wilt dat alle gebruikers in uw organisatie alleen OneDrive gebruiken voor cloudopslag. Dit is wat u mogelijk wilt doen:  
  
-   Ga naar uw **Clouddetectiedashboard** en filter onder **Categorieën** uw apps op **Cloudopslag**. Sorteer de resultaten op **gebruikers** of **IP-adressen**, en controleer welke app het meest wordt gebruikt.  
  
-   U kunt zien welke gebruikers andere apps gebruiken.  
  
     U kunt ook op app-niveau kijken en gebruikers waarschuwen dat u ze wilt migreren naar OneDrive. Dit doet u als volgt:  
  
    1.  Klik in uw **Clouddetectiedashboard** op Dropbox op en klik vervolgens op het tabblad **IP-adres** of **Gebruikers**.  
  
    2.  Klik op de pijl ![pijlpictogram](./media/arrow-icon.png "arrow icon") en selecteer **Exporteren**.  
  
### <a name="find-more-secure-alternatives"></a>Veiligere alternatieven vinden  
In de servicecatalogus van Cloud App Security kunt u alternatieven vinden die veilig werken in uw organisatie in plaats van risicovolle apps die uw gebruikers mogelijk gebruiken.  
  
Stelt u zich eens voor: U wilt een productiviteitstool aanschaffen maar weet niet zeker of uw gebruikers deze tool wel zouden gebruiken.  
  
-   Ga naar uw **Clouddetectiedashboard**.  
  
-   Filter onder **Categorieën** uw apps op **Productiviteit**.  
  
-   Voor elke app die wordt gebruikt, bekijkt u de **Score** om te zien of deze app veilig is en als dat niet het geval is, waarom niet.  
  
-   Als u bepaalt dat u een bedrijfslicentie wilt aanschaffen voor de hele organisatie, kunt u ook in de kolom **Gebruikers** kijken om te zien welke app populair is onder uw gebruikers, of deze vertrouwd is en welke beveiligingsfuncties het heeft, voordat u uw keuze maakt.  
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


