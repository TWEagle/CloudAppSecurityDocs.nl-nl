---
title: Beleidsregels voor Cloud Discovery-apps maken in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u informatie over het werken met beleidsregels voor Cloud Discovery.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 45446111-ed1a-4699-9df5-840cc6664a6b
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 055929af068e07430f011e254e0c16dd8101907c
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="cloud-discovery-policies"></a>Beleidsregels voor Cloud Discovery
    
## <a name="creating-an-app-discovery-policy"></a>Beleid voor appdetectie aanmaken  
Beleidsregels voor appdetectie bieden u de mogelijkheid om waarschuwingen in te stellen zodat u op de hoogte bent wanneer er binnen uw organisatie nieuwe apps gedetecteerd worden.  
  
1.  Klik in de console op **Beheer** gevolgd door **Beleidsregels**.  
  
2.  Klik op **beleid maken** en selecteer **beleid voor appdetectie**.  
  
     ![menu beleid voor app-detectie](./media/app-discovery-policy-menu.png "menu beleid voor app-detectie")  
  
3.  Geef uw beleid een naam en beschrijving, wat u indien gewenst kunt baseren op een sjabloon. Voor meer informatie over beleidssjablonen, bekijk [Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md).  
  
4.  Stel de **ernst** van het beleid.

5. Om in te stellen welke gedetecteerde apps dit beleid geactiveerd, kunt u filters toevoegen.  
  
6.  U kunt een drempelwaarde voor gevoeligheid het beleid moet instellen. Na het inschakelen van de **een overeenkomst beleid activeren als alle volgende op dezelfde dag vallen**, kunt u instellen dat een minimum voor de **aantal gebruikers**, **nummer van de IP-adressen**, **Dagelijkse verkeer**, **gedownloade gegevens**, **gegevens geüpload**, en **aantal transacties** die de app moet voldoen om overeen te de het beleid.  
  
7.  Stel een **dagelijkse waarschuwingslimiet** en selecteer of de waarschuwing wordt verzonden als een e-mailbericht of als een SMS-bericht of beide en geef indien nodig gegevens. U kunt klikken op Standaardwaarden waarschuwingsinstellingen opslaan om het mogelijk te maken voor toekomstig beleid om deze waarschuwingsinstellingen op te slaan als de standaardwaarden, waaronder telefoonnummer en e-mailadressen.  
  
8. Selecteer mogelijk **Governance** acties toe te passen wanneer een app overeenkomt met dit beleid. Het label kan automatisch beleid als **Sanctioned** of **Unsanctioned** 

8.  Klik op **Maken**.  
  
Bijvoorbeeld, als u geïnteresseerd bent in het detecteren van riskante hostapps in uw cloudomgeving, stelt u uw beleid als volgt in:  
  
Stel de beleidsfilters in om services te detecteren die zijn gevonden in de categorie **hostingservices** en die een lage score hebben, wat aangeeft dat ze riskant zijn.   
   
Stel de drempelwaarden die moeten worden geactiveerd door een waarschuwing voor een bepaalde gedetecteerde app - alleen als meer dan 100 gebruikers in de omgeving de app gebruikt, en alleen als ze een bepaalde hoeveelheid gegevens hebt gedownload van de service aan de onderkant.   
Daarnaast kunt u de dagelijkse waarschuwingslimiet instellen.  
  
![voorbeeld van beleid voor app-detectie](./media/app-discovery-policy-example.png "voorbeeld van beleid voor app-detectie")  
  
## <a name="cloud-discovery-anomaly-detection"></a>Afwijkingsdetectie voor Cloud Discovery  
Cloud App Security doorzoekt alle logboeken in uw Cloud Discovery-exemplaar op afwijkingen. Voorbeelden zijn wanneer een gebruiker die nog nooit gebruik heeft gemaakt van Dropbox, plotseling 600 GB uploadt naar Dropbox, of wanneer er veel meer transacties worden uitgevoerd dan gebruikelijk in een bepaalde app. Het beleid voor anomaliedetectie is standaard ingeschakeld. Er hoeft dus geen nieuw beleid geconfigureerd te worden, maar u kunt instellen voor welke afwijkingstypen u gewaarschuwd wilt worden in het standaardbeleid.  
  
1.  Klik in de console op **Beheer** gevolgd door **Beleidsregels**.  
  
2.  Klik op **Beleid maken** en selecteer **Afwijkingsdetectiebeleid Cloud Discovery**.  
  
     ![menu voor beleid voor anomaliedetectie voor cloud discovery](./media/cloud-discovery-anomaly-detection-policy-menu.png "menu voor beleid voor anomaliedetectie voor cloud discovery")  
  
3.  Geef uw beleid een naam en beschrijving, wat u indien gewenst kunt baseren op een sjabloon. Voor meer informatie over beleidssjablonen, bekijk [Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md).  
  
4.  Om in te stellen welke gedetecteerde apps dit beleid geactiveerd, klikt u op **filters toevoegen**.  
  
     De filters worden gekozen vanaf de linkerkant van de pagina van het pop-filter. Het is mogelijk te filteren op servicenaam, domein, risicofactor, risicoscore, en categorie. Aan de rechterkant van de pagina toont de resultaten voor de gekozen filters uit de huidige Servicecatalogus. Sla de filters op nadat u ze hebt geselecteerd en controleer of de juiste labels worden weergegeven in de filters.  
  
5.  Kies onder **Toepassen voor** of dit van toepassing is voor **alle gegevensweergaven** of **specifieke gegevensweergaven** en of dit van toepassing is op **gebruikers**, **IP-adressen** of beide.  
  
6.  Selecteer de datums gedurende welke de afwijkende activiteit heeft plaatsgevonden voor het activeren van de waarschuwing onder **Waarschuwingen alleen genereren voor verdachte activiteiten na datum.**  
  
7.  Onder **Waarschuwingen** kunt u de gevoeligheid voor anomaliedetectie instellen van laag tot hoog om de waarschuwingsfrequentie te configureren.  
Stel een **dagelijkse waarschuwingslimiet** en selecteer of de waarschuwing wordt verzonden als een e-mailbericht of als een SMS-bericht of beide en geef indien nodig gegevens. U kunt klikken op Standaardwaarden waarschuwingsinstellingen opslaan om het mogelijk te maken voor toekomstig beleid om deze waarschuwingsinstellingen op te slaan als de standaardwaarden, waaronder telefoonnummer en e-mailadressen. U kunt ook klikken op **Standaardinstellingen organisatie gebruiken** deze instellingen in te stellen op basis van de standaard voor uw organisatie.  
  
9. Klik op **Maken**.  
  
![nieuw beleid voor anomaliedetectie](./media/new-discovery-anomaly-policy.png "nieuw beleid voor anomaliedetectie")  
  
## <a name="see-also"></a>Zie ook  
[Beleidsregels voor gebruikersactiviteit](user-activity-policies.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  