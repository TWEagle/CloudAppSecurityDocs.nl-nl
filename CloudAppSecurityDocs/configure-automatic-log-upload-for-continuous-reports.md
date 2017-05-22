---
title: Automatisch uploaden van logboeken configureren voor doorlopende rapporten in Cloud App Security | Microsoft Docs
description: In dit onderwerp vindt u informatie over het uploaden van logboeken om automatische Cloud Discovery-rapporten te maken.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 5/16/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c4123272-4111-4445-b6bd-2a1efd3e0c5c
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: a5f360181eb9a39bfe50660cfd733ecb51aa161d
ms.sourcegitcommit: cb8238610222953751ff714b346a0b4cf73ac40c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/16/2017
---
# <a name="configure-automatic-log-upload-for-continuous-reports"></a>Automatisch uploaden van logboeken configureren voor doorlopende rapporten
Met een logboekverzamelaar kunt u het uploaden van logboeken vanaf uw netwerk eenvoudig automatiseren. De logboekverzamelaar wordt uitgevoerd op uw netwerk en ontvangt logboeken via Syslog of FTP. Elk logboek wordt automatisch verwerkt, gecomprimeerd en naar de portal verzonden. De FTP-logboeken worden naar Cloud App Security geüpload nadat de FTP-overdracht naar de logboekverzamelaar voor het bestand is voltooid. Voor Syslogs worden de ontvangen logboeken met de logboekverzamelaar elke 20 minuten naar de schijf geschreven en wordt het bestand vervolgens naar Cloud App Security geüpload.

Voordat u automatische logboekbestandsverzameling instelt, moet u controleren of uw logboek overeenkomt met het verwachte logboektype, zodat uw bestand kan worden geparseerd met Cloud App Security. 

>[!NOTE]
>Cloud App Security biedt ondersteuning voor het doorsturen van logboeken vanaf uw SIEM-server naar de logboekverzamelaar, ervan uitgaande dat de logboeken worden doorgestuurd in hun oorspronkelijke indeling. Het wordt echter ten zeerste aangeraden de logboekverzamelaar rechtstreeks met uw firewall en/of proxy te integreren.


## <a name="technical-requirements"></a>Technische vereisten
- Hypervisor: Hyper-v- of VMware
- Schijfruimte: 250 GB
- CPU: 2
- RAM: 4 GB 
- Firewall-instellingen: 
    - Toestaan dat de logboekverzamelaar inkomend FTP- en Syslog-verkeer mag ontvangen
    - Toestaan dat de logboekverzamelaar uitgaand verkeer naar de portal mag starten (bijvoorbeeld contoso.cloudappsecurity.com) op poort 443

  
## <a name="log-collector-performance"></a>Prestaties logboekverzamelaar
De logboekverzamelaar kan een logboekcapaciteit van maximaal 50 GB per uur aan.
De belangrijkste knelpunten in het logboekverzamelproces zijn:
- Netwerkbandbreedte - de netwerkbandbreedte bepaalt de uploadsnelheid van het logboek.
- I/O-prestaties van de virtuele machine die door uw IT is toegewezen - bepaalt de snelheid waarmee logboeken naar de schijf van de logboekverzamelaar worden geschreven.
De logboekverzamelaar heeft een ingebouwd beveiligingsmechanisme dat de snelheid waarmee logboeken binnenkomen bewaakt en vergelijkt met de uploadsnelheid. In geval van congestie laat de logboekverzamelaar logboekbestanden vallen. Als uw installatie meestal groter is dan 50 GB per uur, dan is het raadzaam om het verkeer over meerdere logboekverzamelaars te spreiden.

## <a name="set-up-and-configuration"></a>Installatie en configuratie  
  
### <a name="step-1--web-portal-configuration-define-data-sources-and-link-them-to-a-log-collector"></a>Stap 1 - Webportalconfiguratie: gegevensbronnen definiëren en deze koppelen aan een logboekverzamelaar  
  
1.  Ga naar de pagina met instellingen voor automatisch uploaden:  
    Klik in de Cloud App Security-portal op het pictogram Instellingen ![pictogram Instellingen](./media/settings-icon.png "settings icon") en vervolgens op **Logboekverzamelaars**.  
  
3.  Maak voor elke firewall of proxy waaruit u logboeken wilt uploaden een overeenkomende gegevensbron aan:  
  
    a.  Klik op **Gegevensbron toevoegen**.  
  
    b.  Geef uw proxy of firewall een **Naam**.  
  
    c.  Selecteer het apparaat in de lijst **Bron**.  
  
    d.  Vergelijk uw logboek met het voorbeeld van de verwachte logboekindeling. Als de bestandsindeling van uw logboek niet met dit voorbeeld overeenkomt, moet u uw gegevensbron toevoegen onder **Overig**.  
  
    e.  Stel het **Type ontvanger** in op **FTP** of **Syslog**. Kies **UDP** of **TCP** voor **Syslog**.  
  
    f.  Herhaal dit proces voor elke firewall en proxy waarvan het logboek kan worden gebruikt om verkeer op uw netwerk te detecteren.  
  
4.  Ga naar het tabblad **Logboekverzamelaars** bovenaan.  
  
    a.  Klik op **Logboekverzamelaar toevoegen**.  
  
    b.  Geef de logboekverzamelaar een **Naam**.  
  
    c.  Selecteer alle **gegevensbronnen** die u aan de verzamelaar wilt koppelen en klik op **Bijwerken** om de configuratie op te slaan en een toegangstoken te genereren.  
![detectiegegevensbronnen](./media/discovery-data-sources.png)
  
  > [!NOTE] 
  > - Eén logboekverzamelaar kan meerdere gegevensbronnen verwerken.
  > - Kopieer de inhoud van het scherm. U hebt deze informatie nodig tijdens het configureren van de logboekverzamelaar voor de communicatie met Cloud App Security. Als u Syslog hebt geselecteerd, wordt ook informatie weergegeven over de poort waarop de Syslog-listener luistert.
4.  **Download** een nieuwe virtuele machine voor de logboekverzamelaar door te klikken op Hyper-V of VMWare en decomprimeer het bestand met het wachtwoord dat u in de portal hebt ontvangen.  
  
###    <a name="step-2--on-premises-deployment-of-the-virtual-machine-and-network-configuration"></a>Stap 2 - On-premises implementatie van de virtuele machine en de netwerkconfiguratie   

> [!NOTE] 
> In de volgende stappen wordt de implementatie in Hyper-V beschreven. De implementatiestappen voor de VM-hypervisor zijn iets anders.  

1.  Open Hyper-V-beheer.  
  
2.  Selecteer **Nieuw** en vervolgens **Virtuele machine** en klik dan op **Volgende**.  
 ![detectie hyperv virtuele machine](./media/discovery-hyperv-virtual-machine.png "discovery hyperv virtual machine")  
  
3.  Geef een **naam** voor de nieuwe virtuele machine op, bijvoorbeeld CloudAppSecurityLogCollector01. Klik vervolgens op **Volgende**.  
  
4.  Selecteer **Generatie 1** en klik op **Volgende**.  
  
5.  Wijzig het **Opstartgeheugen** naar **4096 MB**.  
        
6. Vink **Dynamisch geheugen gebruiken** aan voor deze virtuele machine en klik op **Volgende**.  
  
7.  Kies de **Verbinding** voor het netwerk, indien beschikbaar, en klik op **Volgende**.  
  
8.  Kies **Een bestaande virtuele harde schijf gebruiken** en selecteer het **VHD**-bestand dat in het ZIP-bestand zat dat u hebt gedownload.  
  
9.  Klik op **Volgende** en klik vervolgens op **Voltooien**.  
    De machine wordt aan uw Hyper-V-omgeving toegevoegd.  
  
9. Klik op de machine in de tabel **Virtuele machines** en klik op **Start**.   
  
10. Maak verbinding met de virtuele machine voor de logboekverzamelaar om te zien of hieraan een DHCP-adres is toegewezen. Hiervoor klikt u op de virtuele machine en selecteert u **Verbinden**. Als het goed is, wordt de aanmeldingsprompt weergegeven. Als u een IP-adres ziet, kunt u verbinding maken met de virtuele machine met behulp van een terminal-/SSH-hulpprogramma.  Als u het IP-adres niet ziet, meldt u zich aan met behulp van de Hyper-V-/VMWare-verbindingshulpprogramma's met de referenties die u hebt gekopieerd tijdens het maken van de bovenstaande logboekverzamelaar. U kunt het wachtwoord wijzigen en u kunt de virtuele machine configureren met het netwerkconfiguratiehulpprogramma door de volgende opdracht uit te voeren:
```
sudo network_config
```
> [!NOTE]
> De virtuele machine is vooraf geconfigureerd voor het ophalen van een IP-adres via een DHCP-server. Als u vaste IP-adressen, een standaardgateway, een hostnaam, DNS-servers en NTPS wilt configureren, kunt u het hulpprogramma **network_config** gebruiken of de wijzigingen handmatig aanbrengen.


Uw logboekverzamelaar is nu verbonden met uw netwerk en kan de Cloud App Security-portal bereiken.  

### <a name="step-3--on-premises-configuration-of-the-log-collection"></a>Stap 3 - On-premises configuratie van de logboekverzamelaar 
Ga als volgt te werk als u zich voor het eerst wilt aanmelden bij de logboekverzamelaar en de configuratie van de logboekverzamelaar vanuit de portal wilt importeren: 

1.  Meld u aan bij de logboekverzamelaar via SSH met behulp van de referenties voor de interactieve beheerder die u in de portal heeft gekregen. (Als dit de eerste keer is dat u zich bij de console aanmeldt, moet u het wachtwoord wijzigen en u na het wijzigen van het wachtwoord opnieuw aanmelden. Als u gebruikmaakt van een terminalsessie, moet u de terminalsessie mogelijk opnieuw opstarten. )
2.  Voer het configuratiehulpprogramma van de verzamelaar uit met het toegangstoken dat u tijdens het maken van de logboekverzamelaar hebt gekregen.```sudo collector_config <access token> ```
3. Voer uw consoledomein in. Bijvoorbeeld: ```contoso.portal.cloudappsecurity.com``` Dit is beschikbaar via de URL die u ziet nadat u zich hebt aangemeld bij de Cloud App Security-portal. 

4. Voer de naam in van de logboekverzamelaar die u wilt configureren, bijvoorbeeld: **CloudAppSecurityLogCollector01** of **NewYork** in de afbeelding hierboven.

5.  Importeer op de volgende manier de configuratie van de logboekverzamelaar uit de portal:  
  
      a.  Meld u aan bij de logboekverzamelaar via SSH met behulp van de referenties voor de interactieve beheerder die u in de portal heeft gekregen.  
  
      b.  Voer het configuratiehulpprogramma van de verzamelaar uit met het toegangstoken dat u in de opdracht ```sudo collector_config \<access token>``` hebt gekregen.  
     
      c.  Voer uw consoledomein in, bijvoorbeeld: ``` contoso.portal.cloudappsecurity.com ```
  
      d. Voer de naam in van de logboekverzamelaar die u wilt configureren, bijvoorbeeld: ``` CloudAppSecurityLogCollector01  ```

### <a name="step-4---on-premises-configuration-of-your-network-appliances"></a>Stap 4 - On-premises configuratie van uw netwerkapparaten

Configureer volgens de richtlijnen in het dialoogvenster uw netwerkfirewalls en proxy's, zodat ze periodiek logboeken naar de toegewezen Syslog-poort van de FTP-map exporteren, bijvoorbeeld:  
  
     `London Zscaler - Destination path: 614`  
  
     `SF Blue Coat - Destination path: \\CloudAppSecurityCollector01\BlueCoat\`  
  
### <a name="step-5---verify-the-successful-deployment-in-the-cloud-app-security-portal"></a>Stap 5 - Controleer of de implementatie is voltooid in de Cloud App Security-portal

Gebruik het beheerlogboek om te controleren of de logboeken periodiek naar de portal worden geüpload.  
  
Zie [Problemen met Cloud Discovery oplossen](troubleshooting-cloud-discovery.md) als u tijdens de implementatie problemen ondervindt.



## <a name="see-also"></a>Zie ook  
[Werken met Cloud Discovery-gegevens](working-with-cloud-discovery-data.md)   
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)   
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit Premier Portal kiezen.](https://premier.microsoft.com/)  
    
      
  