---
title: Automatisch uploaden van logboeken configureren voor doorlopende rapporten | Microsoft Docs
description: In dit onderwerp vindt u informatie over het uploaden van logboeken om automatische Cloud Discovery-rapporten te maken.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: c4123272-4111-4445-b6bd-2a1efd3e0c5c
ms.reviewer: reutam
ms.suite: ems
translationtype: Human Translation
ms.sourcegitcommit: ed4ea71b24767d3602d40894d1cbac7447bcd8a2
ms.openlocfilehash: 9672336d69f19875d160eb414bf3ca2c525692e1


---

# <a name="configure-automatic-log-upload-for-continuous-reports"></a>Automatisch uploaden van logboeken configureren voor doorlopende rapporten
Voordat u automatische logboekbestandsverzameling instelt, moet u controleren of uw logboek overeenkomt met het verwachte logboektype, zodat uw bestand kan worden geparseerd met Cloud App Security. 

## <a name="technical-requirements"></a>Technische vereisten
- Hypervisor: Hyper-v- of VMware
- Schijfruimte: 250 GB
- CPU: 2
- RAM: 4 GB 
- Firewall-instellingen: 
- Toestaan dat de logboekverzamelaar inkomend FTP- en Syslog-verkeer mag ontvangen
- Toestaan dat de logboekverzamelaar uitgaand verkeer naar de portal mag starten (bijvoorbeeld contoso.cloudappsecurity.com) op poort 443

  
## <a name="set-up-automatic-log-file-collection"></a>Automatische logboekbestandsverzameling instellen  
  
Met een logboekverzamelaar kunt u het uploaden van logboeken vanaf uw netwerk eenvoudig automatiseren. De logboekverzamelaar wordt uitgevoerd op uw netwerk en ontvangt logboeken via Syslog of FTP. Elk logboek wordt automatisch verwerkt, gecomprimeerd en naar de portal verzonden. De FTP-logboeken worden naar Cloud App Security geüpload nadat de FTP-overdracht naar de logboekverzamelaar voor het bestand is voltooid. Voor Syslogs worden de ontvangen logboeken met de logboekverzamelaar elke 20 minuten naar de schijf geschreven en wordt het bestand vervolgens naar Cloud App Security geüpload.  De virtuele machine voor de logboekverzamelaar is beschikbaar voor de VHD-indeling van Hyper-V en de OVF-indeling voor hypervisor van VMware. Hiervoor is 250 GB aan schijfruimte, 2 CPU's en 4 GB RAM vereist. 
     
  
     The log collector VHD image can be downloaded and run on Azure servers.  
  
2.  Ga naar de pagina met instellingen voor automatisch uploaden:  
    Klik in de Cloud App Security-portal op het pictogram Instellingen ![pictogram Instellingen](./media/settings-icon.png "settings icon"), klik op **Cloud Discovery-instellingen** en selecteer het tabblad **Logboeken automatisch uploaden**.  
  
3.  Maak voor elke firewall of proxy waaruit u logboeken wilt uploaden een overeenkomende gegevensbron aan:  
  
    1.  Klik op **Gegevensbron toevoegen**.  
  
    2.  Geef uw proxy of firewall een **Naam**.  
  
    3.  Selecteer het apparaat in de lijst **Bron**.  
  
    4.  Vergelijk uw logboek met het voorbeeld van de verwachte logboekindeling. Als de bestandsindeling van uw logboek niet met dit voorbeeld overeenkomt, moet u uw gegevensbron toevoegen onder **Overig**.  
  
    5.  Stel het **Type ontvanger** in op **FTP** of **Syslog**.  
  
         Kies **UDP** of **TCP** voor **Syslog**.  
  
    6.  Herhaal dit proces voor elke firewall en proxy waarvan het logboek kan worden gebruikt om verkeer op uw netwerk te detecteren.  
  
4.  Ga naar het tabblad **Logboekverzamelaars** bovenaan.  
  
    1.  Klik op **Logboekverzamelaar toevoegen**.  
  
    2.  Geef de logboekverzamelaar een **Naam**.  
  
    3.  Selecteer alle **Gegevensbronnen** die u met de verzamelaar verbinding wilt laten maken en klik op **Bijwerken**.  
  
         > [!NOTE] 
       > Kopieer de inhoud van het scherm. U hebt deze informatie nodig tijdens het configureren van de logboekverzamelaar voor de communicatie met Cloud App Security. Als u Syslog hebt geselecteerd, wordt ook informatie weergegeven over de poort waarop de Syslog-listener luistert.
         
![Detectiegegevensbronnen](./media/discovery-data-sources.png)
> [!NOTE] 
         > Eén logboekverzamelaar kan meerdere gegevensbronnen verwerken.
  
4.  **Download** een nieuwe virtuele machine voor de logboekverzamelaar door te klikken op Hyper-V of VMWare en decomprimeer het bestand met het wachtwoord dat u in de portal hebt ontvangen.  
  
## <a name="set-up-your-virtual-machine-in-hyperv"></a>Ga als volgt te werk om uw virtuele machine in Hyper-V in te stellen:  
  
1.  Open Hyper-V-beheer.  
  
2.  Selecteer **Nieuw** en vervolgens **Virtuele machine** en klik dan op **Volgende**.  
  
             ![discovery hyperv virtual machine](./media/discovery-hyperv-virtual-machine.png "discovery hyperv virtual machine")  
  
3.  Geef een **naam** voor de nieuwe virtuele machine op, bijvoorbeeld CloudAppSecurityLogCollector01. Klik vervolgens op **Volgende**.  
  
4.  Selecteer **Generatie 1** en klik op **Volgende**.  
  
5.  Wijzig het **Opstartgeheugen** naar **4096 MB**.  
        
6. Vink **Dynamisch geheugen gebruiken** aan voor deze virtuele machine en klik op **Volgende**.  
  
7.  Kies de **Verbinding** voor het netwerk, indien beschikbaar, en klik op **Volgende**.  
  
8.  Kies **Een bestaande virtuele harde schijf gebruiken** en selecteer het **VHD**-bestand dat in het ZIP-bestand zat dat u hebt gedownload.  
  
9.  Klik op **Volgende** en klik vervolgens op **Voltooien**.  
  
             The machine will be added to your Hyper-V environment.  
  
9. Klik op de machine in de tabel **Virtuele machines** en klik op **Start**.   
  
10. Maak verbinding met de virtuele machine voor de logboekverzamelaar om te zien of hieraan een DHCP-adres is toegewezen. Hiervoor klikt u op de virtuele machine en selecteert u **Verbinden**. Als het goed is, wordt de aanmeldingsprompt weergegeven. Als u een IP-adres ziet, kunt u verbinding maken met de virtuele machine met behulp van een terminal-/SSH-hulpprogramma.  Als u het IP-adres niet ziet, meldt u zich aan met behulp van de Hyper-V-/VMWare-verbindingshulpprogramma's met de referenties die u hebt gekopieerd tijdens het maken van de bovenstaande logboekverzamelaar. U kunt het wachtwoord wijzigen en u kunt de virtuele machine configureren door de volgende opdracht uit te voeren:
```
sudo network_config
```
> [!NOTE]
> De virtuele machine is vooraf geconfigureerd voor het ophalen van een IP-adres via een DHCP-server. Als u vaste IP-adressen, een standaardgateway, een hostnaam, DNS-servers en NTPS wilt configureren, kunt u het hulpprogramma **network_config** gebruiken of de wijzigingen handmatig aanbrengen.


Uw logboekverzamelaar is nu verbonden met uw netwerk en kan de Cloud App Security-portal bereiken.  

## <a name="log-in-and-import"></a>Aanmelden en importeren 
Ga als volgt te werk als u zich voor het eerst wilt aanmelden bij de logboekverzamelaar en de configuratie van de logboekverzamelaar vanuit de portal wilt importeren: 

1.  Meld u aan bij de logboekverzamelaar via SSH met behulp van de referenties voor de interactieve beheerder die u in de portal heeft gekregen. (Als dit de eerste keer is dat u zich bij de console aanmeldt, moet u het wachtwoord wijzigen en u na het wijzigen van het wachtwoord opnieuw aanmelden. Als u gebruikmaakt van een terminalsessie, moet u de terminalsessie mogelijk opnieuw opstarten. )
2.  Voer het hulpprogramma voor de configuratie van de verzamelaar uit met het toegangstoken dat u hebt ontvangen tijdens het maken van de logboekverzamelaar. 

```
sudo collector_config <access token>
```

3. Voer uw consoledomein in, bijvoorbeeld:

```
contoso.portal.cloudappsecurity.com
```

Dit is beschikbaar via de URL die u ziet nadat u zich hebt aangemeld bij de Cloud App Security-portal. 
 

4. Voer de naam in van de logboekverzamelaar die u wilt configureren, bijvoorbeeld:

**CloudAppSecurityLogCollector01** of **NewYork** in de bovenstaande afbeelding.
 
8.  Importeer op de volgende manier de configuratie van de logboekverzamelaar uit de portal:  
  
      1.  Meld u aan bij de logboekverzamelaar via SSH met behulp van de referenties voor de interactieve beheerder die u in de portal heeft gekregen.  
  
       2.  Voer het hulpprogramma voor de configuratie van de verzamelaar uit met het toegangstoken dat u in de opdracht **sudo collector_config \<toegangstoken>** hebt ontvangen.  
  
             Voer uw consoledomein in, bijvoorbeeld:  
  
             **contoso.portal.cloudappsecurity.com ** 
  
             Voer de naam in van de logboekverzamelaar die u wilt configureren, bijvoorbeeld:  
  
             **CloudAppSecurityLogCollector01**  
  
5.  Configureer volgens de richtlijnen in het dialoogvenster uw netwerkfirewalls en proxy's, zodat ze periodiek logboeken naar de toegewezen Syslog-poort van de FTP-map exporteren, bijvoorbeeld:  
  
     `London Zscaler - Destination path: 614`  
  
     `SF Blue Coat - Destination path: \\CloudAppSecurityCollector01\BlueCoat\`  
  
6.  Gebruik het beheerlogboek om te controleren dat logboeken periodiek naar de portal worden geüpload.  
  
## <a name="log-collector-performance"></a>Prestaties logboekverzamelaar
De logboekverzamelaar kan een logboekcapaciteit van maximaal 50 GB per uur aan.

De belangrijkste knelpunten in het logboekverzamelproces zijn:
* Netwerkbandbreedte - de netwerkbandbreedte bepaalt de uploadsnelheid van het logboek.
* I/O-prestaties van de virtuele machine die door uw IT is toegewezen - bepaalt de snelheid waarmee logboeken naar de schijf van de logboekverzamelaar worden geschreven.

De logboekverzamelaar heeft een ingebouwd beveiligingsmechanisme dat de snelheid waarmee logboeken binnenkomen bewaakt en vergelijkt met de uploadsnelheid. In geval van congestie laat de logboekverzamelaar logboekbestanden vallen. Als uw installatie meestal groter is dan 50 GB per uur, dan is het raadzaam om het verkeer over meerdere logboekverzamelaars te spreiden.


<!--HONumber=Oct16_HO4-->


