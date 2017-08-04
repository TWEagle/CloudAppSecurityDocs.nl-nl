---
title: Maken van beleid om te bepalen met gebruik van cloud-app met Cloud App Security Proxy | Microsoft Docs
description: Dit onderwerp bevat informatie over het beleid maken om de controle over het gebruik van cloud-app met Cloud App Security-Proxy.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 7/16/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b419aff0-3f50-4917-9ee2-9ecf7539a5d7
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 4544f5b48484f9341bb85d09d8fdc8d11fd4ba00
ms.sourcegitcommit: c5a0d07af558239976ce144c14ae56c81642191b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/03/2017
---
# <a name="controlling-app-use-with-proxy-control"></a>Controle over app-gebruik met Proxy-besturingselement

Na implementatie van de Proxy, kunt u toegang en sessies in uw organisatie cloud door het opstellen van beleid voor het blokkeren van ongewenste toegang en het gedrag bepalen.

## <a name="create-access-control-policies-in-cloud-app-security"></a>Access controlebeleid maken in de Cloud App Security

Access controlebeleid maken:

1.  Onder **besturingselement** Selecteer **beleid**.

2.  Onder **beleid maken**, kies **proxybeleid** en vervolgens als de **activiteitstype**, selecteer **logboek voor eenmalige aanmelding op**.

3.  Kies de relevante app en de filters en kies de gewenste beperkende optie.

>[!NOTE]
> In de filters, kunt u **apparaat tag** en stel deze moet gelijk zijn of niet gelijk is aan **beheerd apparaat**. Zie hieronder voor meer informatie over [beheerde apparaten](#_Managed_devices).

Merk ook op dat in de **beperkende acties,** kunt u **logboek** of **toegang blokkeren**, of kies aan **Route naar de Cloud App Security** waarmee u kunt controleren en maken van beleid op de sessie. Dit wordt beschreven [sessie beleid maken in de Cloud App Security](#_Creating_session_control).

## <a name="create-session-control-policies-in-cloud-app-security"></a>Sessie beleidsregels maken in de Cloud App Security 

Nadat de Proxy is geïmplementeerd, kunt u Sessiecontrole mogelijkheden toevoegen door het definiëren van sessie-beleid in de Cloud App Security-portal.

Het is raadzaam dat u start doordat Sessiecontrole voor een kleine groep gebruikers voordat u deze implementeert in uw organisatie. Bovendien niet aangeraden Sessiecontrole schakelen voor alle sessies of voor het merendeel van de sessies. Aangezien Sessiecontrole is gebaseerd op de implementatie van een zonder Agent met de beperkingen, is ontworpen voor de gevallen in die u hebt beperkte of geen controle over het apparaat en de app.

Beleid voor het beheren van sessie maken:

1.  Maak een [toegangsbeleid](#working-with-proxy-control-features) en kies vervolgens als beperkende actie **Route naar de Cloud App Security**.

2.  Onder **besturingselement**, gaat u naar **beleid** en klikt u onder **beleid maken** kiezen **Proxy-beleid.**

3.  Klik vervolgens als de **type activiteit** kiest u **gedownloade bestand** of **rapport exporteren**. Kies de relevante app en de filters en kies de beperkende indien nodig.

## <a name="enabling-managedunmanaged-device-control"></a>Apparaatbeheer met begeleiding/zonder begeleiding inschakelen

### <a name="step-1-deploy-certificates"></a>STAP 1: Certificaten implementeren

Voor Cloud App Security om te bepalen welke apparaten verbinding maken met uw cloud worden beheerd of onbeheerd, moet u clientcertificaten te implementeren. Dit kan worden uitgevoerd op verschillende manieren meestal dankzij het gebruik van de certificaten van een bestaande oplossing voor beheer van mobiele apparaten of met behulp van het Active Directory-groepsbeleid.

### <a name="step-2-upload-the-root-certificate-to-cloud-app-security"></a>STAP 2: Het basiscertificaat uploaden naar de Cloud App Security

Om de identificatie van beheerde apparaten in de Cloud App Security-portal, moet u eerst het CA-basiscertificaat certificaat uploaden:

1.  Klik op het instellingentandwiel en kies **beheerde apparaten.**

2.  Schakel **apparaat identificatie**.

3. Het basiscertificaat uploaden.

![certificaat voor apparaten worden beheerd door cloud app security-proxy](./media/managed-device-cert.png)

### <a name="step-3-create-managed-device-policies"></a>STAP 3: Maak beheerde apparaatbeleid

Nadat het basiscertificaat is geüpload, gebruikt u het filter **apparaat tag** is gelijk aan of niet gelijk aan **beheerd apparaat** proxy-beleid maken of zoeken naar gebeurtenissen in het gebeurtenissenlogboek.

Wanneer u clientcertificaten gebruikt als een manier om beheerde apparaten te identificeren, wordt u aangeraden starten in de modus controleren voordat u probeert te blokkeren of controleren van de sessie. Dit betekent dat u een toegangsbeleid met definieert een **beheerd apparaat** filteren waarin de beperkende actie is **alleen**. Nadat u enige ervaring met uw gebruikers krijgen, kunt u andere risicobeperking acties zoals het blokkeren van toegang of het controleren van de sessie toevoegen.


## <a name="see-also"></a>Zie ook  
[Werken met de Cloud App Security-Proxy](proxy-intro.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  