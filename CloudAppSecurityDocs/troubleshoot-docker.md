---
title: Het oplossen van de implementatie van Cloud Discovery Docker | Microsoft Docs
description: In dit onderwerp beschrijft het proces voor het wijzigen van de configuratie voor de Cloud App Security Cloud Discovery-docker.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 776e834f-3c20-4d5f-9fab-4c5b975edb06
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 593a5a9ad40a11345ad5d741336dc60250f8a385
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="troubleshooting-the-cloud-app-security-cloud-discovery-docker"></a>Cloud App Security Cloud Discovery Docker probleemoplossing

## <a name="changing-the-ftp-password"></a>Wijzigen van het FTP-wachtwoord


1. Verbinding maken met de host van de collector logboek.

2.  Voer `docker exec -it <collector name> pure-pw passwd <ftp user>` uit

    1. Voer het nieuwe wachtwoord.
    2. Voer het nieuwe wachtwoord nogmaals ter bevestiging.
 
3.  Voer `docker exec -it <collector name> pure-pw mkdb` de wijziging toepassen.


  ![FTP-wachtwoord wijzigen](./media/ftp-connect.png)

## <a name="customize-certificate-files"></a>Certificaatbestanden aanpassen

Volg deze procedure voor het aanpassen van het certificaatbestand dat u voor beveiligde verbindingen met de docker Cloud Discovery gebruiken.

1. Een FTP-client openen en verbinding maken met de logboekverzamelaar.

   ![Verbinding maken met de FTP-client](./media/ftp-connect.png)

2. Navigeer naar de `ssl_update` directory.
3. Uploaden van certificaatbestanden voor nieuwe naar de `ssl_update` directory (de namen zijn verplicht).

   ![FTP-wachtwoord wijzigen](./media/new-certs.png)

   1.  Voor FTP: Slechts één bestand vereist is, met de sleutel en certificaatgegevens gegevens in die volgorde, met de naam **pure ftpd.pem**.
    
   2.  Voor Syslog: Drie bestanden zijn vereist: **ca.pem**, **server key.pem** en **server cert.pem**. Als een van de bestanden ontbreekt, zal de update niet plaatsvinden.

4. In een terminal uitvoeren: `docker exec -t <collector name> update_certs`. Dit moet een vergelijkbare uitvoer naar die zichtbaar zijn in het volgende scherm produceren.

   ![FTP-wachtwoord wijzigen](./media/update-certs.png)

## <a name="see-also"></a>Zie ook
[Cloud Discovery implementeren](set-up-cloud-discovery.md)

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit de Premier Portal kiezen](https://premier.microsoft.com/)

