---
title: De portal aanpassen | Microsoft Docs
description: Dit onderwerp bevat de eerste stappen voor het aanpassen van de portal.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 11/21/2016
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 2e7e57b0-db54-4d75-896c-4700dd9abe48
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: 525a6c5274843f63c300e97d1dbd40ece6465edf
ms.openlocfilehash: 3a6750f244d3d0cd8d691ffd768cf5183da78d32


---

# <a name="customize-the-portal"></a>De portal aanpassen
De volgende procedure bevat instructies voor het aanpassen van de Cloud App Security-portal.
  
## <a name="set-up-the-portal"></a>De portal instellen  
  
1.  In de Cloud App Security-portal klikt u op het pictogram Instellingen ![pictogram instellingen](./media/settings-icon.png "pictogram instellingen") in de menubalk en selecteert u **Algemene instellingen** om het volgende te configureren:  
  
3.  **Organisatiegegevens**  
  
     Het is belangrijk dat u een **Weergavenaam organisatie** opgeeft voor uw organisatie. Deze wordt weergegeven op de e-mailberichten en webpagina's die vanuit het systeem worden verzonden.  
  
     Geef een **omgevingsnaam** (tenant) op. Dit is vooral belangrijk als u meerdere tenants beheert.  
  
4. Het is ook mogelijk om een **Logo** op te geven dat wordt weergegeven in e-mailmeldingen en webpagina’s die vanuit het systeem worden verzonden. Het logo moet een PNG-bestand zijn met een maximale grootte van 150 x 50 pixels op een transparante achtergrond.  

4.  Voeg een lijst met uw **Beheerde domeinen** toe. De beheerde domeinen worden gebruikt om Cloud App Security te helpen bepalen welke gebruikers intern en extern zijn en welke bestanden al dan niet mogen worden gedeeld. Dit wordt gebruikt voor rapporten en waarschuwingen.  
> [!NOTE] 
> - Gebruikers in domeinen die niet zijn geconfigureerd als interne gebruikers, worden gemarkeerd als externe gebruikers en voor deze gebruikers worden de activiteiten of bestanden niet gescand.
> - Zie [Integratie van Azure Information Protection](azip-integration.md) voor informatie als u integreert met behulp van Azure Information Protection-integratie. 
  
4.  **Privacyinstellingen voor het e-mailen van het activiteitenlogboek**  
  
     Als er e-mailberichten worden gedetecteerd vanuit Exchange Online, is het mogelijk om in te stellen hoe deze worden weergegeven, ter bescherming van de privacy. Het is mogelijk om in te stellen dat het e-mailbericht moet worden weergegeven met een **Gemaskeerde onderwerpregel**, met de **Volledige onderwerpregel** of met **Alleen ID**.  
  
     ![algemene instellingen](./media/general-settings.png "algemene instellingen")  
  
5.  **Instellingen voor land/regio en taal**  
  
     De standaardinstelling **Taal** moet worden gebruikt voor de portal. Als u de taal wilt wijzigen voor een specifieke beheerder, gaat u naar **Gebruikersinstellingen** > **Accountinstellingen**.  
  
     ![tijdzonetaal](./media/timezone-language.png "tijdzonetaal")  
  
     Stel de **Hoofdtijdzone** in. In Cloud App Security worden uw gegevens continu geanalyseerd en verzameld. De tijdzone voor de Cloud App Security-portal is standaard ingesteld op UTC. Het is belangrijk om de hoofdtijdzone in te stellen, zodat Cloud App Security de incidenten in uw systeem nauwkeurig kan dateren. Een voorbeeld: de gegevens in de grafiek Activiteit worden georganiseerd op datum. Deze datums worden beïnvloed door de tijdzone van uw systeem. Als u de standaardtijdzone niet hebt gewijzigd, worden uw gegevens georganiseerd in 24-uurs dagen volgens de UTC-tijdzone, wat een afwijking van vele uren kan veroorzaken.  
  
     ![hoofdtijdzone](./media/master-time-zone.png "hoofdtijdzone")  
  
6.  Als u op enig moment een back-up wilt maken van uw portal-instellingen, biedt dit scherm hiervoor de mogelijkheid. Klik op Portal-instellingen exporteren om een json-bestand te maken van al uw portal-instellingen, zoals beleidsregels, gebruikersgroepen en IP-adresbereiken.  
  
     ![back-upconsole](./media/backup-console.png "back-upconsole")  
  
7.  Als u extra beheerders wilt toevoegen aan Cloud App Security, klikt u op het tandwiel Instellingen ![pictogram instellingen](./media/settings-icon.png "pictogram instellingen") en vervolgens op **Beheerderstoegang beheren**. Voeg de beheerders toe die toegang moeten hebben tot Cloud App Security en klik op **Sluiten**.  
>[!NOTE]
>Elke niet-uitgenodigde gebruiker (met een juiste rol: globale beheerder, beveiligingsbeheerder of compliancebeheerder) kan andere gebruikers uitnodigen voor Cloud App Security.
  
![beheerderstoegang beheren](./media/manage-admin-access.png "beheerderstoegang beheren")  
  
##  <a name="a-nameadminsettingsa-customize-your-admin-settings"></a><a name="Adminsettings"></a> Uw beheerinstellingen aanpassen  
Als u uw voorkeuren als beheerder van Cloud App Security wilt instellen, klikt u op uw naam in de menubalk van de portal en selecteert u **Gebruikersinstellingen** om het volgende in te stellen:  
  
1.  Klik op **Accountinstellingen**. Hier kunt u de taal van de portal voor uw eigen weergave aanpassen. U kunt de taal instellen om de portal weer te geven in ofwel de standaardtaal of u kunt een andere taal instellen voor uzelf.  
  
     ![aangepaste gebruikersinstellingen](./media/custom-user-settings.png "aangepaste gebruikersinstellingen")  
  
2.  Klik op **Meldingen** en stel de voorkeuren voor e-mail- en sms-berichten in die u van het systeem ontvangt.  U kunt het ernstniveau instellen voor de waarschuwingen en schendingen waarvoor u e-mails wilt ontvangen. Het ernstniveau wordt per beleid ingesteld, zodat u bij activering van een schending een e-mailmelding ontvangt, afhankelijk van deze instelling en de ernstinstelling in het beleid dat is geschonden. E-mailberichten worden verzonden naar de alias die is gekoppeld aan het beheerdersaccount dat u hebt gebruikt voor aanmelding bij Cloud App Security. Voer een telefoonnummer in zodat Cloud App Security u sms-berichten kan sturen wanneer waarschuwingen en meldingen worden verzonden, en stel het ernstniveau in waarvoor u meldingen wilt ontvangen via een sms-bericht.  
  
> [!NOTE] 
> Het maximum aantal waarschuwingen dat via een sms-bericht kan worden verzonden, is 10 per telefoonnummer per dag. Houd er rekening mee dat de dag wordt bepaald op basis van de UTC-tijdzone. 
  
  ![instellingen voor meldingen](./media/notification-settings.png "instellingen voor meldingen")  
  
3. Wanneer u klaar bent, klikt u op **Opslaan**.  
  
##  <a name="a-nameiptagsandrangesa-organize-the-data-according-to-your-needs"></a><a name="IPtagsandRanges"></a> De gegevens volgens uw behoeften organiseren  
Om bekende IP-adressen, zoals uw fysieke IP-adressen van kantoor, eenvoudig te kunnen herkennen, moet u IP-adresbereiken instellen waarmee u ze op de juiste wijze kunt taggen en indelen en de manier waarop logboeken en waarschuwingen worden weergegeven, kunt aanpassen.   
Elke groep met IP-adresbereiken kan worden ingedeeld op basis van een vooraf gedefinieerde lijst met IP-categorieën of worden getagd met zelfgemaakte IP-tags. Met deze instelling kunt u openbare gegevens over de geografische locatie overschrijven op basis van uw interne netwerkkennis.  
  
IPv4 en IPv6 worden ondersteund.  
  
Klik in de menubalk op het pictogram Instellingen ![pictogram instellingen](./media/settings-icon.png "pictogram instellingen") en selecteer **IP-adresbereiken**. Klik op **+IP-adresbereik toevoegen** en stel het volgende in:  
  
> [!NOTE]  
>  De locatie en de geregistreerde provider overschrijven de standaardinstellingen.   
> IP-tags worden echter toegevoegd aan de activiteit zonder gegevens te overschrijven.  
  
1.  Geef uw IP-adresbereik een **naam**. De naam wordt niet weergegeven in het activiteitenlogboek, maar wordt alleen gebruikt voor het beheren van uw IP-adresbereik.  
  
     Als u het IP-adresbereik wilt opnemen in een IP-categorie, selecteert u een categorie in de vervolgkeuzelijst.  
  
2.  Voer het **IP-adresbereik** in dat u wilt configureren en klik vervolgens op de knop met het plusteken (+). U kunt zoveel IP-adressen en subnetten toevoegen als u wilt met behulp van de notatie voor netwerkvoorvoegsels (ook wel CIDR-notatie genoemd), bijvoorbeeld 192.168.1.0/32.  
  
3.  Als u de (ISP-) velden van de **locatie** of organisatie voor deze adressen wilt overschrijven, voert u een nieuwe waarde in. Als u bijvoorbeeld een IP-adres hebt dat wordt beschouwd als Iers, maar u weet dat het adres zich in de Verenigde Staten bevindt, dan kunt u deze instelling overschrijven.  
  
4.  Voer een **geregistreerde provider** in. Hierdoor worden de gegevens in uw activiteiten overschreven.  
  
5.  Om de activiteiten van deze IP-adressen te **taggen**, voert u een tag in. Als u een woord in het vak invoert, wordt de tag gemaakt. Als u al een geconfigureerde tag hebt, kunt u deze eenvoudig toevoegen aan extra IP-adresbereiken door de tag te kiezen uit de lijst. U kunt zoveel IP-tags toevoegen als u wilt voor elk bereik. IP-tags kunnen worden gebruikt tijdens het samenstellen van beleid.  
  
     Ingebouwde **IP-tags** voor Cloud App Security worden ingesteld voor riskante adressen en worden voortdurend bijgewerkt. Voorbeelden van deze tags zijn anonieme proxy's, satellietproviders, Tor-eindpunten en het Cloud App Security-proxynetwerk. Deze ingebouwde tags zijn niet zichtbaar.  
  
6.  **IP-categorieën** worden gebruikt om activiteiten uit interessante IP-adressen eenvoudig te herkennen. De categorieën die beschikbaar zijn in de portal vereisen nog wel gebruikersconfiguratie om te bepalen welke IP-adressen worden opgenomen in elke categorie, met uitzondering van de categorie Riskant, die twee IP-tags (Anonieme proxy en Tor) omvat.  
  
     De volgende IP-categorieën zijn beschikbaar:  
  
    -   **Beheer**: dit moeten alle IP-adressen van uw beheerders zijn.  
  
    -   **Intern**: dit moeten alle IP-adressen van uw interne netwerk, uw filialen en uw Wifi-roamingadressen zijn.  
  
    -   **Riskant**: dit moeten alle IP-adressen zijn die u beschouwt als riskant. Dit kunnen verdachte IP-adressen zijn die u in het verleden hebt bekeken, IP-adressen in de netwerken van uw concurrenten enzovoort.  
  
    -   **VPN**: dit moeten alle IP-adressen zijn die u voor externe werknemers gebruikt.  
  
    -   **Cloudproxy**: dit moet het IP-adres zijn van uw proxyserver in de cloud.  
  
7.  Wanneer u klaar bent, klikt u op **Maken**.  
  
     ![newipaddress-bereik](./media/newipaddress-range.png "newipaddress-bereik")  
  
##  <a name="a-nameadallommailsettingsa-personalize-your-experience"></a><a name="Adallom_mailsettings"></a> Uw ervaring aanpassen  
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
         

  
3.  Klik op **Een sjabloon uploaden...** en selecteer het bestand dat u hebt gemaakt.  
  
     Klik vervolgens op **Een test-e-mail verzenden** om een test-e‑email te verzenden naar uzelf met een voorbeeld van de sjabloon die u hebt gemaakt.  
     Het e-mailbericht wordt verzonden naar het account waarmee u zich hebt aangemeld bij de portal. In de test-e-mail kunt u de metagegevensvelden, de sjabloon, het onderwerp van de e-mail, de titel in de hoofdtekst van de e-mail en de inhoud zien.  
  
## <a name="single-sign-on"></a>Eenmalige aanmelding  
Cloud App Security is gekoppeld aan Azure Active Directory voor de activiteiten met betrekking tot verificatie, inrichting en licentieverlening. Zie de [federatiecompatibiliteitslijst van Azure Active Directory: eenmalige aanmelding implementeren met identiteitsproviders van derden](https://msdn.microsoft.com/library/azure/jj679342.aspx) voor informatie over het beheren van eenmalige aanmelding.  


> [!NOTE] 
> Als u ExpressRoute gebruikt, is Cloud App Security geïmplementeerd in Azure en volledig geïntegreerd met [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/). Alle interacties met de Cloud App Security-apps en het verkeer dat wordt verzonden naar Cloud App Security, met inbegrip van het uploaden van detectielogboeken, verlopen via **openbare peering** van ExpressRoute voor verbeterde latentie, prestaties en beveiliging. Er zijn geen configuratiestappen vereist door de klant.  
    Zie voor meer informatie over openbare peering [ExpressRoute-circuits en routeringsdomeinen](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/).  
    
## <a name="see-also"></a>Zie ook  
[Cloud Discovery instellen](set-up-cloud-discovery.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
  
  


<!--HONumber=Dec16_HO2-->


