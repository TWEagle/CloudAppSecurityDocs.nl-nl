---
title: Werken met de risicoscore | Microsoft Docs
description: Dit onderwerp bevat instructies voor het gebruiken en aanpassen van de app-risicoscore van Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/30/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 9cb3594e-5007-48be-9b4f-e1d23355d86e
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: c08aa36d651c060f571e580c531a6d4eee22094c
ms.sourcegitcommit: c5a0d07af558239976ce144c14ae56c81642191b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/03/2017
---
# <a name="working-with-the-risk-score"></a>Werken met de risicoscore  

## <a name="the-cloud-app-catalog"></a>De catalogus met Cloud-App

De catalogus met Cloud App biedt een volledig overzicht van wat Cloud Discovery identificeert. Cloud Discovery analyseert uw verkeerslogboeken op basis van de catalogus met Cloud App Security cloud-app van meer dan 15.000 cloud-apps die worden beoordeeld en gewaardeerd op basis van meer dan 60 risicofactoren u doorlopende inzicht in de cloud gebruikt, schaduw-IT, en het risico Shadow IT oplevert voor uw organisatie opgeven.
Met de **catalogus met cloud-apps** wordt het risico voor uw cloud-apps beoordeeld op basis van regelgevingscertificeringen, industrienormen en best practices. In de catalogus met cloud-apps worden vier aanvullende processen uitgevoerd om de catalogus up-to-date te houden:
1.  Geautomatiseerde gegevensextractie rechtstreeks vanuit de cloud-app (voor kenmerken zoals SOC 2-naleving).
2.  Geautomatiseerde geavanceerde gegevensextractie voor gegevens met Cloud App Security-algoritmen (voor kenmerken zoals HTTP-beveiligingsheaders).
3.  Continue analyses door het analistenteam van Cloud App Security (voor kenmerken zoals versleuteling van inactieve gegevens).
4.  Klantgebaseerde revisieaanvragen, gebaseerd op klantaanvragen voor wijzigingen in de catalogus met cloud-apps. Alle aanvragen worden bekeken door ons cloudanalistenteam en bijgewerkt op basis van hun bevindingen.
  
![Catalogus met cloud-Apps](./media/cloud-app-catalog.png)  

De aanvraag door business units voor cloud-apps als een oplossing voor hun behoeften aan veranderende groeit. De catalogus met Cloud-app kunt u goed kiezen welke apps aanpassen aan de beveiligingsvereisten van uw organisatie en de noodzaak om up-to-date met de meest recente beveiligingsstandaarden, beveiligingsproblemen en inbreuken op. Bijvoorbeeld, als u wilt vergelijken CRM-apps en controleert u of ze correct zijn beveiligd, kunt u de pagina app-catalogus filteren op relevante apps die u wilt: In de **Cloud-appcatalogus** pagina onder **bladeren op categorie** Selecteer zowel **CRM**. 

Gebruik vervolgens de **Geavanceerd** filters en set **naleving risicofactor** > **SOC 2** gelijk is aan **True**; **Naleving risicofactor** > **ISO 27001** gelijk is aan **True**; **Beveiliging risicofactor** > **Data-at-rest versleuteling** gelijk is aan **True**; **Beveiliging risicofactor** > **Data-at-rest versleuteling** gelijk is aan **True**; **Beveiliging risicofactor** > **Admin audittrail** gelijk is aan **True** en **beveiliging risicofactor** > **gebruiker audittrail** gelijk is aan **True**.

![Cloud-app-catalogusfilters](./media/cloud-app-catalog-filters.png)

Nadat de resultaten worden gefilterd, kunt u de relevante apps bekijken en vinden die het beste past bij uw behoeften.

## <a name="cloud-app-catalog-filters"></a>Catalogus met cloud-App-filters

Er zijn basiseigenschappen en geavanceerde filters voor Cloud App-catalogus. Een complexe filter gebruiken om te creëren de geavanceerde optie waarin alle van de volgende opties:

- **App-tags**: labels kunnen u de catalogus met Cloud App aanpassen. 
  U kunt kiezen uit een **Sanctioned**, **Unsanctioned** of u aangepaste labels voor apps kunt maken. Deze tags kunnen vervolgens worden gebruikt als filters voor dieper verdiepen specifieke typen apps die u wilt onderzoeken. 
- **Apps en domeinen**: Hiermee kunt u zoeken naar specifieke apps of apps die worden gebruikt in een specifieke domeinen. 
- **Categorieën**: het filter categorieën, dat aan de linkerkant van de pagina bevindt zich, kunt u zoeken naar typen apps volgens app-categorieën, bijvoorbeeld apps sociale netwerken, opslag-Cloud-apps, enzovoort. U kunt meerdere categorieën tegelijk of één categorie selecteren en vervolgens de basiseigenschappen en geavanceerde filters boven deze op toepassen.
- **Naleving risicofactor**: Hiermee kunt u naar een specifieke normen gehanteerd zoeken, certificering en conformiteit die de app kan voldoen aan de (HIPAA, ISO 27001, SOC 2, PCI-DSS, enz.).
- **Algemene risicofactor**: Hiermee kunt u naar algemene risicofactoren zoals Consumer populariteit, Data zoeken center landinstellingen, enzovoort.
- **Risicoscore**: Hiermee kunt u filteren op apps met risico score zodat u zich richten kunt op, bijvoorbeeld alleen zeer risicovolle apps controleren.
- **Beveiliging risicofactor**: kunt u filteren op basis van specifieke veiligheidsmaatregelen (zoals versleuteling op rest, meervoudige verificatie, enz.).

## <a name="suggesting-a-change"></a>Een wijziging wordt voorgesteld

Als u een nieuwe app in uw omgeving die door Cloud App Security, een nieuwe risicofactor of een score-update nog niet is berekend of app-gegevens is verouderd vinden, kunt u een overzicht van de app aanvragen:

**Een nieuwe app voorstellen:**
1. Aan de bovenkant van de **gedetecteerde apps** pagina, klikt u op de drie puntjes en selecteer vervolgens **nieuwe app voorstellen**. 

  ![Een app cloud App Security voorstellen](./media/suggest-new-app.png)

2. In de **suggesties nieuwe cloud-app** pop-up vullen in informatie over de nieuwe app, inclusief de naam en het domein van de app. 

  ![Een app pop en Cloud App Security voorstellen](./media/suggest-new-app-popup.png)

3. We raden u aan als u het vakje voor Cloud App Security analisten contact met u als u meer informatie over de app is vereist en zodat u kan worden bijgewerkt wanneer de analyse is voltooid.

**Een risicofactor, score, bijwerken of bijwerken van app-gegevens:**

1. In de **Cloud-Appcatalogus** pagina in de app-rij die u wilt bijwerken, klik op de drie punten aan het einde van de rij en selecteer **score update aanvragen**.

  ![Score update aanvragen](./media/request-score-update.png)

2. In de **raden een verbetering** pop-up selecteren of u wilt aanvragen van een update score raden een nieuwe risicofactor of update app-gegevens.

  ![voorstellen en verbetering en Cloud App Security](./media/suggest-improvement-popup.png)

3. We raden u aan als u het vakje voor Cloud App Security analisten contact met u als u meer informatie over de app is vereist en zodat u kan worden bijgewerkt wanneer de analyse is voltooid.
 


## <a name="customizing-the-risk-score"></a>De risicoscore aanpassen

Cloud Discovery biedt u belangrijke gegevens over de geloofwaardigheid en betrouwbaarheid van de cloud-apps die in de omgeving worden gebruikt. In de portal wordt elke gedetecteerde app weergegeven met een totale score, die weergeeft hoe Cloud App Security de vervaldatum van gebruik voor ondernemingen evalueert van de desbetreffende app. De totale score van een app is een gewogen gemiddelde van drie subscores voor de drie subcategorieën waarmee Cloud App Security rekening houdt bij het beoordelen van betrouwbaarheid:  
  
-   **Algemeen** - Deze categorie heeft betrekking op de algemene informatie over het bedrijf dat de app produceert, waaronder het domein, jaar van oprichting en de populariteit. Deze velden zijn bedoeld om de stabiliteit van het bedrijf op het meest basale niveau weer te geven.  
  
-   **Beveiliging** - De beveiligingscategorie omvat alle standaarden die gaan over de fysieke beveiliging van de gegevens die door de gedetecteerde app worden gebruikt. Hieronder vallen velden als meervoudige verificatie, versleuteling, gegevensclassificatie en gegevenseigendom.  
  
-   **Naleving** - In deze categorie wordt weergegeven welke algemene best practice-nalevingsstandaarden worden gehandhaafd door het bedrijf dat de app produceert. De lijst met specificaties bevat standaarden als HIPAA, CSA en PCI-DSS.  
  
Elke categorie bevat veel specifieke eigenschappen. Volgens ons score-algoritme krijgt elke eigenschap een voorlopige score tussen 0 en 10, afhankelijk van de waarde. Waarden die waar/onwaar zijn krijgen een 10 of een 0 naar gelang hun waarde, terwijl doorlopende eigenschappen, bijvoorbeeld domeinleeftijd, een bepaalde waarde binnen het spectrum krijgen. De score van elke eigenschap wordt tegen alle andere bestaande velden in de categorie afgewogen om de subscore van de categorie te berekenen. Als u een app zonder score tegenkomt, duidt dit meestal op een app met onbekende eigenschappen, die daarom geen score heeft.  
  
Het is belangrijk dat u even de tijd neemt om de standaardgewichten van de scoreconfiguratie van Cloud Discovery te bekijken en wijzigen. Standaard krijgen alle geëvalueerde parameters een gelijk gewicht. Als bepaalde parameters meer of minder belangrijk voor uw organisatie zijn, is het belangrijk dat u ze als volgt wijzigt:  
  
1.  Selecteer in de portal onder het pictogram Instellingen **Instellingen voor Cloud Discovery**.  
  
2.  Verschuif de knop **Belang** onder **Metrische gegevens voor de score configureren** om het gewicht van het veld of de risicocategorie te wijzigen naar **Genegeerd**, **Laag**, **Gemiddeld**, **Hoog** of **Zeer hoog**.  
  
3.  Daarnaast kunt u instellen of bepaalde waarden niet beschikbaar voor of niet van toepassing op de scoreberekening zijn. Wanneer ze zijn opgenomen, dragen n.v.t.-waarden negatief bij aan de berekende score.  
  
  ![score](./media/score.png "score")  

Alle informatie die nodig is om te begrijpen hoe onze risicoscores worden samengesteld, is beschikbaar in de Cloud App Security-portal.
Gebruik de knop 'i' aan de rechterkant van elke veldnaam in het profiel van de app voor een beter begrip van het gewicht van een risicofactor in een specifieke risicocategorie. Dit biedt informatie over hoe Cloud App Security precies een specifieke risicofactor bepaalt. De score is de waarde van de risicofactor op een schaal van 1-10 + het gewicht in de risicocategorie:

![risicoberekening](./media/cac-weight.png)
  
Beweeg de muisaanwijzer over de risicocategoriescore om het gewicht van een risicocategorie in de totale score van een app te begrijpen:

![risicocategoriegewicht](./media/risk-category-weight.png)

## <a name="overriding-the-risk-score"></a>De risicoscore overschrijven
U kunt de risicoscore van een app zonder verandert de manier waarop die deze zodat u onmiddellijke resultaten voor uw organisatie ophalen worden gewogen overschrijven. Als de risicoscore van een LOB-app die u gebruikt 8 en het is erkend en aangemoedigd door uw organisatie, wilt u mogelijk het risico score tot 10 wijzigen. 

Voor het onderdrukken van de risicoscore de **gedetecteerde apps** tabel of in de **Cloud-appcatalogus**, klik op de drie punten rechts van elke app en selecteer **risicoscore overschrijven**.

![cloud app security gedetecteerde app-risicoscore overschrijven](./media/override-risk-score.png)

Na het bijwerken van de score, kunt u de opmerkingen bij de app om uw zakelijke redenen voor het wijzigen van deze app score wissen aan andere beheerders kunt opnemen. 

U kunt ook de opmerkingen bij om de reden van de wijziging te wissen wanneer iedereen de app bekijkt toevoegen.


 
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  