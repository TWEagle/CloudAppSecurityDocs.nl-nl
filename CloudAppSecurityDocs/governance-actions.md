---
title: Beheerlogboek | Microsoft Docs
description: In dit onderwerp vindt u een overzicht en een beschrijving van alle beheeracties die in Cloud App Security kunnen worden uitgevoerd.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 3536c0a5-fa56-4931-9534-cc7cc4b4dfb0
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 052ca8e20e75fcae7687d17687d7dd1a645ae5e6


---

# <a name="governance-log"></a>Beheerlogboek
Het beheerlogboek biedt een statusrecord voor elke taak die met Cloud App Security moet worden uitgevoerd, waaronder zowel handmatige als automatische taken. Deze taken omvatten taken die u in beleidsregels instelt, beheeracties die u voor bestanden en gebruikers instelt en andere acties die met Cloud App Security moeten worden uitgevoerd. Het beheerlogboek bevat ook informatie over het slagen of mislukken van deze acties. U kunt bepaalde beheeracties in het beheerlogboek opnieuw uitvoeren of ongedaan maken. 

Hieronder vindt u de volledige lijst met acties die u via de Cloud App Security-portal kunt uitvoeren. Deze worden ingeschakeld op verschillende locaties in de console, zoals aangegeven in de kolom **Locatie**. Elke uitgevoerde beheeractie wordt vermeld in het beheerlogboek.
Zie het Engelstalige artikel [Policy Conflicts](control-cloud-apps-with-policies.md) (Beleidsconflicten) voor meer informatie over hoe de beheeracties worden behandeld in het geval van beleidsconflicten. 

**Locatie**|**Doelobjecttype**|**Beheeractie**|**Beschrijving**|**Verwante connectors** 
---------|---------|---------|---------|---------
|Bestandsbeleid|Bestand|Beperken tot uitsluitend de medewerkers|Hiermee hebben alleen benoemde medewerkers toegang tot het bestand.|Box|
|Instellingen > Cloud Discovery-instellingen |Cloud Discovery|Cloud Discovery-scores opnieuw berekenen|Hiermee worden de scores in de catalogus met cloud-apps opnieuw berekend nadat de metrische gegevens voor de score zijn gewijzigd.|Detectie|
|Instellingen > Cloud Discovery-instellingen > Gegevensweergaven beheren|Cloud Discovery|Een aangepaste Cloud Discovery-filtergegevensweergave maken|Hiermee wordt een nieuwe gegevensweergave gemaakt voor een meer gedetailleerd overzicht van de detectieresultaten. Bijvoorbeeld een weergave met specifieke IP-bereiken.|Detectie|
|Detecteren > Gedetecteerde apps/IP-adressen/gebruikers|Cloud Discovery|Detectiegegevens exporteren|Hiermee wordt een CSV-gemaakt van de detectiegegevens.|Detectie|
|Instellingen > Cloud Discovery-instellingen > Gegevens verwijderen|Cloud Discovery|Cloud Discovery-gegevens verwijderen|Hiermee worden alle gegevens verwijderd die worden verzameld vanuit detectiebronnen.|Detectie|
|Instellingen > Cloud Discovery-instellingen > Logboeken handmatig uploaden/Logboeken automatisch uploaden|Cloud Discovery|Cloud Discovery-gegevens parseren|Melding dat alle logboekgegevens zijn geparseerd.|Detectie|
|Onderzoeken > Bestanden en Bestandsbeleid|Bestand|Leesmachtiging verlenen voor domein|Hiermee worden leesmachtigingen voor het bestand verleend aan het opgegeven domein voor uw hele domein of een specifiek domein. Dit is handig als u openbare toegang wilt verwijderen nadat u toegang hebt verleend aan het domein van mensen die eraan moeten werken.|Google Apps|
|Onderzoeken > Bestanden|Bestand|Leesmachtiging verlenen aan mijzelf|Hiermee worden leesmachtigingen voor het bestand verleend aan uzelf, zodat u toegang hebt tot het bestand en overtredingen kunt zien.|Google Apps|
|Bestandsbeleid en activiteitenbeleid|Bestand, activiteit|De gebruiker een melding sturen|Hiermee wordt een e-mail naar gebruikers verzonden om hen te melden dat ze iets hebben gedaan of een bestand hebben dat een beleid schendt. U kunt een aangepaste melding toevoegen om gebruikers te laten weten wat de schending is.|Alles|
|Bestandsbeleid en Onderzoeken > Bestanden|Bestand|De machtiging van de editor om te delen intrekken|In Google Drive staan de standaardmachtigingen van de editor het delen van een bestand ook toe. Deze beheeractie beperkt deze optie en zorgt ervoor dat alleen de eigenaar de bestanden kan delen.|Google Apps|
|Onderzoeken > Bestanden en Bestandsbeleid|Bestand|In gebruikersquarantaine plaatsen|Hiermee worden alle machtigingen uit het bestand verwijderd en wordt het bestand verplaatst naar een quarantainemap onder de hoofdmap van de gebruiker. Hierdoor kan de gebruiker het bestand controleren en verplaatsen. Als het bestand handmatig is teruggeplaatst, wordt de bestandsdeling niet hersteld.|Box, OneDrive, SharePoint|
|Bestandsbeleid en Onderzoeken > Bestanden|Bestand|In beheerquarantaine plaatsen|Hiermee worden machtigingen uit het bestand verwijderd en wordt het bestand verplaatst naar een quarantainemap onder de hoofdmap van de gebruiker. Hierdoor kan de beheerder het bestand controleren en verplaatsen.|Box|
|Onderzoeken > Bestanden en Bestandsbeleid|Bestand|Een samenwerker verwijderen|Hiermee wordt een specifieke samenwerker uit een bestand verwijderd.|Google Apps, Box, OneDrive, SharePoint|
|Onderzoeken > Bestanden en Bestandsbeleid|Bestand|Privé maken|Hiermee wordt het bestand privé gemaakt: er zijn geen samenwerkers of openbare koppelingen meer en het bestand wordt met niemand gedeeld.|Google Apps, OneDrive, SharePoint|
|Onderzoeken > Bestanden en Bestandsbeleid|Bestand|Externe gebruikers verwijderen|Hiermee worden alle externe deelnemers verwijderd (buiten de domeinen die als intern zijn geconfigureerd in Instellingen).|Google Apps, Box |
|Accounts|Bestand|Samenwerkingen van gebruiker verwijderen|Hiermee worden alle samenwerkingen van een specifieke gebruiker verwijderd voor alle bestanden. Dit is handig voor mensen die het bedrijf verlaten.|Box, Google Apps|
|Onderzoeken > Bestanden en Bestandsbeleid|Bestand|Openbare toegang verwijderen|Als een bestand van u is en u het openbaar toegankelijk maakt, wordt het uitsluitend toegankelijk voor anderen voor wie toegang tot het bestand is geconfigureerd (afhankelijk van wat voor soort toegang er is ingesteld voor het bestand). |Google Apps|
|Onderzoeken > Bestanden en Bestandsbeleid|Bestand|De rechtstreeks gedeelde koppeling verwijderen|Hiermee wordt een koppeling voor het bestand verwijderd die openbaar is, maar alleen wordt gedeeld met specifieke personen.|Box|
|App-dashboard > App-machtigingen|Machtigingen|Apps uitsluiten|In Google en Salesforce: de machtigingen voor apps van derden voor Google of Salesforce intrekken en de apps uitsluiten van toekomstige machtigingen. In Office 365: de machtigingen voor toegang van apps van derden tot Office niet toestaan, maar de machtigingen niet intrekken.|Google Apps, Salesforce, Office|
|App-dashboard > App-machtigingen|Machtigingen|Uitsluiten van apps ongedaan maken|In Google en Salesforce: de uitsluiting van apps ongedaan maken en toestaan dat gebruikers apps van derden kunnen machtigen voor Google of Salesforce. In Office 365: de machtigingen van apps van derden voor Office herstellen.|Google Apps, Salesforce, Office|
|App-dashboard > App-machtigingen|Machtigingen|De app intrekken|De machtigingen voor een app van derden intrekken voor Google, Salesforce of Office. Dit is een eenmalige actie die wordt uitgevoerd voor alle bestaande machtigingen, maar waarmee toekomstige verbindingen niet worden voorkomen. |Google Apps, Salesforce, Office|
|App-dashboard > App-machtigingen|Account|De machtiging van de gebruiker voor de app intrekken|Hiermee kunt u machtigingen voor specifieke gebruikers intrekken door op het aantal onder Gebruikers te klikken. De specifieke gebruikers worden weergegeven en u kunt de X gebruiken om machtigingen voor de afzonderlijke gebruikers te verwijderen.|Google Apps, Salesforce, Office|
|Activiteitenbeleid en Onderzoeken > Accounts|Bestand|Het wachtwoord intrekken|Hiermee wordt het wachtwoord voor een gebruikersaccount ingetrokken. U kunt bijvoorbeeld een activiteitenbeleid instellen dat een wachtwoord intrekt na tien mislukte aanmeldingspogingen.|Google Apps|
|Activiteitenbeleid en Onderzoeken > Accounts|Bestand|De beheerdersmachtigingen intrekken|Hiermee wordt het wachtwoord voor een beheerdersaccount ingetrokken. U kunt bijvoorbeeld een activiteitenbeleid instellen dat de beheerdersmachtigingen intrekt na tien mislukte aanmeldingspogingen.|Google Apps|
|Onderzoeken > Bestanden|Bestand|De leesmachtigingen intrekken voor mijzelf|Hiermee worden de leesmachtigingen voor het bestand ingetrokken voor uzelf. Dit is handig wanneer u uzelf een machtiging hebt verleend om te zien of een bestand een beleid schendt.|Google Apps|
|Onderzoeken > Accounts en Beleidsregels|Account|De gebruiker blokkeren|Hiermee wordt ingesteld dat de gebruiker geen toegang heeft en zich niet kan aanmelden. Als de gebruiker is aangemeld wanneer u dit instelt, wordt deze gebruiker onmiddellijk vergrendeld.|Google Apps, Box, Office|
|De pagina Bestanden en Beleidsregels|Bestand|Eigendom van het bestand overdragen|Hiermee wordt de eigenaar gewijzigd. U kiest een specifieke eigenaar in het beleid.|Google Apps|
|Onderzoeken > Accounts |Bestand|Eigendom van alle bestanden overdragen|In een account brengt u het eigendom van de bestanden van een gebruiker over naar een nieuwe persoon, die u selecteert. De vorige eigenaar wordt een editor. Nadat u het eigendom hebt overgedragen, wordt admin@gtest1.adallom.com een editor en kan deze de instellingen voor delen niet langer wijzigen. De nieuwe eigenaar ontvangt een e-mailmelding over het gewijzigde eigendom.|Google Apps|
|Bestandsbeleid|Bestand|Prullenbak|Hiermee wordt het bestand in de prullenbak van de gebruiker geplaatst.|OneDrive, SharePoint|
|Onderzoeken > Accounts|Account|De toegang van de gebruiker herstellen|Hiermee wordt de toegang van de gebruiker hersteld.|Google Apps, Box, Office|
|Onderzoeken > Bestanden|Bestand|Terugplaatsen uit gebruikersquarantaine|Hiermee wordt u een gebruiker teruggeplaatst uit quarantaine.|Box|
|Onderzoeken > Accounts|Account|Accountinstellingen|Hiermee gaat u naar de pagina met accountinstellingen in de specifieke app (bijvoorbeeld in Salesforce).|Alle apps: voor OneDrive en SharePoint worden de instellingen geconfigureerd in Office.|
|Onderzoeken > Bestanden|Bestand|Editors toestaan om te delen|In Google Drive is het delen van een bestand ook toegestaan voor de standaardmachtigingen van de editor. Deze beheeractie is het tegenovergestelde van De machtiging van de editor om te delen intrekken. Hiermee stelt u in dat de editor het bestand kan delen.|Google Apps|
|Bestandsbeleid, activiteitenbeleid|Bestand, activiteit|De laatste editor van het bestand informeren|Hiermee wordt een e-mail verzonden om de laatste persoon die het bestand heeft bewerkt, te laten weten dat het een beleid schendt.|Google Apps, Box|
|Bestandsbeleid, activiteitenbeleid|Bestand, activiteit|De bestandseigenaar een melding sturen|Hiermee wordt een e-mail naar de eigenaar van het bestand verzonden met de optie de beheerder in de CC-regel te zetten wanneer een bestand een beleid schendt. Als in Dropbox geen eigenaar aan een bestand is gekoppeld, wordt de melding verzonden naar de gebruiker die u instelt.|Alle apps|
|Bestandsbeleid, activiteitenbeleid|Bestand, activiteit|Manager van eigenaar in CC-regel opnemen|Wanneer de eigenaar van het bestand een e-mailmelding ontvangt dat het bestand een beleid schendt, wordt hiermee ook de manager van de eigenaar van het bestand op de hoogte gebracht (optioneel).|Alle apps behalve ServiceNow|
|Bestandsbeleid, activiteitenbeleid|Bestand, activiteit|Specifieke gebruikers informeren|Hiermee wordt een e-mail naar specifieke gebruikers verzonden over een bestand dat een beleid schendt.|Alle apps|

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


