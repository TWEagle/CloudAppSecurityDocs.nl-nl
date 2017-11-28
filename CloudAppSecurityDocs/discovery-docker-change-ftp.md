---
title: Wijzigen van het FTP-wachtwoord voor de Cloud Discovery-docker | Microsoft Docs
description: In dit onderwerp beschrijft het proces voor het wijzigen van het wachtwoord van de FTP-Cloud Discovery.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 26/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 776e834f-3c20-4d5f-9fab-4c5b975edb06
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 91411653b36cc5119b1c8e85ceac79c34386482f
ms.sourcegitcommit: 473d96a6383a6e4d01ef03ed31f2e773cea82cab
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/27/2017
---
# <a name="changing-the-ftp-password"></a>Wijzigen van het FTP-wachtwoord


1. Verbinding maken met de host van de collector logboek.

2.  Voer `docker exec -it <collector name> pure-pw passwd <ftp user>` uit

    1. Voer het nieuwe wachtwoord.
    2. Voer het nieuwe wachtwoord nogmaals ter bevestiging.
 
3.  Voer `docker exec -it <collector name> pure-pw mkdb` de wijziging toepassen.


  ![FTP-wachtwoord wijzigen](./media/ftp-connect.png)

## <a name="see-also"></a>Zie ook
[Werken met Cloud Discovery-gegevens](working-with-cloud-discovery-data.md)  
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)  
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit de Premier Portal kiezen](https://premier.microsoft.com/)

