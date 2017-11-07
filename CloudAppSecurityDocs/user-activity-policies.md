---
title: Beleidsregels voor het beheren van activiteiten maken in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u instructies voor het maken van en werken met beleidsregels voor activiteit.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/6/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 99d5fd37-d922-4269-b557-86d7f84180eb
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: abda59dfdde956447ea314f09ab00815ae717a38
ms.sourcegitcommit: b729e881851cdd8dc3f105ddbf6b4b907b8588dd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/06/2017
---
# <a name="activity-policies"></a>Activiteitbeleid
Activiteit-beleid zorgt ervoor dat u een breed scala aan geautomatiseerde processen kunt uitvoeren terwijl u gebruikmaakt van de API’s van de app-provider Met dit beleid kunt u specifieke activiteiten volgen die worden uitgevoerd door verschillende gebruikers of onverwacht hoge frequenties van een bepaald type activiteit volgen.  
  
Nadat u een beleid voor activiteitdetectie hebt ingesteld, worden op basis van het beleid waarschuwingen gegenereerd. Waarschuwingen worden alleen gegenereerd voor activiteiten die plaatsvinden nadat u het beleid hebt gemaakt.
  
  
## <a name="custom-alerts"></a>Aangepaste waarschuwingen  
Beleidsregels voor activiteiten zorgen ervoor dat u een breed scala aan geautomatiseerde processen kunt controleren waarbij u gebruikmaakt van de API’s van de app-provider. Bijvoorbeeld als u een bericht wilt ontvangen elke keer als een gebruiker zich probeert aan te melden en dit 70 keer in één minuut mislukt, als een gebruiker 7000 bestanden downloadt of als een gebruiker aangemeld is vanuit Afghanistan, dan kunt u activiteitswaarschuwingen instellen die naar uzelf of naar de gebruiker verstuurd worden op het moment dat deze situaties voorkomen. U kunt zelfs de gebruiker toegang ontzeggen totdat u tijd heeft te onderzoeken wat er gebeurd is.  
  
Voor de volgende procedure uit om nieuwe beleidsregels voor activiteiten te maken:  
  
1.  Klik in de console op **Beheer** gevolgd door **Beleidsregels**.  
  
2.  Klik op **Beleid maken** en selecteer **Beleidsregel voor activiteiten**.  
  
     ![menu Activiteitenbeleid](./media/activity-policy-menu.png "menu Activiteitenbeleid")  
  
3.  Geef uw beleid een naam en beschrijving, wat u indien gewenst kunt baseren op een sjabloon. Voor meer informatie over beleidssjablonen, bekijk [Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md).  
  
4.  Om in te stellen welke acties of andere meetwaarden dit beleid activeren, werkt u met **Activiteitsfilters**.  
  
5.  Onder **Activiteit overeenkomstig de parameters**, selecteert u of een beleidsovertreding wordt ingesteld als een enkele activiteit voldoet aan de filters of dat een schending alleen wordt gedetecteerd als er een opgegeven aantal **Herhaalde activiteiten** wordt gedetecteerd.  
    Als u **Herhaalde activiteiten** kiest, kunt u **Overeenkomende activiteiten groeperen per app** instellen. Hiermee wordt alleen overeenkomend beleid aangegeven wanneer de herhaalde activiteiten voorkomen in dezelfde app (bijvoorbeeld 5 downloads van Box).  
  
6.  Configureer de **Acties** die moeten worden uitgevoerd wanneer een overeenkomst is gevonden.  
  
Bekijk deze voorbeelden:  
  
-   Meerdere mislukte aanmeldingen  
  
     U kunt het beleid zo instellen dat u een waarschuwing ontvangt als er een groot aantal mislukte aanmeldingspogingen binnen een bepaalde relatief korte periode is. Om een beleid zoals dit te configureren, kiest u het betreffende activiteitfilter op de pagina **Nieuw activiteit-beleid**.  
  
     Onder het veld **Activiteitfilters**, stelt u de parameters in waarbij de waarschuwing geactiveerd wordt.  
  
     ![voorbeeld van beleid voor meerdere mislukte aanmeldingspogingen](./media/multiple-failed-log-on-attempts-policy-example.png "voorbeeld van beleid voor meerdere mislukte aanmeldingspogingen")  
  
-   Hoge downloadsnelheid  
  
     U kunt het beleid zo instellen dat u een waarschuwing ontvangt als er een onverwacht of ongebruikelijk niveau van downloadactiviteit is. Om een beleid zoals dit te configureren, kiest u onder **Tarief**parameters de parameters die de waarschuwing activeren.  
  
     ![voorbeeld van hoge downloadsnelheid](./media/high-download-rate-example.png "voorbeeld van hoge downloadsnelheid")  
  
  
## <a name="activity-policy-reference"></a>Verwijzing naar het activiteitenbeleid  
In deze sectie vindt u naslaginformatie over beleidsregels, met een uitleg van elk beleidstype en de velden die voor elk beleid kunnen worden geconfigureerd.  
  
Een **activiteitenbeleid** is een op API’s gebaseerd beleid waarmee u de cloudactiviteiten van uw organisatie kunt controleren, waarbij rekening wordt gehouden met meer dan twintig filters voor bestanden met metagegevens (inclusief apparaattype en locatie). Op basis van de beleidsresultaten kunnen meldingen worden gegenereerd en kunnen gebruikers worden geblokkeerd vanuit de cloud-app.   
Elk beleid bestaat uit de volgende onderdelen:  
  
-   Activiteitfilters – hiermee kunt u zeer gedetailleerde voorwaarden op basis van metagegevens maken.  
  
-   Activiteit overeenkomstig de parameters – hiermee kunt u een drempel instellen voor het aantal keren dat een activiteit wordt herhaald voordat de activiteit wordt beschouwd als overeenkomstig het beleid.  Geef aan hoe vaak een activiteit moet worden herhaald voordat het overeenkomt met het beleid, bijvoorbeeld het instellen van een beleid om te waarschuwen wanneer een gebruiker tien mislukte aanmeldpogingen uitvoert binnen twee minuten.  **Activiteit overeenkomstig de parameters** vindt standaard een overeenkomst voor elke activiteit die voldoet aan alle activiteitfilters.   
Met behulp van **Herhaalde activiteit** kunt u het aantal herhaalde activiteiten instellen, alsmede de periode waarin de activiteiten worden geteld. U kunt zelfs opgeven dat alle activiteiten moeten worden uitgevoerd door dezelfde gebruiker en in dezelfde cloud-app.  
  
  
-   Acties – het beleid bevat een reeks beheeracties die automatisch kunnen worden toegepast wanneer schendingen worden gedetecteerd.  
## <a name="see-also"></a>Zie ook  
[Beleidsregels voor gegevensbescherming](data-protection-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  