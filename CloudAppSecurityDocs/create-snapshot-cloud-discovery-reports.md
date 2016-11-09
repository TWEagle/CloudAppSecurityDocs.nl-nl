---
title: Momentopnamerapporten maken van Cloud Discovery | Microsoft Docs
description: In dit artikel leest u hoe u logboeken handmatig kunt uploaden om een momentopnamerapport van uw Cloud Discovery-apps te maken.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: ecc1949d-c861-4636-952a-c3a260719bb5
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 669d1c1942e8c7e930cd2421e9b56821eff04d12


---

# <a name="create-snapshot-cloud-discovery-reports"></a>Momentopnamerapporten maken van Cloud Discovery
Het is belangrijk een logboek handmatig te uploaden en het logboek in Cloud App Security te parseren voordat u de automatische logboekverzamelaar gebruikt.

Ga als volgt te werk om een momentopnamerapport te maken:
  
1.  Verzamel de logboekbestanden van uw firewall en proxy, via welke gebruikers in uw organisatie toegang tot het Internet krijgen. Zorg dat u logboeken verzamelt tijdens piekverkeer die representatief zijn voor alle gebruikersactiviteit in uw organisatie.  
  
2.  Klik in de Cloud App Security-portal op **Detecteren** en vervolgens op **Nieuw momentopnamerapport maken**.  
  
     ![Een nieuw momentopnamerapport maken](./media/create-new-snapshot-report.png)
     
      
3.  Voer een **rapportnaam** en een **beschrijving** in.
  
4.  Selecteer de **Gegevensbron** vanwaaruit u de logboekbestanden wilt uploaden.  
  
5.  **Kies de verkeerslogboeken** die u wilt uploaden. U kunt maximaal 20 bestanden tegelijk uploaden.  
  
6.  Klik op **Maken**.  
  
     ![Nieuw momentopnamerapport](./media/new-snapshot-report.png) 
  
7.  Nadat het uploaden is voltooid, verschijnt in de rechterbovenhoek van uw scherm een statusbericht waarin wordt aangegeven dat uw logboek is geüpload.  
  
8.  Na het uploaden van uw logboekbestanden duurt het even voordat ze zijn geparseerd en geanalyseerd.  
Als de verwerking van uw logboekbestanden is voltooid, ontvangt u een e-mail met de melding dat de verwerking is voltooid. 
  
9. Boven aan de portal in de statusbalk verschijnt een meldingsbanner om u op de hoogte te houden van de verwerkingsstatus van uw logboekbestanden.  
  
![Menubalk logboekbestandsverwerking](./media/processing-log-file-menu-bar.png) 
  
     After the logs are uploaded successfully, you should see a notification letting you know that the log file processing completed successfully.  
   
10. U kunt het rapport nu weergeven door op de koppeling in de statusbalk te klikken of door naar het tandwiel Instellingen te gaan en **Detectie-instellingen** te selecteren.   
  
     ![Tabblad Detectie-instellingen](./media/discovery-settings-tab.png)
11. Selecteer vervolgens **Momentopnamerapporten beheren** en selecteer uw momentopnamerapport.
 
![Momentopnamerapport beheren](./media/snapshot-report-managment.png)
      
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
    
      
  


<!--HONumber=Oct16_HO4-->


