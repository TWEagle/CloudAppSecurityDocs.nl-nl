---
title: Beheren welke cloud-apps van derden machtigingen krijgen | Microsoft Docs
description: Dit artikel bevat informatie over hoe u machtigingen voor apps van derden kunt beheren, verbieden en toestaan.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 137e0630-5440-4c49-bfe4-48bbc64575e2
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b75e0c1cc4d91cfcbb8631170a0adfbde9349dee
ms.sourcegitcommit: b729e881851cdd8dc3f105ddbf6b4b907b8588dd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2017
---
# <a name="manage-app-permissions"></a>App-machtigingen beheren
Veel productiviteits-apps van derden die door gebruikers in uw organisatie worden geïnstalleerd, vragen om toestemming voor het krijgen van toegang tot gebruikersinformatie en -gegevens, en het namens de gebruiker aanmelden bij andere cloud-apps, zoals Office 365, G Suite en Salesforce.  Wanneer gebruikers deze apps installeren, klikken ze meestal op Accepteren zonder de details te lezen, zoals welke machtigingen ze de app verlenen.  Daar komt nog bij dat de IT-afdeling mogelijk te weinig inzicht heeft in de beveiligingsrisico's van een app, zodat ze geen goede afweging kunnen maken tussen die risico's en de productiviteitsvoordelen. Omdat het accepteren van app-machtigingen een mogelijk beveiligingsrisico inhoudt voor uw organisatie, is het belangrijk om de app-machtigingen die uw gebruikers verlenen te kunnen bewaken, zodat u de noodzakelijke zichtbaarheid en controle hebt om uw gebruikers en toepassingen te beschermen. Met App-machtigingen van Cloud App Security kunt u zien welke door de gebruikers geïnstalleerde toepassingen toegang hebben tot gegevens van Office 365, G Suite en Salesforce, welke machtigingen de apps hebben en welke gebruikers de apps hebben gemachtigd voor toegang tot hun Office 365-, G Suite- en Salesforce-account. Met app-machtigingen kunt u beslissen welke apps voor uw gebruikers zijn toegestaan en welke u wilt verbieden.


## <a name="working-with-the-app-permissions-page"></a>Werken met de pagina App-machtigingen

Op de pagina **App-machtigingen** wordt informatie weergegeven over app-machtigingen in uw verbonden apps.

U opent het tabblad App-machtigingen als volgt:

Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **App-machtigingen**.


 ![app-machtigingen](./media/app-permissions.png)

De pagina App-machtigingen biedt de volgende informatie over apps van derden waaraan machtigingen zijn verleend:

|Item|Wat het betekent|Van toepassing op|
|-------|-------|-------|
|Pictogram Basis in de querybalk van de app  |Selecteer dit om over te schakelen naar de basisweergave van de query.|Office 365, G Suite, Salesforce|
|Pictogram Geavanceerd in de querybalk van de app  |Selecteer dit om over te schakelen naar de geavanceerde weergave van de query.|Office 365, G Suite, Salesforce|
|Pictogram Alle details openen of sluiten in de lijst met apps  |Selecteer dit pictogram om meer of minder details over elke app weer te geven.|
|Pictogram Exporteren in de lijst met apps  |Selecteer dit pictogram om een CSV-bestand te exporteren met een lijst met apps, het aantal gebruikers van elke app, de machtigingen die zijn gekoppeld aan de app, het machtigingsniveau, de status van de app en het communitygebruik.|Office 365, G Suite, Salesforce|
|App|Naam van de app. Selecteer de naam voor meer informatie, met inbegrip van de beschrijving, de uitgever (voor Office 365), de website van de app en de-ID.|Office 365, G Suite, Salesforce|
|Geautoriseerd door|Het aantal gebruikers dat deze app heeft geautoriseerd voor toegang tot het account van hun app en machtigingen heeft verleend aan de app. Selecteer het aantal om meer informatie weer te geven, zoals een lijst met e-mailadressen van gebruikers en of een beheerder eerder goedkeuring heeft gegeven voor deze app.|Office 365, G Suite, Salesforce|
|Machtigingsniveau  |Het pictogram en de tekst geven een machtigingsniveau van Hoog, Gemiddeld of Laag aan. Dit niveau geeft aan welke toegang de app tot de app-gegevens heeft. Laag betekent bijvoorbeeld dat de app alleen toegang heeft tot het profiel en de naam van de gebruiker. Selecteer het niveau om meer informatie weer te geven, zoals de machtigingen die aan de app zijn verleend, het communitygebruik of gerelateerde activiteit in het [Beheerlogboek](governance-actions.md).|Office 365, G Suite|
|App-status|Een beheerder kan een app markeren als goedgekeurd, verboden of laten staan op onbepaald.|Office 365, G Suite, Salesforce|
|Gebruik van de community|Selecteer deze optie als u wilt weten hoe populair de app is bij al uw gebruikers (algemeen, niet gebruikelijk, zeldzaam)|Office 365, G Suite, Salesforce|
|Laatst geautoriseerd|De meest recente datum waarop een gebruiker een machtiging voor deze app heeft gekregen.|Office 365, Salesforce|
|Uitgever|De naam van de leverancier die de app levert.|Office 365|
|Laatst gebruikt|De meest recente datum waarop deze app door iemand in uw organisatie is gebruikt.|SalesForce|


## <a name="ban-or-approve-an-app"></a>Een app verbieden of goedkeuren
1. Klik op de pagina App-machtigingen op de app te openen van de App lade voor meer informatie over de app en de machtigingen die deze heeft gekregen. U kunt klikken op de koppeling Machtigingen voor een volledige lijst met machtigingen die aan de app zijn verleend. Onder Gebruik van community's kunt u zien in hoeverre de app wordt gebruikt bij andere organisaties. U kunt ook klikken op de koppeling Gerelateerde activiteiten om de activiteiten weer te geven die zijn vermeld in het beheerlogboek voor deze app.
2. Als u de app wilt verbieden, klikt u op het pictogram Verbieden aan het einde van de rij voor de app in de tabel. <br></br>
 ![pictogram app verbieden](./media/ban-app-icon.png) <br></br>
Wanneer u een app verbiedt, kunt u kiezen of u wilt dat de gebruikers die de app hebben geïnstalleerd en geautoriseerd, ervan op de hoogte worden gebracht dat de app is verboden en uitgeschakeld, en geen toegang heeft tot de verbonden app. Als u dat niet wilt, schakelt u de optie Gebruikers op de hoogte stellen die toegang hebben verleend tot deze verboden app in het dialoogvenster App verbieden uit.

    ![app verbieden](./media/ban-app.png)
> [!Note]
> Het is raadzaam om de gebruikers van de app te laten weten dan hun app wordt verboden.

3. Als u de app wilt goedkeuren, klikt u op het pictogram Goedkeuren aan het einde van rij voor de app in de tabel. <br></br>
 ![app goedkeuren](./media/approve-app.png) <br></br>
Het pictogram wordt groen en de app is goedgekeurd voor alle gebruikers van uw verbonden app.
> [!Note]
> Wanneer u een app markeert als goedgekeurd, heeft dat geen gevolgen voor de eindgebruikers. Het biedt alleen een visuele indicatie, zodat u gemakkelijk onderscheid kunt maken tussen de apps die u hebt goedgekeurd en de apps die u nog niet hebt geëvalueerd.

3. Typ het bericht dat u naar de gebruikers van de app wilt sturen in het vak Voer een aangepast meldingsbericht in en werk zo nodig het antwoordadres van de meldings-e-mail bij. 
 Klik op **App verbieden** om de e-mail te verzenden en de app te verbieden voor de gebruikers van uw verbonden app.

## <a name="revoke-app-and-notify-user"></a>De app intrekken en de gebruiker waarschuwen

Voor G Suite en Salesforce, is het mogelijk om in te trekken van de machtiging voor een app of op de hoogte van de gebruiker die dit moet wilt is gedaan. 

1. Op de pagina App-machtigingen op drie punten aan het einde van de rij van de app en selecteer **hoogte gebruiker**. Standaard de gebruiker een melding als volgt: *u de app Adallom Google beveiliging toegang tot uw account G Suite gemachtigd. Deze app is strijdig met het beveiligingsbeleid van uw organisatie. Andere geven of de machtigingen intrekken hebt u deze app in uw account G Suite gegeven. Als u wilt intrekken van toegang tot Apps, gaat u naar: https://security.google.com/settings/security/permissions?hl=en&pli=1 selecteert u de app en klik op 'Toegang intrekken' op de juiste menubalk.* U kunt het bericht dat is verzonden.
2. U kunt ook machtigingen voor het gebruik van de app voor de gebruiker door te klikken op het pictogram aan het einde van de app-rij in de tabel intrekken en het selecteren van **app intrekken**. 

 ![de app intrekken](./media/revoke-app.png)

## <a name="query-app-permissions"></a>App-machtigingen opvragen

U kunt app-machtigingen opvragen in de weergave **Standaard** of **Geavanceerd**. In de standaardweergave selecteert u waarden uit een of meer vervolgkeuzelijsten om de specifieke apps weer te geven. In de geavanceerde weergave kunt u de vervolgkeuzelijst **Een filter selecteren** gebruiken om uw zoekactie te beperken. U kunt operators en 'is gelijk aan' en 'is niet gelijk aan' toevoegen aan een geselecteerde waarde om uw query te voltooien.

- Kies het pictogram **Een filter toevoegen** om meer filters toe te voegen en uw query verder te verfijnen. De filters worden automatisch toegepast en de lijst met apps wordt bijgewerkt.

- Kies het pictogram **Een filter verwijderen** naast het filter om filters te verwijderen.


## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  