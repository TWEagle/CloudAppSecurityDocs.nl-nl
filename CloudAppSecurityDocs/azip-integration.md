---
title: Integratie van Azure Information Protection | Microsoft Docs
description: Dit artikel bevat informatie over hoe u de labels van Azure Information Protection kunt gebruiken in Cloud App Security, voor meer controle over het gebruik van cloud-apps binnen uw organisatie.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/23/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 8168319a-199f-4e6c-ad68-e0f236480803
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 86a5f7371b7a1d0fd16f68fd3060390b05601607
ms.openlocfilehash: 3497225dfa98b487fd384a819cc51a51bd79a7cb


---

# <a name="azure-information-protection-integration"></a>Integratie van Azure Information Protection

Met Cloud App Security kunt u bestanden onderzoeken en beleid instellen op basis van bestandslabels van Azure Information Protection. Dat zorgt voor meer zichtbaarheid van en controle over uw gevoelige gegevens in de cloud. Als u dit wilt gebruiken, maakt u een beleidsregel in Cloud App Security voor het scannen van bestanden met inhoudsinspectie ingeschakeld. Daarnaast kunt u waarschuwingen activeren voor activiteiten met betrekking tot geclassificeerde bestanden. Na integratie van Azure Information Protection kunt u het volgende doen:
-   De blootstelling van gevoelige gegevens via uw cloudtoepassingen kwantificeren.
-   Beleid maken en waarschuwingen instellen voor schendingen van het verbod op het uploaden van geclassificeerde gegevens in uw gekoppelde cloud-apps, of gevoelige gegevens blokkeren of in quarantaine plaatsen om extern delen te voorkomen.
-   Audittrails onderzoeken en bestanden herstellen die uw beleid schenden 

> [!NOTE] 
> Standaard worden bestanden alleen gescand op labels wanneer er een beleid is voor het scannen van bestanden met inhoudsinspectie ingeschakeld. Als u alle bestanden wilt scannen op labels zonder bestandsbeleid, schakelt u automatisch scannen in.

## <a name="terminology-overview"></a>Overzicht van de terminologie
-   Azure Information Protection-classificatielabel: een kenmerk dat wordt toegevoegd aan bestanden in uw organisatie. Dit gebeurt automatisch, op basis van een beleid of handmatig door eindgebruikers.
-   Extern: een label dat is ingesteld door iemand buiten uw organisatie.
-   Bestandslabel: de presentatie van het classificatielabel van een bestand in Cloud App Security. Dit veld wordt weergegeven voor elk bestand in de bestandstabel en kan worden gebruikt in filters.
-   Bestandsbeleid: een set regels op basis van bestandsfilters, waarmee u een breed scala aan geautomatiseerde processen kunt afdwingen, waarbij u gebruikmaakt van de API's van de cloudprovider.

## <a name="license-and-tenant-creation"></a>Licentie en tenant maken
Als u deze functie wilt inschakelen, moet u beschikken over een licentie voor Cloud App Security en een licentie voor Azure Information Protection Premium P1 of P2. Zodra beide licenties aanwezig zijn, synchroniseert Cloud App Security de labels van de organisatie uit de Azure Information Protection-service:

![voorbeeld van azip-scherm](./media/azip-screen.png)

![cas vergeleken met azip](./media/cas-compared-azip.png)
     
Daarnaast worden bestanden waarvan de inhoud wordt geïnspecteerd op basis van een of meer beleidsregels, standaard ook gescand op classificatielabels.

## <a name="gain-visibility"></a>Meer zichtbaarheid

De bestandslabels die zijn gescand voor elk bestand zijn zichtbaar in de bestandslade.
Klik op de pagina **Bestanden** op het relevante bestand om te zien of het bestandslabels heeft:

![bestandslade](./media/azip-file-drawer.png)

U kunt op de labels klikken om meer informatie te zien of de volledige lijst labels weer te geven:
 
![lijst met labels](./media/azip-tags-list.png)

Gebruik het filter **Bestandslabels** om te zoeken naar bestanden die zijn voorzien van een specifiek label:
 
![bestandslabelfilter](./media/azip-file-tags-filter.png)

Of naar bestanden die zijn voorzien van een willekeurig label:

![alle bestandslabelfilters](./media/azip-file-tags-all-filter.png)

## <a name="how-it-works"></a>Hoe het werkt
Nadat u Cloud App Security hebt verbonden met Azure Information Protection, scant Cloud App Security bestanden als volgt:
1. De lijst met alle classificatielabels binnen uw tenant wordt opgehaald. Dit wordt ieder uur uitgevoerd om te zorgen dat de lijst actueel is.
2. De bestanden worden gescand op classificatielabels. Dit kan op twee manieren gebeuren: a. Bestanden die op basis van een bestandsbeleid worden gescand op inhoud, worden ook toegevoegd aan de wachtrij voor het scannen op classificatielabels.
    b. Als u al uw bestanden wilt toevoegen aan de scanwachtrij zonder een bestandsbeleid in te instellen, schakelt u automatisch scannen in (zie hieronder), waarmee alle nieuwe of aangepaste bestanden worden gescand.
3. Externe labels worden alleen toegevoegd aan de lijst met classificatielabels als ze worden weergegeven voor een specifiek bestand, tenzij u het selectievakje **Azure Information Protection-classificatielabels van andere tenants negeren** inschakelt (zie hieronder).

## <a name="enable-automatic-scan"></a>Automatisch scannen inschakelen
Door automatisch scannen in te schakelen, is het mogelijk om naar Azure Information Protection-classificatielabels van uw Office 365-bestanden te zoeken zonder dat daarvoor een beleid gemaakt hoeft te worden. Deze functie is beschikbaar als u een zelfstandige licentie hebt voor Cloud App Security.
Automatisch scannen op bestandslabels van nieuwe bestanden inschakelen:

1. In Cloud App Security gaat u naar de pagina **Algemene instellingen**.
2. Selecteer onder de Azure-beveiligingsinstellingen de optie **Bestanden automatisch scannen op classificatielabels van Azure Information Protection**. Nadat u deze optie hebt ingeschakeld, worden alle nieuwe bestanden die worden toegevoegd aan Office 365, dus niet alleen de bestanden waarvan de inhoud wordt gescand op basis van een beleidsregel, ook gescand op bestandslabels.

![azure information protection inschakelen](./media/enable-azip.png)
 

## <a name="internal-and-external-tags"></a>Interne en externe labels
Standaard scant Cloud App Security op classificatielabels die in uw organisatie zijn gedefinieerd en op externe labels die zijn gedefinieerd door andere organisaties. 

Als u wilt dat deze genegeerd worden, selecteert u in de Cloud App Security-portal onder **Algemene instellingen** onder **Azure-beveiligingsinstellingen** de optie **Azure Information Protection-classificatielabels van andere tenants negeren**.
 
![labels negeren](./media/azip-ignore.png)

> [!Note]
> Als u in een testtenant werkt, is het beter om externe classificatielabels niet te negeren als u bestanden wilt testen die u van andere tenants ontvangt.

![azure information protection-labels in cloud app security](./media/azip-tags-in-cas.png)

## <a name="use-azure-information-protection-tags-to-apply-control"></a>Azure Information Protection-labels gebruiken voor controle
U kunt een bestandsbeleid maken in Cloud App Security om bestanden te zoeken die op de verkeerde manier zijn gedeeld, en om bestanden te vinden met een label, die onlangs zijn aangepast. 

**Beleid 1: vertrouwelijke gegevens die extern worden gedeeld op Box:**

1.  Maak een bestandsbeleid.
2.  Stel de naam, ernst en categorie van het beleid in.
3.  Voeg de volgende bestandsfilters toe om alle vertrouwelijke gegevens te vinden die extern worden gedeeld op Box:

![vertrouwelijkheidsbeleid](./media/azip-confidentiality-policy.png) 

**Beleid 2: beperkte gegevens die onlangs zijn gewijzigd buiten de map Financiën van SharePoint:**

1.  Maak een bestandsbeleid.
2.  Stel de naam, ernst en categorie van het beleid in.
3.  Voeg de volgende filters toe om alle beperkte bestanden te zoeken die onlangs zijn gewijzigd, en sluit de map Financiën uit van de zoekactie bij de optie voor het selecteren van mappen: 
 
![beleid voor beperkte gegevens](./media/azip-restricted-data-policy.png) 

U kunt ook waarschuwingen en meldingen voor gebruikers instellen of direct actie ondernemen op dit beleid.
Meer informatie over [beheeracties](governance-actions.md).

Lees meer informatie over [Azure Information Protection](https://docs.microsoft.com/en-us/information-protection/understand-explore/what-is-information-protection) en volg de zelfstudie [Snel aan de slag](https://docs.microsoft.com/en-us/information-protection/get-started/infoprotect-quick-start-tutorial) voor Azure Information Protection.

  

## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  



<!--HONumber=Dec16_HO1-->


