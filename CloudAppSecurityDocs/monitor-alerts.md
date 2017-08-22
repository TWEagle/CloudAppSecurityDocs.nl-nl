---
title: Werken met waarschuwingen in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u een lijst met alle waarschuwingen en de bijbehorende beschrijvingen.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/18/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: f118a3bf-1663-46ba-884f-b1b03a84ab66
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b5027699862a6cfe4b8dd8037f26d569b788a412
ms.sourcegitcommit: 27170447acfaeded585c264e425a46a485e7fb19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2017
---
# <a name="alerts"></a>Waarschuwingen
Ga als volgt te werk als u waarschuwingen wilt weergeven:

Klik in de Cloud App Security-portal op Waarschuwingen.


![Het menu Waarschuwing](./media/alert-menu.png)

Klik op de waarschuwing in de tabel voor het afhandelen van elke waarschuwing en selecteer een van de volgende opties:
- **Waarschuwing oplossen**: nadat u onderzoeken en acties om het risico van de waarschuwing te kunnen uitvoeren, klikt u op **waarschuwing oplossen**. U kunt een opmerking voor het opslaan van gegevens over uzelf over welke acties zijn uitgevoerd invoeren en kunt u ervoor kiezen **feedback verzenden naar de Cloud App Security-team** met betrekking tot de waarschuwing. Nadat u een waarschuwing dat deze niet meer wordt weergegeven in de tabel waarschuwingen oplossen.
- Waarschuwing oplossen en **markeren als gelezen**: U kunt de waarschuwing sluit maar Markeer deze als lezen.
- Waarschuwing oplossen en **aangepast beleid**: U kunt het beleid dat voor de waarschuwing in het antwoord op de waarschuwing wijzigen.
- **Negeren**: U kunt de waarschuwing die de waarschuwing wordt weergegeven in de tabel wordt gestopt, maar wordt niet weergegeven voor de waarschuwing als opgelost dat negeren. Dit wordt waarschijnlijk gebruikt wanneer de waarschuwing onschadelijk wordt of een fout-positief.

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
  
  