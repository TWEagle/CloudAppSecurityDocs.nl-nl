---
title: Foutberichten gebruiken om problemen met API-connectors op te lossen | Microsoft Docs
description: In dit onderwerp vindt u een lijst met foutberichten voor API-connectors, evenals de aanbevolen oplossingen voor elke fout.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 4b6ac04a-4653-4c4a-bd6f-5926743475cc
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 61492a0126bff93c2a61d5d1317784ca96687df7


---

# <a name="troubleshooting-api-connectors-using-error-messages"></a>Foutberichten gebruiken om problemen met API-connectors op te lossen
|Foutbericht|Relevante app|Beschrijving|Oplossing|
|----|----|----|----|
|HttpRequestFailure: De server heeft de volgende fout geretourneerd: 400 - Ongeldige aanvraag: {"error":{"code":"AF20012","message":"De opgegeven tenant-id (Tenant_ID wordt hier ingevoegd) is onjuist geconfigureerd in het systeem."|Office 365 |Er zijn geen toegewezen Office 365-licenties gevonden. |Wijs ten minste één Office 365-licentie toe aan uw tenant.| 
|AuthFatalFailureException: com.box.boxjavalibv2.exceptions.BoxServerException: {"error":"invalid_grant","error_description":"Ongeldig vernieuwingstoken"}|Box|Het vernieuwingstoken in Box is ongeldig|Volg opnieuw de procedure voor het maken van verbinding tussen Box en Cloud App Security.|
|BoxRestException: Kan reactie niet parseren.|Box|Interne fout|Klik nogmaals op de koppeling Nu testen om de verbinding met Box te testen.|
|ContextManagerServiceException: com.adallom.adalib.httputils.exceptions.TokenRefreshException: {"error":"invalid_grant","error_description":"Ongeldig vernieuwingstoken"}'|Box|Het vernieuwingstoken in Box is ongeldig|Volg opnieuw de procedure voor het maken van verbinding tussen Box en Cloud App Security.|
|BoxServerException: De gebruiker heeft zonder Enterprise-account geen toegang tot deze functie|Box|Het Box-account is geen Enterprise-account.|Voer een upgrade van uw Box-licentie uit naar de Enterprise-versie van Box en volg opnieuw de procedure voor het maken van verbinding tussen Box en Cloud App Security.|
|BoxServerException: Niet gemachtigd - Machtiging bij deze service is niet mogelijk|Box|De Box-beheerder heeft de toepassing Cloud App Security in Box verwijderd.|Volg opnieuw de procedure voor het maken van verbinding tussen Box en Cloud App Security.|
|HttpRequestFailure: De server heeft de volgende fout geretourneerd: 401 - Niet gemachtigd|Okta|Het Okta-token is ongeldig.|Volg opnieuw de procedure voor het maken van verbinding tussen Okta en Cloud App Security.|
|IOException:|Okta|Interne fout|Neem contact op met ondersteuning|
|HttpRequestFailure: De server heeft de volgende fout geretourneerd: 404 - Niet gevonden|Okta|Interne fout|Neem contact op met ondersteuning|
|SocketTimeoutException: Time-out tijdens lezen|SalesForce|Interne fout|Klik nogmaals op de koppeling Nu testen om de verbinding met Salesforce te testen.|
|HttpRequestFailure: De server heeft de volgende fout geretourneerd: 400 - Ongeldige aanvraag|SalesForce|De verbinding met Salesforce is niet voltooid of is verlopen.|Volg opnieuw de procedure voor het maken van verbinding tussen Salesforce en Cloud App Security.|
|HttpRequestFailure: De server heeft de volgende fout geretourneerd: 401 - Niet gemachtigd|Office 365|Intern probleem|Klik opnieuw op de koppeling Nu testen.|
|TokenRefreshException: {"error":"invalid_grant","error_description":"AADSTS70002: Fout bij het valideren van de referenties. AADSTS70008: De opgegeven autorisatiecode of het opgegeven vernieuwingstoken is verlopen. Verzend een nieuwe interactieve autorisatieaanvraag voor deze gebruiker en bron.|Office 365|Token is verlopen|Volg opnieuw de procedure voor het maken van verbinding tussen Office 365 en Cloud App Security.|
|SocketTimeoutException: Time-out tijdens lezen|Office 365|Interne fout|Klik opnieuw op de koppeling Nu testen.|
|NullPointerException|Office 365|Interne fout|Neem contact op met ondersteuning|
|IgniteException|Office 365|Het domein of de gebruiker is ongeldig|Herstel de instellingen en volg opnieuw de procedure voor het maken van verbinding tussen Office 365 en Cloud App Security.|
|ContextManagerServiceException: com.adallom.adalib.httputils.exceptions.TokenRefreshException: {"error":"invalid_grant","error_description":"AADSTS70002: Fout bij valideren van referenties. AADSTS70008: De opgegeven autorisatiecode of het opgegeven vernieuwingstoken is verlopen. Verzend een nieuwe interactieve autorisatieaanvraag voor deze gebruiker en bron.|Office 365|Het domein of de gebruiker is ongeldig|Herstel de instellingen en volg opnieuw de procedure voor het maken van verbinding tussen Office 365 en Cloud App Security.|
|HttpRequestFailure: De server heeft de volgende fout geretourneerd: 400 - Ongeldige aanvraag|Office 365|Interne fout|Klik over een aantal minuten nogmaals op de koppeling Nu testen. Als deze niet werkt, volgt u nogmaals de procedure voor het maken van verbinding tussen Office 365 en Cloud App Security.|
|GoogleJsonResponseException: 401 - Niet gemachtigd|Google Apps|Toegang geweigerd. U bent niet gemachtigd om activiteitsrecords te lezen. De gebruiker die u gebruikt voor aanmelding bij Google Apps, moet een gebruiker met beheerdersrechten zijn.|Volg nogmaals de procedure voor het maken van verbinding tussen Google Apps en Cloud App Security met een beheerdersaccount.|
|GoogleJsonResponseException: 403 - Verboden|Google Apps|Probleem bij het uitvoeren van de API van Google Apps.|Als u de Cloud App Security-connector voor Google Apps hebt geïmplementeerd, controleert u het volgende: als u op Onbeperkt hebt geklikt, controleert u of uw Google Apps-account daadwerkelijk onbeperkt is. Als dit niet het geval is, voert u de App-connector nogmaals uit en selecteert u de optie voor een onbeperkt account. Controleer of de tijdens de installatie gedefinieerde de bereiken juist zijn. Als dit geen nieuwe implementatie is en u deze fout ziet, kan het zijn dat de API-limiet voor vandaag is bereikt en de Google Apps-gebeurtenissen morgen worden vernieuwd.|
|TokenResponseException: 400 - Ongeldige aanvraag|Google Apps|De verbinding met Google Apps is niet voltooid of is verlopen.|Volg opnieuw de procedure voor het maken van verbinding tussen Google Apps en Cloud App Security.|
|RuntimeException: com.adallom.adalib.httputils.exceptions.HttpRequestFailure: De server heeft de volgende fout geretourneerd: 403 - Verboden|ServiceNow|De machtigingen zijn onjuist|Volg nogmaals de procedure voor het maken van verbinding tussen ServiceNow en Cloud App Security met een beheerdersaccount.|
|HttpRequestFailure: De server heeft de volgende fout geretourneerd: 401 - Niet gemachtigd|Exchange Online|De gebruiker of het wachtwoord is onjuist|Controleer of de gebruikersnaam en het wachtwoord juist zijn en volg opnieuw de procedure voor het maken van verbinding tussen Exchange Online en Cloud App Security.|
|HttpRequestFailure: De server heeft de volgende fout geretourneerd: 404 - Niet gevonden|Exchange Online|De gebruiker die u gebruikt voor aanmelding bij Exchange Online, heeft geen primair postvak in Exchange Online (bijvoorbeeld een gebruiker die niet in Azure AD bestaat of een gebruiker die in Azure AD bestaat, maar geen licentie heeft voor Exchange Online).|Volg nogmaals de procedure voor het maken van verbinding tussen Exchange Online en Cloud App Security met een nieuw beheerdersaccount.|
|NullPointerException|AWS|Interne fout|Neem contact op met ondersteuning|
|HttpRequestFailure: De server heeft de volgende fout geretourneerd: 500 - Interne serverfout|Alle apps|Er is een fout opgetreden in de app.|Controleer de status van de app.|
|Servicetime-out|Alle apps|Er is een time-out opgetreden in de verbinding tussen Cloud App Security en de app. Dit kan worden veroorzaakt door een probleem met de app.|Probeer het later opnieuw.|

## <a name="see-also"></a>Zie ook  
[Dagelijkse activiteiten ter bescherming van uw cloudomgeving](daily-activities-to-protect-your-cloud-environment.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


