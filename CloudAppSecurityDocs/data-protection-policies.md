---
title: Beleidsregels voor gegevensbescherming | Microsoft Docs
description: In dit onderwerp vindt u een beschrijving van de procedure voor het instellen van een gegevensbeleid om de gegevens en bestanden met betrekking tot het gebruik van cloud-apps in uw organisatie te beheren en te controleren.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: ac53fbd6-4d31-4bce-b2bc-9dc65ad83b3e
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: a413236b04726dddc69068e39967f6ad17218719
ms.openlocfilehash: ed0701c4513f9501e0b2e5a7b0b7931f5d76a628


---

# <a name="data-protection-policies"></a>Beleidsregels voor gegevensbescherming
    
## <a name="file-policies"></a>Beleidsregels voor bestanden  
Met Beleidsregels voor bestanden kunt u een breed scala aan geautomatiseerde processen controleren waarbij u gebruikmaakt van de API’s van de cloudprovider. Beleidsregels kunnen worden ingesteld voor het uitvoeren van continue scans voor naleving, juridische eDiscovery-taken, DLP voor gevoelige inhoud die openbaar is gedeeld en veel meer gebruiksvoorbeelden.  
Met Cloud App Security kunt u elk bestandstype controleren op basis van meer dan twintig metagegevensfilters (bijvoorbeeld toegangsniveau, bestandstype). 
 
**Ondersteunde bestandstypen** 

Met de ingebouwde DLP-engines van Cloud App Security worden inhoudsinspecties uitgevoerd door tekst te extraheren uit meer dan 100 algemene bestandstypen (Office-bestanden, Open Office-bestanden, gecomprimeerde bestanden, verschillende RTF-indelingen, XML- en HTML-bestanden, enzovoort).

De engine combineert drie aspecten onder elk beleid:  
  
-   Scan van de inhoud op basis van vooraf gedefinieerde sjablonen of aangepaste expressies.  
  
-   Contextfilters inclusief gebruikersrollen, metagegevens van bestanden, niveau van bestandsdeling, integratie met organisatie-eenheid, context van samenwerking en extra aanpasbare kenmerken.  
  
-   Automatische acties voor beheer en herstel. Zie voor meer informatie [Beheer](control.md).  
  
Wanneer het beleid is ingeschakeld, scant het beleid uw cloudomgeving voortdurend en worden bestanden geïdentificeerd die overeenkomen met de filters voor inhoud en context. Vervolgens worden de gevraagde geautomatiseerde acties toegepast. Deze beleidsregels detecteren en herstellen eventuele schendingen voor inactieve gegevens of wanneer er nieuwe inhoud wordt gemaakt. Beleidsregels kunnen worden gecontroleerd via realtimewaarschuwingen of met behulp van rapporten die met de console zijn gegenereerd.  
  
Hier volgen enkele voorbeelden van beleidsregels voor bestanden die kunnen worden gemaakt:  
  
-   Openbaar gedeelde bestanden:  
    Ontvang een waarschuwing over een bestand in uw cloud dat openbaar wordt gedeeld door alle bestanden te selecteren waarvan het niveau van bestandsdeling openbaar is.  
  
-   De openbaar gedeelde bestandsnaam bevat de naam van de organisatie:  
    Ontvang een waarschuwing over een bestand dat de naam van uw organisatie bevat en openbaar wordt gedeeld. Selecteer bestanden die de naam van uw organisatie bevatten en die openbaar worden gedeeld.  
  
-   Delen met externe domeinen:  
    Ontvang een waarschuwing over een bestand dat wordt gedeeld met accounts die eigendom zijn van de specifieke externe domeinen, bijvoorbeeld met het domein van een concurrent. Selecteer het externe domein waarmee u het delen wilt beperken.  
  
-   Gedeelde bestanden die niet worden gewijzigd tijdens de laatste periode in quarantaine plaatsen:  
    Ontvang een waarschuwing over gedeelde bestanden die niemand onlangs gewijzigd heeft, om ze in quarantaine te plaatsen of een geautomatiseerde actie in te schakelen. Sluit alle persoonlijke bestanden die niet zijn gewijzigd tijdens een opgegeven datumbereik uit. Op Google Apps kunt u deze bestanden in quarantaine plaatsen met behulp van het selectievakje ‘bestand in quarantaine plaatsen’ op de pagina voor het maken van een beleid.  
  
-   Delen met niet geautoriseerde gebruikers:  
    Ontvang een waarschuwing over bestanden die worden gedeeld met een niet geautoriseerde groep gebruikers in uw organisatie. Selecteer de gebruikers met wie delen niet is toegestaan.  
  
-   Gevoelige bestandsextensie:  
    Ontvang een waarschuwing over bestanden met specifieke extensies die mogelijk veel worden blootgesteld. Selecteer de specifieke extensie (bijvoorbeeld .crt voor certificaten) of bestandsnaam en sluit extensies en bestandsnamen waarbij het niveau voor bestandsdeling Privé is uit.  
  
Voer de volgende procedure uit om een nieuw bestandsbeleid te maken:  
  
1.  Klik in de console op **Beheer** gevolgd door **Beleidsregels**.  
  
2.  Klik op **Beleid maken** en selecteer **Bestandsbeleid**.  
  
3.  Geef uw beleid een naam en beschrijving, wat u indien gewenst kunt baseren op een sjabloon. Voor meer informatie over beleidssjablonen, bekijk [Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md).  
  
4.  Binnen **Type risico** koppelt u het beleid aan het meest geschikte type risico. Dit veld is alleen informatief en hiermee kunt u later zoeken naar specifieke beleidsregels en waarschuwingen, op basis van het type risico.  Het risico is mogelijk al vooraf geselecteerd volgens de categorie die u hebt gekozen om het beleid te maken. Beleidsregels voor bestanden zijn standaard ingesteld op DLP.  
  
5.  Om in te stellen door welke gedetecteerde apps dit beleid wordt geactiveerd **maakt u een filter voor de bestanden waarop dit beleid wordt toegepast**. Verfijn de beleidsfilters totdat u de meest nauwkeurige set bestanden hebt bereikt waarop u dit beleid wilt toepassen. Wees zo strikt mogelijk om valse positieven te voorkomen. Bijvoorbeeld, als u openbare machtigingen wilt verwijderen moet u het filter “Openbaar” toevoegen, als u een externe gebruiker wilt verwijderen gebruikt u het filter “Extern” enz.  
  
6.  Voor Box, SharePoint, Dropbox en OneDrive kunt u het bestandsbeleid afdwingen voor alle bestanden in de app of in specifieke mappen. Onder **Van toepassing op** selecteert u **Geselecteerde mappen** of **Alle bestanden met uitzondering van de geselecteerde mappen**. U wordt doorgestuurd om u aan te melden bij de cloud-app en vervolgens voegt u de relevante mappen toe.  
  
7.  Selecteer de **Methode voor inhoudscontrole**. Met de ingebouwde DLP kunt u bestanden filteren op de inhoud ervan. Als u bestanden wilt scannen op de inhoud, selecteert u vervolgens **Ingebouwde DLP**. Zodra inhoudscontrole is ingeschakeld, kunt u vooraf ingestelde expressies gebruiken of zoeken naar andere aangepaste expressies als een subtekenreeks of als een reguliere expressie van uzelf.  
    Bovendien kunt u een reguliere expressie opgeven als u een bestand wilt uitsluiten van de resultaten. Dit is zeer nuttig als u een standaard voor trefwoorden met de binnenste classificatie hebt die u wilt uitsluiten van het beleid.  
    Bovendien kunt u bepalen wat het minimumaantal schendingen van inhoud is dat moet worden bereikt voordat het bestand wordt beschouwd als een schending. U kunt bijvoorbeeld 10 kiezen als u waarschuwingen wilt ontvangen voor bestanden waarin ten minste 10 creditcardnummers worden gevonden.  
    Wanneer inhoud wordt vergeleken met de geselecteerde expressie, kunt u kiezen om de overeenkomst zelf te maskeren voor de meldingen en logboeken van schendingen. Als dit is ingeschakeld, wordt de schendende tekst vervangen door "X"-tekens. Denk eraan dat getallen worden vervangen door #-tekens en nooit worden opgeslagen in Cloud App Security.  
  
8.  Kies de **beheer**acties die in Cloud App Security moeten worden uitgevoerd wanneer een overeenkomst wordt gedetecteerd.  
  
9. Als u het beleid hebt gemaakt, vindt u dit op het tabblad **Bestandsbeleid**. U kunt een beleid altijd bewerken, de filters kalibreren of de geautomatiseerde acties wijzigen. Het beleid wordt automatisch ingeschakeld tijdens het maken en het begint direct met het scannen van uw cloudbestanden.  
  
> [!NOTE]  
>  Let goed op bij het instellen van beheeracties, want ze kunnen leiden tot onherstelbaar verlies van toegangsmachtigingen tot uw bestanden.  
> We bevelen aan om de filters te verfijnen tot de precieze bestanden waarbij actie moet worden ondernomen. Gebruik hiervoor meerdere zoekvelden. Hoe fijner de filters, hoe beter.  
>   
>  Als hulp kunt u de knop **Bewerken en voorbeeld van resultaten bekijken** in de sectie Filters gebruiken.  
  
![Bestandsbeleid bewerken en voorbeeld van de resultaten bekijken](./media/file-policy-edit-and-preview-results.png "file policy edit and preview results")  
  
10. Als u overeenkomsten voor een bestandsbeleid (bestanden waarvan wordt vermoed dat ze het beleid schenden) wilt weergeven, klikt u op **Controle** en vervolgens op **Beleidsregels**. Filter de resultaten met het filter **Type** bovenaan, zodat alleen de bestandsbeleidsregels worden weergegeven. Klik op een beleid voor meer informatie over de overeenkomsten voor elk beleid. Hiermee wordt de bestanden met actuele overeenkomsten voor het beleid weergegeven. Klik op het tabblad **Geschiedenis** om de geschiedenis tot zes maanden terug te zien van bestanden met een overeenkomst met het beleid.     
  
## <a name="file-policy-reference"></a>Verwijzing naar het bestandsbeleid  
In deze sectie vindt u naslaginformatie over beleidsregels, met een uitleg van elk beleidstype en de velden die voor elk beleid kunnen worden geconfigureerd. 
  
Een **bestandsbeleid** is een beleid op basis van API's waarmee u kunt beheren welke inhoud uw organisatie in de cloud bewaart, waarbij rekening wordt gehouden met meer dan twintig filters voor bestanden met metagegevens (waaronder eigenaar en niveau van bestandsdeling) en de resultaten van de inhoudscontrole. Op basis van de beleidsresultaten kunnen beheeracties worden toegepast. De engine voor inhoudscontrole kan worden uitgebreid via DLP-engines van derden en ook via antimalwareoplossingen.  
  
Elk beleid bestaat uit de volgende onderdelen:  
  
-   Bestandsfilters – hiermee kunt u zeer gedetailleerde voorwaarden op basis van metagegevens maken.  
  
-   Inhoudscontrole – hiermee kunt u het beleid verfijnen op basis van de resultaten van DLP-engines.  
  
-   Acties – het beleid bevat een reeks beheeracties die automatisch kunnen worden toegepast wanneer schendingen worden gevonden.  Deze worden onderverdeeld in samenwerkingsacties, beveiligingsacties en onderzoeksacties.

![Vervolgkeuzelijst voor bestandsbeheer](./media/file-governance-drop-down.png)
  
-   Extensies  
  
    > [!NOTE]  
    >  Extensies zijn alleen beschikbaar in de Technical Preview-versie van Cloud App Security.  
  
    -   Inhoudsinspectie kan worden uitgevoerd via engines van derden voor verbeterde DLP- of antimalwaremogelijkheden.  
  
    -   Beheeracties kunnen worden uitgevoerd via engines van derden voor het afdwingen van versleutelingsbeheer of andere typen bestandsverwerking (bijvoorbeeld aangepaste watermerken).  
  
## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO5-->

