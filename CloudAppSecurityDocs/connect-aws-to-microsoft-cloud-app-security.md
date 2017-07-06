---
title: Verbinding maken tussen AWS en Cloud App Security voor zichtbaarheid en gebruikscontrole | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen de AWS-app en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/19/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a6b4c745-cd5c-4458-819c-80cbe8b25f29
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 68d4c221626706ca641a5d3e1986da543771561a
ms.sourcegitcommit: 2f4474084c7e07ac4853945ab5aa1ea78950675d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/28/2017
---
# <a name="connect-aws-to-microsoft-cloud-app-security"></a>Verbinding maken tussen AWS en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande Amazon Web Services-account met behulp van de connector-API's.  
  
## <a name="how-to-connect-amazon-web-services-to-cloud-app-security"></a>Verbinding maken tussen Amazon Web Services en Cloud App Security  
  
1.  Klik in uw [Amazon Web Services-console](https://console.aws.amazon.com/)onder **Identiteits- en toegangsbeheer** op **IAM**.  
  
     ![aws identity and access](./media/aws-identity-and-access.png "aws identity and access")  
  
2.  Klik op het tabblad **Gebruikers** en klik vervolgens op **Gebruiker toevoegen**.  
  
     ![aws users](./media/aws-users.png "aws users")      
  
4.  In de stap **Details** geeft u een nieuwe gebruikersnaam op voor Cloud-App Security en zorgt u ervoor dat u onder **Toegangstype** **Programmeerniveau** selecteert en klikt u op **Volgende machtigingen**.  

     ![AWS create user](./media/aws-create-user.png "AWS create user")

5. In de stap **Machtigingen** selecteert u **Bestaande beleidsregels rechtstreeks koppelen** en klikt u vervolgens op **Beleid maken**.

   ![AWS attach user](./media/aws-attach-user-policy.png "AWS attach existing policy")

6.  Onder **Beleid maken** selecteert u **Uw eigen beleid maken**.
 
    ![AWS create your own policy](./media/aws-create-own-policy.png "AWS create policy")
 
7.  Onder **Beleid controleren**, geeft u een **Beleidsnaam** op, bijvoorbeeld CloudAppSecurityPolicy.

    ![AWS review policy](./media/aws-review-policy.png "AWS review policy")

8. Plak het volgende in het **Beleidsdocument**-veld en klik op **Beleid maken**:
  
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
  
9. Terug in het scherm **Gebruiker toevoegen**, vernieuwt u indien nodig de lijst, selecteert u vervolgens de gebruiker die u zojuist hebt gemaakt en klikt u op **Volgende controle**.

   ![AWS review user policy](./media/aws-review-user.png "AWS review user")

10. Als alle informatie juist is, klikt u op **Gebruiker toevoegen**.

    ![AWS user permissions](./media/aws-user-permissions.png "AWS review user permissions")

11. Wanneer u het bericht ontvangt dat het is voltooid, klikt u op **Downloaden .csv** om een kopie van de referenties van de nieuwe gebruiker op te slaan. U hebt deze later nodig.  

    ![AWS downloaden csv](./media/aws-download-csv.png "AWS csv downloaden")
  
10. Klik in de AWS-console op **Services** en klik vervolgens onder **Beheerhulpprogramma's** op **CloudTrail**.  
  
     ![aws cloudtrail](./media/aws-cloudtrail.png "aws cloudtrail")  
  
    Als u CloudTrail nog niet eerder hebt gebruikt, klikt u op **Get Started** (Aan de slag) en stelt u dit in door een naam in te geven, de juiste S3-bucket te kiezen en op **Inschakelen** te klikken. Als u zeker wilt weten dat u volledige dekking hebt, stelt u **Toepassen op alle regio's** in op **Ja**.
  
       ![AWS turn on CloudTrail](./media/aws-turnon-cloudtrail.png "AWS turn on CloudTrail")
  
    U moet nu de naam van de nieuwe CloudTrail in de **Trails**-lijst zien.
    
      ![AWS CloudTrail list](./media/aws-cloudtrail-list.png "AWS CloudTrail list")
  
11. Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **Verbonden apps**.  
  
12. Klik op de pagina **App-connectors** op de knop met het plusteken en vervolgens op **AWS**.  
  
     ![connect AWS](./media/connect-aws.png "connect AWS")  
  
13. Plak in het pop-upvenster de **Toegangssleutel** en **Geheime sleutel** uit het CSV-bestand in de relevante velden en klik op **Verbinden**.  
   ![AWS connect app](./media/aws-connect-app.png "AWS connect app") 
  
14. Controleer of de verbinding tot stand is gekomen door op **Test API** te klikken.  
  
     Het testen kan enkele minuten duren. Wanneer de test is voltooid, ontvangt u een melding dat deze is Geslaagd of Mislukt. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Gereed**.  
  
Nadat u AWS hebt verbonden, ontvangt u gebeurtenissen van 7 dagen voorafgaand aan de verbinding, tenzij u CloudTrail zojuist hebt ingeschakeld, in welk geval u gebeurtenissen ontvangt vanaf het moment dat u CloudTrail hebt ingeschakeld.
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  