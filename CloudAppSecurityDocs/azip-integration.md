---
title: Azure Information Protection integreren met Cloud App Security | Microsoft Docs
description: Dit artikel bevat informatie over hoe u de labels van Azure Information Protection kunt gebruiken in Cloud App Security, voor meer controle over het gebruik van cloud-apps binnen uw organisatie.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/3/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 8168319a-199f-4e6c-ad68-e0f236480803
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 92182731b6ee80c24aa2f3d7836415b2dfa4da2c
ms.sourcegitcommit: c5533d66b8e037d6221c48bdbad81574f25f2817
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="azure-information-protection-integration"></a>Integratie van Azure Information Protection

Cloud App Security kunt u Azure Information Protection classificatielabels automatisch toepassen met of zonder beveiliging, op bestanden als bestand beleid governance actie. U kunt bestanden ook nagaan door te filteren voor het label toegepaste classificatie in de Cloud App Security-portal. Hierdoor kunnen meer zichtbaarheid en controle van uw vertrouwelijke gegevens in de cloud. U hoeft slechts één selectievakje in te schakelen om Azure Information Protection te integreren met Cloud App Security. 

Door Azure Information Protection te integreren met Cloud App Security kunt u gebruikmaken van de kracht van beide services en bestanden beveiligen in de cloud. U beschikt over de volgende mogelijkheden:
- De mogelijkheid om toe te passen classificatielabels als een beheeractie op bestanden die overeenkomen met specifieke beleidsregels
- De mogelijkheid om alle geclassificeerde bestanden weer te geven op een centrale locatie.
- De mogelijkheid om onderzoek uit te voeren op basis van classificatieniveau en blootstelling van gevoelige gegevens te kwantificeren via uw cloudtoepassingen.
- De mogelijkheid om beleid te maken om ervoor te zorgen dat geclassificeerde bestanden correct worden verwerkt


> [!NOTE] 
> Om deze functie inschakelt, moet u zowel een Cloud App Security-licentie en een licentie voor Azure Information Protection Premium P2. Als beide licenties gemaakt zijn, wordt de organisaties labels van de Azure Information Protection-service door Cloud App Security gesynchroniseerd.


## <a name="prerequisites"></a>Vereisten

- Met Azure Information Protection-integratie wilt werken, moet u inschakelen de [App-connector voor Office 365](connect-office-365-to-microsoft-cloud-app-security.md).

Cloud App Security ondersteunt momenteel toepassen Azure Information Protection-classificatielabels voor de volgende bestandstypen:

- Word: docm, docx, dotm, dotx
- Excel: xlam, xlsm, xlsx, xltx
- PowerPoint: potm, potx, ppsx, ppsm, pptm, pptx
- PDF-bestand is beschikbaar in toekomstige versies 

Deze functie is momenteel beschikbaar zijn voor bestanden die zijn opgeslagen in het vak, G Suite, SharePoint Online en OneDrive voor bedrijven. In toekomstige versies worden meer cloud-apps ondersteund.

Bestanden die zijn gelabeld met beveiliging buiten Cloud App Security kunnen momenteel gescand of gewijzigd door Cloud App Security. Bestanden die zijn gelabeld (zonder beveiliging) extern en Cloud App Security kan worden gescand en Cloud App Security kunt een ander label (met of zonder beveiliging) toepassen, zoals gedefinieerd in de Cloud App Security-beleid.


## <a name="how-it-works"></a>Hoe het werkt
U bent waarschijnlijk bekend met classificatielabels voor bestanden in [Azure Information Protection](https://docs.microsoft.com/information-protection/). U kunt de Azure Information Protection-classificatielabels zien in Cloud App Security. Nadat u Cloud App Security hebt geïntegreerd in Azure Information Protection, scant Cloud App Security bestanden als volgt:
1. Cloud App Security haalt de lijst met alle classificatielabels binnen uw tenant op. Dit wordt ieder uur uitgevoerd om te zorgen dat de lijst actueel is.
2. Cloud App Security scant de bestanden dan als volgt op classificatielabels: a. Als u automatische ingeschakeld scannen (Zie hieronder), alle nieuwe of gewijzigde bestanden worden toegevoegd aan de wachtrij scan en alle bestaande bestanden en opslagplaatsen worden gescand, ingedeeld en beveiligd.
    b. Als u een bestand (Zie hieronder) om te zoeken voor, classificatielabels, deze bestanden worden toegevoegd aan de wachtrij scan voor classificatielabels.
3. Zoals hierboven vermeld, gelden deze scans voor de classificatielabels die worden gedetecteerd tijdens de initiële scan die Cloud App Security uitvoert om vast te stellen welke classificatielabels in uw tenant worden gebruikt. Externe labels, classificatielabels die zijn ingesteld door iemand buiten uw tenant, worden toegevoegd aan de lijst met classificatielabels. Als u niet wilt zoeken naar deze, selecteert u de **alleen scannen bestanden voor Azure Information Protection classificatielabels van deze tenant** selectievakje (Zie hieronder).
4. Nadat u Azure Information Protection in Cloud App Security hebt ingeschakeld, worden ook alle nieuwe bestanden die aan Office 365 worden toegevoegd op classificatielabels gescand.
5. U kunt nieuwe beleidsregels in de Cloud App Security die van toepassing zijn de classificatielabels automatisch maken.

## <a name="how-to-integrate-azure-information-protection-with-cloud-app-security"></a>Azure Information Protection integreren met Cloud App Security
  
### <a name="enable-azure-information-protection"></a>Azure Information Protection inschakelen

Het enige wat u hoeft te doen om Azure Information Protection te integreren met Cloud App Security, is automatisch scannen instellen om te zoeken naar Azure Information Protection-classificatielabels in uw Office 365-bestanden zonder hiervoor een beleid te maken. Nadat u deze mogelijkheid hebt ingeschakeld, worden bestanden in uw cloudomgeving die een Azure Information Protection-classificatielabel hebben, weergegeven Cloud App Security.

U kunt Cloud App Security als volgt instellen om bestanden te scannen met inhoudsinspectie ingeschakeld voor classificatielabels:

1. Selecteer de pagina **Algemene instellingen** onder het tandwiel Instellingen in Cloud App Security.
2. Selecteer onder Azure Information Protection de optie **Bestanden automatisch scannen op classificatielabels van Azure Information Protection**. 

Nadat u Azure Information Protection hebt ingeschakeld, kunt u bestanden met classificatielabels zien en de bestanden op basis van label filteren in Cloud App Security. Nadat de Cloud App Security is verbonden met de cloud-app, kunt u zich de Cloud App Security Azure Information Protection-integratie-functies waarmee u kunt het toepassen van Azure Information Protection labels (met of zonder beveiliging) rechtstreeks in de Cloud kunnen gebruiken App Security-portal door deze rechtstreeks aan bestanden toe te voegen of door een bestandsbeleid om toe te passen classificatielabels automatisch als een beheeractie te configureren.


 ![azure information protection inschakelen](./media/enable-azip.png)

> [!NOTE] 
> Automatisch scannen wordt de bestaande bestanden niet gescand totdat deze opnieuw worden gewijzigd. Als u bestaande bestanden wilt scannen voor classificatielabels van Azure Information Protection, moet u ten minste een **bestandsbeleid voor inhoudsinspectie** hebben. Als u dit nog niet hebt, maakt u een nieuw **bestandsbeleid**, verwijdert u alle vooraf ingestelde filters en schakelt u de optie **Inhoudsinspectie** in. Klik vervolgens onder **Inhoudsinspectie** op **Bestanden opnemen die overeenkomen met een vooraf ingestelde expressie**, selecteer een vooraf gedefinieerde waarde en sla het beleid op. Hierdoor inhoudscontrole die automatisch de classificatielabels Azure Information Protection detecteert.

#### <a name="set-internal-and-external-tags"></a>Interne en externe labels instellen
Cloud App Security scant standaard classificatielabels die zijn gedefinieerd in uw organisatie, evenals externe waarden die zijn gedefinieerd door andere organisaties. 


Als u wilt dat deze extern ingestelde labels worden genegeerd, gaat u in de Cloud App Security-portal onder **Algemene instellingen** naar **Azure-beveiligingsinstellingen** en selecteert u de optie **Azure Information Protection-classificatielabels van andere tenants negeren**.
 
![labels negeren](./media/azip-ignore.png)

### <a name="apply-labels-directly-to-files"></a>Labels rechtstreeks toepassen op bestanden

1. Van de **bestanden** pagina, selecteert u het bestand dat u wilt beveiligen en klik op de drie punten aan het einde van de rij van het bestand en kies **toepassen classificatie label**.

 ![Beveilig-app](./media/protect-app.png)
  
  >[!NOTE]
  > Cloud App Security kunt Azure Information Protection toepassen op bestanden die maximaal 50 MB zijn.  

2. U wordt gevraagd om een van de classificatielabels van uw organisatie op het bestand wilt toepassen en klik op **toepassen**. 
![beveiliging classificatie label](./media/protect-template.png)

3. Nadat u kiest een classificatie-label en klik op toepassen, Cloud App Security wordt het label voor de classificatie van toepassing op het oorspronkelijke bestand.

5. U kunt ook classificatielabels verwijderen door het kiezen van de **classificatie-label verwijderen** optie. 


Zie voor meer informatie over hoe Cloud App Security en Azure Information Protection samen [beveiligen van gegevens tegen fouten van de gebruiker](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-data-user-mistake).

### <a name="automatically-label-files-preview"></a>Automatisch labelbestanden (preview)

U kunt automatisch classificatielabels toepassen op bestanden door het maken van een beleid voor bestanden en de instelling **toepassen classificatie label** als de beheeractie.

Volg deze instructies voor het bestandsbeleid maken:

1.  Maak een bestandsbeleid.
2.  Stel het beleid met inbegrip van het type bestand dat u wilt detecteren, bijvoorbeeld alle bestanden waar **toegangsniveau** is niet gelijk aan **intern** en waar de **eigenaar OE** gelijk is aan uw Finance team. 
3.  Onder beheeracties voor de relevante app **toepassen van een label classificatie** en selecteer vervolgens het labeltype.

   ![Label worden toegepast](./media/aip-gov-action.png)

> [!NOTE]
> De mogelijkheid om automatisch een Azure Information Protection-label via beleid voor bestanden is een krachtige functie. Om klanten te beschermen van per ongeluk een label wordt toegepast op een groot aantal bestanden, omdat er een veiligheidsmaatregel een dagelijkse limiet van 100 **toepassen label** acties per app per tenant. Nadat de dagelijkse limiet is bereikt, wordt de label-actie toepassen tijdelijk wordt onderbroken en wordt automatisch voortgezet de volgende dag (na 12:00 UTC). De limiet voor uw tenant verhogen [contact op met ondersteuning voor Cloud App Security](mailto:cascoresupport@microsoft.com).

### <a name="control-file-exposure"></a>Blootstelling van bestanden beheren

- Als dit het document dat u gelabeld met een Azure Information Protection classificatie label:

   ![voorbeeld Azure Information Protection scherm](./media/azip-screen.png)

- Kunt u dit bestand in de Cloud App Security zien in de **bestanden** pagina met een filter voor de classificatie-label:

   ![Cloud App Security vergeleken met Azure Information Protection](./media/cas-compared-azip.png)

- U kunt meer informatie over deze bestanden en hun classificatielabels krijgen in de bestandslade door te klikken op het relevante bestand in de **bestanden** pagina en controleer of er een label classificatie:

   ![bestandslade](./media/azip-file-drawer.png)

- Vervolgens kunt u bestandsbeleid maken in Cloud App Security om bestanden te beheren die op de verkeerde manier zijn gedeeld, en om bestanden met een label te vinden die onlangs zijn aangepast.
- Daarnaast kunt u waarschuwingen activeren voor activiteiten met betrekking tot geclassificeerde bestanden.

  ![azure information protection-labels in cloud app security](./media/azip-tags-in-cas.png)

- U kunt ook een beleid dat automatisch een label classificatie voor specifieke bestanden geldt maken.


> [!Note]
> Wanneer Azure Identity Protection labels zijn uitgeschakeld op een bestand, wordt de uitgeschakelde labels verschijnen als uitgeschakeld in de Cloud App Security. Verwijderde labels worden niet weergegeven.


**Voorbeeld beleid - vertrouwelijke gegevens die extern wordt gedeeld op het selectievakje:**

1.  Maak een bestandsbeleid.
2.  Stel de naam, de ernst en de categorie van het beleid.
3.  Voeg de volgende bestandsfilters toe om alle vertrouwelijke gegevens te vinden die extern worden gedeeld op Box:

![vertrouwelijkheidsbeleid](./media/azip-confidentiality-policy.png) 

**Voorbeeld beleid - vertrouwelijke gegevens die onlangs is gewijzigd buiten de map Finance op SharePoint:**

1.  Maak een bestandsbeleid.
2.  Stel de naam, de ernst en de categorie van het beleid.
3.  Voeg de volgende filters toe om alle beperkte bestanden te zoeken die onlangs zijn gewijzigd, en sluit de map Financiën uit van de zoekactie bij de optie voor het selecteren van mappen: 
 
![beleid voor beperkte gegevens](./media/azip-restricted-data-policy.png) 

U kunt ook waarschuwingen en meldingen voor gebruikers instellen of direct actie ondernemen op dit beleid.
Meer informatie over [beheeracties](governance-actions.md).

Lees meer informatie over [Azure Information Protection](https://docs.microsoft.com/en-us/information-protection/understand-explore/what-is-information-protection) en volg de zelfstudie [Snel aan de slag](https://docs.microsoft.com/en-us/information-protection/get-started/infoprotect-quick-start-tutorial) voor Azure Information Protection.


 
## <a name="related-videos"></a>Verwante video 's  
[Cloud App Security + Azure Information Protection integraties](https://channel9.msdn.com/Shows/Microsoft-Security/MCAS--AIP-Integrations)  

## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
