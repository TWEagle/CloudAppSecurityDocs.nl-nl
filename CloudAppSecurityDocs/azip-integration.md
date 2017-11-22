---
title: Azure Information Protection integreren met Cloud App Security | Microsoft Docs
description: Dit artikel bevat informatie over hoe u de labels van Azure Information Protection kunt gebruiken in Cloud App Security, voor meer controle over het gebruik van cloud-apps binnen uw organisatie.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/9/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 8168319a-199f-4e6c-ad68-e0f236480803
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 64fd889e309be254d5aa99320e040129a5de8e1d
ms.sourcegitcommit: fbeb299e8c41fc57b50d491b1becbf488fdd3642
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/14/2017
---
# <a name="azure-information-protection-integration"></a>Integratie van Azure Information Protection

Met Cloud App Security kunt u bestanden onderzoeken en beleid instellen op basis van classificatielabels van Azure Information Protection. Dat zorgt voor meer zichtbaarheid van en controle over uw gevoelige gegevens in de cloud. U hoeft slechts één selectievakje in te schakelen om Azure Information Protection te integreren met Cloud App Security. 

Door Azure Information Protection te integreren met Cloud App Security kunt u gebruikmaken van de kracht van beide services en bestanden beveiligen in de cloud. U beschikt over de volgende mogelijkheden:
- De mogelijkheid om alle geclassificeerde bestanden weer te geven op een centrale locatie.
- De mogelijkheid om onderzoek uit te voeren op basis van classificatieniveau en blootstelling van gevoelige gegevens te kwantificeren via uw cloudtoepassingen.
- De mogelijkheid om beleid te maken om ervoor te zorgen dat geclassificeerde bestanden correct worden verwerkt

> [!NOTE] 
> U schakelt deze functie moet u zowel een Cloud App Security-licentie en een licentie voor Azure Information Protection Premium P1 of P2. Als beide licenties gemaakt zijn, wordt de organisaties labels van de Azure Information Protection-service door Cloud App Security gesynchroniseerd.
> Cloud App Security biedt geen ondersteuning voor Azure Information Protection binnen het bereik van beleid.


## <a name="how-it-works"></a>Hoe het werkt
U bent waarschijnlijk bekend met classificatielabels voor bestanden in [Azure Information Protection](https://docs.microsoft.com/information-protection/). U kunt de Azure Information Protection-classificatielabels zien in Cloud App Security. Nadat u Cloud App Security hebt geïntegreerd in Azure Information Protection, scant Cloud App Security bestanden als volgt:
1. Cloud App Security haalt de lijst met alle classificatielabels binnen uw tenant op. Dit wordt ieder uur uitgevoerd om te zorgen dat de lijst actueel is.
2. Cloud App Security scant de bestanden dan als volgt op classificatielabels: a. Als u automatisch scannen (Zie de volgende) hebt ingeschakeld, worden alle nieuwe en gewijzigde bestanden worden toegevoegd aan de wachtrij van de scan.
    b. Als u een bestand (Zie hieronder) om te zoeken voor, classificatielabels, deze bestanden worden toegevoegd aan de wachtrij scan voor classificatielabels.
3. Zoals hierboven vermeld, gelden deze scans voor de classificatielabels die worden gedetecteerd tijdens de initiële scan die Cloud App Security uitvoert om vast te stellen welke classificatielabels in uw tenant worden gebruikt. Externe labels, classificatielabels die zijn ingesteld door iemand buiten uw tenant, worden toegevoegd aan de lijst met classificatielabels. Als u niet wilt zoeken naar deze, selecteert u de **alleen scannen bestanden voor Azure Information Protection classificatielabels van deze tenant** selectievakje (Zie hieronder).
4. Nadat u Azure Information Protection in Cloud App Security hebt ingeschakeld, worden ook alle nieuwe bestanden die aan Office 365 worden toegevoegd op classificatielabels gescand.

## <a name="how-to-integrate-azure-information-protection-with-cloud-app-security"></a>Azure Information Protection integreren met Cloud App Security
  
### <a name="enable-azure-information-protection"></a>Azure Information Protection inschakelen

Het enige wat u hoeft te doen om Azure Information Protection te integreren met Cloud App Security, is automatisch scannen instellen om te zoeken naar Azure Information Protection-classificatielabels in uw Office 365-bestanden zonder hiervoor een beleid te maken. Nadat u deze mogelijkheid hebt ingeschakeld, worden bestanden in uw cloudomgeving die een Azure Information Protection-classificatielabel hebben, weergegeven Cloud App Security.

U kunt Cloud App Security als volgt instellen om bestanden te scannen met inhoudsinspectie ingeschakeld voor classificatielabels:

1. Selecteer de pagina **Algemene instellingen** onder het tandwiel Instellingen in Cloud App Security.
2. Selecteer onder Azure Information Protection de optie **Bestanden automatisch scannen op classificatielabels van Azure Information Protection**. 

Nadat u Azure Information Protection hebt ingeschakeld, kunt u bestanden met classificatielabels zien en de bestanden op basis van label filteren in Cloud App Security.

 ![azure information protection inschakelen](./media/enable-azip.png)

> [!NOTE] 
> Automatisch scannen wordt de bestaande bestanden niet gescand totdat deze opnieuw worden gewijzigd. Als u bestaande bestanden wilt scannen voor classificatielabels van Azure Information Protection, moet u ten minste een **bestandsbeleid voor inhoudsinspectie** hebben. Als u dit nog niet hebt, maakt u een nieuw **bestandsbeleid**, verwijdert u alle vooraf ingestelde filters en schakelt u de optie **Inhoudsinspectie** in. Klik vervolgens onder **Inhoudsinspectie** op **Bestanden opnemen die overeenkomen met een vooraf ingestelde expressie**, selecteer een vooraf gedefinieerde waarde en sla het beleid op. Hierdoor inhoudscontrole die automatisch de classificatielabels Azure Information Protection detecteert.

### <a name="set-internal-and-external-tags"></a>Interne en externe labels instellen
Cloud App Security scant standaard classificatielabels die zijn gedefinieerd in uw organisatie, evenals externe waarden die zijn gedefinieerd door andere organisaties. 


Als u wilt dat deze extern ingestelde labels worden genegeerd, gaat u in de Cloud App Security-portal onder **Algemene instellingen** naar **Azure-beveiligingsinstellingen** en selecteert u de optie **Azure Information Protection-classificatielabels van andere tenants negeren**.
 
![labels negeren](./media/azip-ignore.png)

### <a name="control-file-exposure"></a>Blootstelling van bestanden beheren
- Als dit het document, wordt u gelabeld met een Azure Information Protection classificatie label:

![voorbeeld Azure Information Protection scherm](./media/azip-screen.png)

- Kunt u dit bestand in de Cloud App Security zien in de **bestanden** pagina met een filter voor de classificatie-label:

![Cloud App Security vergeleken met Azure Information Protection](./media/cas-compared-azip.png)

- U kunt meer informatie opvragen over deze bestanden en bijbehorende classificatielabels via de bestandslade.

- Klik op de pagina **Bestanden** op het betreffende bestand om te zien of het classificatielabels heeft:

![bestandslade](./media/azip-file-drawer.png)

- U kunt klikken op het classificatielabel om meer informatie weer te geven of om de volledige lijst met classificatielabels te bekijken:
 
![lijst met labels](./media/azip-tags-list.png)

- Vervolgens kunt u bestandsbeleid maken in Cloud App Security om bestanden te beheren die op de verkeerde manier zijn gedeeld, en om bestanden met een label te vinden die onlangs zijn aangepast.
- Daarnaast kunt u waarschuwingen activeren voor activiteiten met betrekking tot geclassificeerde bestanden.

![azure information protection-labels in cloud app security](./media/azip-tags-in-cas.png)

> [!Note]
> Wanneer Azure Identity Protection labels zijn uitgeschakeld op een bestand, wordt de uitgeschakelde labels verschijnen als uitgeschakeld in de Cloud App Security. Verwijderde labels worden niet weergegeven.


**Beleid 1: vertrouwelijke gegevens die extern worden gedeeld op Box:**

1.  Maak een bestandsbeleid.
2.  Stel de naam, de ernst en de categorie van het beleid.
3.  Voeg de volgende bestandsfilters toe om alle vertrouwelijke gegevens te vinden die extern worden gedeeld op Box:

![vertrouwelijkheidsbeleid](./media/azip-confidentiality-policy.png) 

**Beleid 2: beperkte gegevens die onlangs zijn gewijzigd buiten de map Financiën van SharePoint:**

1.  Maak een bestandsbeleid.
2.  Stel de naam, de ernst en de categorie van het beleid.
3.  Voeg de volgende filters toe om alle beperkte bestanden te zoeken die onlangs zijn gewijzigd, en sluit de map Financiën uit van de zoekactie bij de optie voor het selecteren van mappen: 
 
![beleid voor beperkte gegevens](./media/azip-restricted-data-policy.png) 

U kunt ook waarschuwingen en meldingen voor gebruikers instellen of direct actie ondernemen op dit beleid.
Meer informatie over [beheeracties](governance-actions.md).

Lees meer informatie over [Azure Information Protection](https://docs.microsoft.com/en-us/information-protection/understand-explore/what-is-information-protection) en volg de zelfstudie [Snel aan de slag](https://docs.microsoft.com/en-us/information-protection/get-started/infoprotect-quick-start-tutorial) voor Azure Information Protection.


## <a name="integration-with-azure-rights-management"></a>Integratie met Azure Rights Management

Uw organisatie moet Azure Rights Management in licentie en geactiveerd hebben voor integratie tussen Cloud App Security en Azure RMS. Deze twee afzonderlijke stappen vindt u in [Azure Rights Management activeren](https://docs.microsoft.com/information-protection/deploy-use/activate-service).

Cloud App Security ondersteunt momenteel systeemeigen beveiliging voor Office-bestanden (2016 en up-to-date). PDF-en afbeeldingsbestanden zijn beschikbaar in toekomstige versies. 

Deze functie is momenteel beschikbaar voor bestanden die zijn opgeslagen in SharePoint Online en OneDrive voor Bedrijven. In toekomstige versies worden meer cloud-apps ondersteund.

Nadat Cloud App Security is verbonden met uw Office 365-service, kunt u de Cloud App Security RMS-integratiefuncties gebruiken waarmee u documenten met RMS rechtstreeks in de Cloud App Security-portal als volgt kunt beveiligen:

1. Selecteer in de pagina **Bestanden** het bestand dat u wilt beveiligen, klik dan op de drie puntjes aan het einde van de bestandsrij en kies **Beveiligen**. 
![app beveiligen](./media/protect-app.png)
>[!NOTE]
>Azure Information Protection beschermt bestanden met een maximale grootte van 50 MB. 

2. U wordt gevraagd om een van de classificatielabels van uw organisatie te gebruiken voor het beveiligen van het bestand en klik op **beveiligen**. 
![beveiliging classificatie label](./media/protect-template.png)
3. Nadat u ervoor kiezen een classificatie-label en klik op beveiligen, Cloud App Security wordt de classificatie-label worden toegepast en beveiligt u het oorspronkelijke bestand.
> [!NOTE]
>   Het verdient aanbeveling bedrijfsbreed RMS classificatielabels toepassen op bestanden, zodat alle gebruikers in de organisatie toegang tot deze bestanden, met inbegrip van de oorspronkelijke eigenaar van het bestand zijn. De eigenaar van het bestand, het beleid voor het delen van het bestand en de lijst met gebruikers die al toegang hebben, veranderen niet wanneer het bestand wordt beveiligd.

4. Als gebruikers toegang willen tot het beveiligde bestand, moeten ze de RMS sharing-app op hun apparaat hebben geïnstalleerd. Zie voor meer informatie de [technisch overzicht en beveiligingsdetails voor de Microsoft Rights Management-toepassing voor delen](https://docs.microsoft.com/information-protection/rms-client/sharing-app-admin-guide-technical).

5. U kunt deze actie op elk gewenst moment terugdraaien in het **Beheerlogboek** door te klikken op de knop **Herstellen** aan het einde van de rij van de eerder genomen beveiligingsactie. 


Zie voor meer informatie over hoe Cloud App Security en Azure Information Protection samen [beveiligen van gegevens tegen fouten van de gebruiker](https://docs.microsoft.com/enterprise-mobility-security/solutions/protect-data-user-mistake).

 
## <a name="related-videos"></a>Verwante video 's  
[Cloud App Security + Azure Information Protection integraties](https://channel9.msdn.com/Shows/Microsoft-Security/MCAS--AIP-Integrations)  

## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
