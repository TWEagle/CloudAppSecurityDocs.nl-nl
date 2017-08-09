---
title: Verbinding maken met Azure Cloud App Security voor zichtbaarheid en controle over gebruik | Microsoft Docs
description: In dit onderwerp bevat informatie over verbinding maken tussen Azure en Cloud App Security met de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/8/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 3a677bc7-c8b7-4c6a-aada-82c8b3778352
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b418663d21653b1393999f50cc620a230d0b97dc
ms.sourcegitcommit: b446a82c945de6452813aac7780f6a3a264495e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/09/2017
---
# <a name="connect-azure-to-microsoft-cloud-app-security"></a>Verbinding maken met Azure en Microsoft Cloud App Security

Deze sectie geeft instructies voor de Cloud App Security verbinding met uw bestaande Azure-account met behulp van de connector-API van de app.  
  
## <a name="setting-up-azure-for-connection-to-cloud-app-security"></a>Instellen van Azure voor verbinding met Cloud App Security

Cloud App Security verbindt met Azure via Event Hubs. Deze sectie biedt instructies voor het streamen van uw activiteitenlogboeken naar een enkele Event Hub in uw abonnement. 

### <a name="step-1-stream-your-azure-activity-logs-to-event-hubs"></a>Stap 1: Uw Azure-activiteit stroom logboeken naar Event Hubs

1.  De Azure Activity Log van uw Azure-abonnement naar een Event Hub stream. Ga als volgt de officiële guide in de documentatie van Azure: https://docs.microsoft.com/en-us/azure/monitoring-and-diagnostics/monitoring-stream-activity-logs-event-hubs

 > [!NOTE]
 > Als u meer dan één Azure-abonnement hebt, Herhaal dit voor elk abonnement, maar een enkele Event Hub die wordt gedeeld met uw abonnementen gebruiken.

 Na het voltooien van de instructies wordt een nieuwe Event Hub gemaakt in de Namespace die u hebt gekozen.
 
 > [!NOTE]
 > Als u een fout krijgt na het exporteren van de logboeken van de activiteit, gaat u naar de **resourceproviders** blade in Azure en zorg ervoor dat 'microsoft.insights' is geregistreerd.

### <a name="step-2-get-a-connection-string-to-your-event-hub"></a>Stap 2: Een verbindingsreeks naar uw Event Hub ophalen

1.  Ga naar de **Event Hubs** blade.
  
   ![Event hubs-blade](media/azure-event-hubs.png "Azure event hubs")

2.  Selecteer uw Event Hub-Namespace.
  
    ![Event hub naamruimte](media/azure-namespace.png "Azure naamruimte")

3.  In het menu onder **entiteiten**, klikt u op **Event Hubs**. 
  
    ![Event hubs entiteiten](media/azure-event-hubs-entities.png "Azure event hub-entiteiten")

4.  Selecteer de nieuwe Event Hub is gemaakt door Azure Monitor. Dit sjabloon heet **insights operationele logboeken**.
  
    ![Operational Insights-logboeken](media/azure-insight-operational-logs.png "Azure inzicht operationele Logboeken")
  
  > [!NOTE]
  > Er enkele minuten duren tot de Event Hub is gemaakt.

5. Maak een nieuwe-beleid waarmee u Cloud App Security-machtiging voor het lezen van de Event Hub door te klikken op **gedeeld toegangsbeleid** en klik vervolgens op **toevoegen**.
  
    ![Gedeeld toegangsbeleid](media/azure-shared-access-policies.png "Azure gedeeld toegangsbeleid")

6.  Voer een naam voor het nieuwe beleid en zorg ervoor dat ten minste de **Listen claim**. Wanneer u klaar bent, klikt u op **maken**.
  
    ![Nieuw beleid voor Azure](media/azure-new-policy.png "Azure nieuw beleid maken")

7.  Onder **instellingen** en vervolgens **gedeeld toegangsbeleid**, klikt u op in het toegangsbeleid dat u zojuist hebt gemaakt.   
  
    ![Azure Selecteer beleid](media/azure-select-policy.png "Azure beleid selecteren")

8. Kopieer een van de verbindingsreeksen in het venster beleid door te klikken op de knop naast de **Connection string - primaire sleutel** of **Connection String - secundaire sleutel**.

### <a name="step-3-add-azure-to-cloud-app-security"></a>Stap 3: Azure cloud App Security toevoegen
 
1.  Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
3.  In de **App-connectors** pagina, klikt u op het plusteken om en selecteer **Microsoft Azure**.  
  
     ![verbinding maken met Azure Cloud App Security](media/azure-connect-app.png "verbinding maken met Azure")  
  
4.  In de **verbindingsreeks** veld, plak de verbindingsreeks die u in de vorige stap hebt gekopieerd.  
  
5.  In de **consumergroep** veld:`$Default`
    
   >[!NOTE] 
   > Als u een andere consumergroep moet worden gebruikt hebt gemaakt, gebruikt u dat **consumergroep** naam.
  
6.  Klik op **Verbinden**.
8.  Controleer of de verbinding tot stand is gekomen door op **Test API** te klikken.  
  
     Het testen kan enkele minuten duren. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Sluiten**.  
  





## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  