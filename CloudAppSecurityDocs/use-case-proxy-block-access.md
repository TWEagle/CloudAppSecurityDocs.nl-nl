---
title: Het blokkeren van toegang tot de cloud-apps van niet-beheerde apparaten | Microsoft Docs
description: Dit onderwerp beschrijft het scenario voor het beveiligen van uw organisatie tegen toegang tot de cloud-apps van niet-beheerde apparaten.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/15/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 9aec9c6f-c9e2-4a4b-8b6a-2f8e4465ee3f
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b12fabca53c6174fb674f9de260eadb2c1311775
ms.sourcegitcommit: 84f358a5dd0ab7f362dd3a2cf9999a6184fba856
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2017
---
# <a name="blocking-access-to-cloud-apps-from-unmanaged-devices"></a>Toegang tot de cloud-apps van niet-beheerde apparaten blokkeren

Bring-your-own-device is in de zakelijke wereld is ideaal voor werknemers die u wilt maken van hun persoonlijke telefoons en tablets op de werkplek. Echter wilt veel IT-beheerders, op de hoogte van de bedreigingen die hierdoor ontstaat tot de gegevens en het netwerk, een organisatie kunnen toegang vanaf deze niet-beheerde apparaten tot bepaalde of alle van het bedrijf cloud-apps blokkeren. 

## <a name="how-does-cloud-app-security-detect-unmanaged-devices"></a>Hoe detecteert Cloud App Security niet-beheerde apparaten
.

>[!NOTE]
> Deze gebruiksvoorbeeld van toepassing op.

## <a name="the-threat"></a>DE BEDREIGING
Een Verkoopmanager in uw organisatie heeft een beheerd apparaat dat ze regelmatig gebruikt, maar soms wil iets in Salesforce op haar persoonlijke mobiele telefoon te controleren. Het telefoonnummer wordt niet beheerd door uw organisatie, wat betekent dat deze is geïnfecteerd met virussen en kwaadaardige software of mogelijk niet wachtwoord beveiligd en iedereen die deze opneemt voor toegang tot uw Salesforce-account kan worden.

## <a name="the-solution"></a>DE OPLOSSING
Beveiligen van uw organisatie door gebruik van cloud-app in de Cloud App Security controleren en maken van een beleid voor toegang bepalen en activiteiten van niet-beheerde apparaten te blokkeren.

## <a name="prerequisites"></a>Vereisten

[Implementeer](proxy-deployment.md) de Cloud App Security-Proxy voor Salesforce.

## <a name="set-up-unmanaged-device-detection"></a>Detectie van niet-beheerde apparaten instellen


## <a name="create-an-access-policy"></a>Een toegangsbeleid maken
Toegangsbeleid kunnen u bewaken aanmeldpogingen van uw gebruikers zich aanmelden bij cloud-apps en, indien nodig, ze toegang krijgen tot de app blokkeren.


1.  Klik in de console op **Beheer** gevolgd door **Beleidsregels**.  
  
2.  Klik op **beleid maken** en selecteer **toegangsbeleid**.  
  
3.  Geef uw beleid een naam en beschrijving, zoals **toegang blokkeren tot Salesforce vanaf niet-beheerde apparaten**.  
  
3. Geef een **ernstniveau van beleid** op voor uw beleid. Als u in Cloud App Security hebt ingesteld dat u meldingen krijgt over beleidsovereenkomsten voor een specifiek ernstniveau van beleid, wordt aan de hand hiervan bepaald of er op basis van de overeenkomsten van dit beleid een melding wordt gedaan.

4.  U kunt laten de **categorie** instellen als de **toegangsbeheer**.  
  
7. Onder **activiteitbron**, klikt u op **apps selecteren in de onderstaande lijst** en selecteer **Salesforce**.

8. Selecteer in het gedeelte van de filters activiteit **apparaattype** en vervolgens **is niet gelijk aan** en selecteer **compatibele**, **verbonden met het domein** en **geldig clientcertificaat**.
  
10. Op dit stadium, onder **acties** om te worden uitgevoerd wanneer het beleid wordt gevonden, selecteer:
    - Toestaan: Als u toestaat, kunnen gebruikers de bestanden te downloaden. 
    of
    
 
 >[!WARNING]
 >Het is raadzaam dat u geen **blok** gedownload voordat de eerste waarop het beleid **toestaan** modus en controleren of de resultaten zijn zoals verwacht en pas nadat u hebt vastgesteld dat het beleid niet iedereen onbedoeld blokkeert, schakelt u het beleid **blok** downloadt.
 
 9. Stel de waarschuwingen die u wilt ontvangen wanneer het beleid wordt vergeleken. U kunt een limiet kunt instellen, zodat u geen te veel waarschuwingen ontvangt en u kunt aangeven of de waarschuwingen krijgt als een e-mailbericht of SMS-bericht of beide.

10. Om weer te geven toegangsbeleid komt overeen met, klikt u op **besturingselement** en vervolgens **beleid**. Filteren van de resultaten om weer te geven alleen de beleidsregels voor toegang met behulp van de **Type** filter aan de bovenkant. Klik op een beleid voor meer informatie over de overeenkomsten voor elk beleid. Klik op de **geschiedenis** tabblad een historisch overzicht terug naar maximaal zes maanden van beleid overeenkomsten.     
  
## <a name="validate-your-policy"></a>Valideren van het beleid

1. Om te simuleren van een waarschuwing, van een onbeheerd apparaat probeert aan te melden in Salesforce.
3. Ga naar het beleidsrapport. Een beleid toegang overeenkomst moet binnenkort worden weergegeven. 
4. U kunt klikken op de overeenkomst om te zien wie er heeft geprobeerd om te registreren in Salesforce en vanaf welk apparaat. 

## <a name="blocking-access"></a>Toegang blokkeren

Nadat u het hebt gevalideerd en het beleid op uw wensen hebt afgestemd, verwijdert u mogelijke valse positieven die overeenkomen met uw beleid. Ga als volgt verder: 

1. Wanneer een toegangsbeleid is gekoppeld, kunt u het herstellen door het instellen van geautomatiseerde [beheeracties](governance-actions.md).

2. Om dit te doen, bewerkt u hiervoor hebt gemaakt en stel **acties** naar **blok** downloadt wanneer het beleid wordt vergeleken. De gebruiker zich niet ato toegang Salesforce vanaf elk apparaat dat niet wordt beheerd.
  
 
 ## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  