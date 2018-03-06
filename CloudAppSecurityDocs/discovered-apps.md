---
title: Werken met gedetecteerde apps in de Cloud App Security | Microsoft Docs
description: In dit onderwerp beschrijft het proces voor het opsporen en oplossen van problemen met risicovolle cloud discovery-apps in de Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/5/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 645fd8c7-06d0-4f93-a85c-2976e7b3766d
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 276af05cd289496c277a5ab0709e7fca3453d469
ms.sourcegitcommit: c47fd92c71028ede8840e0766f20eb0ad2898e70
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="working-with-discovered-apps"></a>Werken met gedetecteerde apps

## <a name="review-the-cloud-discovery-dashboard"></a>Het Cloud Discovery-dashboard bekijken

Met het Cloud Discovery-dashboard hebt u meer inzicht in de manier waarop cloud-apps in uw organisatie worden gebruikt. Met het dashboard kunt u in één oogopslag een overzicht bekijken van de apps die worden gebruikt, uw openstaande waarschuwingen en de risiconiveaus van de apps in uw organisatie. Daarnaast kunt u zien wie de belangrijkste gebruikers in uw organisatie zijn en wordt een app-hoofdkantoorkaart weergegeven. Het Cloud Discovery-dashboard heeft verschillende opties voor het filteren van gegevens, zodat u specifieke weergaven kunt genereren (afhankelijk van de gegevens die het interessantst zijn voor u), en eenvoudig te begrijpen afbeeldingen zodat u in één oogopslag een volledig beeld krijgt.

![Cloud Discovery-dashboard](./media/cloud-discovery-dashboard.png)

Het eerste wat u moet doen als u een algemeen beeld wilt krijgen van uw Cloud Discovery-apps, is kijken naar het Cloud Discovery-dashboard en de volgende gegevens controleren:
 
1. Bekijk eerst de algemene cloud-app-gebruik in uw organisatie in de **overzicht van hoog niveau gebruik**.

2. Hier vindt u één niveau lager om te zien die de **top categorieën** voor elk van de parameters van de verschillende gebruiken en hoeveel dit gebruik is door keuren apps in uw organisatie wordt gebruikt.

3. Zelfs dieper en zien van de apps in een specifieke categorie in de **gedetecteerde apps** widget.

4. U ziet de **top gebruikers en de brontabel van de IP-adressen** om te bepalen welke gebruikers zijn de meest verwerkingsflexibiliteit gebruikers van cloud-apps in uw organisatie.
5. Controleer hoe het gedetecteerde apps verdeeld volgens de geografische locatie (op basis van hun hoofdkantoor) in de **App Headquarters kaart**.

6. Ten slotte Vergeet niet om te controleren van de risicoscore van de gedetecteerde app in de **overzicht van de App risico** en controleer de **detectie waarschuwingen status** om te zien hoeveel waarschuwingen openen moeten u onderzoeken.

## <a name="deep-dive-into-discovered-apps"></a>Diepgaand in doorzochte apps
Als u diepgaand in de gegevens van Cloud Discovery wilt moet u de filters gebruiken om te controleren welke apps riskant zijn en die vaak worden gebruikt.


Bijvoorbeeld, als u identificeren veelgebruikte risicovolle cloud-opslag- en samenwerking apps wilt, kunt u de apps doorzochte pagina voor de apps die u wilt filteren. Daarna kunt u [goed of blokkeren](governance-discovery.md) ze als volgt:

In de **gedetecteerde apps** pagina onder **bladeren op categorie** Selecteer zowel **Cloudopslag** en **samenwerking**. Vervolgens gebruikt u de geavanceerde filters en stel **naleving risicofactor** naar **SOC 2** gelijk is aan **False**; **Gebruik** > **gebruikers** tot meer dan 50 van gebruikers; en **gebruik** > **transacties** tot meer dan 100; **Beveiliging risicofactor** > **Data-at-rest versleuteling** gelijk is aan **False** en stel vervolgens **risicoscore** resulteert in minder dan 6.

![Gedetecteerde app-filters](./media/discovered-app-filters.png)

Nadat de resultaten worden gefilterd, kunt u [goed en blokkeren](governance-discovery.md) ze met behulp van het selectievakje in bulk-actie voor goed ze allemaal in één actie. Nadat ze niet-toegestane zijn kunt u een blokkerende script kunt gebruiken om te blokkeren ze worden gebruikt in uw omgeving.

Cloud discovery kan u zelfs diepere Duik in de cloud-gebruik van uw organisatie en identificeren van specifieke exemplaren die gebruikt worden door de gedetecteerde subdomeinen onderzoeken.
     
U kunt bijvoorbeeld onderscheid maken tussen verschillende SharePoint-sites.

Dit wordt alleen ondersteund in firewalls en proxy's die doel-URL gegevens bevatten. Zie de lijst met ondersteunde apparaten in [firewalls en proxy's ondersteund](set-up-cloud-discovery#supported-firewalls-and-proxies).

 ![subdomein informatie](./media/discovery-domains.png) 

## <a name="exclude-entities"></a>Entiteiten uitsluiten  
Als u gebruikers of IP-adressen heeft die bijzonder veel ruis veroorzaken en oninteressant zijn of apps die niet relevant zijn, dan kunt u hun gegevens uitsluiten van de Cloud Discovery-gegevens die worden geanalyseerd. U zou bijvoorbeeld alle gegevens kunnen uitsluiten die afkomstig zijn van 127.0.0.1 of de lokale host.  
  
Een uitzondering aanmaken:  
  
1.  Selecteer in de portal onder het pictogram Instellingen **Instellingen voor Cloud Discovery**.  
  
2.  Klik op het tabblad **Entiteiten uitsluiten**.  
  
3.  Kies het tabblad **Uitgesloten gebruikers** of het tabblad **Uitgesloten IP-adressen** en klik op de knop **Gebruiker toevoegen** of **IP-adres toevoegen**.  
  
4.  Voeg een gebruikersalias of IP-adres toe. Het is raadzaam om informatie toe te voegen over waarom de gebruiker of het IP-adres is uitgesloten.  
  
     ![gebruiker uitsluiten](./media/exclude-user.png "gebruiker uitsluiten")  
  
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
  
6.  Stel de gewenste filters in voor gegevens (**Organisatie-eenheden**, **IP-adrestags** of **IP-adresbereiken**). Zie het Engelstalige artikel [Organize the data according to your needs](ip-tags.md) (De gegevens organiseren op basis van uw behoeften) voor meer informatie over het werken met IP-adrestags en IP-adresbereiken.  
  
    ![Aangepast doorlopend rapport maken](./media/create-custom-continuous-report.png) 

> [!NOTE]
> Alle aangepaste rapporten zijn beperkt tot een maximum van 1 GB aan niet-gecomprimeerde gegevens. Als er meer dan 1 GB aan gegevens, wordt de eerste 1 GB aan gegevens geëxporteerd naar het rapport.


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
 
[Momentopnamerapporten maken van Cloud Discovery](create-snapshot-cloud-discovery-reports.md)

[Automatisch uploaden van logboeken configureren voor doorlopende rapporten](configure-automatic-log-upload-for-continuous-reports.md)

[Werken met Cloud Discovery-gegevens](working-with-cloud-discovery-data.md)

