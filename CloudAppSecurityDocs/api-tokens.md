---
title: Token management API in de Cloud App Security | Microsoft Docs
description: In dit onderwerp bevat informatie over API-tokens te genereren voor Cloud App Security.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/24/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4f5e6b1e-6b2c-4358-98f0-945e2993d5fe
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: d4e56bc0b09b27b600d1f397f89ba13e5ee15350
ms.sourcegitcommit: 8759541301241e03784c5ac87b56986f22bd0561
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2017
---
# <a name="api-tokens"></a>API-tokens
    
De Cloud App Security-API biedt programmatische toegang tot Cloud App Security via REST API-eindpunten. Toepassingen kunnen gebruikmaken van de API lezen uitvoeren en bewerkingen voor Cloud App Security-gegevens en objecten bijwerken. De Cloud App Security-API ondersteunt bijvoorbeeld de volgende algemene bewerkingen voor een gebruikersobject:

- Logboekbestanden voor Cloud Discovery uploaden
- Genereren van scripts blokkeren
- Lijst activiteiten, waarschuwingen en rapporten van het beleid
- Negeren of waarschuwingen oplossen

Om te zien van de volledige documentatie over de API, in de Cloud App Security-portal-Ga naar Help > **API-documentatie**.

U hebt toegang tot de API wordt een API-token maken en deze gebruiken in uw software verbinding maken met de Cloud App Security-API.

Het tabblad API-tokens kunt u helpen bij het beheren van de API-tokens van uw tenant. 


## <a name="generate-a-token"></a>Een token genereren

1. Op de **instellingen** selecteert u **Security extensions** en vervolgens **API tokens**.

2. Klik op het plusteken **nieuw token genereren** en geef een naam voor het token in de toekomst te identificeren en op **volgende**.
![Cloud App Security genereert API-token](./media/api-token-gen.png)

3. Kopieer de token waarde en sla het ergens voor herstel - als je het kwijtraakt moet u het token te genereren. Het token heeft de bevoegdheden van de gebruiker die deze is uitgegeven. Een lezer van de beveiliging kan niet bijvoorbeeld uitgeven van een token dat gegevens kunt wijzigen.

4. U kunt de tokens filteren op status: actief of inactief gegenereerde. 

  - Gegenereerd zijn tokens die nooit zijn gebruikt. 
  - Actieve zijn tokens die zijn gegenereerd en in de afgelopen zeven dagen zijn gebruikt. 
  - Niet-actief zijn gebruikt, maar er is geen activiteit in de afgelopen zeven dagen.
5. Nadat u een nieuw token genereren, krijgt u een nieuwe URL op voor toegang tot de Cloud App Security-portal. 

 ![Cloud App Security-API-token](./media/generate-api-token.png)

De algemene portal URL blijft werken, maar is aanzienlijk langzamer dan de aangepaste URL voorzien van uw token. Als u de URL op elk gewenst moment vergeet, kunt u deze bekijken door te gaan naar de **?** pictogram in het menu en selecteer **over**.

## <a name="api-token-management"></a>Token management API

De token API-pagina bevat een tabel met alle API-tokens die zijn gegenereerd.

Volledige beheerders zien alle tokens die worden gegenereerd voor deze tenant. Andere gebruikers zien alleen de tokens die ze zelf gegenereerd.

De tabel bevat informatie over wanneer het token is gegenereerd en waarop het laatst is gebruikt en kunt u in te trekken van het token. 

Nadat een token is ingetrokken, wordt deze verwijderd uit de tabel en de software die werd gebruikt mislukt API-aanroepen maken totdat een nieuw token is opgegeven. 

> [!NOTE]
> SIEM-connectors en logboekverzamelaars ook API tokens te gebruiken. Deze tokens moeten worden beheerd vanaf de SIEM-agent secties en logboekverzamelaars en worden niet weergegeven in deze tabel. 


## <a name="view-your-data-center"></a>Weergeven van uw datacenter

Als u wilt zien welke datacenter die u in de Cloud App Security-portal verbinding maakt, klikt u op de **?** in de menubalk en selecteer **over**. 

U ziet in het scherm Cloud App Security-versie van het datacenter.


## <a name="see-also"></a>Zie ook  
[Problemen met SIEM-integratie oplossen](troubleshooting-siem.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  