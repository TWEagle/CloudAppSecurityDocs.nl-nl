---
title: Verbinding maken tussen Box en Cloud App Security voor zichtbaarheid en gebruikscontrole | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen de Box-app en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 9/25/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b3e4713e-986f-4a5e-9fcc-f8de94dd0df7
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 6c8b27ac5d148980463b68feded3667e1ebb19e1
ms.sourcegitcommit: 8759541301241e03784c5ac87b56986f22bd0561
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2017
---
# <a name="connect-box-to-microsoft-cloud-app-security"></a>Verbinding maken tussen Box en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande Box-account met behulp van de connector-API's voor de app.  
  
## <a name="how-to-connect-box-to-cloud-app-security"></a>Verbinding maken tussen Box en Microsoft Cloud App Security  
  
> [!NOTE]  
>  Implementeren met een account dat is niet een beheerdersaccount leidt tot een fout in de API-test en kan geen Cloud App Security alle bestanden in Box scannen. Als dit problemen voor u oplevert, kunt u gebruikmaken van een co-beheerder waarbij alle bevoegdheden zijn aangevinkt. Hierdoor blijft de API-test echter mislukken en worden bestanden van andere beheerders in Box niet gescand.  
  
1.  Als u toegang tot machtigingen van de toepassing beperkt, volgt u deze stap. Ga anders verder met stap 2.  
  
    -   Klik op het pictogram Instellingen en vervolgens op **Bedrijfsinstellingen** in de beheerconsole van Box.  
  
         ![box business settings](./media/box-business-settings.png "box business settings")  
  
    -   Klik op het tabblad **Apps**.  
  
         ![box apps](./media/box-apps.png "box apps")  
  
    -   Als **niet-gepubliceerde toepassingen** is geselecteerd in de **behalve voor** tekst Voeg het serienummer van de Cloud App Security-app:<br></br>US1 Datacenter:`nduj1o3yavu30dii7e03c3n7p49cj2qh` <br></br>EU1 Datacenter:`me9cm6n7kr4mfz135yt0ab9f5k4ze8qp`<br></br>Klik vervolgens op **Opslaan**. Voor meer informatie over om te zien welke gegevens Cloud App Security center u bent verbonden, Zie [API tokens](api-tokens.md). 
  
         ![box settings except for](./media/box-settings-except-for.png "box settings except for")  
  
    > [!NOTE]  
    >  Als u een bestaande Adallom-klant bent en uw console-URL voor Adallom is en niet voor Cloud App Security, gebruikt u dit serienummer voor de app: bwahmilhdlpbqy2ongkl119o3lrkoshc.  
  
2.  Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
3.  Klik op de pagina **App-connectors** op de knop met het plusteken en selecteer **Box**.  
  
     ![connect box](./media/connect-box.png "connect box")  
  
4.  Klik in het pop-upvenster **Vakinstellingen** op **Deze koppeling volgen**.  
  
5.  Hiermee opent u de aanmeldingspagina Box. Voer uw referenties in om Cloud App Security toegang te geven tot de Box-app van uw team.  
  
6.  Vak wordt u gevraagd of u wilt toestaan Cloud App Security-toegang tot de teamgegevens van uw, activiteitenlogboek, en activiteiten uitvoeren als teamlid van een. Klik op **Toestaan** om door te gaan.  
  
7.  In de Cloud App Security-portal zou u nu een bericht moeten ontvangen, waarin staat vermeld dat er verbinding is gemaakt met Box.  
  
8.  Controleer of de verbinding tot stand is gekomen door op **Test API** te klikken.  
  
     Het testen kan enkele minuten duren. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Sluiten**.  
  
Box is nu verbonden met Cloud App Security.  
 
Nadat u verbinding hebt gemaakt met Box, ontvangt u gebeurtenissen tot 60 dagen voorafgaand aan de verbinding.
  
Na de verbinding met Box wordt in Cloud App Security een volledige scan uitgevoerd. Afhankelijk van hoeveel bestanden en gebruikers u hebt, kan het voltooien van de volledige scan even duren. Zodat bijna de real-timescans worden waarop activiteiten worden gedetecteerd verplaatst naar het begin van de wachtrij scan. Bijvoorbeeld, een bestand dat wordt bewerkt, bijgewerkt of gedeeld gescand meteen in plaats van te wachten tot de reguliere scanproces. Bijna de real-timescans geldt niet voor bestanden die inherent niet zijn gewijzigd. Bijvoorbeeld worden bestanden die worden weergegeven, bekeken, afgedrukt of geëxporteerd gescand als onderdeel van de regelmatig geplande scan.
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  