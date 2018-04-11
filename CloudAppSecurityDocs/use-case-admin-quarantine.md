---
title: Aanvraag voor het onderzoeken en oplossen bestand schendingen met beheerquarantaine gebruiken | Microsoft Docs
description: Dit onderwerp beschrijft het scenario voor met beheerquarantaine schendingen van gegevens controleren.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 3fc04cfb-ad4c-4ac2-980a-ee9f4c740d88
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: f463c28abdbc948713c71afbf1b4b9ae3e1b7215
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="protecting-your-files-with-admin-quarantine"></a>Uw bestanden met beheerquarantaine beveiligen

> [!NOTE]
> Dit is een preview-functie.

[Beleid voor het bestand](data-protection-policies.md) zijn een uitstekend hulpprogramma voor het vinden van bedreigingen voor de beleidsregels voor gegevensbeveiliging, bijvoorbeeld locaties waar gebruikers gevoelige informatie, creditcardnummers en derden ICAP bestanden in uw cloud opgeslagen te zoeken. Met Cloud App Security, niet alleen kunt u deze ongewenste bestanden opgeslagen in de cloud die u kwetsbaar detecteren maar u kunt direct actie ondernemen om te stoppen ze hun houdt en de bestanden die een bedreiging vormen voor het vergrendelen. Met behulp van **beheerquarantaine**, u kunt bestanden in de cloud beveiligen en gevonden problemen kunt oplossen, evenals voorkomen toekomstige lekken. 

>[!NOTE] 
> Zie voor een lijst met apps die ondersteuning bieden voor beheerquarantaine, de de lijst met [beheeracties](governance-actions.md).
 
## <a name="how-quarantine-works"></a>Hoe werkt in quarantaine plaatsen 

1. Wanneer een bestand overeenkomt met een beleid, de **beheerquarantaine** optie beschikbaar zullen zijn voor het bestand.

2. Voer een van de volgende opties in quarantaine plaatsen van het bestand:
   - Handmatig toe te passen de **beheerquarantaine** actie:
     
     ![quarantaine actie](./media/quarantine-action.png)

   - Stel dit in als een actie geautomatiseerde quarantaine in het beleid: 

     ![automatisch in quarantaine plaatsen](./media/quarantine-automated.png)

3. Wanneer **beheerquarantaine** wordt toegepast, gebeurt het volgende achter de schermen:

   1. Het oorspronkelijke bestand wordt verplaatst naar de quarantainemap van beheerder instellen.
   2. Het oorspronkelijke bestand wordt verwijderd.
   3. Een tombstone-bestand wordt geüpload naar de locatie van het oorspronkelijke bestand.

      ![quarantaine tombstone](./media/quarantine-tombstone.png)

   4. De gebruiker heeft alleen toegang tot de tombstone, waar ze over de aangepaste richtlijnen lezen kunnen van IT en de correlatie-ID contact opnemen met IT voor het vrijgeven van het bestand.

4. Wanneer u de waarschuwing dat een bestand is in quarantaine ontvangt, het bestand in de Cloud App Security onderzoeken **waarschuwingen** pagina:

   ![waarschuwingen voor quarantaine](./media/quarantine-alerts.png)
 
5. En ook in de **beleid rapport** op de **in quarantaine** tabblad:

   ![quarantaine](./media/quarantine-report.png)
    
6. Nadat een bestand in quarantaine is geplaatst, gebruikt u het volgende proces voor de bedreiging situatie oplossen:
       
    1. Controleer het bestand in de map in quarantaine geplaatste op SharePoint online.
    3. U kunt ook de controlelogboeken om diepgaand in de bestandseigenschappen te bekijken.
    4. Als het bestand tegen bedrijfsbeleid wordt gevonden, kunt u de organisatie Incident antwoord (IR) proces uitvoeren.
    5. Als het bestand moet onschadelijke wordt gevonden, kunt u het bestand uit quarantaine terugzetten, waarna het oorspronkelijke bestand wordt uitgebracht, dat wil zeggen terug naar de oorspronkelijke locatie wordt gekopieerd, de tombstone wordt verwijderd en de gebruiker toegang tot het bestand.
       ![quarantaine terugzetten](./media/quarantine-restore.png)
7. Nadat u hebt geverifieerd dat het beleid soepel wordt uitgevoerd, kunt u de automatische beheeracties in het beleid om te voorkomen dat verdere lekken en automatisch toepassen beheerquarantaine wanneer het beleid wordt vergeleken.

> [!NOTE]
> Wanneer u een bestand te herstellen:
> - Oorspronkelijke shares zijn niet hersteld, standaard overname toegepast.
> - Het herstelde bestand bevat alleen de meest recente versie.
> 
> 
> [!NOTE]
> De map voor quarantaine site toegangsbeheer is de verantwoordelijkheid van de klant.

#### <a name="how-to-set-up-admin-quarantine"></a>Het instellen van beheerquarantaine

1. Instellen van beleidsregels voor bestanden die schendingen, zoals een metagegevens alleen beleid (zoals een classificatie-label in SharePoint Online), een systeemeigen DLP-beleid (zoals een beleid waarin wordt gezocht naar creditcardnummers) of een beleid ICAP van derden (zoals een beleid dat wordt gezocht naar Vontu) te detecteren.

2. Stel een Quarantainelocatie:
   1. Voor Office 365 SharePoint of OneDrive voor bedrijven, voordat u beheerquarantaine instelt, u zich niet kunnen bestanden in beheerquarantaine plaatsen als onderdeel van een beleid: ![instellingen in quarantaine plaatsen](./media/quarantine-warning.png)

      Ga naar admin quarantaine als instellingen wilt instellen, onder het instellingentandwiel **algemene instellingen**, en een locatie opgeven voor het in quarantaine geplaatste bestanden en een melding voor gebruikers die de gebruiker ontvangt wanneer een bestand in quarantaine is geplaatst. 
      ![instellingen voor quarantaine](./media/quarantine-settings.png)

   2. Voor Box, kan niet de locatie en gebruikerstoegang-bericht voor de map voor quarantaine worden aangepast. Locatie van de map is het station van de beheerder die vak met Cloud App Security verbonden en de gebruikersbericht is: dit bestand is in quarantaine naar uw beheerder station omdat deze mogelijk van uw bedrijf-beveiliging en naleving beleid schenden. Neem contact op met uw IT-beheerder voor hulp.



## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  