---
title: Inzicht in de velden van de ingebouwde rapporten in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u een lijst met ingebouwde rapporten en de manier waarop deze worden gebruikt.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.app: cloud-app-security
ms.technology: ''
ms.assetid: 588b3639-f748-45a6-bc4b-a6ee47c1865e
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 8793c7f60b3c18b2330552f9d300b557c1347e6d
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="built-in-report-reference"></a>Naslaginformatie ingebouwde rapporten

CAS biedt u een volledige lijst kant-en-klare ingebouwde rapporten waarmee u inzicht kunt verwerven en de manier kunt controleren waarop mensen de cloud gebruiken. U kunt de filters in de afzonderlijke rapporten gebruiken om het rapport aan te passen en de rapportgegevens te exporteren.


De volgende tabel bevat een lijst met ingebouwde rapporten en de typen gebeurtenissen die u ermee kunt bewaken.  
  
## <a name="built-in-report-list"></a>Lijst met ingebouwde rapporten  
  
|Rapporttype|Naam van ingebouwd rapport|Description|  
|-----------------|---------------------------|-----------------|  
|Beveiliging|Activiteit per locatie|Dit rapport geeft de landen weer waar activiteit in de cloud-apps vandaan komt, met verschillende parameters voor het volume van de activiteit vanuit elk land, zoals het aantal gebeurtenissen, aantal gebruikers, enz. Gebruik dit rapport voor een overzicht van de geografische verdeling van uw gebruikers.|  
|Beveiliging|Browsergebruik|Tot de meest voorkomende aanvalsvectoren behoren aanvallen via de browser. Leveranciers investeren enorm veel middelen in het beveiligen van browsersoftware en creëren een effectief updatemechanisme om updates naar eindpunten te verspreiden. Door een afgeschafte browser te gebruiken lang nadat deze moet worden bijgewerkt, wordt het een makkelijk doelwit voor bedreigingen die beschikbare aanvalspakketten gebruiken. Dit rapport geeft een lijst met verouderde browsers die in de afgelopen 7 dagen zijn gebruikt door gebruikers die toegang tot uw cloud-apps verkregen. Het rapport laat u ook weten of de verouderde browsers door een robot werden gebruikt.|  
|Beveiliging|IP-adressen - bevoegde accounts|Dit rapport bevat een lijst met IP-adressen die zijn gebruikt door apparaten om de laatste 7 dagen beheeractiviteiten uit te voeren in uw cloudomgeving die door Cloud App Security wordt beveiligd. Het rapport is gebaseerd op auditlogboeken die door Cloud App Security zijn verzameld. IP-adressen zijn gekoppeld aan een geografische locatie en een bronorganisatie. Gebruik dit rapport om verdachte IP-adressen te identificeren die verbinding maken met uw beveiligde apps. U kunt de auditlogboeken voor elk IP-adres weergeven door erop te klikken.|  
|Gebruikersbeheer|Inactieve accounts|Inactieve accounts zijn accounts met toegang tot uw cloud-exemplaar, maar die in de afgelopen 60 dagen geen gebeurtenissen hebben uitgevoerd. Dit kan erop wijzen dat deze accounts niet meer actief zijn en moeten worden geblokkeerd om toekomstige toegang door een bedreiging of een voormalig werknemer te voorkomen. Met deze best practice verbetert u niet alleen uw beveiligingspostuur, maar verlaagt u ook uw bedrijfskosten.|  
|Gebruikersbeheer|Gebruikers met bevoegdheden|Dit rapport geeft een overzicht van de gebruikers met verhoogde bevoegdheden in zakelijke apps, zoals beheerders, in de afgelopen 7 dagen. Bedreigingen gebruiken dit soort bevoegde accounts graag als aanvalsvector, omdat ze mogelijk aanzienlijke toegang kunnen krijgen tot zakelijke gegevens en de netwerkconfiguratie. Als er bevoegde accounts zijn die recentelijk niet zijn gebruikt, kan dat wijzen op een gebrek aan aandacht voor IT-beveiliging binnen ondernemingen, wat mogelijk de deur opent voor een golf van gegevensschendingen. U kunt het gebruik van verhoogde gebruikersbevoegdheden verder onderzoeken via het auditlogboek en overwegen bevoegdheden in te trekken als ze niet nodig zijn.|  
|Gebruikersbeheer|Accounts met speciale bevoegdheden|SalesForce heeft verschillende typen bevoegde accounts, met inbegrip van wijzigen van alle gegevens, alle gegevens weergeven en beheren van alle gebruikers. Bedreigingen gebruiken dit soort bevoegde accounts graag als aanvalsvector, omdat ze mogelijk aanzienlijke toegang kunnen krijgen tot zakelijke gegevens en configuraties.|  
|Gegevensbeheer|Overzicht van gegevensdeling|Dit rapport vermeldt het aantal bestanden dat is opgeslagen in uw cloud-apps, verdeeld volgens de toegangsmachtigingen. Delen is nu eenvoudig met cloud-apps vanwege de goede toegankelijkheid en alomtegenwoordigheid.<br /><br /> Een bestand dat met niemand wordt gedeeld behalve met de eigenaar, wordt een privébestand genoemd. Als het bestand wordt gedeeld, onderscheidt Cloud App Security vier typen statussen:<br /><br /> Een openbaar gedeeld (web)bestand is een bestand dat zelfs via een zoekmachine zonder verificatie toegankelijk is.<br /><br /> Een openbaar gedeeld bestand is een bestand dat zonder verificatie via een koppeling toegankelijk is.<br /><br /> Een extern gedeeld bestand is een bestand dat na verificatie met de cloud-app toegankelijk is voor personen buiten de organisatie.<br /><br /> Een intern gedeeld bestand is een bestand dat toegankelijk is voor alle of een aantal gebruikers van uw organisatie.|  
|Gegevensbeheer|Delen van gegevens (uitgaand) per domein|Dit rapport geeft een lijst met de domeinen waarmee bedrijfsbestanden worden gedeeld door uw werknemers. Voor elk domein welke zakelijke gebruikers bestanden met dat domein delen, welke bestanden worden gedeeld, en die de deelnemers bestanden worden gedeeld met details van het rapport. Het wordt aanbevolen dat u het delen met deze domeinen beheert via het tabblad Bestanden op de app-pagina van elke relevante app.|  
|Gegevensbeheer|Eigenaren van gedeelde bestanden|Dit rapport geeft een lijst van gebruikers die zakelijke bestanden met de buitenwereld delen. Extern gedeelde bestanden worden gedeeld met specifieke externe deelnemers. Openbaar gedeelde bestanden zijn via een privékoppeling toegankelijk voor iedereen op internet en kunnen alleen worden gevonden door degenen die expliciet de koppeling hebben gekregen. Openbaar gedeelde (internet)bestanden zijn toegankelijk voor iedereen op internet, zelfs via een zoekmachine.  Als u gebruikers die een uitzonderlijk groot aantal bestanden delen vindt, wordt u aangeraden dat u de aard van deze overmatige deelmachtigingen met behulp van het tabblad bestanden onderzoeken en neem contact op met deze gebruikers voor meer informatie over hun gebruik van extern delen.|  
  
## <a name="see-also"></a>Zie ook  
[Controle](control.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  