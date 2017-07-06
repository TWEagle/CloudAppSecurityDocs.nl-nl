---
title: Verbinding maken tussen Box en Cloud App Security voor zichtbaarheid en gebruikscontrole | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen de Box-app en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/19/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b3e4713e-986f-4a5e-9fcc-f8de94dd0df7
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 11716fb83acfb893dce29c7f4179788d40bef7a4
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2017
---
# <a name="connect-box-to-microsoft-cloud-app-security"></a>Verbinding maken tussen Box en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande Box-account met behulp van de connector-API's voor de app.  
  
## <a name="how-to-connect-box-to-cloud-app-security"></a>Verbinding maken tussen Box en Microsoft Cloud App Security  
  
> [!NOTE]  
>  Als u een account implementeert dat geen beheerdersaccount is, mislukt de API-test en kan Cloud App Security niet alle bestanden in Box scannen. Als dit problemen voor u oplevert, kunt u gebruikmaken van een co-beheerder waarbij alle bevoegdheden zijn aangevinkt. Hierdoor blijft de API-test echter mislukken en worden bestanden van andere beheerders in Box niet gescand.  
  
1.  Als u toegang tot machtigingen van de toepassing beperkt, volgt u deze stap. Ga anders verder met stap 2.  
  
    -   Klik op het pictogram Instellingen en vervolgens op **Bedrijfsinstellingen** in de beheerconsole van Box.  
  
         ![box business settings](./media/box-business-settings.png "box business settings")  
  
    -   Klik op het tabblad **Apps**.  
  
         ![box apps](./media/box-apps.png "box apps")  
  
    -   Als **Unpublished Applications** (Niet-gepubliceerde toepassingen) is geselecteerd, voegt u in het tekstvak **Except for** (Behalve voor) het serienummer in van de Cloud App Security-app (`nduj1o3yavu30dii7e03c3n7p49cj2qh`) en klikt u op **Save** (Opslaan).  
  
         ![box settings except for](./media/box-settings-except-for.png "box settings except for")  
  
    > [!NOTE]  
    >  Als u een bestaande Adallom-klant bent en uw console-URL voor Adallom is en niet voor Cloud App Security, gebruikt u dit serienummer voor de app: bwahmilhdlpbqy2ongkl119o3lrkoshc.  
  
2.  Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
3.  Klik op de pagina **App-connectors** op de knop met het plusteken en selecteer **Box**.  
  
     ![connect box](./media/connect-box.png "connect box")  
  
4.  Klik in het pop-upvenster **Vakinstellingen** op **Deze koppeling volgen**.  
  
5.  Hiermee opent u de Box-aanmeldingspagina. Voer uw referenties in om Cloud App Security toegang te geven tot de Box-app van uw team.  
  
6.  Box geeft een melding weer om u te vragen of u Cloud App Security toegang wilt geven tot de gegevens van uw team en het activiteitenlogboek en toestemming wilt geven om willekeurige activiteiten uit te voeren als een willekeurig teamlid. Klik op **Toestaan** om door te gaan.  
  
7.  In de Cloud App Security-portal zou u nu een bericht moeten ontvangen, waarin staat vermeld dat er verbinding is gemaakt met Box.  
  
8.  Controleer of de verbinding tot stand is gekomen door op **Test API** te klikken.  
  
     Het testen kan enkele minuten duren. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Sluiten**.  
  
Box is nu verbonden met Cloud App Security.  
 
Nadat u verbinding hebt gemaakt met Box, ontvangt u gebeurtenissen tot 60 dagen voorafgaand aan de verbinding.
  
Na de verbinding met Box wordt in Cloud App Security een volledige scan uitgevoerd. Afhankelijk van hoeveel bestanden en gebruikers u hebt, kan het voltooien van de volledige scan even duren. Als u NRT-scans (Near Real-Time) wilt inschakelen, worden de bestanden waarvoor activiteit is gedetecteerd naar het begin van de scanwachtrij verplaatst. Een bestand dat wordt bewerkt, bijgewerkt of gedeeld, wordt bijvoorbeeld direct gescand en voor een dergelijk bestand wordt niet op het reguliere scanproces gewacht. Dit geldt niet voor bestanden die niet inherent zijn gewijzigd, bijvoorbeeld bestanden die zijn weergegeven, afgedrukt, geëxporteerd of waarvan een voorbeeld is bekeken.
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  