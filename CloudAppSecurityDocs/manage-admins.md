---
title: Beheerderstoegang tot de Cloud App Security-portal beheren | Microsoft Docs
description: Dit onderwerp biedt instructies voor het instellen van toegang tot de Cloud App Security-portal voor uw beheerders.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/6/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b718edad-350c-4d90-b045-92529d701dc5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: e1c38d54a503f84a68a60812c1a6558ff7f92a4b
ms.sourcegitcommit: b729e881851cdd8dc3f105ddbf6b4b907b8588dd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2017
---
## <a name="managing-admin-access"></a>Beheerderstoegang beheren

Cloud App Security ondersteunt op rollen gebaseerd toegangsbeheer. De volgende Office 365- en Azure AD-beheerdersrollen hebben standaard toegang tot Cloud App Security:

- Globale beheerder en Beveiligingsbeheerder: beheerders met **volledige toegang** beschikken over volledige machtigingen in de Cloud App Security admins toevoegen, het toevoegen van beleidsregels en instellingen, het uploaden van Logboeken en beheeracties uitvoeren.

- Naleving administrator: alleen-lezen-machtigingen heeft en waarschuwingen kunt beheren. Kunt maken en wijzigen van beleidsregels voor bestanden, bestand governance toestaan acties en bekijk de ingebouwde rapporten onder beheer. 

- Beveiligingslezer: heeft alleen-lezenmachtiging en kan waarschuwingen beheren. Beveiligingslezers kunnen de volgende acties niet uitvoeren:
      - Beleidsregels maken of bestaande beleidsregels bewerken of wijzigen 
      - Beheeracties uitvoeren 
      - Detectielogboeken uploaden
      - Apps van derden verbieden of goedkeuren
      - De instellingenpagina voor het IP-adresbereik openen en weergeven
      - Instellingenpagina’s in het algemeen openen en weergeven 
      - Toegang tot en het weergeven van de instellingen voor netwerkdetectie 
      - Toegang tot en het weergeven van het tabblad App-connectors
      - Het beheerlogboek openen en weergeven 
      - De pagina Momentopnamerapporten beheren openen en weergeven 

Zie voor meer informatie [Beheerdersrollen toewijzen in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-assign-admin-roles).

U kunt via de volgende stappen ook extra beheerders toevoegen aan Cloud App Security zonder gebruikers toe te voegen aan Azure Active Directory-beheerdersrollen:

1. Klik op het tandwiel Instellingen ![instellingenpictogram](./media/settings-icon.png "instellingenpictogram") en vervolgens op **Beheerderstoegang beheren**. 

2. Voeg de beheerders toe die toegang moeten hebben tot Cloud App Security.
  
      
3. Klik vervolgens op de vervolgkeuzelijst om het type toegang voor de beheerder in te stellen: **volledige toegang** of **alleen lezen en waarschuwingen beheren**.

     >[!NOTE]
      >Een beheerder die slechts toegang heeft voor **alleen lezen en waarschuwingen beheren** en die probeert toegang te krijgen tot een pagina met beperkte toegang of probeert een actie met beperkte toegang uit te voeren, ontvangt een foutbericht dat hij of zij geen machtiging heeft om de pagina te openen of de actie uit te voeren.

   ![beheerderstoegang beheren](./media/manage-admin-access.png "beheerderstoegang beheren")  

4. Klik op **Sluiten**.  

   >[!NOTE]
    >Alleen globale beheerders of beveiligingsbeheerders kunnen andere gebruikers toegang verlenen tot Cloud App Security.
  
**Beheerdersmachtigingen overschrijven:**

Als u een beheerdersmachtiging van Azure Active Directory of Office 365 wilt overschrijven, kunt u de gebruiker handmatig toevoegen aan Cloud App Security en machtigingen toewijzen aan de gebruiker.
Als u bijvoorbeeld aan Sabien, die beveiligingslezer is in Azure Active Directory, **volledige toegang** wilt toewijzen in Cloud App Security, kunt u haar handmatig toevoegen aan Cloud App Security en haar **volledige toegang** toewijzen om haar rol te overschrijven en haar de gewenste machtigingen te verlenen in Cloud App Security. 


Meer beheerders toevoegen aan Cloud App Security:
1. Klik op het tandwiel Instellingen ![instellingenpictogram](./media/settings-icon.png "instellingenpictogram") en vervolgens op **Beheerderstoegang beheren**. 

2. Voeg de beheerders toe die toegang moeten hebben tot Cloud App Security, selecteer hun toegangsniveau en klik op **Sluiten**.



## <a name="see-also"></a>Zie ook  
[Cloud Discovery instellen](set-up-cloud-discovery.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  