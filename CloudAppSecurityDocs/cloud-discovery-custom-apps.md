---
title: Aangepaste apps toevoegen aan Cloud Discovery in de Cloud App Security | Microsoft Docs
description: Dit onderwerp bevat informatie over het toevoegen van aangepaste apps aan Cloud Discovery in de Cloud App Security Shadow IT bewaken.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/27/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 98b0d841-b33d-4ae9-b48b-d9ee77785eaa
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: fd484e86f9caf4b9fd5a27f0f6c3f3f0f622488f
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="add-custom-apps-to-cloud-discovery"></a>Aangepaste apps toevoegen aan Cloud Discovery
    
Cloud Discovery analyseert uw verkeerslogboeken tegen Microsoft Cloud App Security van cloud app-catalogus van meer dan 15.000 cloud-apps. De catalogus bevat alleen openbaar cloud-apps waarvoor Cloud App Security zichtbaarheid en risico-informatie biedt.

Om meer inzicht verkrijgen in cloud-apps die zijn uitgesloten van de catalogus met Cloud-App, kunt Cloud App Security u gebruik van aangepaste cloud-apps (LOB-apps) die zijn ontwikkeld of toegewezen specifiek voor uw organisatie te detecteren.

Door een nieuwe aangepaste cloud-app toe te voegen Cloud App Security kan overeenkomen met geüploade firewall en proxy-verkeer Leg berichten vast in de app en geeft u inzicht in het gebruik van deze app in uw organisatie in de Cloud Discovery-pagina's, zoals hoeveel gebruikers t gebruiken hij app, hoeveel unieke bron-IP-adressen gebruiken en hoeveel verkeer wordt verzonden naar en van de app. 

Een nieuwe aangepaste cloud-app toevoegen:

1. Klik in de Cloud App Security-portal op **Discover** en vervolgens **Cloud Discovery-dashboard**. 
  
   ![cloud discovery-dashboard menu](./media/cloud-discovery-dashboard-menu.png)

2. Klik op de 3 punten in de rechterbovenhoek, en selecteer vervolgens **nieuwe aangepaste app toevoegen**. 

   ![menu aangepaste app toevoegen](./media/add-custom-app-menu.png)

3. Vul de velden voor het definiëren van de nieuwe record voor de app die wordt weergegeven in de catalogus met Cloud-App en in de Cloud Discovery nadat deze is gedetecteerd in de logboeken van uw firewall.

   ![aangepaste app](./media/add-custom-app.png)

4. Onder **domeinen**, vult u de unieke domeinen die worden gebruikt bij het openen van de aangepaste app. Deze domeinen worden gebruikt om overeen met de logboekberichten verkeer naar deze app. Als de gegevensbron die u gebruikt geen informatie over app-URL bevat, zorg ervoor dat u de **IPv4** en **IPv6** adresvelden.
5. Het is raadzaam opmerkingen waarmee u kunt het bijhouden van wijzigingen voor deze record toevoegen.

Nadat de app is gemaakt, is het voor u beschikbaar zijn in de catalogus met Cloud-App.

U kunt op elk gewenst moment de 3 punten aan het einde van de rij bewerken of verwijderen van een aangepaste app klikken.

>[!NOTE]
> - Aangepaste apps automatisch worden gemarkeerd met de **aangepaste app** tag nadat u deze hebt toegevoegd. Deze app-code kan niet worden verwijderd.
Instellen als u wilt weergeven van uw aangepaste apps, de **App tag** niet gelijk zijn aan de aangepaste-app-filter. 
> - Standaard, aangepaste apps een risicoscore van 10 hebben, maar u kunt de **overschrijven app score** actie kan op elk moment wijzigen.

  
## <a name="see-also"></a>Zie ook  
[Beleidsregels voor gebruikersactiviteit](user-activity-policies.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  