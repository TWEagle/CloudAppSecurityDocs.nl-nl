---
title: Verbinding maken tussen AWS en Microsoft Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u informatie over het maken van verbinding tussen de AWS-app en Cloud App Security via de API-connector.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: a6b4c745-cd5c-4458-819c-80cbe8b25f29
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 4b9ab028bb45f77513217dd3784cefc73e984962


---

# <a name="connect-aws-to-microsoft-cloud-app-security"></a>Verbinding maken tussen AWS en Microsoft Cloud App Security
In deze sectie vindt u instructies voor het maken van een verbinding tussen Cloud App Security en uw bestaande Amazon Web Services-account met behulp van de connector-API's.  
  
## <a name="how-to-connect-amazon-web-services-to-cloud-app-security"></a>Verbinding maken tussen Amazon Web Services en Cloud App Security  
  
1.  Klik in de Amazon Web Services-console op **Identiteits- en toegangsbeheer**.  
  
     ![AWS-identiteit en -toegang](./media/aws-identity-and-access.png "aws identity and access")  
  
2.  Klik op het tabblad **Gebruikers**.  
  
     ![AWS-gebruikers](./media/aws-users.png "aws users")  
  
3.  Klik op **Nieuwe gebruikers maken**.  
  
     ![AWS-gebruiker maken](./media/aws-create-user.png "AWS create user")  
  
4.  Maak een nieuwe gebruiker voor Cloud App Security en zorg ervoor dat het selectievakje **Generate an access key for each user** (Voor elke gebruiker een toegangssleutel genereren) is ingeschakeld.  
  
5.  Klik op **Referenties downloaden**.  
  
     ![AWS-referenties downloaden](./media/aws-dl-cred.png "aws dl cred")  
  
6.  Klik op het tabblad **Permissions** (Machtigingen) op **Attach Policy** (Beleid koppelen).  
  
     ![AWS-gebruikersbeleid koppelen](./media/aws-attach-user-policy.png "aws attach user policy")  
  
7.  Het scherm **Review Policy** (Controlebeleid) wordt geopend.
 
     ![Controlebeleid](./media/aws-review-policy.png "aws review policy")  
  

8. Typ AdallomTrustPolicy onder **Policy Name** (Naam van beleid). 
10. Kopieer en plak het volgende onder **Policy Document** (Beleidsdocument):  
  
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
  
9. In het gedownloade bestand `credentials.csv`, vindt u de referenties voor de nieuwe gebruiker. U moet deze later kopiëren.  
  
10. Ga terug naar de hoofdpagina van de AWS-console en kies rechts bovenin uw regio uit het vervolgkeuzemenu. Klik vervolgens op **CloudTrail** in het hoofdmenu.  
  
     ![AWS-cloudtrail](./media/aws-cloudtrail.png "aws cloudtrail")  
  
    1.  Als u CloudTrail nog niet hebt gebruikt voor deze regio, klikt u op **Get Started** (Aan de slag) en stelt u dit in door de juiste S3-bucket te kiezen.  
  
         Klik op het tabblad **Configuratie** links bovenin het scherm. Klik onder **Aanvullende configuratie** op het pictogram Bewerken.  
  
         ![AWS-cloudtrail configureren](./media/aws-cloudtrail-config.png "aws cloudtrail config")  
  
    2.  Klik op **Ja** wanneer u wordt gevraagd **Globale services omvatten** en klik vervolgens op **Opslaan**. Dit is alleen van toepassing op de regio die u hebt gekozen.  
  
         ![Globale AWS-services opnemen](./media/aws-include-global-svc.png "aws include global svc")  
  
    3.  Herhaal stap 11 voor alle regio's, maar stel geen andere regio in op Include global services.  
  
11. Klik in de Cloud App Security-portal op **Onderzoeken** en vervolgens op **Erkende apps**.  
  
12. Klik in de rij AWS op **Verbinden** in de kolom **App Connector-status**, of klik op de knop **Verbinding maken met een app** en vervolgens op **AWS**.  
  
     ![Verbinding maken met AWS](./media/connect-aws.png "connect AWS")  
  
13. Ga naar de pagina Instellingen in Amazon Web Service, plak de **Toegangssleutel** en **Geheime sleutel** uit het CSV-bestand in de velden op de API-pagina en klik op **Toegangssleutel bijwerken**.  
  
14. Controleer of de verbinding tot stand is gekomen door op **API testen** te klikken.  
  
     Het testen kan enkele minuten duren. Wanneer de test is voltooid, ontvangt u een melding dat deze is Geslaagd of Mislukt. Na de ontvangst van de melding dat de actie voltooid is, klikt u op **Gereed**.  
  
Nadat u verbinding hebt gemaakt met AWS, ontvangt u gebeurtenissen tot 7 dagen voorafgaand aan de verbinding.
  
## <a name="see-also"></a>Zie ook  
[Cloud-apps beheren met beleidsregels](control-cloud-apps-with-policies.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Oct16_HO4-->


