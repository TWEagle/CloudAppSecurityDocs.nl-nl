---
title: Beheerderstoegang tot de Cloud App Security-portal beheren | Microsoft Docs
description: Dit onderwerp biedt instructies voor het instellen van toegang tot de Cloud App Security-portal voor uw beheerders.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b718edad-350c-4d90-b045-92529d701dc5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: e20af36ddf5d3758d42a13caab89663ec1fab985
ms.sourcegitcommit: c47fd92c71028ede8840e0766f20eb0ad2898e70
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2018
---
## <a name="managing-admin-access"></a>Beheerderstoegang beheren

Toegangsbeheer op basis van rollen biedt ondersteuning voor cloud App Security. De volgende Office 365- en Azure AD-beheerdersrollen hebben standaard toegang tot Cloud App Security:

- Globale beheerder en Beveiligingsbeheerder: beheerders met **volledige toegang** volledige machtigingen hebben in de Cloud App Security admins toevoegen, het toevoegen van beleidsregels en instellingen, het uploaden van Logboeken en beheeracties uitvoeren.

- Naleving administrator: alleen-lezen-machtigingen heeft en waarschuwingen kunt beheren. Kunt maken en wijzigen van beleidsregels voor bestanden, bestand governance toestaan acties en bekijk de ingebouwde rapporten onder beheer. 

- Beveiligingslezer: heeft alleen-lezenmachtiging en kan waarschuwingen beheren. Beveiligingslezers kunnen de volgende acties niet uitvoeren:
      - Beleidsregels maken of bestaande beleidsregels bewerken of wijzigen 
      - Beheeracties uitvoeren 
      - Detectielogboeken uploaden
      - Verboden of voor het goedkeuren van apps van derden
      - De instellingenpagina voor het IP-adresbereik openen en weergeven
      - Instellingenpagina’s in het algemeen openen en weergeven 
      - Toegang tot en het weergeven van de instellingen voor netwerkdetectie 
      - Toegang tot en het weergeven van het tabblad App-connectors
      - Het beheerlogboek openen en weergeven 
      - De pagina Momentopnamerapporten beheren openen en weergeven 

Zie voor meer informatie [beheerdersrollen toewijzen in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-assign-admin-roles).

U kunt ook extra beheerders toevoegen aan de Cloud App Security zonder gebruikers toevoegen aan Azure Active Directory-beheerdersrollen, door de volgende stappen uit te voeren:

1. Klik op het instellingentandwiel ![Instellingenpictogram](./media/settings-icon.png "Instellingenpictogram") en vervolgens **beheerders beheren**. 

2. Voeg de beheerders toe die toegang moeten hebben tot Cloud App Security.
  
      
3. Volgende, klikt u op de vervolgkeuzelijst om in te stellen welk type toegang tot de beheerder heeft, **volledige toegang** of **alleen-lezen en waarschuwingen beheren**.

     >[!NOTE]
      >Een beheerder, waarvoor de toegang beperkt tot is **alleen-lezen en waarschuwingen beheren**, die probeert te krijgen van een pagina met beperkte toegang of het uitvoeren van een beperkte actie wordt een foutbericht dat ze niet gemachtigd voor toegang tot de pagina of de actie uitvoeren.

   ![beheerderstoegang beheren](./media/manage-admin-access.png "beheerderstoegang beheren")  

4. Klik op **Sluiten**.  

   >[!NOTE]
    >Alleen globale beheerders of beveiligingsbeheerders kunnen andere gebruikers toegang verlenen tot Cloud App Security.
  
**Beheerdersmachtigingen overschrijven:**

Als u een beheerdersmachtiging van Azure Active Directory of Office 365 wilt overschrijven, kunt u de gebruiker handmatig toevoegen aan Cloud App Security en machtigingen toewijzen aan de gebruiker.
Als u bijvoorbeeld aan Sabien, die beveiligingslezer is in Azure Active Directory, **volledige toegang** wilt toewijzen in Cloud App Security, kunt u haar handmatig toevoegen aan Cloud App Security en haar **volledige toegang** toewijzen om haar rol te overschrijven en haar de gewenste machtigingen te verlenen in Cloud App Security. 


Meer beheerders toevoegen aan Cloud App Security:
1. Klik op het tandwiel Instellingen ![instellingenpictogram](./media/settings-icon.png "instellingenpictogram") en vervolgens op **Beheerderstoegang beheren**. 

2. Voeg de beheerders toe die toegang moeten hebben tot Cloud App Security. Selecteer het toegangsniveau en klik op **sluiten**.



## <a name="see-also"></a>Zie ook  
[Cloud Discovery instellen](set-up-cloud-discovery.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  