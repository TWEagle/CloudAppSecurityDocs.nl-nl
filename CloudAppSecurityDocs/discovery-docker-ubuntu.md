---
title: Automatisch uploaden van logboeken configureren voor doorlopende rapporten | Microsoft Docs
description: In dit onderwerp beschrijft het proces automatisch logboekgegevens uploaden voor continue rapporten configureren in de Cloud App Security met een Docker op Ubuntu in een on-premises server.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 29/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cc29a6cb-1c03-4148-8afd-3ad47003a1e3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 7b28565c3dc87fb1134bec17ac8d0f464bcd5cdb
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

### <a name="step-2--on-premises-deployment-of-your-machine"></a>Stap 2: On-premises implementatie van uw machine

> [!Note]
> De volgende stappen beschrijven de implementatie in Ubuntu. De implementatiestappen voor andere platforms zijn enigszins anders.

1.  Open een terminal op uw Ubuntu-machine.

2.  Wijzig in de hoofdmap bevoegdheden met de opdracht:`sudo -i`

3. Voer de volgende twee opdrachten voor het overslaan van een proxyserver in uw netwerk:
        
        export http_proxy='<IP>:<PORT>' (e.g. 168.192.1.1:8888)
        export https_proxy='<IP>:<PORT>'

3.  Als u akkoord gaan met de [softwarelicentievoorwaarden](https://go.microsoft.com/fwlink/?linkid=862492), verwijderen van oude versies en Docker CE installeren met de volgende opdracht:

    `curl -o /tmp/MCASInstallDocker.sh
    https://adaprodconsole.blob.core.windows.net/public-files/MCASInstallDocker.sh
    && chmod +x /tmp/MCASInstallDocker.sh; /tmp/MCASInstallDocker.sh`

     > [!NOTE] 
     > Als deze opdracht is mislukt om uw proxycertificaat te valideren, voert u de opdracht met behulp van `curl -k` aan het begin.
    
    ![ubuntu5](./media/ubuntu5.png)

4.  De collector-installatiekopie op de host machine implementeren door het importeren van configuratie van de collector. Dit doen met het kopiëren van de opdracht uitvoeren in de portal is gegenereerd. Als u nodig hebt voor het configureren van een proxy toevoegen van de proxy-IP-adres en poort-nummer. Bijvoorbeeld, als uw proxy-gegevens 192.168.10.1:8080 zijn, is uw bijgewerkte opdracht uitvoeren:

            (echo 6f19225ea69cf5f178139551986d3d797c92a5a43bef46469fcc997aec2ccc6f) | docker run --name MyLogCollector -p 21:21 -p 20000-20099:20000-20099 -e "PUBLICIP='192.2.2.2'" -e "PROXY=192.168.10.1:8080" -e "CONSOLE=tenant2.eu1-rs.adallom.com" -e "COLLECTOR=MyLogCollector" --security-opt apparmor:unconfined --cap-add=SYS_ADMIN --restart unless-stopped -a stdin -i microsoft/caslogcollector starter

   ![Logboekverzamelaar maken](./media/windows7.png)

5.  Controleer of de collector correct wordt uitgevoerd met de volgende opdracht:`docker logs \<collector_name\>`

U ziet het bericht: **is voltooid!**

  ![ubuntu8](./media/ubuntu8.png)

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

