---
title: Logboek automatisch uploaden voor continue rapporten met behulp van een Docker op Windows configureren | Microsoft Docs
description: In dit onderwerp beschrijft het proces automatisch logboekgegevens uploaden voor continue rapporten configureren in de Cloud App Security met een Docker in Windows.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 8/6/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 308c06b3-f58b-4a21-86f6-8f87823a893a
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: dfa0e6d884fde67f901c9dcdec208a447f2c6cb9
ms.sourcegitcommit: f9851779aa15b11f559e56ac818f1333f027c000
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/07/2017
---
# <a name="set-up-and-configure-the-automatic-log-collector-docker-on-windows-server-2016"></a>Installeren en configureren van de automatische logboek Collector Docker op Windows Server 2016

> [!NOTE]
> Deze functie wordt geleidelijk wordt hersteld uit tussen de tenants. Neem contact op met ondersteuning als u wilt worden toegevoegd aan de Preview-versie.

## <a name="technical-requirements"></a>Technische vereisten

-   Besturingssysteem: Windows Server 2016 of Windows 10

-   Schijfruimte: 250 GB

-   CPU: 2

-   RAM: 4 GB

-   Firewall-instellingen:

    -   Toestaan dat de logboekverzamelaar binnenkomend FTP- en Syslog-verkeer ontvangen.

    -   De logboekverzamelaar initiëren uitgaand verkeer naar de portal (bijvoorbeeld contoso.cloudappsecurity.com) op poort 443 toestaan.

## <a name="log-collector-performance"></a>Prestaties logboekverzamelaar

De logboekverzamelaar kan een logboekcapaciteit van maximaal 50 GB per uur aan. De belangrijkste knelpunten in het logboekverzamelproces zijn:

-   Netwerkbandbreedte - de netwerkbandbreedte bepaalt de uploadsnelheid van het logboek.

-   I/O-prestaties van de virtuele machine die door uw IT is toegewezen - bepaalt de snelheid waarmee logboeken naar de schijf van de logboekverzamelaar worden geschreven. De logboekverzamelaar heeft een ingebouwd beveiligingsmechanisme dat de snelheid waarmee logboeken binnenkomen bewaakt en vergelijkt met de uploadsnelheid. In geval van congestie laat de logboekverzamelaar logboekbestanden vallen. Als uw installatie meestal groter is dan 50 GB per uur, dan is het raadzaam om het verkeer over meerdere logboekverzamelaars te spreiden.

## <a name="set-up-and-configuration"></a>Installatie en configuratie  

### <a name="step-1--web-portal-configuration-define-data-sources-and-link-them-to-a-log-collector"></a>Stap 1 - Webportalconfiguratie: gegevensbronnen definiëren en deze koppelen aan een logboekverzamelaar

1.  Ga naar de pagina met instellingen voor automatisch uploaden:<br></br> Klik in de Cloud App Security-portal op het Instellingenpictogram [Instellingenpictogram](./media/settings-icon.png) gevolgd door **Logboekverzamelaars**.

2.  Maak voor elke firewall of proxy waaruit u logboeken wilt uploaden een overeenkomende gegevensbron aan:

    ![Windows 1](./media/windows1.png)

    a. Klik op **Gegevensbron toevoegen**.

    b. Geef uw proxy of firewall een **Naam**.

    c. Selecteer het apparaat in de lijst **Bron**. Als u selecteert **aangepaste logboekindeling** om te werken met een netwerkapparaat die niet specifiek wordt vermeld, Zie [werken met de aangepaste log parser](custom-log-parser.md) voor configuratie-instructies.

    d. Vergelijk uw logboek met het voorbeeld van de verwachte logboekindeling. Als de bestandsindeling van uw logboek niet met dit voorbeeld overeenkomt, moet u uw gegevensbron toevoegen onder **Overig**.

    e. Instellen de **type ontvanger** naar elk **FTP**, **FTPS**, **Syslog – UDP**, of **Syslog – TCP**, of **Syslog – TLS**.

    > [!NOTE]
    > Integratie met veilige overdrachtprotocollen (FTPS en Syslog-TLS) vaak aanvullende instelling of uw Firewall/de Proxy is vereist.

    f. Herhaal dit proces voor elke firewall en proxy waarvan het logboek kan worden gebruikt om verkeer op uw netwerk te detecteren.

3.  Ga naar het tabblad **Logboekverzamelaars** bovenaan.

    a. Klik op **Logboekverzamelaar toevoegen**.

    b. Geef de logboekverzamelaar een **Naam**.

    c. Voer de **hosten van IP-adres** van de computer die u gebruiken wilt voor het implementeren van de Docker op.

    d. Selecteer alle **gegevensbronnen** die u wilt verbinding maken met de collector en klikt u op **Update** om op te slaan van het configuratie-Zie de volgende implementatiestappen.

    ![Windows2](./media/windows2.png)

    > [!NOTE]
    > - Eén logboekverzamelaar kan meerdere gegevensbronnen verwerken.

    > -   Kopieer de inhoud van het scherm. U hebt deze informatie nodig tijdens het configureren van de logboekverzamelaar voor de communicatie met Cloud App Security. Als u Syslog hebt geselecteerd, wordt ook informatie weergegeven over de poort waarop de Syslog-listener luistert.

4.  Meer informatie over de implementatie wordt weergegeven.

    ![Windows3](./media/windows3.png)

5.  **Kopiëren** de opdracht uitvoeren in het dialoogvenster. U kunt de kopiëren naar Klembord-pictogram [kopiëren naar Klembord-pictogram](./media/copy-icon.png).

6.  **Exporteren** de configuratie van de verwachte gegevensbronnen. Deze configuratie wordt beschreven hoe u de geëxporteerde activiteitenlogboeken moet instellen in uw apparaten.

    ![Windows4](./media/windows4.png)

### <a name="step-2--on-premises-deployment-of-your-machine"></a>Stap 2: On-premises implementatie van uw machine

>[!NOTE]
>De volgende stappen wordt de implementatie in Windows Server beschreven. De implementatiestappen voor andere platforms zijn enigszins anders.

1.  **Download** de [nieuwste stabiele Docker voor Windows](https://docs.docker.com/docker-for-windows/install/\#download-docker-for-windows).
    
2.  **Voer** het installatieprogramma InstallDocker.msi.

3.  Open een PowerShell-terminal op uw Windows-machine.

4.  **Verbinding maken met** met de docker-hub met de volgende opdracht:`docker login -u caslogcollector`

5.  Het volgende wachtwoord gebruiken`C0llector3nthusiast`

    ![windows5](./media/windows5.png)

6.  **Pull-** naar de installatiekopie van het verzamelen van de docker-hub met de volgende opdracht:`docker pull microsoft/caslogcollector`

    ![Windows6](./media/windows6.png)

7.  De collector installatiekopie met de opdracht uitvoeren in de portal gegenereerd implementeren.

    ![windows8](./media/windows8.png)

    >[!NOTE]
    >Als u nodig hebt voor het configureren van een proxy toevoegen van de proxy-IP-adres en poort onder. Bijvoorbeeld, als uw proxy-gegevens 192.168.10.1:8080 zijn, is uw bijgewerkte opdracht uitvoeren:  
 `   docker run --name MyLogCollector -p 21:21 -p 20000-20099:20000-20099 -e
    "PUBLICIP='192.168.1.1'" -e "PROXY=192.168.10.1:8080" -e
    "TOKEN=41f8f442c9a30519a058dd3bb9a19c79eb67f34a8816270dc4a384493988863a" -e
    "CONSOLE=tenant2.eu1-rs.adallom.com" -e "COLLECTOR=MyLogCollector" --security-opt
    apparmor:unconfined --cap-add=SYS_ADMIN -dt microsoft/caslogcollector starter`

    ![windows9](./media/windows9.png)

9.  Controleer of dat de collector correct wordt uitgevoerd met de volgende opdracht:`docker logs <collector_name>`

U ziet het bericht **is voltooid!**.
  ![windows10](./media/windows10.png)

### <a name="step-3---on-premises-configuration-of-your-network-appliances"></a>Stap 3 - On-premises configuratie van uw netwerkapparaten

Configureer volgens de richtlijnen in het dialoogvenster uw netwerkfirewalls en proxy's, zodat ze periodiek logboeken naar de toegewezen Syslog-poort van de FTP-map exporteren, bijvoorbeeld:

        BlueCoat_HQ - Destination path: \<<machine_name>>\BlueCoat_HQ\

### <a name="step-4---verify-the-successful-deployment-in-the-cloud-app-security-portal"></a>Stap 4: Controleer of de geslaagde implementatie in de Cloud App Security-portal

Controleer de status van de collector in de **logboekverzamelaar** tabel en zorg ervoor dat de status **verbonden**. Als het **gemaakt**, is het mogelijk dat de verbinding van de collector logboek en parseren is niet voltooid.

![windows11](./media/windows11.png)

U kunt ook gaan naar de **beheerlogboek** en controleren dat Logboeken periodiek wordt geüpload naar de portal.

Zie [Problemen met Cloud Discovery oplossen](troubleshooting-cloud-discovery.md) als u tijdens de implementatie problemen ondervindt.

## <a name="optional---create-custom-continuous-reports"></a>Optioneel: aangepaste continue rapporten maken

Nadat u hebt gecontroleerd dat de logboeken worden naar de Cloud App Security wordt geüpload en de rapporten worden gegenereerd, kunt u aangepaste rapporten maken. U kunt nu de detectie van aangepaste rapporten op basis van Azure Active Directory-gebruikersgroepen maken. Bijvoorbeeld, als u wilt zien van de cloud gebruiken van de marketingafdeling kunt u de marketing-groep met de functie importeren groep importeren en maak vervolgens een aangepast rapport voor deze groep. U kunt ook een rapport op basis van IP-adreslabel of IP-adresbereiken aanpassen.

1. Selecteer in de Cloud App Security-portal onder het instellingentandwiel **Cloud Discovery-instellingen** en selecteer vervolgens **continue rapporten beheren**. 
2. Klik op de **rapport maken** knop en vul de velden in.
3. Onder de **Filters** kunt u gegevens door gegevensbron door filteren [geïmporteerde gebruikersgroep](user-groups.md), of door [IP-adres-tags en bereiken](ip-tags.md). 

![Aangepast continue rapport](./media/custom-continuous-report.png)

## <a name="see-also"></a>Zie tevens
 
[Momentopnamerapporten maken van Cloud Discovery](create-snapshot-cloud-discovery-reports.md)

[Automatisch uploaden van logboeken configureren voor doorlopende rapporten](configure-automatic-log-upload-for-continuous-reports.md)

[Werken met Cloud Discovery-gegevens](working-with-cloud-discovery-data.md)

