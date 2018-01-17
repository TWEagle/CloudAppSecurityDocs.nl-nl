---
title: Verbinding maken tussen AWS en Cloud App Security voor zichtbaarheid en gebruikscontrole | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen de AWS-app en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 1/15/2018
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a6b4c745-cd5c-4458-819c-80cbe8b25f29
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 06844dfc86947bff1baaf3234b3c2949b57ff49a
ms.sourcegitcommit: 458e936e1ac548eda37e9bf955b439199bbdd018
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2018
---
# <a name="connect-aws-to-microsoft-cloud-app-security"></a>Verbinding maken tussen AWS en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande Amazon Web Services-account met behulp van de connector-API's.  
  
## <a name="how-to-connect-amazon-web-services-to-cloud-app-security"></a>Verbinding maken tussen Amazon Web Services en Cloud App Security  
  
1.  Klik in uw [Amazon Web Services-console](https://console.aws.amazon.com/)onder **Identiteits- en toegangsbeheer** op **IAM**.  
  
     ![AWS identiteits- en toegangsbeheer](./media/aws-identity-and-access.png "AWS identiteits- en toegangsbeheer")  
  
2.  Klik op het tabblad **Gebruikers** en klik vervolgens op **Gebruiker toevoegen**.  
  
     ![AWS users](./media/aws-users.png "AWS users")      
  
4.  In de **Details** stap, typt u een nieuwe gebruikersnaam voor Cloud App Security. Zorg ervoor dat onder **toegangstype** u **toegang op programmeerniveau** en klik op **volgende machtigingen**.  

     ![gebruiker maken in AWS](./media/aws-create-user.png "gebruiker maken in AWS")

5. Klik op het tabblad JSON:

     ![AWS JSON](./media/aws-json.png "AWS JSON-tabblad")

6. Plak het volgende script in het opgegeven gebied:

    ```     
    {  
      "Version" : "2012-10-17",  
      "Statement" : [{  
          "Action" : [  
            "cloudtrail:DescribeTrails",  
            "cloudtrail:LookupEvents",  
            "cloudtrail:GetTrailStatus",  
            "cloudwatch:Describe*",  
            "cloudwatch:Get*",  
            "cloudwatch:List*",  
            "iam:List*",  
            "iam:Get*"  
          ],  
          "Effect" : "Allow",  
          "Resource" : "*"  
        }  
      ]  
     }  
  
    ```  

     ![AWS code](./media/aws-code.png "AWS code")
    
6. Klik op **beleid bekijken**.

7. Geef een **naam** en klik op **beleid maken**.

     ![AWS naam beleid](./media/aws-create-policy.png "AWS-beleid maken")

9. Terug in de **gebruiker toevoegen** scherm en vernieuw de lijst met indien nodig, selecteert u de gebruiker hebt gemaakt Klik op **volgende controle**.

   ![Bekijk gebruikersbeleid in AWS](./media/aws-review-user.png "revisie gebruiker in AWS")

10. Als alle informatie juist is, klikt u op **Gebruiker toevoegen**.

    ![Gebruikersmachtigingen in AWS](./media/aws-user-permissions.png "gebruikersmachtigingen in AWS controleren")

11. Wanneer u het bericht ontvangt, klikt u op **downloaden CSV** een kopie van de referenties van de nieuwe gebruiker wilt opslaan, moet u deze later.  

    ![Downloaden van csv in AWS](./media/aws-download-csv.png "csv in AWS downloaden")
  
10. Klik in de AWS-console op **Services** en klik vervolgens onder **Beheerhulpprogramma's** op **CloudTrail**.  
  
     ![AWS CloudTrail](./media/aws-cloudtrail.png "AWS CloudTrail")  
  
    Als u CloudTrail nog niet eerder hebt gebruikt, klikt u op **Get Started** (Aan de slag) en stelt u dit in door een naam in te geven, de juiste S3-bucket te kiezen en op **Inschakelen** te klikken. Als u zeker wilt weten dat u volledige dekking hebt, stelt u **Toepassen op alle regio's** in op **Ja**.
  
       ![Schakelt u CloudTrail in AWS](./media/aws-turnon-cloudtrail.png "CloudTrail in AWS inschakelen")
  
    U moet nu de naam van de nieuwe CloudTrail in de **Trails**-lijst zien.
    
      ![Lijst met CloudTrail in AWS](./media/aws-cloudtrail-list.png "CloudTrail lijst in AWS")
  
11. Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
12. Klik op de pagina **App-connectors** op de knop met het plusteken en vervolgens op **AWS**.  
  
     ![connect AWS](./media/connect-aws.png "connect AWS")  
  
13. Plak in het pop-upvenster de **Toegangssleutel** en **Geheime sleutel** uit het CSV-bestand in de relevante velden en klik op **Verbinden**.  
   ![Verbinding maken met de app AWS](./media/aws-connect-app.png "AWS-app verbinden") 
  
14. Controleer of de verbinding tot stand is gekomen door op **Test API** te klikken.  
  
     Het testen kan enkele minuten duren. Als dit is voltooid, krijgt u een melding slagen of mislukken. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Gereed**.  
  
Nadat u verbinding maakt met AWS, ontvangt u gebeurtenissen voor zeven dagen vóór de verbinding. Als u CloudTrail zojuist hebt ingeschakeld, in dat geval ontvangt u gebeurtenissen van de tijd die u CloudTrail ingeschakeld.
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  