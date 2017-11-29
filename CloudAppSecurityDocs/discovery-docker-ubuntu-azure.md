---
title: Automatisch uploaden van logboeken configureren voor doorlopende rapporten | Microsoft Docs
description: In dit onderwerp beschrijft het proces automatisch logboekgegevens uploaden voor continue rapporten configureren in de Cloud App Security met behulp van een Docker op Ubuntu in Azure.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 29/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 9c51b888-54c0-4132-9c00-a929e42e7792
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: feb5bf67709d2bed80af0d6d52cf1efd3d4dc479
ms.sourcegitcommit: 80faf74bea04f9e09b6f04bab1fa99728aff0e3e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/28/2017
---
# <a name="set-up-and-configuration-on-ubuntu"></a>Stel omhoog en configuratie op Ubuntu


## <a name="technical-requirements"></a>Technische vereisten

-   Besturingssysteem: Ubuntu 14.04 of hoger

-   Schijfruimte: 250 GB

-   CPU: 2

-   RAM: 4 GB

-   Uw firewall ingesteld zoals beschreven in [vereisten](network-requirements#log-collector)

## <a name="log-collector-performance"></a>Prestaties logboekverzamelaar

De logboekverzamelaar kan een logboekcapaciteit van maximaal 50 GB per uur aan. De belangrijkste knelpunten in het logboekverzamelproces zijn:

-   Netwerkbandbreedte - de netwerkbandbreedte bepaalt de uploadsnelheid van het logboek.

-   I/O-prestaties van de virtuele machine die door uw IT is toegewezen - bepaalt de snelheid waarmee logboeken naar de schijf van de logboekverzamelaar worden geschreven. De logboekverzamelaar heeft een ingebouwd beveiligingsmechanisme dat de snelheid waarmee logboeken binnenkomen bewaakt en vergelijkt met de uploadsnelheid. In geval van congestie laat de logboekverzamelaar logboekbestanden vallen. Als uw installatie meestal groter is dan 50 GB per uur, is het raadzaam om het verkeer over meerdere logboekverzamelaars te splitsen.

## <a name="set-up-and-configuration"></a>Installatie en configuratie  

### <a name="step-1--web-portal-configuration-define-data-sources-and-link-them-to-a-log-collector"></a>Stap 1 - Webportalconfiguratie: gegevensbronnen definiëren en deze koppelen aan een logboekverzamelaar

1.  Ga naar de pagina met instellingen voor automatisch uploaden:  <br></br>Klik in de Cloud App Security-portal op het Instellingenpictogram ![Instellingenpictogram](./media/settings-icon.png) gevolgd door **Logboekverzamelaars**.

2.  Maak voor elke firewall of proxy waaruit u logboeken wilt uploaden een overeenkomende gegevensbron aan:

    ![ubuntu1](./media/ubuntu1.png)

    a. Klik op **Gegevensbron toevoegen**.

    b. Geef uw proxy of firewall een **Naam**.

    c. Selecteer het apparaat in de lijst **Bron**. Als u selecteert **aangepaste logboekindeling** om te werken met een netwerkapparaat die niet specifiek wordt vermeld, Zie [werken met de aangepaste log parser](custom-log-parser.md) voor configuratie-instructies.

    d. Vergelijk uw logboek met het voorbeeld van de verwachte logboekindeling. Als de bestandsindeling van uw logboek niet met dit voorbeeld overeenkomt, moet u uw gegevensbron toevoegen onder **Overig**.

    e. Instellen de **type ontvanger** naar elk **FTP**, **FTPS**, **Syslog – UDP**, of **Syslog – TCP**, of **Syslog – TLS**.
    >[!NOTE]
    >Integratie met veilige overdrachtprotocollen (FTPS en Syslog-TLS) vaak aanvullende instellingen of uw firewall/de proxy is vereist.

    f. Herhaal dit proces voor elke firewall en proxy waarvan het logboek kan worden gebruikt om verkeer op uw netwerk te detecteren.

3.  Ga naar het tabblad **Logboekverzamelaars** bovenaan.

    a. Klik op **Logboekverzamelaar toevoegen**.

    b. Geef de logboekverzamelaar een **Naam**.

    c. Voer de **Host-IP-adres** van de computer die u gebruiken wilt voor het implementeren van de Docker.

    d. Selecteer alle **gegevensbronnen** die u wilt verbinding maken met de collector en klikt u op **Update** om op te slaan van het configuratie-Zie de volgende implementatiestappen.

    ![ubuntu2](./media/ubuntu2.png)

    >  [!NOTE]
    > - Eén logboekverzamelaar kan meerdere gegevensbronnen verwerken.
    >- Kopieer de inhoud van het scherm. U hebt deze informatie nodig tijdens het configureren van de logboekverzamelaar voor de communicatie met Cloud App Security. Als u Syslog hebt geselecteerd, wordt ook informatie weergegeven over de poort waarop de Syslog-listener luistert.

4.  Meer informatie over de implementatie wordt weergegeven. **Kopiëren** de opdracht uitvoeren in het dialoogvenster. U kunt de kopiëren naar Klembord-pictogram ![kopiëren naar Klembord-pictogram](./media/copy-icon.png).

6.  **Exporteren** configuratie van de verwachte gegevensbron. Deze configuratie wordt beschreven hoe u de geëxporteerde activiteitenlogboeken moet instellen in uw apparaten.

   ![Logboekverzamelaar maken](./media/windows7.png)

### <a name="step-2--deployment-of-your-machine-in-azure"></a>Stap 2: implementatie van uw machine in Azure

> [!NOTE]
> De volgende stappen beschrijven de implementatie in Ubuntu. De implementatiestappen voor andere platforms zijn enigszins anders.


1.  Maak een nieuwe Ubuntu-machine in uw Azure-omgeving. 
2.  Nadat de computer is, opent u de poorten die door:
    1.  Ga in de weergave van de machine naar **Networking** Selecteer de relevante interface door dubbele erop te klikken.
    2.  Ga naar **netwerkbeveiligingsgroep** en selecteer de relevante netwerkbeveiligingsgroep.
    3.  Ga naar **inkomende beveiligingsregels** en klik op **toevoegen**,
      
      ![Ubuntu Azure](./media/ubuntu-azure.png)
    
    4. De volgende regels toevoegen (in **Geavanceerd** modus):

    |Naam|Poortbereik van doel|Protocol|Bron|Bestemming|
    |----|----|----|----|----|
    |caslogcollector_ftp|21|TCP|Alle|Alle|
    |caslogcollector_ftp_passive|20000-20099|TCP|Alle|Alle|
    |caslogcollector_syslogs_tcp|601-700|TCP|Alle|Alle|
    |caslogcollector_syslogs_udp|514-600|UDP|Alle|Alle|
      
      ![Ubuntu Azure regels](./media/ubuntu-azure-rules.png)

3.  Ga terug naar de machine en klik op **Connect** openen van een terminal op de machine.

4.  Wijzig in de hoofdmap bevoegdheden met `sudo -i`.

5.  Als u akkoord gaan met de [softwarelicentievoorwaarden](https://go.microsoft.com/fwlink/?linkid=862492), verwijderen van oude versies en Docker CE installeren met de volgende opdracht:
        
        curl -o /tmp/MCASInstallDocker.sh https://adaprodconsole.blob.core.windows.net/public-files/MCASInstallDocker.sh && chmod +x /tmp/MCASInstallDocker.sh; /tmp/MCASInstallDocker.sh

6. In de Cloud App Security-portal in de **maken nieuwe logboekverzamelaar** venster de opdracht voor het importeren van de configuratie van de collector op de host machine kopiëren:

      ![Ubuntu Azure](./media/ubuntu-azure.png)

7. Voer de opdracht voor het implementeren van de logboekverzamelaar.

      ![Ubuntu Azure-opdracht](./media/ubuntu-azure-command.png)

     >[!NOTE]
     >Voor het configureren van een proxy toevoegen de proxy IP-adres en poort. Bijvoorbeeld, als uw proxy-gegevens 192.168.10.1:8080 zijn, is uw bijgewerkte opdracht: 

        (echo db3a7c73eb7e91a0db53566c50bab7ed3a755607d90bb348c875825a7d1b2fce) | docker run --name MyLogCollector -p 21:21 -p 20000-20099:20000-20099 -e "PUBLICIP='192.168.1.1'" -e "PROXY=192.168.10.1:8080" -e "CONSOLE=mod244533.us.portal.cloudappsecurity.com" -e "COLLECTOR=MyLogCollector" --security-opt apparmor:unconfined --cap-add=SYS_ADMIN --restart unless-stopped -a stdin -i microsoft/caslogcollector starter

     ![Ubuntu-proxy](./media/ubuntu-proxy.png)

8. Om te bevestigen dat de logboekverzamelaar correct wordt uitgevoerd, voert u de volgende opdracht uit: `Docker logs <collector_name>`. Krijgt u de resultaten: **is voltooid!**


### <a name="step-3---on-premises-configuration-of-your-network-appliances"></a>Stap 3 - On-premises configuratie van uw netwerkapparaten

Configureer volgens de richtlijnen in het dialoogvenster uw netwerkfirewalls en proxy's, zodat ze periodiek logboeken naar de toegewezen Syslog-poort van de FTP-map exporteren, bijvoorbeeld:

    BlueCoat_HQ - Destination path: \<<machine_name>>\BlueCoat_HQ\

### <a name="step-4---verify-the-successful-deployment-in-the-cloud-app-security-portal"></a>Stap 4: Controleer of de geslaagde implementatie in de Cloud App Security-portal

Controleer de status van de collector in de **logboekverzamelaar** tabel en zorg ervoor dat de status **verbonden**. Als het **gemaakt**, is het mogelijk dat de verbinding van de collector logboek en parseren is niet voltooid.

 ![ubuntu9](./media/ubuntu9.png)

U kunt ook gaan naar de **beheerlogboek** en controleren dat Logboeken periodiek wordt geüpload naar de portal.

Zie [Problemen met Cloud Discovery oplossen](troubleshooting-cloud-discovery.md) als u tijdens de implementatie problemen ondervindt.

### <a name="optional---create-custom-continuous-reports"></a>Optioneel: aangepaste continue rapporten maken

Nadat u hebt gecontroleerd dat de logboeken worden naar de Cloud App Security wordt geüpload en de rapporten worden gegenereerd, kunt u aangepaste rapporten maken. U kunt nu de detectie van aangepaste rapporten op basis van Azure Active Directory-gebruikersgroepen maken. Bijvoorbeeld, als u wilt zien van de cloud gebruiken van de marketingafdeling kunt u de marketing-groep met de functie importeren groep importeren en maak vervolgens een aangepast rapport voor deze groep. U kunt ook een rapport op basis van IP-adreslabel of IP-adresbereiken aanpassen.

1. Selecteer in de Cloud App Security-portal onder het instellingentandwiel **Cloud Discovery-instellingen** en selecteer vervolgens **continue rapporten beheren**. 
2. Klik op de **rapport maken** knop en vul de velden in.
3. Onder de **Filters** kunt u gegevens door gegevensbron door filteren [geïmporteerde gebruikersgroep](user-groups.md), of door [IP-adres-tags en bereiken](ip-tags.md). 

![Aangepast continue rapport](./media/custom-continuous-report.png)

## <a name="see-also"></a>Zie ook
[Problemen met Cloud Discovery docker-implementatie oplossen](troubleshoot-docker.md)
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)  
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit de Premier Portal kiezen](https://premier.microsoft.com/)

