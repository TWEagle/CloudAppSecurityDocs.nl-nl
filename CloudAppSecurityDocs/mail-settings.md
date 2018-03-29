---
title: Voorkeuren voor e mailmeldingen instellen | Microsoft Docs
description: Dit artikel bevat informatie over het aanpassen van de e-mailmeldingen die worden verzonden door Cloud App Security.
keywords: ''
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 3/26/2018
ms.topic: get-started-article
ms.prod: ''
ms.service: cloud-app-security
ms.technology: ''
ms.assetid: 8402cdc9-4969-4150-b567-ccc9d75e5370
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 96f3b317a453053ceb55a304c6f1481e5c371def
ms.sourcegitcommit: 1d5d46beb200cf1eed0ef46806effa93eac1a224
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/28/2018
---
##  <a name="mailsettings"></a> Voorkeuren voor e mailmeldingen instellen  

Volg deze procedure om parameters voor e-mailmeldingen van Cloud App Security wordt verzonden naar beheerders instellen aanvragende waarschuwingen en meldingen te verzenden naar eindgebruikers over schendingen waarbij zij betrokken zijn, zijn. Zie voor informatie over de IP-adres voor Cloud App Security e-server die u moet de goedgekeurde IP-adressen in uw service tegen ongewenste e-mail [vereisten](network-requirements.md). 


1. Klik in de menubalk op het instellingentandwiel ![Instellingenpictogram](./media/settings-icon.png "Instellingenpictogram") en selecteer **instellingen**, en selecteer vervolgens de **e-mailinstellingen** tabblad.  

2. **Van e-mailadres**: het e-mailaccount dat u wilt gebruiken om de melding te verzenden.  
   
   **Van weergavenaam**: de naam die u wilt weergeven in het veld **Van** van het e-mailbericht.  
   > [!NOTE]
   > Unicode-tekens worden ondersteund in de weergavenaam en het e-mailadres volgens de [standaard rfc822](http://www.rfc-editor.org/rfc/rfc822.txt).

   **E-mailadres voor beantwoording**: het e-mailaccount dat moet worden gebruikt voor antwoorden op het bericht.  
  
     ![e-mailinstellingen, configuratie](./media/mail-settings-config.png "e-mailinstellingen, configuratie")  

  >[!NOTE]
  >Wijzigen van de **van e-mailadres** veld aan een domein van uw eigen, raadpleegt u de instructies [hier](https://mandrill.zendesk.com/hc/articles/205582277-How-do-I-add-DNS-records-for-my-sending-domains-).
  
2.  U kunt een HTML-bestand gebruiken voor het aanpassen en **ontwerpen van de e-mailberichten** die vanuit het systeem worden verzonden. Het HTML-bestand dat wordt gebruikt voor de sjabloon moet het volgende omvatten:  
  
    -   Alle sjabloon CSS-bestanden moeten inline in de sjabloon.  
  
    -   De sjabloon moet drie niet-bewerkbare tijdelijke aanduidingen hebben:  
  
         %%logo%% - een URL naar uw bedrijfslogo, dat is geüpload naar de pagina met algemene instellingen.  
  
         %%title%% - een tijdelijke aanduiding voor de titel van het e‑mailbericht, zoals ingesteld door het beleid.  

         %%content%% - een tijdelijke aanduiding voor de inhoud die wordt opgenomen voor eindgebruikers, zoals ingesteld door het beleid.  
     
3.  Klik op **Een sjabloon uploaden...** en selecteer het bestand dat u hebt gemaakt. 

4. Klik vervolgens op **Een test-e-mail verzenden** om een test-e‑email te verzenden naar uzelf met een voorbeeld van de sjabloon die u hebt gemaakt. Het e-mailbericht wordt verzonden naar het account waarmee u zich hebt aangemeld bij de portal. In de test-e-mail kunt u de metagegevensvelden, de sjabloon, het onderwerp van de e-mail, de titel in de hoofdtekst van de e-mail en de inhoud zien.  Hier volgt een voorbeeld e-mailsjabloon: 



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
  

  
  

  
    
## <a name="see-also"></a>Zie ook  
[Cloud Discovery instellen](set-up-cloud-discovery.md)   

[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  