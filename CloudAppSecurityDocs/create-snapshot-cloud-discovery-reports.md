---
title: Momentopnamerapporten maken van het gebruik van Cloud Discovery-apps | Microsoft Docs
description: In dit artikel leest u hoe u logboeken handmatig kunt uploaden om een momentopnamerapport van uw Cloud Discovery-apps te maken.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 2/25/2018
ms.topic: article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: ecc1949d-c861-4636-952a-c3a260719bb5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 05cb45b90f6527a6e4fd08ac29cca2a5ecd9ab0d
ms.sourcegitcommit: 3c66f12aa31ba211235787ee6f233138ea5f8a75
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2018
---
# <a name="create-snapshot-cloud-discovery-reports"></a>Momentopnamerapporten maken van Cloud Discovery
Het is belangrijk een logboek handmatig te uploaden en het logboek in Cloud App Security te parseren voordat u de automatische logboekverzamelaar gebruikt.
Als u nog geen logboek hebt en wilt zien hoe uw logboek eruit zou kunnen zien, volgt u de onderstaande procedure om een voorbeeld van een logboekbestand te downloaden.


Ga als volgt te werk om een momentopnamerapport te maken:
  
1. Verzamel de logboekbestanden van uw firewall en proxy, via welke gebruikers in uw organisatie toegang tot het Internet krijgen. Zorg dat u logboeken verzamelt tijdens piekverkeer die representatief zijn voor alle gebruikersactiviteit in uw organisatie.  
  
2. Klik in de Cloud App Security-portal op **Detecteren** en vervolgens op **Nieuw momentopnamerapport maken**.  
  
   ![Een nieuw momentopnamerapport maken](./media/create-new-snapshot-report.png)
     
3. Voer een **rapportnaam** en een **beschrijving** in.
  
    ![Nieuw momentopnamerapport](./media/new-snapshot-report.png) 

4. Selecteer de **Gegevensbron** vanwaaruit u de logboekbestanden wilt uploaden.  
  
5. Controleer uw logboekindeling en controleer of deze hetzelfde is als in het voorbeeld dat u kunt downloaden. Klik op **Weergeven en controleren** en klik op **Voorbeeldlogboek downloaden**. Vergelijk vervolgens uw logboek met het voorbeeld om te controleren of de indeling hetzelfde is. 

   ![De logboekindeling controleren](./media/cloud-discovery-snapshot-verify.png)  

   > [!NOTE]
   > De FTP-voorbeeld-indeling wordt ondersteund in momentopnamen en geautomatiseerde uploaden terwijl syslog automatisch uploaden alleen wordt ondersteund.<br></br>
   Downloaden van een voorbeeldlogboek downloadt een FTP-voorbeeldlogboek.


6. **Kies de verkeerslogboeken** die u wilt uploaden. U kunt maximaal 20 bestanden tegelijk uploaden. Gecomprimeerde en gezipte bestanden worden ook ondersteund.  
  
7. Klik op **Maken**.  

8. Nadat het uploaden is voltooid, verschijnt in de rechterbovenhoek van uw scherm een statusbericht waarin wordt aangegeven dat uw logboek is geüpload.  
  
9. Na het uploaden van uw logboekbestanden duurt het even voordat ze zijn geparseerd en geanalyseerd.  
   Als de verwerking van uw logboekbestanden is voltooid, ontvangt u een e-mail met de melding dat de verwerking is voltooid. 
  
10. Boven aan de portal in de statusbalk verschijnt een meldingsbanner om u op de hoogte te houden van de verwerkingsstatus van uw logboekbestanden.  
    ![Menubalk logboekbestandsverwerking](./media/processing-log-file-menu-bar.png) 
   
11. Nadat de logboeken zijn geüpload, krijgt u een melding te zien waarin wordt aangegeven dat de verwerking van de logboekbestanden is voltooid. U kunt het rapport nu weergeven door op de koppeling in de statusbalk te klikken of door naar het tandwiel Instellingen te gaan en **Detectie-instellingen** te selecteren.   
  
     ![Tabblad Detectie-instellingen](./media/discovery-settings-tab.png)
12. Selecteren **momentopname maken van rapporten** en selecteert u de momentopname van een rapport.
 
![momentopnamerapport beheren](./media/snapshot-report-managment.png)

  
      
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
    
      
  