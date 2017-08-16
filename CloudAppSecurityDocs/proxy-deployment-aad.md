---
title: De Proxy van Cloud App Security voor Azure AD implementeren | Microsoft Docs
description: Dit onderwerp bevat informatie over het implementeren van de Proxy Cloud App Security voor Azure AD-apps.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/10/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2490c5e5-e723-4fc2-a5e0-d0a3a7d01fc2
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 58b309ddcc893d47a8adc89e9b286eff97ec99ed
ms.sourcegitcommit: 4cf65f627f2d370ee4a4decae1acbb9658874056
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2017
---
# <a name="deploying-the-cloud-app-security-proxy-for-azure-ad"></a>Implementatie van de Cloud App Security-Proxy voor Azure AD

> [!NOTE]
> Het is raadzaam om te proberen de installatie in een sandbox- of testomgeving voordat u deze installeert in een productieomgeving.

De stappen die hieronder worden beschreven moeten worden genomen om de Cloud App Security-Proxy implementeren en zowel toegangsbeheer als Sessiecontrole inschakelen.


## <a name="step-1-create-an-azure-ad-conditional-access-policy"></a>Stap 1: Maak een beleid voor voorwaardelijke toegang van Azure AD

1. In Azure Active Directory, onder **beveiliging**, klikt u op **voorwaardelijke toegang**.

 ![Voorwaardelijke toegang van Azure AD](./media/conditional-access.png)

2. Klik op **nieuw beleid** en maak een nieuw beleid om ervoor te zorgen dat onder **sessie** u **beperkingen afgedwongen proxy gebruiken**.

## <a name="step-2-log-on-to-each-app"></a>Stap 2: Meld u aan bij elke app

Gebruik uw referenties aan te melden bij elke app die u wilt beheren in met de Proxy.

## <a name="step-3-add-the-apps-in-cloud-app-security"></a>Stap 3: De apps toevoegen in de Cloud App Security

1.  In de Cloud App Security-portal, gaat u naar het instellingentandwiel en kies **Proxy**.

2. De apps die u bent aangemeld, wordt nu weergegeven in de tabel. 

3. Klik op de drie punten in de rechterhoek van de tabelrij voor elke app en klik op **gaan met setup**.

4. Klik in de wizard Proxy **voltooien**.


Alle logboekbestanden in hun aanvragen aan uw app wordt binnen een paar minuten gerouteerd via de Cloud App Security-Proxy. 

## <a name="test-the-configuration"></a>Test de configuratie

1.  Probeer aan te melden bij de app. Als de aanmelding is mislukt, zorg er dan voor dat u de stappen voor de wizard Proxy correct voltooid. 

2.  In de Cloud App Security-portal onder **onderzoeken**, selecteer **activiteitenlogboek** en zorg ervoor dat er **logboek voor eenmalige aanmelding op** gebeurtenissen vastgelegd door de Proxy.



## <a name="see-also"></a>Zie ook  
[Werken met de Cloud App Security-Proxy](proxy-intro.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  