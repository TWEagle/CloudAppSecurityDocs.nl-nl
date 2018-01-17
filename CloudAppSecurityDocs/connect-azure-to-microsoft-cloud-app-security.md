---
title: Verbinding maken met Azure Cloud App Security voor zichtbaarheid en controle over gebruik | Microsoft Docs
description: In dit onderwerp bevat informatie over verbinding maken tussen Azure en Cloud App Security met de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 3a677bc7-c8b7-4c6a-aada-82c8b3778352
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 81860849cb2c1a2a6d35c34e893d0e241a5f670f
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2018
---
# <a name="connect-azure-to-microsoft-cloud-app-security"></a>Verbinding maken met Azure en Microsoft Cloud App Security

Deze sectie geeft instructies voor de Cloud App Security verbinding met uw bestaande Azure-account met behulp van de connector-API van de app.  
  
## <a name="setting-up-azure-for-connection-to-cloud-app-security"></a>Instellen van Azure voor verbinding met Cloud App Security

Cloud App Security verbindt met Azure via Event Hubs. Deze sectie biedt instructies voor het streamen van uw activiteitenlogboeken naar een enkele Event Hub in uw abonnement. 

### <a name="step-1-stream-your-azure-activity-logs-to-event-hubs"></a>Stap 1: Uw Azure-activiteit stroom logboeken naar Event Hubs

1.  De Azure Activity Log van uw Azure-abonnement naar een Event Hub stream. Ga als volgt de officiële guide in de documentatie van Azure: https://docs.microsoft.com/en-us/azure/monitoring-and-diagnostics/monitoring-stream-activity-logs-event-hubs

 > [!NOTE]
 > Als u meer dan één Azure-abonnement hebt, herhaalt u deze stap voor elk abonnement met behulp van een enkele Event Hub, gedeeld door uw abonnementen.

 Na het voltooien van de instructies wordt een nieuwe Event Hub gemaakt in de Namespace die u hebt gekozen.
 
 > [!NOTE]
 > Als u een fout krijgt na het exporteren van de logboeken van de activiteit, gaat u naar **resourceproviders** in Azure, in het menu links en zorg ervoor dat 'microsoft.insights' is geregistreerd.

### <a name="step-2-get-a-connection-string-to-your-event-hub"></a>Stap 2: Een verbindingsreeks naar uw Event Hub ophalen

1.  Ga naar de **Event Hubs - Preview** in het menu links.
  
   ![Event hubs menu](media/azure-event-hubs.png "Azure event hubs")

2.  Selecteer uw Event Hub-Namespace.
  
    ![Event hub naamruimte](media/azure-namespace.png "Azure naamruimte")

3.  In het menu onder **entiteiten**, klikt u op **Event Hubs**. 
  
    ![Event hubs entiteiten](media/azure-event-hubs-entities.png "Azure event hub-entiteiten")

4.  Selecteer de nieuwe Event Hub is gemaakt door Azure Monitor. Dit sjabloon heet **insights operationele logboeken**.
  > [!NOTE]
  > Duurt enkele minuten tot de Event Hub is gemaakt.

   ![Operational Insights-logboeken](media/azure-insight-operational-logs.png "Azure inzicht operationele Logboeken")
  
  
5. Maak een nieuwe-beleid waarmee u Cloud App Security-machtiging voor het lezen van de Event Hub door te klikken op **gedeeld toegangsbeleid** en klik vervolgens op **toevoegen**.
  
    ![Gedeeld toegangsbeleid](media/azure-shared-access-policies.png "Azure gedeeld toegangsbeleid")

6.  Voer een naam voor het nieuwe beleid en zorg ervoor dat ten minste de **Listen claim**. Wanneer u klaar bent, klikt u op **maken**.
  
    ![Nieuw beleid voor Azure](media/azure-new-policy.png "Azure nieuw beleid")

7.  Onder **instellingen** en vervolgens **gedeeld toegangsbeleid**, klikt u op in het toegangsbeleid dat u hebt gemaakt.   
  
    ![Azure beleid](media/azure-select-policy.png "Azure beleid")

8. Kopieer een van de verbindingsreeksen in het venster beleid door te klikken op de knop naast **Connection string - primaire sleutel** of **Connection String - secundaire sleutel**.

### <a name="step-3-add-azure-to-cloud-app-security"></a>Stap 3: Azure cloud App Security toevoegen
 
1.  Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
3.  In de **App-connectors** pagina, klikt u op het plusteken om en selecteer **Microsoft Azure**.  
  
     ![verbinding maken met Azure Cloud App Security](media/azure-connect-app.png "verbinding maken met Azure")  
  
4.  In de **verbindingsreeks** veld, plak de verbindingsreeks die u in de vorige stap hebt gekopieerd.  
  
5.  In de **consumergroep** veld:`$Default`
    
   >[!NOTE] 
   > Als u een andere consumergroep moet worden gebruikt hebt gemaakt, gebruikt u dat **consumergroep** naam.
  
6.  Klik op **Connect** verbinding maakt en test de verbinding. Het kan enkele minuten duren. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Sluiten**.  


> [!NOTE]
> Deze functie is afgeschermd voorbeeld.


## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  