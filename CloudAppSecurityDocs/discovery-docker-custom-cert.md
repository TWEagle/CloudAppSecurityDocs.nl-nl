---
title: Certificaten voor de Cloud Discovery-docker aanpassen | Microsoft Docs
description: In dit onderwerp beschrijft het proces voor het aanpassen van certificaten voor de Cloud Discovery-docker.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 26/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 0e9c15d3-902b-4b8f-8dec-31953b4451e0
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 6052e5b7b3db9e3f69f86fbbfe9930432ce2a30c
ms.sourcegitcommit: 473d96a6383a6e4d01ef03ed31f2e773cea82cab
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/27/2017
---
# <a name="customize-certificate-files"></a>Certificaatbestanden aanpassen

Volg deze procedure voor het aanpassen van het certificaatbestand dat u voor beveiligde verbindingen met de docker Cloud Discovery gebruiken.

1.  Een FTP-client openen en verbinding maken met de logboekverzamelaar.

  ![Verbinding maken met de FTP-client](./media/ftp-connect.png)

2.  Navigeer naar de `ssl_update` directory.
3.  Uploaden van certificaatbestanden voor nieuwe naar de `ssl_update` directory (de namen zijn verplicht).

    ![Ftp-wachtwoord wijzigen](./media/new-certs.png)

    1.  Voor FTP: Slechts één bestand vereist is, met de sleutel en certificaatgegevens gegevens in die volgorde, met de naam **pure ftpd.pem**.
    
    2.  Voor Syslog: Drie bestanden zijn vereist: **ca.pem**, **server key.pem** en **server cert.pem**. Als een van de bestanden ontbreekt, zal de update niet plaatsvinden.

4.  In een terminal uitvoeren: `docker exec -t <collector name> update_certs`. Dit moet een vergelijkbare uitvoer naar die zichtbaar zijn in het volgende scherm produceren.

    ![Ftp-wachtwoord wijzigen](./media/update-certs.png)

## <a name="see-also"></a>Zie ook
[Werken met Cloud Discovery-gegevens](working-with-cloud-discovery-data.md)  
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)  
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit de Premier Portal kiezen](https://premier.microsoft.com/)

