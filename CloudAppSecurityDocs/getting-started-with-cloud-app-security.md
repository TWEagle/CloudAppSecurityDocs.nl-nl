---
title: Aan de slag met Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u een overzicht van de taken die u moet uitvoeren om aan de slag te gaan met Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cf040b18-93d1-41e8-a26a-647c56afb00f
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 8b454edde557c408b644c9bff6f7bf6136ba9819


---

# <a name="getting-started-with-cloud-app-security"></a>Aan de slag met Cloud App Security
Cloud App Security helpt klanten te profiteren van de voordelen van cloudtoepassingen, waarbij de controle behouden kan blijven dankzij verbeterde zichtbaarheid van activiteiten en verhoogde bescherming van essentiële bedrijfsgegevens.  Deze documentatie leidt u door de volgende stappen om aan de slag te gaan met Cloud App Security.  
  
Uw organisatie moet beschikken over een licentie voor Cloud App Security om het product te kunnen gebruiken. Voor meer informatie raadpleegt u [Cloud App Security aanschaffen](https://www.microsoft.com/server-cloud/products/cloud-app-security/default.aspx) en kijkt u bij de [Licentieresources](https://www.microsoft.com/server-cloud/products/cloud-app-security/default.aspx).  
  
>[!NOTE]
>Een Office 365-licentie is niet vereist voor Cloud App Security.  
  
## <a name="get-started-quickly-with-cloud-app-security"></a>Snel aan de slag met Cloud App Security  
  
|Wat u moet doen:|Taak|Nodig?|Procedure:|Beschrijving|  
|-------------------------|----------|---------------|-------------|-----------------|  
|STAP 1. [Stel Cloud Discovery in](set-up-cloud-discovery.md).|Verkeerslogboeken uploaden|Vereist|**Een doorlopend Cloud Discovery-rapport maken**<br /><br /> 1.   Ga naar **Instellingen** -> **Cloud Discovery-instellingen**.<br /><br /> 2.    Klik op **Logboek automatisch uploaden**.<br /><br /> 3.   Voeg uw gegevensbronnen toe op het tabblad **Gegevensbronnen**.<br /><br /> 4.    Configureer logboekverzamelaar op het tabblad **Logboekverzamelaars**.<br /><br /> Een momentopnamerapport van Cloud Discovery maken<br /><br /> 1.    Ga naar **Detecteren** -> **Nieuw momentopnamerapport maken** en volg de stappen.|**Waarom zou ik Cloud Discovery-rapporten configureren?** Inzicht krijgen in Shadow IT is essentieel voor uw organisatie.  <br />Nadat de logboeken zijn geanalyseerd, kunt u gemakkelijk ontdekken welke cloud-apps worden gebruikt, door welke mensen ze worden gebruikt en op welke apparaten.|  
|STAP 2. [Schakel directe zichtbaarheid, beveiliging en beheeracties in voor uw apps](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).|Apps koppelen|Vereist|1.   Ga naar **Instellingen** -> **Goedgekeurde apps**.<br /><br /> 2. Klik op **App koppelen** en kies een app.<br /><br /> 3. Volg de configuratiestappen om de app te koppelen.|**Waarom moet ik een app koppelen?**<br /><br /> U kunt alleen beter inzicht krijgen in de activiteiten, bestanden en accounts in uw cloudomgeving voor uw cloud-apps nadat u een app hebt gekoppeld.|  
|STAP 3. [Beheer cloud-apps met beleid](control-cloud-apps-with-policies.md).|Beleidsregels maken|Vereist|**Beleidsregels maken**<br /><br /> 1.  Ga naar **Controle** -> **Sjablonen**.<br /><br /> 2.    Kies een beleidssjabloon in de lijst en klik op (+) **Beleid maken**.<br /><br /> 3.  Pas het beleid aan uw behoeften aan door filters, acties en andere configuraties te kiezen en klik vervolgens op **Maken**.<br /><br /> 4.    Klik op het tabblad **Beleidsregels** op het beleid dat u hebt gemaakt om de relevante overeenkomsten (activiteiten, bestanden, waarschuwingen, enzovoort) te bekijken.<br /><br /> Tip: maak voor elke **risicocategorie** een beleid, zodat alle beveilligingsscenario's voor uw cloudomgeving zijn gedekt.|**Hoe kunnen beleidsregels mijn organisatie helpen?**<br /><br /> Beleidsregels bieden u de hulpmiddelen om trends te bewaken, beveiligingsdreigingen in te zien en aangepaste rapporten en waarschuwingen te genereren. Met beleidsregels kunt u verschillende beheeracties, DLP en besturingselementen voor het delen van bestanden maken.|  
|STAP 4. [Personaliseer uw ervaring](general-setup.md#Adallom_mailsettings).|De gegevens van uw organisatie toevoegen|Aanbevolen|**E-mailinstellingen invoeren**<br /><br /> 1. Ga naar **Instellingen** -> **E-mailinstellingen**.<br /><br /> 2.   Voer uw e-mailadressen en weergavenaam in onder **Identiteit afzender**.<br /><br /> 3. Upload de e-mailsjabloon van uw organisatie onder **E-mailontwerp**.<br /><br /> **Meldingen voor beheerders instellen**<br /><br /> 1.    Klik op uw gebruikersnaam in de navigatiebalk en ga naar **Gebruikersinstellingen**.<br /><br /> 2.    Configureer onder **Meldingen** de methoden die u wilt instellen voor systeemmeldingen.<br /><br /> 3.  Klik op **Opslaan**.<br /><br /> **Metrische gegevens voor de score aanpassen**<br /><br /> 1.  Ga naar **Instellingen** -> **Cloud Discovery-instellingen**.<br /><br /> 2.    Configureer het belang van verschillende risicowaarden onder **Configuratie scorewaarden**.<br /><br /> 3.    Klik op **Opslaan**.<br /><br /> De risicoscores die zijn gegeven aan de gedetecteerde apps worden nu nauwkeurig geconfigureerd op basis van de behoeften en prioriteiten van uw organisatie.|**Waarom zou ik de omgeving aan mijn persoonlijke voorkeuren aanpassen?**<br /><br /> Sommige functies werken het beste wanneer u ze aanpast aan uw behoeften.  <br />Biedt uw gebruikers een betere ervaring met uw eigen e‑mailsjablonen, besluit welke meldingen u ontvangt en pas de risicoscorewaarden aan zodat deze aansluiten bij de voorkeuren van uw organisatie.|  
|STAP 5. [Organiseer de gegevens naar eigen gelang](general-setup.md#IPtagsandRanges).|Belangrijke instellingen configureren|Aanbevolen|**IP-adrestags maken**<br /><br /> 1.   Ga naar **Instellingen** -> **IP-adrestags**.<br /><br /> 2. Klik op (+) **IP-adresbereik toevoegen**.<br /><br /> 3.    Voer de **details**, **locatie**, **labels** en **categorie** van het IP-bereik in.<br /><br /> 4. Klik op **Maken**.<br /><br /> U kunt nu IP-labels gebruiken bij het aanmaken van beleidsregels, bij het filteren en bij het aanmaken van gegevensweergaven.<br /><br /> **Weergaven maken**<br /><br /> 1.  Ga naar **Instellingen** -> **Cloud Discovery-instellingen**.<br /><br /> 2.    Klik onder **Gegevensweergaven** op (+) **Gegevensweergave toevoegen**.<br /><br /> 3.  Volg de configuratiestappen.<br /><br /> 4.  Klik op **Aanmaken**.<br /><br /> U kunt nu gedetecteerde gegevens weer laten geven op basis van uw eigen voorkeuren zoals bedrijfseenheden of IP-adresbereiken.<br /><br /> **Domeinen toevoegen**<br /><br /> 1.    Ga naar **Instellingen** -> **Algemene instellingen**.<br /><br /> 2.    Voeg de interne domeinen van uw organisatie toe onder **Organisatiedetails**.<br /><br /> 3. Klik op **Opslaan**.|**Waarom moet ik deze instellingen configureren?**<br /><br /> Deze instellingen leiden tot beter en eenvoudiger beheer van verschillende functies in de console. Met IP-labels is het eenvoudiger om beleidsregels aan te maken die aan uw behoeften voldoen, evenals om nauwkeurig gegevens te filteren. Gebruik gegevensweergaven om uw gegevens in logische categorieën te groeperen.|  
  
## <a name="see-also"></a>Zie ook  
[Algemene instellingen](general-setup.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


