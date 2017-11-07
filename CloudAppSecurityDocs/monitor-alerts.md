---
title: Werken met waarschuwingen in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u een lijst met alle waarschuwingen en de bijbehorende beschrijvingen.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: f118a3bf-1663-46ba-884f-b1b03a84ab66
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 6d2d677ef91a22a4489c4709a84742410d991899
ms.sourcegitcommit: b729e881851cdd8dc3f105ddbf6b4b907b8588dd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2017
---
# <a name="alerts"></a>Waarschuwingen
Ga als volgt te werk als u waarschuwingen wilt weergeven:

Klik in de Cloud App Security-portal op Waarschuwingen.


![Het menu Waarschuwing](./media/alert-menu.png)

Nadat u een waarschuwing bekijkt en is geen interessante, kunt u **sluiten** deze. U kunt een opmerking om uit te leggen waarom u de waarschuwing gesloten en u kunt invoeren **feedback verzenden naar de Cloud App Security-team**. Deze feedback wordt gecontroleerd door onze beveiligingsteam research voortdurend het mechanisme voor waarschuwingen te verbeteren. 

Als u de waarschuwing onderzoeken en de kans vermindert, kunt u deze vervolgens **los** de waarschuwing. De waarschuwing wordt niet meer weergegeven in de tabel waarschuwingen. Als u onderzoeken een probleem hebt gestart, maar u controleren of u wilt wilt doorgaan, kunt u onthouden **markeren als ongelezen**. U kunt ook **aanpassen van het beleid** die overeenkomen met de waarschuwing om toekomstige waarschuwing overeenkomsten imrpove. Het omzetten van een waarschuwing biedt u eveneens de optie een opmerking invoeren en **feedback verzenden naar de Cloud App Security-team**.



De volgende typen waarschuwingen worden weergegeven. 

## <a name="built-in-alerts"></a>Ingebouwde waarschuwingen

|Naam van waarschuwing|Waarschuwings-id|Beschrijving|
|----|----|----|
|Nieuwe locatie|ALERT_GEOLOCATION_NEW_COUNTRY|Sinds het begin van de scan (maximaal zes maanden) is een nieuwe locatie gedetecteerd. Deze waarschuwing wordt eenmaal weergegeven voor elk land in uw hele organisatie. |
|Nieuwe gebruiker met beheerdersrechten|ALERT_ADMIN_USER|Voor een specifieke app is een nieuwe beheerder gedetecteerd. Dit kan een persoon zijn die beheerder is in een bepaalde toepassing en nu beheerder is voor een andere toepassing. Deze waarschuwing heeft betrekking op een specifiek beheerderstype. Dit betekent dat telkens wanneer het beheerderstype wordt gewijzigd, de waarschuwing wordt weergegeven. Als een gebruiker zijn of haar beheerdersbevoegdheden is kwijtgeraakt en deze vervolgens opnieuw worden toegewezen, wordt deze waarschuwing weergegeven.|
|Inactieve account|ALERT_ZOMBIE_USER|Een gebruiker is inactief als deze gedurende 60 dagen inactief is in een toepassing. Als iemand bijvoorbeeld actief is in Box, maar al 60 dagen inactief is in G Suite, wordt de gebruiker als inactief beschouwd in G Suite. Er wordt een tag toegevoegd aan deze gebruikers, zodat u kunt zoeken naar inactieve accounts.|
|Onverwachte beheerderslocatie|ALERT_NEW_ADMIN_LOCATION|Sinds het begin van de scan (maximaal zes maanden) is een nieuwe locatie voor beheerders gedetecteerd. Deze waarschuwing wordt eenmaal weergegeven voor elk land en voor elke beheerder in uw hele organisatie. |
|Verdacht account|ALERT_COMPROMISED_ACCOUNT|Als er sprake is van een inbreuk op een toepassing en de lijst met geschonden accounts wordt gepubliceerd, wordt de lijst met Cloud App Security gedownload en vergeleken met uw lijst met gebruikers (waaronder interne gebruikers, externe gebruikers en persoonlijke accounts). |

## <a name="custom-alerts"></a>Aangepaste waarschuwingen

|Naam van waarschuwing|Waarschuwings-id|Beschrijving|
|----|----|----|
|Waarschuwing verdachte activiteit|ALERT_SUSPICIOUS_ACTIVITY|Verdachte activiteiten worden beoordeeld op basis van hoe verdacht de afwijkende activiteit is (bijvoorbeeld: is er een inactief account bij betrokken? Is de activiteit afkomstig van een nieuwe locatie?). Deze criteria worden samen beoordeeld, waarna een risicoscore wordt berekend op basis van de volgende risicofactoren: <br>Gebruiker is beheerder <br>Alleen externe gebruikers<br>Anonieme proxy<br> Aanmeldingspogingen van de hele sessie zijn mislukt<br>Groot aantal mislukte aanmeldingspogingen<br>Nieuw (beheerder)<br>IP/ISP/land/gebruikersagent voor gebruiker/tenant<br> IP/ISP/land/gebruikersagent alleen gebruikt door gebruiker (met beheerdersrechten)<br>Eerste activiteit van gebruiker (met beheerdersrechten) sinds langere tijd<br>Eerste keer sinds langere tijd dat deze specifieke beheeractiviteit is uitgevoerd<br>Deze specifieke beheeractiviteit is niet gebruikelijk of niet eerder uitgevoerd<br>Voor dit IP bestaan alleen mislukte aanmeldingspogingen in het verleden<br>Onmogelijk traject|
|Waarschuwing verdacht gebruik van de cloud|ALERT_DISCOVERY_ANOMALY_DETECTION|Met de anomaliedetectie van Cloud Discovery wordt het patroon van normaal gedrag gecontroleerd en wordt gekeken naar gebruikers en apps die op een ongebruikelijke manier worden gebruikt. |
|Schending van activiteitenbeleid|ALERT_CABINET_EVENT_MATCH_AUDIT|Met deze waarschuwing wordt aangegeven dat er een beleidsovereenkomst is gedetecteerd.|
|Schending van bestandsbeleid|ALERT_CABINET_EVENT_MATCH_FILE|Met deze waarschuwing wordt aangegeven dat er een beleidsovereenkomst is gedetecteerd.|
|Schending van proxybeleid|ALERT_CABINET_INLINE_EVENT_MATCH|Met deze waarschuwing wordt aangegeven dat er een beleidsovereenkomst is gedetecteerd.|
|Schending van veldbeleid|ALERT_CABINET_EVENT_MATCH_OBJECT|Met deze waarschuwing wordt aangegeven dat er een beleidsovereenkomst is gedetecteerd.|
|Nieuwe gedetecteerde service|ALERT_CABINET_DISCOVERY_NEW_SERVICE|Er is een nieuwe app gedetecteerd.|
|Gebruik van persoonlijk account|ALERT_PERSONAL_USER_SAGE|De detectie-engine zoekt naar persoonlijke accounts op basis van bestandsshares en gebruikersnamen. |

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  