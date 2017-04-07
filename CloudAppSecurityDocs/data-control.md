---
title: Overzicht van het scenario voor gegevensbeheer | Microsoft-documenten
description: In dit onderwerp wordt het scenario voor het beheren van gegevens in uw cloudomgeving beschreven.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 4/2/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 57927618-cb66-4c7f-afd7-c96926460816
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: e7e735519caa7da514f06db13afc737cf6ef1806
ms.sourcegitcommit: 661f4ce41262e8462c90fd2a4f1232e2154d5113
translationtype: HT
---
# <a name="controlling-and-protecting-your-files"></a>Uw bestanden beheren en beveiligen  

In de zakenwereld van tegenwoordig waar veel gegevens en veel apparaten worden gebruikt, kan het moeilijk zijn om bij te houden waar de gegevens zich bevinden en wie toegang heeft. Met Cloud App Security kunt u de controle over uw gegevens behouden door bestandsbeveiliging over de cloud in te schakelen. Cloud App Security biedt u hulpmiddelen om beleid te maken voor wat u wel en niet wilt toestaan over uw bedrijfscloud en uiteenlopende geautomatiseerde processen voor de uitvoering van continue compliancescans, juridische eDiscovery-taken, DLP voor gevoelige inhoud die is opgeslagen in uw cloud of extern of openbaar is gedeeld en veel meer use cases.  
Met Cloud App Security kunt u elk bestandstype controleren op basis van meer dan twintig metagegevensfilters (bijvoorbeeld toegangsniveau, bestandstype). Zie [Bestanden](file-filters.md) voor meer informatie. Hieronder vindt u twee voorbeelden van dreigingen gerelateerd aan gegevens waarmee alle organisaties worden geconfronteerd, met procedures voor het beveiligen van uw bestanden in de cloud.
 
## <a name="files-that-contain-sensitive-data-are-being-shared-externally"></a>Bestanden die gevoelige gegevens bevatten worden extern gedeeld 

Deze use case is van toepassing op Office 365, G Suite, Box, Dropbox en Salesforce.

### <a name="the-threat"></a>DE BEDREIGING
Werknemers delen bedrijfsbestanden met gevoelige gegevens buiten de organisatie. Dit kan leiden tot het onbewaakt lekken van gegevens. Dit kan onschuldig zijn en uw bedrijfsbeleid niet schenden, maar zelfs in dat geval is het belangrijk om te controleren wat wordt gedeeld, zodat u altijd weet hoe uw netwerk wordt gebruikt en welke gegevens extern worden gedeeld.

### <a name="the-solution"></a>DE OPLOSSING
Meer inzicht verkrijgen in het delen van bestanden in uw netwerk en gegevensbeheersacties implementeren door het volgende in de Cloud App Security te implementeren uit de volgende beleids- en gegevensbeheeractie in de Cloud App Security.

#### <a name="prerequisites"></a>Vereisten

[Verbind](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) ten minste een cloud-app met de Cloud App Security.

#### <a name="setting-up-monitoring"></a>Controle instellen

1.    Bestanden beheren door een beleid te maken

    1. Op de pagina **Beleid**, klikt u op [ **Bestandsbeleid maken**](data-protection-policies.md). 
    ![Bestandsbeleid maken](./media/create-file-policy.png)

    2. Kies in het veld [ **Beleidssjabloon** ](policy-template-reference.md) **Bestand aangetroffen met PII in de cloud (ingebouwde DLP-engine)** en klik op **Sjabloon toepassen**. 
    ![Bestandsbeleidssjabloon](./media/file-policy-template.png)
    3. Als u het ongepast delen van deze bestanden met persoonlijke gegevens wilt bewaken, voeg dan een filter toe met het toegangsniveau dat u probeert te blokkeren - bijvoorbeeld **Toegangsniveau is gelijk aan extern, openbaar, openbaar (internet)**. 
     ![Bestandsbeleidfilter](./media/file-policy-filter.png)

2. Uw overeenkomsten onderzoeken
    
    1. Klik in de pagina **Beleid** op de naam van het beleid om naar het **Beleidsrapport** te gaan en bekijk de resultaten die zijn geactiveerd door het beleid.

    2. U kunt de overeenkomende reeks onderzoeken door te klikken op een specifieke overeenkomst om de bestandslade te openen. In de lade ziet u de andere beleidsregels voor dit bestand, de status van de inhoudsscan en als u daarop klikt, kunt u de inhoudsovereenkomsten zien, u kunt klikken op de **Deelnemers** om de lijst met collega's te zien en u kunt zien of er classificatielabels op het bestand rusten. U kunt ook het **Pad** bekijken om te zien waar het bestand is opgeslagen om meer context over het bestand zelf te krijgen.
    
    3. Als u vals-positieven vindt, markeer ze dan met een vinkje om ze uit te sluiten van het rapport en live-matches. U kunt de feedbackfunctie gebruiken om het Cloud App Security-team verbeteringen die u wilt toevoegen door te geven. 


#### <a name="validating-your-policy"></a>Uw beleid valideren

1. Maak een nieuw Word-document met de volgende tekst: 078-05-1120.
2. Sla het bestand dan op als *testbestand.docx* en deel het met iemand buiten uw domein of met een openbare URL. 
3. Ga naar het beleidsrapport. Binnen enkele ogenblikken zou een bestandsbeleidovereenkomst moeten worden weergegeven. 
4. U kunt op de overeenkomst klikken om de context van het bestand te zien. De overeenkomst zelf wordt gemaskeerd ter bescherming van gevoelige gegevens. 

#### <a name="removing-the-risk"></a>Het risico verwijderen

Nadat u het hebt gevalideerd en het beleid op uw wensen afgestemd om ervoor te zorgen dat het wordt uitgevoerd als u bedoelt, doet u het volgende: 
  1. U kunt onmiddellijk [bestuursacties](governance-actions.md) ondernemen door op de drie puntjes aan het einde van de rij te klikken en de relevante bestuursactie te selecteren, bijvoorbeeld **Gebruiker in quarantaine plaatsen**.

 ![auto gov extern](./media/auto-gov-external.png)

   2. Nadat deze volledig is gevalideerd, kunt u deze automatische bestuursacties uit laten voeren. In SharePoint en OneDrive kunt u bijvoorbeeld **Externe gebruikers verwijderen** of **Gebruiker in quarantaine plaatsen** en voor G Suite en Box kunt u **Externe gebruikers verwijderen** en **Publieke toegang verwijderen**.

  ![automatische bestuursacties toepassen](./media/apply-automatic-gov-actions.png)

## <a name="files-shared-publicly-and-labeled-as-confidential"></a>Openbaar gedeelde bestanden met het label vertrouwelijk

Deze use case is van toepassing op Office 365, G Suite, Box, Dropbox en Salesforce.

Deze use case maakt gebruik van de integratie tussen Cloud App Security en Azure Information Protection. Als u Azure Information Protection uitvoert in uw organisatie en de tijd hebt genomen om uw bestanden te labelen met Azure Information Protection-labels, kunt u met Cloud App Security bewaken en bepalen wat er met die bestanden gebeurt nadat ze zijn gelabeld.

## <a name="the-threat"></a>DE BEDREIGING

U weet dat u uw gegevens moet beveiligen, u hebt al de moeite genomen uw bestanden te classificeren in Azure Information Protection. Maar als u ze hebt geclassificeerd, hoe weet u dan waar ze zijn en wie ernaar kijkt? 

## <a name="the-solution"></a>DE OPLOSSING
 U kunt deze geclassificeerde bestanden controleren in de cloud met Cloud App Security. Hiermee kunt u ervoor zorgen dat de gegevens die u hebt geclassificeerd als **vertrouwelijk** (of een andere gevoelige classificatie) niet ongepast gedeeld worden. Laat Cloud App Security de bestanden die u in Azure Information Protection geclassificeerd hebt, controleren en beheren door de volgende beleids- en gegevensbeheersacties te implementeren.

### <a name="prerequisites"></a>Vereisten

- [Verbind](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md) ten minste één cloud-app met Cloud App Security.
- Volg de [Azure Information Protection integratie-instructies](azip-integration.md) om de automatische scan in te schakelen.

### <a name="setting-up-monitoring"></a>Controle instellen

1. Uw gegevens beheren door een beleid te maken    
    
    1. Op de pagina **Beleid**, klikt u op [ **Bestandsbeleid maken**](data-protection-policies.md). 

    2.    In de sectie filteren kunt u de filters voor **Toegangsniveau** en **Laatst gewijzigd** verwijderen om dit beleid op alle bestanden in uw cloud uit te laten voeren. Deze filters zijn alleen van toepassing op bestanden die vanaf nu worden gewijzigd. Voeg het filter **Classificatielabel** toe en vervolgens **is gelijk aan** en selecteer het classificatielabel van uw organisatie. 
    
    ![classificatielabel bestandsbeleid](./media/file-policy-class-label.png)

    3.    Voeg een filter toe met het toegangsniveau dat u probeert te blokkeren om het ongepast delen van deze geclassificeerde bestanden te bewaken, bijvoorbeeld **Toegangsniveau is gelijk aan openbaar, openbaar (internet)**.  Nadat u het beleid hebt gestart, doet Cloud App Security er even over om bestaande bestanden en ook nieuwe bestanden die u toevoegt te scannen. Afhankelijk van de hoeveelheid gegevens die u in uw cloud hebt, kan het even duren om de scan te voltooien.

    ![bestandsbeleidfilter openbaar](./media/file-policy-filter-public.png)

2. Uw overeenkomsten onderzoeken

    1. Klik op de naam van het beleid om naar het **Beleidsrapport** te gaan en bekijk de resultaten die zijn geactiveerd door het beleid.
    
    2. U kunt de overeenkomende reeks onderzoeken door te klikken op een specifieke overeenkomst om de bestandslade te openen. In de lade ziet u de classificatielabels die zijn ingesteld voor dit bestand en andere beleidsregels die voor dit bestand gelden, en kunt u klikken op de **Deelnemers** om de lijst met deelnemers te zien. U kunt ook het **Pad** bekijken om te zien waar het bestand is opgeslagen om meer context over het bestand zelf te krijgen.
      
    3. Als u vals-positieven vindt, markeer ze dan met een vinkje om ze uit te sluiten van het rapport en live-matches. U kunt de feedbackfunctie gebruiken om het Cloud App Security-team verbeteringen die u wilt toevoegen door te geven. 


### <a name="validating-your-policy"></a>Uw beleid valideren

1. Maak een nieuw Word-document en gebruik de werkbalk van Azure Information Protection om eventuele gevoeligheidslabels als **Vertrouwelijk** in te stellen. 

2. Upload het bestand naar uw cloud-app en deel het vervolgens met een openbare URL. 

3. Ga naar het **Beleidsrapport**. Binnen enkele ogenblikken zou een bestandsbeleidovereenkomst moeten worden weergegeven. 

4. U ziet het classificatielabel door op het bestand te klikken en de **Bestandslade** te openen. 


#### <a name="removing-the-risk"></a>Het risico verwijderen

Nadat u het hebt gevalideerd en het beleid op uw wensen afgestemd om ervoor te zorgen dat het wordt uitgevoerd als u bedoelt, doet u het volgende: 

1. U kunt onmiddellijk [Bestuursacties](governance-actions.md) ondernemen door op de drie puntjes aan het einde van de rij te klikken en de relevante bestuursactie te selecteren, bijvoorbeeld **Gebruiker in quarantaine plaatsen**.
    
2. Nadat deze volledig is gevalideerd, kunt u deze automatische bestuursacties uit laten voeren. In SharePoint en OneDrive kunt u bijvoorbeeld **Gebruiker in quarantaine plaatsen** en voor G Suite en Box kunt u **Publieke toegang verwijderen**.
 
 ![automatische bestuursactie verwijderen publieke toegang](./media/gov-action-public-access.png)

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  