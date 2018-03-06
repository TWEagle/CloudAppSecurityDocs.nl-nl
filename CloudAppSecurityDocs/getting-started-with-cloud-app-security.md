---
title: Implementeer Cloud App Security voor inzicht in cloud-app-gebruik en controle | Microsoft-documenten
description: In dit onderwerp vindt u een overzicht van de taken die u moet uitvoeren om aan de slag te gaan met Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/3/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cf040b18-93d1-41e8-a26a-647c56afb00f
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: e33f277a9576ab1855cf5700584d7ddbb7dfac6c
ms.sourcegitcommit: c47fd92c71028ede8840e0766f20eb0ad2898e70
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
# <a name="deploy-cloud-app-security"></a>Cloud App Security implementeren
Met Cloud App Security kunt u profiteren van de voordelen van cloudtoepassingen, terwijl u de controle houdt over uw bedrijfsbronnen. Dit gebeurt door de zichtbaarheid van de activiteit van de cloud en de beveiliging van bedrijfsgegevens te verbeteren. In dit onderwerp wordt u stapsgewijs begeleid door de stappen voor het instellen en gebruiken van Cloud App Security.  

Uw organisatie moet beschikken over een licentie om Cloud App Security te kunnen gebruiken. Zie voor meer informatie de [Cloud App Security aanschaffen](https://www.microsoft.com/cloud-platform/cloud-app-security) sectie op de startpagina van de Cloud App Security.  

>[!NOTE]
>U hebt geen Office 365-licentie nodig om Cloud App Security te kunnen gebruiken.  

## <a name="prerequisites"></a>Vereisten  
  
-   Uw organisatie moet beschikken over een licentie voor Cloud App Security om het product te kunnen gebruiken. Zie voor meer informatie de [Cloud App Security aanschaffen](https://www.microsoft.com/cloud-platform/cloud-app-security) sectie op de startpagina van de Cloud App Security.  
  
     Raadpleeg voor activering van de tenant [Contact opnemen met de ondersteuning van Office 365 voor bedrijven - Help voor beheerders](https://support.office.com/article/Contact-Office-365-for-business-support-Admin-Help-32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).  
  
> [!NOTE] 
> Een Office 365-licentie is niet vereist voor Cloud App Security.  
  
-   Nadat u een licentie voor Cloud App Security hebt aangeschaft, ontvangt u een e-mail met activeringsgegevens en een koppeling naar de Cloud App Security-portal.  
  
-   Als u Cloud App Security instelt, moet u een globale beheerder, een beheerder naleving of een lezer beveiliging in Azure Active Directory of Office 365. Het is belangrijk om te begrijpen dat een gebruiker aan wie een beheerdersrol is toegewezen, dezelfde machtigingen heeft voor alle cloud-apps waar uw organisatie een abonnement voor heeft, ongeacht of u die rol toewijst in de Office 365-portal of in de klassieke Azure-portal of met behulp van de Azure AD-module voor [Windows PowerShell](https://technet.microsoft.com/library/mt736914.aspx). Zie voor meer informatie [Beheerdersrollen toewijzen in Office 365](https://support.office.com/article/Assigning-admin-roles-in-Office-365-eac4d046-1afd-4f1a-85fc-8219c79e1504) en [Beheerdersrollen toewijzen in Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-assign-admin-roles/).  
  
-   Als u de Cloud App Security-portal wilt uitvoeren, gebruikt u Internet Explorer 11, Microsoft Edge (meest recente versie), Google Chrome (meest recente versie), Mozilla Firefox (meest recente versie) of Apple Safari (meest recente versie).  

## <a name="to-access-the-portal"></a>Toegang krijgen tot de portal

Als u de Cloud App Security-portal wilt openen, gaat u naar [https://portal.cloudappsecurity.com](https://portal.cloudappsecurity.com).  
  
U kunt de portal ook openen via het **Office 365-beheercentrum** door te klikken op het pictogram van de beheercentrums ![pictogram van O365-beheercentrums](./media/o365-admin-centers-icon.png "pictogram van O365-beheercentrums") gevolgd door **Cloud App Security**.  
  
![Toegang vanuit O365](./media/access-from-o365.png "Toegang vanuit O365")  
  



## <a name="get-started-quickly-with-cloud-app-security"></a>Snel aan de slag met Cloud App Security  

 

### <a name="step-1-set-up-cloud-discoveryset-up-cloud-discoverymd"></a>Stap 1. [Stel Cloud Discovery in](set-up-cloud-discovery.md).
Vereiste taak: verkeerslogboeken uploaden **Een doorlopend Cloud Discovery-rapport maken**

 1 Selecteer in het instellingentandwiel **Cloud Discovery-instellingen**.
 2. Kies **logboek automatisch uploaden**.
 3. Voeg uw bronnen toe op het tabblad **Gegevensbronnen**.
 4. Configureer de logboekverzamelaar op het tabblad **Logboekverzamelaars**.
 
**Een momentopnamerapport van Cloud Discovery maken**

 1. Ga naar **Discover** > **een momentopname van rapport** en volg de stappen die wordt weergegeven.

**Waarom zou ik Cloud Discovery-rapporten configureren?**
Inzicht in Shadow IT is essentieel voor uw organisatie.
Nadat de logboeken zijn geanalyseerd, kunt u gemakkelijk ontdekken welke cloud-apps worden gebruikt, door welke personen ze worden gebruikt en op welke apparaten.


### <a name="step-2-set-instant-visibility-protection-and-governance-actions-for-your-appsenable-instant-visibility-protection-and-governance-actions-for-your-appsmd"></a>Stap 2. [Directe zichtbaarheid, beveiliging en beheeracties voor uw apps instellen](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md).
Vereiste taak: verbinding maken met apps

1 Selecteer in het instellingentandwiel **App-connectors**.
2. Klik op het plusteken om een app toevoegen en selecteer een app.
3. Volg de configuratiestappen om de app te koppelen.

**Waarom moet ik een app koppelen?**
Nadat u een app hebt gekoppeld, kunt u meer inzicht krijgen zodat u activiteiten, bestanden en accounts voor de apps in uw cloudomgeving kunt onderzoeken.


### <a name="step-3-control-cloud-apps-with-policiescontrol-cloud-apps-with-policiesmd"></a>Stap 3. [Beheer cloud-apps met beleid](control-cloud-apps-with-policies.md).
Vereiste taak: beleidsregels maken

**Beleidsregels maken**

1. Ga naar **Controle** > **Sjablonen**.
2. Selecteer een beleidssjabloon in de lijst en kies (+) **Beleid maken**.
3. Pas het beleid aan (selecteer filters, acties en andere instellingen) en kies **Maken**.
4. Kies op het tabblad **Beleidsregels** het beleid dat u hebt gemaakt om de relevante overeenkomsten (activiteiten, bestanden, waarschuwingen, enzovoort) te bekijken.
 Tip: maak voor elke **risicocategorie** een beleid, zodat alle beveilligingsscenario's voor uw cloudomgeving zijn gedekt.

**Hoe kunnen beleidsregels mijn organisatie helpen?**
U kunt beleidsregels gebruiken om trends te bewaken, beveiligingsdreigingen in te zien en aangepaste rapporten en waarschuwingen te genereren. Met beleidsregels kunt u beheeracties, DLP en besturingselementen voor het delen van bestanden maken.


### <a name="step-4-personalize-your-experiencemail-settingsmd"></a>Stap 4. [Personaliseer uw ervaring](mail-settings.md).
Aanbevolen taak: gegevens van uw organisatie toevoegen

**E-mailinstellingen invoeren**

1. Selecteer in het instellingentandwiel **e-mailinstellingen**.
2. Voer uw e-mailadressen en weergavenaam in onder **Identiteit afzender**.
3. Upload de e-mailsjabloon van uw organisatie onder **E‑mailontwerp**.

**Meldingen voor beheerders instellen**

1. Kies uw gebruikersnaam op de navigatiebalk en ga vervolgens naar **Gebruikersinstellingen**.
2. Configureer onder **Meldingen** de methoden die u wilt instellen voor systeemmeldingen.
3. Kies **Opslaan**.

**Metrische gegevens voor de score aanpassen**

1. Selecteer in het instellingentandwiel **Cloud Discovery-instellingen**.
1 Selecteer in het instellingentandwiel **Cloud Discovery-instellingen**.
2. Onder **Score metrische gegevens**, configureer het belang van verschillende risicowaarden.
3. Kies **Opslaan**.

De risicoscores die zijn gegeven aan de gedetecteerde apps worden nu nauwkeurig geconfigureerd op basis van de behoeften en prioriteiten van uw organisatie.

**Waarom zou ik de omgeving aan mijn persoonlijke voorkeuren aanpassen?**
Sommige functies werken het beste wanneer u ze aanpast aan uw behoeften. Biedt uw gebruikers een betere ervaring met uw eigen e‑mailsjablonen, besluit welke meldingen u ontvangt en pas de risicoscorewaarden aan zodat deze aansluiten bij de voorkeuren van uw organisatie.


### <a name="step-5-organize-the-data-according-to-your-needsip-tagsmd"></a>Stap 5. [Organiseer de gegevens naar eigen gelang](ip-tags.md).
Aanbevolen taak: belangrijke instellingen configureren

**IP-adrestags maken**

1 Selecteer in het instellingentandwiel **Cloud Discovery-instellingen**.
1 Selecteer in het instellingentandwiel **IP-adresbereiken**.
2. Klik op het plusteken om een IP-adresbereik toevoegen.
3. Voer de **details**, **locatie**, **tags** en **categorie** van het IP-bereik in.
4. Kies **Maken**.

 U kunt nu IP-tags gebruiken wanneer u beleidsregels maakt, en wanneer u filteren en continue rapporten maken.

**Continue rapporten maken**

1. Van het instellingentandwiel **Cloud Discovery-instellingen**.
2. Onder **continue rapporten**, kies **rapport maken**.
3. Volg de configuratiestappen.
4. Kies **Maken**.

U kunt nu gedetecteerde gegevens weer laten geven op basis van uw eigen voorkeuren zoals bedrijfseenheden of IP-adresbereiken.

**Domeinen toevoegen**

1. Selecteer in het instellingentandwiel **instellingen**.
2. Voeg de interne domeinen van uw organisatie toe onder **Organisatiedetails**.
3. Kies **Opslaan**.

**Waarom moet ik deze instellingen configureren?**
Met deze instellingen hebt u meer controle over de functies in de console. Met IP-tags is het eenvoudiger om beleidsregels te maken die aan uw behoeften voldoen, kunt u nauwkeurig gegevens filteren, enzovoort. Gebruik gegevensweergaven om uw gegevens in logische categorieën te groeperen.
  

## <a name="see-also"></a>Zie ook

Beleidsregels instellen [Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md).    

Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit [Premier Portal](https://premier.microsoft.com/) kiezen.   
