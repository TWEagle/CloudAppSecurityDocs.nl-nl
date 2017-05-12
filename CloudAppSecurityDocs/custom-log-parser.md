---
title: Gebruik de aangepaste logboekparser voor logboeken die niet worden ondersteund | Microsoft Docs
description: Dit artikel biedt informatie over hoe u de aangepaste logboekparser kunt gebruiken om logboeken voor apparaten die niet worden ondersteund naar Cloud App Security te uploaden.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/7/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a612d87e-5471-4add-b4b1-dbbb530f2b61
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 73da4104de24a7b2e6814f04b227140b0b57235f
ms.sourcegitcommit: 945cb3c047ae1bfc05be20cc7798c43005b27c9b
ms.translationtype: HT
ms.contentlocale: nl-NL
---
# <a name="use-a-custom-log-parser"></a>Een aangepaste logboekparser gebruiken
In Cloud App Security kunt u een aangepaste parser configureren die overeenkomt met de indeling van uw logboeken en die deze indeling kan verwerken. Zo kunt u de logboeken gebruiken voor Cloud Discovery, ook als ze afkomstig zijn van een firewall of apparaat die of dat niet expliciet wordt ondersteund door Cloud App Security. 

Met de aangepaste parser kunt u logboeken van niet-ondersteunde firewalls gebruiken door deze procedure te volgen. 


 
Een aangepaste CSV-parser configureren:
1.    Klik in de Cloud App Security-portal op **Detecteren** en vervolgens op **Nieuw momentopnamerapport maken**.  
  
    ![Een nieuw momentopnamerapport maken](./media/create-new-snapshot-report.png)
     
3.  Voer een **rapportnaam** en een **beschrijving** in.
  
4.  Selecteer bij **Gegevensbron** **Aangepaste logboekindeling...**.  

     ![Nieuw momentopnamerapport](./media/custom-log-upload.png)   

5. Verzamel de logboeken van uw firewall en proxy, waarmee gebruikers in uw organisatie toegang tot internet hebben. Zorg dat u logboeken verzamelt tijdens piekverkeer die representatief zijn voor alle gebruikersactiviteit in uw organisatie. 

6. Open de logboeken die u wilt verwerken in een teksteditor en controleer de indeling. Zorg dat de kolomnamen in het logboek overeenkomen met de velden op het scherm **Aangepaste logboekindeling**.

  ![aangepaste logboekparser](./media/log-data.png) 

7. Vul vervolgens de velden in op basis van uw gegevens om af te bakenen welke kolommen in de gegevens betrekking hebben op welke specifieke velden in Cloud App Security. Mogelijk moet u de kolomnamen in het logboekbestand wijzigen om juiste correlaties te maken.
  
   > [!NOTE]
    > De namen van de velden zijn hoofdlettergevoelig. Zorg dat u de dezelfde namen van de kolommen in Cloud App Security en in het logboekbestand typt, met precies dezelfde spelling. Zorg ook dat de datumnotatie die u kiest identiek is.

   ![aangepaste logboekparser](./media/custom-log-parser.png) 


7. Klik op **Opslaan**. De aangepaste logboekindeling die u hebt geconfigureerd, wordt opgeslagen als standaardversie van de aangepaste parser. U kunt deze op elk gewenst moment bewerken door op Bewerken te klikken.

5. Selecteer onder **Verkeerslogboeken kiezen** het logboek dat u hebt gewijzigd en upload dit. U kunt maximaal 20 bestanden tegelijk uploaden. Gecomprimeerde en gezipte bestanden worden ook ondersteund.  
  

6.  Klik op **Maken**.  

7.  Nadat het uploaden is voltooid, verschijnt in de rechterbovenhoek van uw scherm een statusbericht waarin wordt aangegeven dat uw logboek is geüpload.  
  
8.  Na het uploaden van uw logboekbestanden duurt het even voordat ze zijn geparseerd en geanalyseerd.  
Als de verwerking van uw logboekbestanden is voltooid, ontvangt u een e-mail met de melding dat de verwerking is voltooid. 
  
9. Boven aan de portal in de statusbalk verschijnt een meldingsbanner om u op de hoogte te houden van de verwerkingsstatus van uw logboekbestanden.  
![Menubalk logboekbestandsverwerking](./media/processing-log-file-menu-bar.png) 
   
10. Nadat de logboeken zijn geüpload, krijgt u een melding te zien waarin wordt aangegeven dat de verwerking van de logboekbestanden is voltooid. U kunt het rapport nu weergeven door op de koppeling in de statusbalk te klikken of door naar het tandwiel Instellingen te gaan en **Detectie-instellingen** te selecteren.   
  
     ![Tabblad Detectie-instellingen](./media/discovery-settings-tab.png)
11. Selecteer vervolgens **Momentopnamerapporten beheren** en selecteer uw momentopnamerapport.
 
    ![momentopnamerapport beheren](./media/snapshot-report-managment.png)

  
      




## <a name="see-also"></a>Zie ook
 
[Momentopnamerapporten maken van Cloud Discovery](create-snapshot-cloud-discovery-reports.md)

[Automatisch uploaden van logboeken configureren voor doorlopende rapporten](configure-automatic-log-upload-for-continuous-reports.md)

[Werken met Cloud Discovery-gegevens](working-with-cloud-discovery-data.md)

