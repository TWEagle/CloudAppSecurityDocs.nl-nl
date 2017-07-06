---
title: Waarschuwingen beheren die zijn geactiveerd in de portal van Cloud App Security | Microsoft Docs
description: Dit artikel bevat informatie over het werken met waarschuwingen die zijn geactiveerd in de portal van Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/23/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 1b1dbcc6-472f-43ea-af59-2aa926e3e5a9
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c4134370302fe8d35e6a3e2232d6ff8a65ad96f6
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2017
---
## <a name="manage-your-alerts"></a>De waarschuwingen beheren  
Waarschuwingen zijn het uitgangspunt van waaruit u meer inzicht in uw cloudomgeving krijgt. Mogelijk wilt u nieuwe beleidsregels maken naar aanleiding van uw bevindingen. U ziet bijvoorbeeld dat een beheerder is aangemeld vanuit Groenland en er heeft zich nog nooit iemand aangemeld vanuit Groenland binnen uw organisatie. U kunt een beleid maken waarmee een beheerdersaccount automatisch tijdelijk wordt ingetrokken als dit wordt gebruikt voor aanmelding vanaf die locatie.  

Het is een goed idee alle waarschuwingen te bekijken en ze als hulpmiddel te gebruiken om uw beleid aan te passen. Als een onschuldige gebeurtenis wordt beschouwd als een schending van het bestaande beleid, moet u uw beleid verfijnen zodat u minder onnodige waarschuwingen ontvangt.  

1.   Klik onder **Waarschuwingen openen** op **Alle waarschuwingen bekijken**.  

     Dit gedeelte van het dashboard biedt volledige zichtbaarheid van alle verdachte activiteiten of schendingen van de ingestelde beleidsregels. Vervolgens kunt u hiermee de beveiliging verbeteren die u voor uw cloudomgeving hebt gedefinieerd.  

     ![Waarschuwingen](./media/alerts.png "waarschuwingen")  

2.   Bij elke waarschuwing dient u de aard van de schending te onderzoeken en de vereiste actie te bepalen.  

     U kunt de waarschuwingen filteren op type waarschuwing of ernst, zodat u de belangrijkste het eerst kunt verwerken.  

     Selecteer een specifieke waarschuwing. Afhankelijk van het type waarschuwing krijgt u verschillende acties te zien die kunnen worden uitgevoerd voordat de waarschuwing wordt opgelost.  

     U heeft te maken met drie soorten schendingen wanneer u waarschuwingen onderzoekt:  

    #### <a name="serious-violations"></a>Ernstige schendingen
     Voor ernstige schendingen is onmiddellijke actie nodig.

         Examples:  

         For a suspicious activity alert, you might want to suspend the account until the user changes their password.  

         For a data leak you might want to restrict permissions or quarantine the file.  

         If a new app is discovered, you might want to block access to the service on your proxy or firewall.  

    #### <a name="questionable-violations"></a>Verdachte schendingen
    Verdachte schendingen moeten verder worden onderzocht.  

         You can contact the  user or the user's manager about the nature of the activity.  

         Leave the activity open until you have more information.  

 #### <a name="authorized-violations-or-anomalous-behavior"></a>Geautoriseerde schendingen of afwijkend gedrag
 Geautoriseerde schendingen of afwijkend gedrag kunnen het resultaat zijn van legitiem gebruik.  

         Dismiss the alert.  

3.   Markeer de waarschuwing als opgelost wanneer u klaar bent.  

De volgende tabel geeft een lijst van de typen waarschuwingen die kunnen worden geactiveerd en de aanbevolen manier om ze op te lossen.  

|Waarschuwingstype|Beschrijving|Aanbevolen oplossing|  
|----------------|-----------------|----------------------------|  
|Schending van activiteitenbeleid|Dit type waarschuwing is het resultaat van een beleid dat u hebt gemaakt.|Als u groepsgewijs met dit type waarschuwingen wilt werken, wordt u aangeraden in het beleidscentrum te werken om deze te verhelpen.<br /><br /> Verfijn het beleid om ruisentiteiten uit te sluiten door meer filters en gedetailleerdere besturingselementen toe te voegen.<br /><br /> Als het beleid nauwkeurig is, de waarschuwing gerechtvaardigd was en het een schending is die u onmiddellijk wilt stoppen, kunt u overwegen automatisch herstel aan het beleid toe te voegen.|  
|Schending van bestandsbeleid|Dit type waarschuwing is het resultaat van een beleid dat u hebt gemaakt.| Als u groepsgewijs met dit type waarschuwingen wilt werken, wordt u aangeraden in het beleidscentrum te werken om deze te verhelpen.<br /><br /> Verfijn het beleid om ruisentiteiten uit te sluiten door meer filters en gedetailleerdere besturingselementen toe te voegen.<br /><br /> Als het beleid nauwkeurig is, de waarschuwing gerechtvaardigd was en het een schending is die u onmiddellijk wilt stoppen, kunt u overwegen automatisch herstel aan het beleid toe te voegen.|  
|Verdacht account|Dit type waarschuwing wordt geactiveerd wanneer Cloud App Security een account identificeert dat is aangetast, wat inhoudt dat de kans zeer groot is dat het account op niet-toegestane wijze is gebruikt.|U wordt aangeraden het account te blokkeren totdat u de gebruiker kunt bereiken en ervoor kunt zorgen dat deze zijn of haar wachtwoord wijzigt.|  
|Inactieve account|Deze waarschuwing wordt geactiveerd wanneer een account 60 dagen lang niet is gebruikt in een van de verbonden cloud-apps.|Neem contact op met de gebruiker en de manager van de gebruiker om te bepalen of het account nog steeds actief is. Als dat niet het geval is, blokkeer dan de gebruiker en beëindig de licentie voor de app.|  
|Nieuwe gebruiker met beheerdersrechten|Hiermee wordt u gewaarschuwd voor wijzigingen in uw beschermde accounts voor verbonden apps.|Bevestig dat de nieuwe beheerdersmachtigingen vereist zijn voor de gebruiker. Als dit niet het geval is, kunt de beheerdersbevoegdheden het beste intrekken om beveiligingsrisico's te beperken.|  
|Nieuwe locatie beheerder|Hiermee wordt u gewaarschuwd voor wijzigingen in uw beschermde accounts voor verbonden apps.|Bevestig dat de aanmelding vanaf deze afwijkende locatie is toegestaan. Als dit niet het geval is, kunt de beheerdersbevoegdheden het beste intrekken of het account tijdelijk intrekken om beveiligingsrisico's te beperken.|  
|Nieuwe locatie|Dit is een informatieve waarschuwing over de toegang tot een verbonden app vanaf een nieuwe locatie, die slechts één keer per land wordt geactiveerd.|Onderzoek de activiteit van de specifieke gebruiker.|  
|Nieuwe gedetecteerde service|Dit is een waarschuwing over Shadow IT - er is een nieuwe app gedetecteerd door Cloud Discovery.|<ul><li>Bepaal het risico van de service op basis van de app-catalogus.</li><li>Zoom in op de activiteit om inzicht te krijgen in gebruikspatronen en invloed.</li><li>Bepaal of u de app wel of niet wilt toestaan.</li><br /></ul>Voor niet-toegestane apps:<br /><br /><ul><li>U kunt het gebruik blokkeren in uw proxy of firewall.</li><li>Als de app niet is goedgekeurd en u een goedgekeurde app in dezelfde categorie hebt, kunt u een lijst met gebruikers van de niet-goedgekeurde app exporteren en vervolgens contact met hen opnemen om ze naar de goedgekeurde app te migreren.</li></ul></li>|  
|Verdachte activiteiten|Deze waarschuwing laat u weten dat er afwijkende activiteit is aangetroffen die niet overeenkomt met de verwachte activiteiten of gebruikers in uw organisatie.|Onderzoek het gedrag en bevestig het met de gebruiker.<br /><br /> Dit type waarschuwing is een goed uitgangspunt om meer over uw omgeving te weten te komen en nieuwe beleidsregels te maken met deze waarschuwingen. Als iemand bijvoorbeeld plotseling een grote hoeveelheid gegevens naar een van uw verbonden apps uploadt, kunt u een regel instellen voor dat type afwijkend gedrag.|  
|Verdacht cloudgebruik|Deze waarschuwing laat u weten dat er afwijkende activiteit is aangetroffen die niet overeenkomt met de verwachte activiteiten of gebruikers in uw organisatie.|Onderzoek het gedrag en bevestig het met de gebruiker.<br /><br /> Dit type waarschuwing is een goed uitgangspunt om meer over uw omgeving te weten te komen en nieuwe beleidsregels te maken met deze waarschuwingen. Als iemand bijvoorbeeld plotseling een grote hoeveelheid gegevens naar een van uw verbonden apps uploadt, kunt u een regel instellen voor dat type afwijkend gedrag.|  
|Gebruik van persoonlijk account|Deze waarschuwing laat u weten dat een nieuw persoonlijk account toegang heeft tot bronnen in uw verbonden apps.|Verwijder de samenwerkingen van de gebruiker in het externe account.|  


## <a name="next-steps"></a>Volgende stappen  
Zie [Onderzoeken](investigate.md) voor meer informatie over het onderzoeken van waarschuwingen.  
Ga naar de [ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit [Premier Portal](https://premier.microsoft.com/) kiezen.  
