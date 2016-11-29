---
title: Aan de slag met Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u een overzicht van de taken die u moet uitvoeren om aan de slag te gaan met Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/21/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cf040b18-93d1-41e8-a26a-647c56afb00f
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 3c342e019dfca316ee89f68de60886d848abdb17
ms.openlocfilehash: 7137b7f362718f36a416d3c8e33040d208a92126


---

# <a name="getting-started-with-cloud-app-security"></a>Aan de slag met Cloud App Security
Met Cloud App Security kunt u profiteren van de voordelen van cloudtoepassingen, terwijl u de controle houdt over bedrijfsbronnen. Dit gebeurt door de zichtbaarheid van de activiteit van de cloud en de beveiliging van bedrijfsgegevens te verbeteren. In dit onderwerp wordt u stapsgewijs begeleid door de stappen voor het instellen en gebruiken van Cloud App Security.  

Uw organisatie moet beschikken over een licentie om Cloud App Security te kunnen gebruiken. Zie de sectie 'Licentieresources' in [Cloud App Security aanschaffen](https://www.microsoft.com/en-us/cloud-platform/cloud-app-security) voor meer informatie.  

>[!NOTE]
>U hebt geen Office 365-licentie nodig om Cloud App Security te kunnen gebruiken.  

## <a name="get-started-quickly-with-cloud-app-security"></a>Snel aan de slag met Cloud App Security  

|Wat u moet doen|Taak|Nodig?|Procedure|Beschrijving|  
|-------------------------|----------|---------------|-------------|-----------------|  
|Stap 1. [Stel Cloud Discovery in](set-up-cloud-discovery.md).|Verkeerslogboeken uploaden|Vereist|**Een doorlopend Cloud Discovery-rapport maken**<br /><br /> 1. Ga naar **Instellingen** > **Cloud Discovery-instellingen**.<br /><br /> 2. Kies **Logboek automatisch uploaden**.<br /><br /> 3. Voeg uw bronnen toe op het tabblad **Gegevensbronnen**.<br /><br /> 4. Configureer de logboekverzamelaar op het tabblad **Logboekverzamelaars**.<br /><br /> **Een momentopnamerapport van Cloud Discovery maken**<br /><br /> 1. Ga naar **Detecteren** > **Nieuw momentopnamerapport maken** en volg de weergegeven stappen.|**Waarom zou ik Cloud Discovery-rapporten configureren?**<br /> Inzicht in Shadow IT is essentieel voor uw organisatie. <br />Nadat de logboeken zijn geanalyseerd, kunt u gemakkelijk ontdekken welke cloud-apps worden gebruikt, door welke personen ze worden gebruikt en op welke apparaten.|
|Stap 2. [Directe zichtbaarheid, beveiliging en beheeracties voor uw apps instellen](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).|Apps koppelen|Vereist|1. Ga naar **instellingen** > **App connectors**.<br /><br /> 2. Kies **App koppelen** en selecteer een app.<br /><br /> 3. Volg de configuratiestappen om de app te koppelen.|**Waarom moet ik een app koppelen?**<br />Nadat u een app hebt gekoppeld, kunt u meer inzicht krijgen zodat u activiteiten, bestanden en accounts voor de apps in uw cloudomgeving kunt onderzoeken.|
|Stap 3. [Beheer cloud-apps met beleid](control-cloud-apps-with-policies.md).|Beleidsregels maken|Vereist|**Beleidsregels maken**<br /><br /> 1. Ga naar **Controle** > **Sjablonen**.<br /><br /> 2. Selecteer een beleidssjabloon in de lijst en kies (+) **Beleid maken**.<br /><br /> 3. Pas het beleid aan (selecteer filters, acties en andere instellingen) en kies **Maken**.<br /><br /> 4. Kies op het tabblad **Beleidsregels** het beleid dat u hebt gemaakt om de relevante overeenkomsten (activiteiten, bestanden, waarschuwingen, enzovoort) te bekijken.<br /><br /> Tip: maak voor elke **risicocategorie** een beleid, zodat alle beveilligingsscenario's voor uw cloudomgeving zijn gedekt.|**Hoe kunnen beleidsregels mijn organisatie helpen?**<br />U kunt beleidsregels gebruiken om trends te bewaken, beveiligingsdreigingen in te zien en aangepaste rapporten en waarschuwingen te genereren. Met beleidsregels kunt u beheeracties, DLP en besturingselementen voor het delen van bestanden maken.|
|Stap 4. [Personaliseer uw ervaring](general-setup.md#Adallom_mailsettings).|De gegevens van uw organisatie toevoegen|Aanbevolen|**E-mailinstellingen invoeren**<br /><br /> 1. Ga naar **Instellingen** > **E-mailinstellingen**.<br /><br /> 2. Voer uw e-mailadressen en weergavenaam in onder **Identiteit afzender**.<br /><br /> 3. Upload de e-mailsjabloon van uw organisatie onder **E‑mailontwerp**.<br /><br /> **Meldingen voor beheerders instellen**<br /><br /> 1. Kies uw gebruikersnaam op de navigatiebalk en ga vervolgens naar **Gebruikersinstellingen**.<br /><br /> 2. Configureer onder **Meldingen** de methoden die u wilt instellen voor systeemmeldingen.<br /><br /> 3. Kies **Opslaan**.<br /><br /> **Metrische gegevens voor de score aanpassen**<br /><br /> 1. Ga naar **Instellingen** > **Cloud Discovery-instellingen**.<br /><br /> 2. Configureer het belang van verschillende risicowaarden onder **Configuratie scorewaarden**.<br /><br /> 3. Kies **Opslaan**.<br /><br /> De risicoscores die zijn gegeven aan de gedetecteerde apps worden nu nauwkeurig geconfigureerd op basis van de behoeften en prioriteiten van uw organisatie.|**Waarom zou ik de omgeving aan mijn persoonlijke voorkeuren aanpassen?**<br />Sommige functies werken het beste wanneer u ze aanpast aan uw behoeften. <br />Biedt uw gebruikers een betere ervaring met uw eigen e‑mailsjablonen, besluit welke meldingen u ontvangt en pas de risicoscorewaarden aan zodat deze aansluiten bij de voorkeuren van uw organisatie.|
|Stap 5. [Organiseer de gegevens naar eigen gelang](general-setup.md#IPtagsandRanges).|Belangrijke instellingen configureren|Aanbevolen|**IP-adrestags maken**<br /><br /> 1. Ga naar **Instellingen** > **IP-adrestags**.<br /><br /> 2. Kies (+) **IP-adresbereik toevoegen**.<br /><br /> 3. Voer de **details**, **locatie**, **tags** en **categorie** van het IP-bereik in.<br /><br /> 4. Kies **Maken**.<br /><br /> Nu kunt u IP-adrestags gebruiken tijdens het maken van beleidsregels en tijdens het filteren en maken van gegevensweergaven.<br /><br /> **Weergaven maken**<br /><br /> 1. Ga naar **Instellingen** > **Cloud Discovery-instellingen**.<br /><br /> 2. Kies (+) **Gegevensweergave toevoegen** onder **Gegevensweergaven**.<br /><br /> 3. Volg de configuratiestappen.<br /><br /> 4. Kies **Maken**.<br /><br /> U kunt nu gedetecteerde gegevens weer laten geven op basis van uw eigen voorkeuren zoals bedrijfseenheden of IP-adresbereiken.<br /><br /> **Domeinen toevoegen**<br /><br /> 1. Ga naar **Instellingen** > **Algemene instellingen**.<br /><br /> 2. Voeg de interne domeinen van uw organisatie toe onder **Organisatiedetails**.<br /><br /> 3. Kies **Opslaan**.|**Waarom moet ik deze instellingen configureren?**<br />Met deze instellingen hebt u meer controle over de functies in de console. Met IP-tags is het eenvoudiger om beleidsregels te maken die aan uw behoeften voldoen, kunt u nauwkeurig gegevens filteren, enzovoort. Gebruik gegevensweergaven om uw gegevens in logische categorieën te groeperen.|  

## <a name="see-also"></a>Zie ook

Zie [Aan de slag met Cloud App Security](getting-started-with-cloud-app-security.md) voor meer informatie over de basisprincipes.    
Ga naar de [ondersteuningspagina van Cloud App Security](http://support.microsoft.com/oas/default.aspx?prid=16031) voor technische ondersteuning.   
Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit [Premier Portal](https://premier.microsoft.com/) kiezen.   



<!--HONumber=Nov16_HO4-->


