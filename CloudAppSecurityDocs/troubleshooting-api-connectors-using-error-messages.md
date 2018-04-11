---
title: Foutberichten gebruiken om problemen met app-connectors op te lossen in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u een lijst met foutberichten voor API app-connectors en de aanbevolen oplossingen voor elke fout.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 4b6ac04a-4653-4c4a-bd6f-5926743475cc
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 06ae149ab179714221f90d2ad7b405d830f68b24
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="troubleshooting-app-connectors-using-error-messages"></a>Foutberichten gebruiken om problemen met app-connectors op te lossen

App-connectorfouten worden weergegeven in het dialoogvenster van de app-connector nadat er is geprobeerd verbinding te maken met een cloud-app met de API app-connector.


> [!div class="mx-tableFixed"]
> 
> |Foutbericht|Relevante app|Description|Oplossing|
> |----|----|----|------------|
> |HttpRequestFailure: De server heeft de volgende fout geretourneerd: 400 - Ongeldige aanvraag: {"error":{"code":"AF20012","message":"De opgegeven tenant-id (Tenant_ID wordt hier ingevoegd) is onjuist geconfigureerd in het systeem."|Office 365 |Er zijn geen toegewezen Office 365-licenties gevonden. |Wijs ten minste één Office 365-licentie toe aan uw tenant.| 
> |AuthFatalFailureException: com.box.boxjavalibv2.exceptions.BoxServerException: {"error":"invalid_grant","error_description":"Ongeldig vernieuwingstoken"}|Box|Het vernieuwingstoken in Box is ongeldig|Volg opnieuw de procedure voor het maken van verbinding tussen Box en Cloud App Security.|
> |BoxRestException: Kan reactie niet parseren.|Box|Interne fout|Klik nogmaals op de koppeling Nu testen om de verbinding met Box te testen.|
> |ContextManagerServiceException: com.adallom.adalib.httputils.exceptions.TokenRefreshException: {"error":"invalid_grant","error_description":"Ongeldig vernieuwingstoken"}'|Box|Het vernieuwingstoken in Box is ongeldig|Volg opnieuw de procedure voor het maken van verbinding tussen Box en Cloud App Security.|
> |BoxServerException: De gebruiker heeft zonder Enterprise-account geen toegang tot deze functie|Box|Het Box-account is geen Enterprise-account.|Voer een upgrade van uw Box-licentie uit naar de Enterprise-versie van Box en volg opnieuw de procedure voor het maken van verbinding tussen Box en Cloud App Security.|
> |BoxServerException: Niet gemachtigd - Machtiging bij deze service is niet mogelijk|Box|De Box-beheerder heeft de toepassing Cloud App Security in Box verwijderd.|Volg opnieuw de procedure voor het maken van verbinding tussen Box en Cloud App Security.|
> |HttpRequestFailure: De server heeft de volgende fout geretourneerd: 401 - Niet gemachtigd|Okta|Het Okta-token is ongeldig.|Volg opnieuw de procedure voor het maken van verbinding tussen Okta en Cloud App Security.|
> |IOException:|Okta|Interne fout|Neem contact op met ondersteuning|
> |HttpRequestFailure: De server heeft de volgende fout geretourneerd: 404 - Niet gevonden|Okta|Interne fout|Neem contact op met ondersteuning|
> |SocketTimeoutException: Time-out tijdens lezen|SalesForce|Interne fout|Klik nogmaals op de koppeling Nu testen om de verbinding met Salesforce te testen.|
> |HttpRequestFailure: De server heeft de volgende fout geretourneerd: 400 - Ongeldige aanvraag|SalesForce|De verbinding met Salesforce is niet voltooid of is verlopen.|Volg opnieuw de procedure voor het maken van verbinding tussen Salesforce en Cloud App Security.|
> |HttpRequestFailure: De server heeft de volgende fout geretourneerd: 401 - Niet gemachtigd|Office 365|Intern probleem|Klik opnieuw op de koppeling Nu testen.|
> |TokenRefreshException: {"error":"invalid_grant","error_description":"AADSTS70002: Fout bij het valideren van de referenties. AADSTS70008: De opgegeven autorisatiecode of het opgegeven vernieuwingstoken is verlopen. Verzend een nieuwe interactieve autorisatieaanvraag voor deze gebruiker en bron.|Office 365|Token is verlopen|Volg opnieuw de procedure voor het maken van verbinding tussen Office 365 en Cloud App Security.|
> |SocketTimeoutException: Time-out tijdens lezen|Office 365|Interne fout|Klik opnieuw op de koppeling Nu testen.|
> |NullPointerException|Office 365|Interne fout|Neem contact op met ondersteuning|
> |IgniteException|Office 365|Het domein of de gebruiker is ongeldig|Herstel de instellingen en volg opnieuw de procedure voor het maken van verbinding tussen Office 365 en Cloud App Security.|
> |ContextManagerServiceException: com.adallom.adalib.httputils.exceptions.TokenRefreshException: {"error":"invalid_grant","error_description":"AADSTS70002: Fout bij valideren van referenties. AADSTS70008: De opgegeven autorisatiecode of het opgegeven vernieuwingstoken is verlopen. Verzend een nieuwe interactieve autorisatieaanvraag voor deze gebruiker en bron.|Office 365|Het domein of de gebruiker is ongeldig|Herstel de instellingen en volg opnieuw de procedure voor het maken van verbinding tussen Office 365 en Cloud App Security.|
> |HttpRequestFailure: De server heeft de volgende fout geretourneerd: 400 - Ongeldige aanvraag|Office 365|Interne fout|Klik over een aantal minuten nogmaals op de koppeling Nu testen. Als deze niet werkt, volgt u nogmaals de procedure voor het maken van verbinding tussen Office 365 en Cloud App Security.|
> |GoogleJsonResponseException: 401 - Niet gemachtigd|G Suite|Toegang geweigerd. U bent niet gemachtigd om activiteitsrecords te lezen. De gebruiker die wordt aangemeld bij G Suite, moet een gebruiker met beheerdersrechten zijn.|Volg nogmaals de procedure voor het instellen van een verbinding tussen G Suite en Cloud App Security met een beheerdersaccount.|
> |GoogleJsonResponseException: 403 - Verboden|G Suite|Probleem bij het uitvoeren van de API van G Suite.|Als u de Cloud App Security-connector voor G Suite hebt geïmplementeerd, controleert u het volgende: als u op Onbeperkt hebt geklikt, controleert u of uw G Suite-account daadwerkelijk onbeperkt is. Als dit niet het geval is, voert u de App-connector nogmaals uit en selecteert u de optie voor een onbeperkt account. Controleer of de tijdens de installatie gedefinieerde de bereiken juist zijn. Als dit geen nieuwe implementatie is en u deze fout ziet, kan het zijn dat de API-limiet voor vandaag is bereikt en de G Suite-gebeurtenissen morgen worden vernieuwd.|
> |TokenResponseException: 400 - Ongeldige aanvraag|G Suite|De verbinding met G Suite is niet voltooid of is verlopen.|Volg nogmaals de procedure voor het instellen van een verbinding tussen G Suite en Cloud App Security.|
> |RuntimeException: com.adallom.adalib.httputils.exceptions.HttpRequestFailure: De server heeft de volgende fout geretourneerd: 403 - Verboden|ServiceNow|De machtigingen zijn onjuist|Volg nogmaals de procedure voor het maken van verbinding tussen ServiceNow en Cloud App Security met een beheerdersaccount.|
> |HttpRequestFailure: De server heeft de volgende fout geretourneerd: 401 - Niet gemachtigd|Exchange Online|De gebruiker of het wachtwoord is onjuist|Controleer of de gebruikersnaam en het wachtwoord juist zijn en volg opnieuw de procedure voor het maken van verbinding tussen Exchange Online en Cloud App Security.|
> |HttpRequestFailure: De server heeft de volgende fout geretourneerd: 404 - Niet gevonden|Exchange Online|De gebruiker die u gebruikt voor aanmelding bij Exchange Online, heeft geen primair postvak in Exchange Online (bijvoorbeeld een gebruiker die niet in Azure AD bestaat of een gebruiker die in Azure AD bestaat, maar geen licentie heeft voor Exchange Online).|Volg nogmaals de procedure voor het maken van verbinding tussen Exchange Online en Cloud App Security met een nieuw beheerdersaccount.|
> |NullPointerException|AWS|Interne fout|Neem contact op met ondersteuning|
> |HttpRequestFailure: De server heeft de volgende fout geretourneerd: 500 - Interne serverfout|Alle apps|Er is een fout opgetreden in de app.|Controleer de status van de app.|
> |Servicetime-out|Alle apps|Er is een time-out opgetreden in de verbinding tussen Cloud App Security en de app. Dit kan worden veroorzaakt door een probleem met de app.|Probeer het later opnieuw.|

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  

