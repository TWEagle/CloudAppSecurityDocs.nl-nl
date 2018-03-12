---
title: Beleidregels maken voor het controleren en beveiligen van bestanden in uw cloud-apps | Microsoft Docs
description: In dit onderwerp vindt u een beschrijving van de procedure voor het instellen van een gegevensbeleid om de gegevens en bestanden met betrekking tot het gebruik van cloud-apps in uw organisatie te beheren en te controleren.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/11/2018
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: ac53fbd6-4d31-4bce-b2bc-9dc65ad83b3e
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 63024ea9395c6f765928076a8d6eb9861fa35238
ms.sourcegitcommit: 2f1ccff60194573325afa01f1634eea373c829b6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/12/2018
---
# <a name="file-policies"></a>Beleidsregels voor bestanden  
Met Beleidsregels voor bestanden kunt u een breed scala aan geautomatiseerde processen controleren waarbij u gebruikmaakt van de API’s van de cloudprovider. Beleidsregels kunnen worden ingesteld om te bieden continue scans voor naleving, juridische eDiscovery-taken, DLP voor gevoelige inhoud openbaar, gedeeld en veel meer gebruiksvoorbeelden.  <br></br>

Met Cloud App Security kunt u elk bestandstype controleren op basis van meer dan twintig metagegevensfilters (bijvoorbeeld toegangsniveau, bestandstype). 
 
**Ondersteunde bestandstypen** 

Cloud App Security ingebouwde DLP engines inhoudscontrole uitvoeren door het extraheren van tekst uit alle algemene bestandstypen (100 +) zoals Office, Open Office gecomprimeerde bestanden, verschillende RTF-indelingen, XML, HTML en meer.

De engine combineert drie aspecten onder elk beleid:  
  
-   Scan van de inhoud op basis van vooraf gedefinieerde sjablonen of aangepaste expressies.  
  
-   Contextfilters inclusief gebruikersrollen, metagegevens van bestanden, niveau, integratie van de organisatie-eenheid, context van samenwerking en extra aanpasbare kenmerken delen.  
  
-   Automatische acties voor beheer en herstel. Zie voor meer informatie [Beheer](control.md).  
  
Eenmaal is ingeschakeld, het beleid continu scant uw cloudomgeving en identificeren van bestanden die overeenkomen met de inhoud en context filters en de gevraagde geautomatiseerde acties toegepast. Deze beleidsregels detecteren en herstellen eventuele schendingen voor gegevens in rust of wanneer nieuwe inhoud wordt gemaakt. Beleidsregels kunnen worden gecontroleerd via realtimewaarschuwingen of met behulp van rapporten die met de console zijn gegenereerd.  
  
Hier volgen enkele voorbeelden van beleidsregels voor bestanden die kunnen worden gemaakt:  
  
-   Openbaar gedeelde bestanden: <br></br>
    Ontvang een waarschuwing over een bestand in uw cloud dat openbaar wordt gedeeld door alle bestanden te selecteren waarvan het niveau van bestandsdeling openbaar is.  
  
-   De openbaar gedeelde bestandsnaam bevat de naam van de organisatie: <br></br> Ontvang een waarschuwing over een bestand dat de naam van uw organisatie bevat en openbaar wordt gedeeld. Selecteer bestanden die de naam van uw organisatie bevatten en die openbaar worden gedeeld.  
  
-   Delen met externe domeinen:  <br></br>
    Ontvang een waarschuwing over een bestand dat wordt gedeeld met accounts die eigendom zijn van de specifieke externe domeinen, bijvoorbeeld met het domein van een concurrent. Selecteer het externe domein waarmee u het delen wilt beperken.  
  
-   Gedeelde bestanden die niet worden gewijzigd tijdens de laatste periode in quarantaine plaatsen:  <br></br>
    Ontvang een waarschuwing over gedeelde bestanden die niemand onlangs gewijzigd heeft, om ze in quarantaine te plaatsen of een geautomatiseerde actie in te schakelen. Sluit alle persoonlijke bestanden die niet zijn gewijzigd tijdens een opgegeven datumbereik uit. In G Suite kunt u deze bestanden in quarantaine plaatsen met behulp van het selectievakje 'bestand in quarantaine plaatsen' op de pagina voor het maken van een beleid.  
  
-   Delen met niet geautoriseerde gebruikers:  <br></br>
    Ontvang een waarschuwing over bestanden die worden gedeeld met een niet geautoriseerde groep gebruikers in uw organisatie. Selecteer de gebruikers voor wie delen is niet toegestaan.  
  
-   Gevoelige bestandsextensie:  <br></br>
    Ontvang een waarschuwing over bestanden met specifieke extensies die mogelijk maximaal beschikbaar worden gesteld. Selecteer de specifieke extensie (bijvoorbeeld .crt voor certificaten) of bestandsnaam en sluit extensies en bestandsnamen waarbij het niveau voor bestandsdeling Privé is uit.  
  
Voer de volgende procedure uit om een nieuw bestandsbeleid te maken:  
  
1.  Klik in de console op **Beheer** gevolgd door **Beleidsregels**.  
  
2.  Klik op **Beleid maken** en selecteer **Bestandsbeleid**.  
  
3.  Geef uw beleid een naam en beschrijving, wat u indien gewenst kunt baseren op een sjabloon. Voor meer informatie over beleidssjablonen, bekijk [Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md).  
  
3. Geef een **ernstniveau van beleid** op voor uw beleid. Als u Cloud App Security meldingen verzendt op overeenkomt met beleid voor een specifiek beleid ernstniveau hebt ingesteld, wordt dit gebruikt om te bepalen of dit beleid komt overeen met een melding geactiveerd.

4.  Binnen **Categorie** koppelt u het beleid aan het meest geschikte type risico. Dit veld is alleen informatief en hiermee kunt u later zoeken naar specifieke beleidsregels en waarschuwingen, op basis van het type risico.  Het risico is mogelijk al vooraf geselecteerd volgens de categorie die u hebt gekozen om het beleid te maken. Beleidsregels voor bestanden zijn standaard ingesteld op DLP.  
  
5.  Om in te stellen welke gedetecteerde apps dit beleid geactiveerd **maken van een filter voor de bestanden die dit beleid wordt toegepast op**. Verfijn de beleidsfilters totdat u de meest nauwkeurige set bestanden hebt bereikt waarop u dit beleid wilt toepassen. Wees zo strikt mogelijk om valse positieven te voorkomen dat. Als u bijvoorbeeld openbare machtigingen wilt verwijderen moet u het filter **Openbaar** toevoegen, als u een externe gebruiker wilt verwijderen gebruikt u het filter Extern enzovoort.  
> [!NOTE] 
> Wanneer u de beleidsfilters **bevat** wordt alleen gezocht naar volledige woorden die zijn gescheiden door komma's, punten, spaties of onderstrepingstekens bevatten. Bijvoorbeeld als u zoeken naar **malware** of **virus**, wordt virus_malware_file.exe gevonden maar malwarevirusfile.exe niet gevonden. Als u zoekt **malware.exe**, en u alle bestanden met kwaadaardige software of exe in de bestandsnaam, vinden dat als u zoekt **"malware.exe"** (met aanhalingstekens) vindt u alleen bestanden die bevatten precies "malware.exe". **Is gelijk aan** wordt alleen gezocht naar de volledige tekenreeks, bijvoorbeeld als u zoeken naar **malware.exe** malware.exe gevonden maar malware.exe.txt niet gevonden.  
6.   Selecteer **geselecteerde mappen** of **alle bestanden uitgezonderd geselecteerde mappen** onder het eerste filter **Toepassen op** voor Box, SharePoint, Dropbox, OneDrive. Hier kunt u uw bestandsbeleid doorvoeren voor alle bestanden in de app of in specifieke mappen. U wordt omgeleid voor aanmelding bij de cloud-app en voeg vervolgens de relevante mappen.  

6. Onder het tweede filter **Toepassen op** selecteert u **alle bestandsbeheerders**, **bestandsbeheerders van geselecteerde gebruikersgroepen** of **alle bestandsbeheerders uitgezonderd geselecteerde groepen**, en selecteert u de relevante gebruikersgroepen om te bepalen welke gebruikers en groepen moeten worden opgenomen in het beleid.
  
7.  Selecteer de **Methode voor inhoudscontrole**. Met de ingebouwde DLP kunt u bestanden filteren op de inhoud ervan. Als u bestanden wilt scannen op de inhoud, selecteert u vervolgens **Ingebouwde DLP**. Zodra inhoudscontrole is ingeschakeld, kunt u vooraf ingestelde expressies gebruiken of zoeken naar andere aangepaste expressies als een subtekenreeks of als een [reguliere expressie](working-with-the-regex-engine.md) van uzelf.  <br></br>

    Bovendien kunt u een reguliere expressie opgeven als u een bestand wilt uitsluiten van de resultaten. Dit is zeer nuttig als u een standaard voor trefwoorden met de binnenste classificatie hebt die u wilt uitsluiten van het beleid. <br></br> U kunt bepalen wat het minimumaantal schendingen van inhoud is dat moet worden bereikt voordat het bestand wordt beschouwd als een schending. U kunt bijvoorbeeld 10 kiezen als u waarschuwingen wilt ontvangen voor bestanden waarin ten minste 10 creditcardnummers worden gevonden.  <br></br>
    Wanneer inhoud wordt vergeleken met de geselecteerde expressie, wordt de schendende tekst vervangen door 'X' tekens. Standaard worden schendingen gemaskeerd en weergegeven in de context dat 100 tekens voor en na de schending. Getallen in de context van de expressie worden vervangen door #-tekens en worden nooit opgeslagen in Cloud App Security. U kunt de optie voor **Ontmaskert u de laatste vier tekens van een schending** om te maskeren, de laatste vier tekens van de schending zelf. U hoeft in te stellen welke gegevenstypen van de reguliere expressie zoekopdrachten: de naam van inhoud, metagegevens en/of bestand. Standaard zoekt de inhoud en de metagegevens. U moet ten minste één gegevenstype voor de zoekopdracht selecteren of de reguliere expressie kan niet werken en het beleid kan niet worden gemaakt. 
  
8.  Kies de **beheer**acties die in Cloud App Security moeten worden uitgevoerd wanneer een overeenkomst wordt gedetecteerd.  
  
9. Als u het beleid hebt gemaakt, vindt u dit op het tabblad **Bestandsbeleid**. U kunt altijd een beleid bewerken, de filters kalibreren of de geautomatiseerde acties wijzigen. Het beleid wordt automatisch ingeschakeld tijdens het maken en start het scannen van uw cloud-bestanden direct.  Let goed op bij het instellen van beheeracties, want ze kunnen leiden tot onherstelbaar verlies van toegangsmachtigingen tot uw bestanden. We bevelen aan om de filters te verfijnen tot de precieze bestanden waarbij actie moet worden ondernomen. Gebruik hiervoor meerdere zoekvelden. Hoe fijner de filters, hoe beter. Als hulp kunt u de knop **Bewerken en voorbeeld van resultaten bekijken** in de sectie Filters gebruiken.  
  
   ![bestandsbeleid bewerken en voorbeeld van resultaten](./media/file-policy-edit-and-preview-results.png "bestandsbeleid bewerken en voorbeeld van resultaten")  
  
10. Als u overeenkomsten voor een bestandsbeleid (bestanden waarvan wordt vermoed dat ze het beleid schenden) wilt weergeven, klikt u op **Controle** en vervolgens op **Beleidsregels**. Filter de resultaten met het filter **Type** bovenaan, zodat alleen de bestandsbeleidsregels worden weergegeven. Klik op een beleid voor meer informatie over de overeenkomsten voor elk beleid. Hiermee wordt de bestanden met actuele overeenkomsten voor het beleid weergegeven. Klik op de **geschiedenis** tabblad een historisch overzicht terug naar maximaal zes maanden van bestanden die overeenkomen met het beleid.     
  
## <a name="file-policy-reference"></a>Verwijzing naar het bestandsbeleid  
In deze sectie vindt u naslaginformatie over beleidsregels, met een uitleg van elk beleidstype en de velden die voor elk beleid kunnen worden geconfigureerd. 
  
Een **bestandsbeleid** is een beleid op basis van API's waarmee u kunt beheren welke inhoud uw organisatie in de cloud bewaart, waarbij rekening wordt gehouden met meer dan twintig filters voor bestanden met metagegevens (waaronder eigenaar en niveau van bestandsdeling) en de resultaten van de inhoudscontrole. Op basis van de beleidsresultaten kunnen beheeracties worden toegepast. De engine voor inhoudscontrole kan worden uitgebreid via DLP-engines van derden en ook via antimalwareoplossingen.  
  
Elk beleid bestaat uit de volgende onderdelen:  
  
-   Bestandsfilters – Hiermee kunt u gedetailleerde voorwaarden op basis van metagegevens maken.  
  
-   Inhoudscontrole – hiermee kunt u het beleid verfijnen op basis van de resultaten van DLP-engines. U kunt een aangepaste expressie of een vooraf ingestelde expressie opnemen. Er kunnen uitsluitingen worden ingesteld en u kunt het aantal overeenkomsten kiezen. U kunt ook anonimiseren om de gebruikersnaam te maskeren. 
  
-   Acties – het beleid bevat een reeks beheeracties die automatisch kunnen worden toegepast wanneer schendingen worden gevonden.  Deze zijn acties samenwerking, beveiligingsacties en onderzoek acties verdeeld.

-   Extensies  
   
    -  Inhoudsinspectie kan worden uitgevoerd via engines van derden voor verbeterde DLP- of antimalwaremogelijkheden.  

  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  