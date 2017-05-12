---
title: Beheerderstoegang tot de Cloud App Security-portal beheren | Microsoft Docs
description: Dit onderwerp biedt instructies voor het instellen van toegang tot de Cloud App Security-portal voor uw beheerders.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/7/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: b718edad-350c-4d90-b045-92529d701dc5
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: ce7a3bb3951e16efeaeafa3e2fc463a3ac5d9dbc
ms.sourcegitcommit: 945cb3c047ae1bfc05be20cc7798c43005b27c9b
ms.translationtype: HT
ms.contentlocale: nl-NL
---
## <a name="managing-admin-access"></a>Beheerderstoegang beheren

Cloud App Security ondersteunt de volgende beheerdersrollen:

- Globale beheerder: globale beheerders hebben **volledige toegang**: beheerders met volledige toegang hebben volledige machtigingen in Cloud App Security om beheerders toe te voegen, beleidsregels en -instellingen toe te voegen, logboeken te uploaden en beheeracties uit te voeren.
- Beveiligingsbeheerder: beveiligingsbeheerders hebben **volledige toegang**: beheerders met volledige toegang hebben volledige machtigingen in Cloud App Security om beheerders toe te voegen, beleidsregels en -instellingen toe te voegen, logboeken te uploaden en beheeracties uit te voeren.
- Beveiligingslezer: beveiligingslezers hebben alleen-lezenmachtigingen en kunnen waarschuwingen beheren. Beveiligingslezers kunnen de volgende acties niet uitvoeren:
      - Beleidsregels maken of bestaande beleidsregels bewerken of wijzigen 
      - Beheeracties uitvoeren 
      - Detectielogboeken uploaden
      - Apps van derden verbieden of goedkeuren
      - De instellingenpagina voor het IP-adresbereik openen en weergeven
      - Instellingenpagina’s in het algemeen openen en weergeven 
      - De detectie-instellingen openen en weergeven 
      - De pagina App-connectors openen en weergeven
      - Het beheerlogboek openen en weergeven 
      - De pagina Momentopnamerapporten beheren openen en weergeven 

Beheerders die deze rollen hebben in Azure Active Directory of Office 365, hebben dezelfde rollen in Cloud App Security. Zie voor meer informatie [Beheerdersrollen toewijzen in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/active-directory-assign-admin-roles).

Meer beheerders toevoegen aan Cloud App Security:

1. Klik op het tandwiel Instellingen ![instellingenpictogram](./media/settings-icon.png "instellingenpictogram") en vervolgens op **Beheerderstoegang beheren**. 

2. Voeg de beheerders toe die toegang moeten hebben tot Cloud App Security.
  
      
3. Klik vervolgens op de vervolgkeuzelijst om het type toegang voor de beheerder in te stellen, **volledige toegang** of **beveiligingslezer**.

     >[!NOTE]
      >Een **beveiligingslezer** die probeert toegang te krijgen tot een pagina met beperkte toegang of probeert een actie met beperkte toegang uit te voeren, ontvangt een foutbericht dat hij of zij geen machtiging heeft om de pagina te openen of de actie uit te voeren.

4. Klik op **Sluiten**.  

   >[!NOTE]
    >Elke niet-uitgenodigde gebruiker (met een juiste rol: globale beheerder, beveiligingsbeheerder of compliancebeheerder) kan andere gebruikers uitnodigen voor Cloud App Security.
  
 ![beheerderstoegang beheren](./media/manage-admin-access.png "beheerderstoegang beheren")  

**Beheerdersmachtigingen overschrijven:**

Als u een beheerdersmachtiging van Azure Active Directory of Office 365 wilt overschrijven, kunt u de gebruiker handmatig toevoegen aan Cloud App Security en een rol toewijzen aan de gebruiker.
Als u bijvoorbeeld aan Sabien, die beveiligingslezer is in Azure Active Directory, volledige toegang wilt toewijzen in Cloud App Security, kunt u haar handmatig toevoegen aan Cloud App Security en haar volledige toegang toewijzen om haar rol te overschrijven en haar de gewenste machtigingen te verlenen in Cloud App Security. 


##  <a name="Adminsettings"></a> Uw beheerinstellingen aanpassen  
Als u uw voorkeuren als beheerder van Cloud App Security wilt instellen, klikt u op uw naam in de menubalk van de portal en selecteert u **Gebruikersinstellingen** om het volgende in te stellen:  
  
1.  Klik op **Accountinstellingen**. Hier kunt u de taal van de portal voor uw eigen weergave aanpassen. U kunt de taal instellen om de portal weer te geven in ofwel de standaardtaal of u kunt een andere taal instellen voor uzelf.  
  
     ![aangepaste gebruikersinstellingen](./media/custom-user-settings.png "aangepaste gebruikersinstellingen")  
  
2.  Klik op **Meldingen** en stel de voorkeuren voor e-mail- en sms-berichten in die u van het systeem ontvangt.  U kunt het ernstniveau instellen voor de waarschuwingen en schendingen waarvoor u e-mails wilt ontvangen. Het ernstniveau wordt per beleid ingesteld, zodat u bij activering van een schending een e-mailmelding ontvangt, afhankelijk van deze instelling en de ernstinstelling in het beleid dat is geschonden. E-mailberichten worden verzonden naar de alias die is gekoppeld aan het beheerdersaccount dat u hebt gebruikt voor aanmelding bij Cloud App Security. Voer een telefoonnummer in zodat Cloud App Security u sms-berichten kan sturen wanneer waarschuwingen en meldingen worden verzonden, en stel het ernstniveau in waarvoor u meldingen wilt ontvangen via een sms-bericht.  
  
   > [!NOTE] 
   > Het maximum aantal waarschuwingen dat via een sms-bericht kan worden verzonden, is 10 per telefoonnummer per dag. Houd er rekening mee dat de dag wordt bepaald op basis van de UTC-tijdzone. 
  
  ![instellingen voor meldingen](./media/notification-settings.png "instellingen voor meldingen")  
  
3. Wanneer u klaar bent, klikt u op **Opslaan**.  


## <a name="region-and-language-settings"></a>De regio-en taalinstellingen  
  
1. De standaardinstelling **Taal** moet worden gebruikt voor de portal. Als u de taal wilt wijzigen voor een specifieke beheerder, gaat u naar **Gebruikersinstellingen** > **Accountinstellingen**.  
  
   ![tijdzonetaal](./media/timezone-language.png "tijdzonetaal")  
  
2. Stel de **Hoofdtijdzone** in. In Cloud App Security worden uw gegevens continu geanalyseerd en verzameld. De tijdzone voor de Cloud App Security-portal is standaard ingesteld op UTC. Het is belangrijk om de hoofdtijdzone in te stellen, zodat Cloud App Security de incidenten in uw systeem nauwkeurig kan dateren. Een voorbeeld: de gegevens in de grafiek Activiteit worden georganiseerd op datum. Deze datums worden beïnvloed door de tijdzone van uw systeem. Als u de standaardtijdzone niet hebt gewijzigd, worden uw gegevens georganiseerd in 24-uurs dagen volgens de UTC-tijdzone, wat een afwijking van vele uren kan veroorzaken.  
  
     ![hoofdtijdzone](./media/master-time-zone.png "hoofdtijdzone")  
  
## <a name="back-up-portal-settings"></a>Back-up maken van portal-instellingen

Als u op enig moment een back-up wilt maken van uw portal-instellingen, biedt dit scherm hiervoor de mogelijkheid. Klik op Portal-instellingen exporteren om een json-bestand te maken van al uw portal-instellingen, zoals beleidsregels, gebruikersgroepen en IP-adresbereiken.  
  
![back-upconsole](./media/backup-console.png "back-upconsole")  
  
##  <a name="mailsettings"></a> Uw ervaring aanpassen  
Klik in de menubalk op het pictogram Instellingen ![pictogram instellingen](./media/settings-icon.png "pictogram instellingen") en selecteer **E‑mailinstellingen** om de parameters in te stellen voor e‑mailmeldingen die vanuit Cloud App Security worden verzonden naar beheerders die om waarschuwingen vragen, en voor meldingen die naar eindgebruikers worden verzonden over schendingen waarbij zij betrokken zijn.  
  
![e-mailinstellingen, menu](./media/mail-setting-menu.png "e-mailinstellingen, menu")  
  
Configureer het volgende:  
  
1.  **Van e-mailadres**: het e-mailaccount dat u wilt gebruiken om de melding te verzenden.  
  
     **Van weergavenaam**: de naam die u wilt weergeven in het veld **Van** van het e-mailbericht.  
  
     **E-mailadres voor beantwoording**: het e-mailaccount dat moet worden gebruikt voor antwoorden op het bericht.  
  
     ![e-mailinstellingen, configuratie](./media/mail-settings-config.png "e-mailinstellingen, configuratie")  
  
2.  U kunt een HTML-bestand gebruiken voor het aanpassen en ontwerpen van de e-mailberichten die vanuit het systeem worden verzonden. Het HTML-bestand dat wordt gebruikt voor de sjabloon moet het volgende omvatten:  
  
    -   Alle sjabloon-CSS moet inline in de sjabloon zitten.  
  
    -   De sjabloon moet drie niet-bewerkbare tijdelijke aanduidingen hebben:  
  
         %%logo%% - een URL naar uw bedrijfslogo, dat is geüpload naar de pagina met algemene instellingen.  
  
         %%title%% - een tijdelijke aanduiding voor de titel van het e‑mailbericht, zoals ingesteld door het beleid.  
  
         %%content%% - een tijdelijke aanduiding voor de inhoud die wordt opgenomen voor eindgebruikers, zoals ingesteld door het beleid.  
  
     Hier volgt een voorbeeld e-mailsjabloon: 
```html
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
  <html>  
       <head>  
            <meta http-equiv="Content-Type" content="text/html; charset=UTF-8"/>  
            <meta name="viewport" content="width=device-width, initial-scale=1.0"/>  
          </head>  
          <body class="end-user">  
          <table border="0" cellpadding="20%" cellspacing="0" width="100%" id="background-table">  
            <tr>  
              <td align="center">  
                <!--[if (gte mso 9)|(IE)]>  
                <table width="600" align="center" cellpadding="0" cellspacing="0" border="0">  
                  <tr>  
                    <td>  
                <![endif]-->  
                <table bgcolor="#ffffff" align="center" border="0" cellpadding="0" cellspacing="0" style="padding-bottom: 40px;" id="container-table">  
                  <tr>  
                    <td align="right" id="header-table-cell">  
                      <img src="%%logo%%" alt="Microsoft Cloud App Security" id="org-logo" />  
                    </td>  
                  </tr>  
                  <tr>  
                    <td style="padding-top: 58px;" align="center" valign="top">  
                      <table width="100%" cellpadding="12">  
                        <tr>  
                          <td align="center" class="round-title">  
                            %%title%%  
                          </td>  
                        </tr>  
                      </table>  
                    </td>  
                  </tr>  
                  <tr>  
                    <td style="padding: 0 40px 79px 40px;" class="content-table-cell" align="left" valign="top">  
                        %%content%%  
                    </td>  
                  </tr>  
                  <tr>  
                    <td class="last-row"></td>  
                  </tr>  
                </table>  
                <!--[if (gte mso 9)|(IE)]>  
                </td>  
                </tr>  
                </table>  
                  <![endif]-->  
              </td>  
              </tr>  
          </table>  
            </body>  
          </html>  
    ```

  
3.  Click **Upload a template...** and select the file you created.  
  
     Then, click **Send a test email** to send yourself a test email to see an example of the template you created.  
     The email will be sent to the account you used to log into the portal. In the test email you will be able to see the metadata fields, the template, the email subject, the title in the email body and the content.  
  
## Single sign-on  
Cloud App Security is coupled with Azure Active Directory for authentication, provisioning, and licensing related activities. For information on how to manage single sign-on, see [Azure Active Directory federation compatibility list: third-party identity providers that can be used to implement single sign-on](https://msdn.microsoft.com/library/azure/jj679342.aspx).  


> [!NOTE] 
> If you use ExpressRoute, Cloud App Security is deployed in Azure and fully integrated with [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). All interactions with the Cloud App Security apps and traffic sent to Cloud App Security, including upload of discovery logs, is routed via ExpressRoute **public peering** for improved latency, performance and security. There are no configuration steps required from the customer side.  
    For more information about  Public Peering, see [ExpressRoute circuits and routing domains](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/).  
    
## See Also  
[Set up Cloud Discovery](set-up-cloud-discovery.md)   
[For technical support, please visit the Cloud App Security assisted support page.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier customers can also choose Cloud App Security directly from the Premier Portal.](https://premier.microsoft.com/)  
  
  