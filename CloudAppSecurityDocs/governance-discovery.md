---
title: Gedetecteerde apps blokkeren | Microsoft Docs
description: In dit onderwerp wordt de procedure beschreven voor het exporteren van blokkeerscripten voor gedetecteerde apps.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/21/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: e451031e-4764-411a-b366-73a49d4f25df
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: ca4a10f64429c481f49c75740f651302b1c7d1ef
ms.sourcegitcommit: 7493d88e4fe7c827f870b81e2090ffcc77f1408a
translationtype: HT
---
# <a name="governing-discovered-apps"></a>Gedetecteerde apps beheren
Met Cloud App Security kunt u toegang tot niet-goedgekeurde apps blokkeren door gebruik te maken van uw bestaande on-premises beveiligingsapparaten. Genereer een toegewezen blokkeerscript en importeer dit naar uw apparaat.
Deze oplossing vereist geen omleiding van alle webverkeer van de organisatie naar een proxy.


## <a name="export-a-block-script-to-govern-discovered-apps"></a>Een blokkeerscript exporteren om gedetecteerde apps te beheren

1. Label alle apps die u wilt blokkeren, in het Cloud Discovery-dashboard als **Niet-goedgekeurd**.

   ![Labelen als Niet-goedgekeurd](./media/tag-as-unsanctioned.png)  

2. Klik op de drie punten in de titelbalk en selecteer **Blokkeerscript genereren...**. 

   ![Blokkeerscript genereren](./media/generate-block-script.png)  

3. Selecteer in **Blokkeerscript genereren** het apparaat waarvoor u het blokkeerscript wilt genereren. 

   ![Pop-upvenster Blokkeerscript genereren](./media/generate-block-script-popup.png)  

4. Klik vervolgens op de knop Script genereren. Er wordt nu een blokkeerscript gemaakt voor al uw niet-goedgekeurde apps. In de naam van het bestand worden standaard de datum verwerkt waarop het bestand is geëxporteerd en het apparaattype dat u hebt geselecteerd. Bijvoorbeeld: *2017-02-19_CAS_Fortigate_block_script.txt* 

   ![Knop Blokkeerscript genereren](./media/generate-block-script-button.png)  

5. Importeer het gemaakte bestand naar uw apparaat.



## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  