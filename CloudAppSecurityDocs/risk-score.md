---
title: Werken met de risicoscore | Microsoft Docs
description: Dit onderwerp bevat instructies voor het gebruiken en aanpassen van de app-risicoscore van Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/26/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 9cb3594e-5007-48be-9b4f-e1d23355d86e
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d617631819744211df5e6bee1f48df36dcedb7ce
ms.sourcegitcommit: cda4a69f9ad9c6eb66fbdb98610f54d79585b84b
translationtype: HT
---
# <a name="working-with-the-risk-score"></a>Werken met de risicoscore  
Cloud Discovery biedt u belangrijke gegevens over de geloofwaardigheid en betrouwbaarheid van de cloud-apps die in de omgeving worden gebruikt. In de portal wordt elke gedetecteerde app weergegeven met een totale score, die weergeeft hoe Cloud App Security de vervaldatum van gebruik voor ondernemingen evalueert van de desbetreffende app. De totale score van een app is een gewogen gemiddelde van drie subscores voor de drie subcategorieën waarmee Cloud App Security rekening houdt bij het beoordelen van betrouwbaarheid:  
  
-   **Algemeen** - Deze categorie heeft betrekking op de algemene informatie over het bedrijf dat de app produceert, waaronder het domein, jaar van oprichting en de populariteit. Deze velden zijn bedoeld om de stabiliteit van het bedrijf op het meest basale niveau weer te geven.  
  
-   **Beveiliging** - De beveiligingscategorie omvat alle standaarden die gaan over de fysieke beveiliging van de gegevens die door de gedetecteerde app worden gebruikt. Hieronder vallen velden als meervoudige verificatie, versleuteling, gegevensclassificatie en gegevenseigendom.  
  
-   **Naleving** - In deze categorie wordt weergegeven welke algemene best practice-nalevingsstandaarden worden gehandhaafd door het bedrijf dat de app produceert. De lijst met specificaties bevat standaarden als HIPAA, CSA en PCI-DSS.  
  
Elke categorie bevat veel specifieke eigenschappen. Volgens ons score-algoritme krijgt elke eigenschap een voorlopige score tussen 0 en 10, afhankelijk van de waarde. Waarden die waar/onwaar zijn krijgen een 10 of een 0 naar gelang hun waarde, terwijl doorlopende eigenschappen, bijvoorbeeld domeinleeftijd, een bepaalde waarde binnen het spectrum krijgen. De score van elke eigenschap wordt tegen alle andere bestaande velden in de categorie afgewogen om de subscore van de categorie te berekenen. Als u een app zonder score tegenkomt, duidt dit meestal op een app met onbekende eigenschappen, die daarom geen score heeft.  
  
Het is belangrijk dat u even de tijd neemt om de standaardgewichten van de scoreconfiguratie van Cloud Discovery te bekijken en wijzigen. Standaard krijgen alle geëvalueerde parameters een gelijk gewicht. Als bepaalde parameters meer of minder belangrijk voor uw organisatie zijn, is het belangrijk dat u ze als volgt wijzigt:  
  
1.  Selecteer in de portal onder het pictogram Instellingen **Instellingen voor Cloud Discovery**.  
  
2.  Verschuif de knop **Belang** onder **Metrische gegevens voor de score configureren** om het gewicht van het veld te wijzigen naar **Genegeerd**, **Laag**, **Gemiddeld**, **Hoog** of **Zeer hoog**.  
  
3.  Daarnaast kunt u instellen of bepaalde waarden niet beschikbaar voor of niet van toepassing op de scoreberekening zijn. Wanneer ze zijn opgenomen, dragen n.v.t.-waarden negatief bij aan de berekende score.  
  
     ![score](./media/score.png "score")  
  
## <a name="manage-continuous-reports"></a>Doorlopende rapporten beheren  
Met aangepaste doorlopende rapporten beschikt u over meer details bij de controle van de Cloud Discovery-logboekgegevens van uw organisatie. Als u aangepaste rapporten maakt, kunt u filteren op specifieke geografische locaties, netwerken, sites of organisatie-eenheden. Standaard worden alleen de volgende rapporten in de Cloud Discovery-rapportkiezer weergegeven:  
  
-  Met het **algemene rapport** worden alle gegevens in de portal samengevoegd uit alle gegevensbronnen die u aan de logboeken hebt toegevoegd.  
  
- In het **specifieke gegevensbronrapport** worden alleen gegevens voor een specifieke gegevensbron weergegeven.  
  
Ga als volgt te werk om een nieuw doorlopend rapport te maken:  
  
1.  Selecteer in de portal onder het pictogram Instellingen **Instellingen voor Cloud Discovery**.  
  
2.  Klik op het tabblad **Doorlopend rapport beheren**.  
  
3.  Klik op de knop **Rapport maken**.  
  
4.  Voer een rapportnaam in.  
  
5.  Selecteer de gegevensbronnen die u wilt opnemen (alle of specifiek).  
  
6.  Stel de gewenste filters in voor gegevens (**Organisatie-eenheden**, **IP-adrestags** of **IP-adresbereiken**). Zie het Engelstalige artikel [Organize the data according to your needs](general-setup.md#IPtagsandRanges) (De gegevens organiseren op basis van uw behoeften) voor meer informatie over het werken met IP-adrestags en IP-adresbereiken.  
  
    ![Aangepast doorlopend rapport maken](./media/create-custom-continuous-report.png) 
  
## <a name="exclude-entities"></a>Entiteiten uitsluiten  
Als u gebruikers of IP-adressen heeft die bijzonder veel ruis veroorzaken en oninteressant zijn of apps die niet relevant zijn, dan kunt u hun gegevens uitsluiten van de Cloud Discovery-gegevens die worden geanalyseerd. U zou bijvoorbeeld alle gegevens kunnen uitsluiten die afkomstig zijn van 127.0.0.1 of de lokale host.  
  
Een uitzondering aanmaken:  
  
1.  Selecteer in de portal onder het pictogram Instellingen **Instellingen voor Cloud Discovery**.  
  
2.  Klik op het tabblad **Entiteiten uitsluiten**.  
  
3.  Kies het tabblad **Uitgesloten gebruikers** of het tabblad **Uitgesloten IP-adressen** en klik op de knop **Gebruiker toevoegen** of **IP-adres toevoegen**.  
  
4.  Voeg een gebruikersalias of IP-adres toe. Het is raadzaam om informatie toe te voegen over waarom de gebruiker of het IP-adres is uitgesloten.  
  
     ![gebruiker uitsluiten](./media/exclude-user.png "gebruiker uitsluiten")  
  
## <a name="deleting-cloud-discovery-data"></a>Cloud Discovery-gegevens verwijderen  
Er zijn een aantal redenen waarom u uw Cloud Discovery- gegevens zou willen verwijderen. In de volgende gevallen is het raadzaam de gegevens te verwijderen:  
  
-   Als u logboekbestanden handmatig heeft geüpload, er veel tijd is verstreken voordat u het systeem met nieuwe logboekbestanden heeft bijgewerkt en u niet wilt dat oude gegevens uw resultaten beïnvloeden.  
  
-   Wanneer u een nieuwe aangepaste gegevensweergave instelt, is deze alleen van toepassing op nieuwe gegevens vanaf dat moment. U zou oude gegevens dus kunnen wissen en vervolgens de logboekbestanden opnieuw uploaden, zodat de aangepaste gegevensweergave de gebeurtenissen uit de gegevens van het logboekbestand kan meenemen.  
  
-   Als onlangs veel gebruikers of IP-adressen weer zijn gaan werken, nadat ze een tijd offline waren, dan wordt hun activiteit aangeduid als afwijkend en krijgt u mogelijk veel fout-positieve schendingen.  
  
Cloud Discovery-gegevens verwijderen:  
  
1.  Selecteer in de portal onder het pictogram Instellingen **Instellingen voor Cloud Discovery**.  
  
2.  Klik op het tabblad **Gegevens verwijderen**.  
  
     Het is belangrijk om er zeker van te zijn dat u gegevens wilt verwijderen voordat u doorgaat; deze actie kan niet ongedaan worden gemaakt en hiermee worden **alle** Cloud Discovery-gegevens in het systeem verwijderd.  
  
3.  Klik op de knop **Verwijderen**.  
  
     ![gegevens verwijderen](./media/delete-data.png "gegevens verwijderen")  
  
    > [!NOTE]  
    >  De verwijdering duurt een paar minuten en is niet direct.  



 
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  