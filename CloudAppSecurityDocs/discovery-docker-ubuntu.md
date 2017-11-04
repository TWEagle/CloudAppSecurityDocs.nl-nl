---
title: Automatisch uploaden van logboeken configureren voor doorlopende rapporten | Microsoft Docs
description: In dit onderwerp beschrijft het proces automatisch logboekgegevens uploaden voor continue rapporten in de Cloud App Security met behulp van een Docker op Ubuntu configureren.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: cc29a6cb-1c03-4148-8afd-3ad47003a1e3
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: 1f8b9bb679d402e52c009f811e55c3023e516eeb
ms.sourcegitcommit: 991e957c70d49e3fbf77828c2d2064fa363da667
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2017
---
# <a name="set-up-and-configuration-on-ubuntu"></a>Stel omhoog en configuratie op Ubuntu

> [!NOTE]
> Deze functie wordt geleidelijk wordt hersteld uit tussen de tenants. Neem contact op met ondersteuning als u wilt worden toegevoegd aan de Preview-versie.

## <a name="technical-requirements"></a>Technische vereisten

-   Besturingssysteem: Ubuntu 14.04 of hoger

-   Schijfruimte: 250 GB

-   CPU: 2

-   RAM: 4 GB

-   Firewall-instellingen:

    -   Toestaan dat de logboekverzamelaar binnenkomend FTP- en Syslog-verkeer ontvangen.

    -   De logboekverzamelaar initiëren uitgaand verkeer naar de portal (bijvoorbeeld contoso.cloudappsecurity.com) op poort 443 toestaan.

    - Toestaan dat de logboekverzamelaar initiëren uitgaand verkeer naar Azure blob storage (https://adaprodconsole.blob.core.windows.net/) op poort 80 en 443.

> [!NOTE]
> Als uw firewall vereist dat een lijst met statische IP-adressen toegang en biedt geen ondersteuning voor whitelisting op basis van de URL, staan de logboekverzamelaar initiëren uitgaand verkeer naar de [Microsoft Azure datacenter IP-bereiken op poort 443](https://www.microsoft.com/download/details.aspx?id=41653&751be11f-ede8-5a0c-058c-2ee190a24fa6=True).

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

4.  Meer informatie over de implementatie wordt weergegeven.

 ![ubuntu3](./media/windows7.png)

5.  **Kopiëren** de opdracht uitvoeren in het dialoogvenster. U kunt de kopiëren naar Klembord-pictogram ![kopiëren naar Klembord-pictogram](./media/copy-icon.png).

6.  **Exporteren** configuratie van de verwachte gegevensbron. Deze configuratie wordt beschreven hoe u de geëxporteerde activiteitenlogboeken moet instellen in uw apparaten.

  ![ubuntu4](./media/ubuntu4.png)

### <a name="step-2--on-premises-deployment-of-your-machine"></a>Stap 2: On-premises implementatie van uw machine

> [!Note]
> De volgende stappen beschrijven de implementatie in Ubuntu. De implementatiestappen voor andere platforms zijn enigszins anders.

1.  Open een terminal op uw Ubuntu-machine.

2.  Wijzig in de hoofdmap bevoegdheden met de opdracht:`sudo -i`

3.  Verwijderen van oude versies en Docker CE installeren met de volgende opdracht:

    `curl -o /tmp/MCASInstallDocker.sh
    https://adaprodconsole.blob.core.windows.net/public-files/MCASInstallDocker.sh
    && chmod +x /tmp/MCASInstallDocker.sh; sudo /tmp/MCASInstallDocker.sh`

    ![ubuntu5](./media/ubuntu5.png)

4.  De collector installatiekopie met de opdracht uitvoeren in de portal gegenereerd implementeren.

    ![ubuntu6](./media/ubuntu6.png)

    >[!NOTE]
    >Als u nodig hebt voor het configureren van een proxy toevoegen van de proxy-IP-adres en poort onder. Bijvoorbeeld, als uw proxy-gegevens 192.168.10.1:8080 zijn, is uw bijgewerkte opdracht uitvoeren:<br></br>
     `sudo docker run --name MyLogCollector -p 21:21 -p 20000-20099:20000-20099 -e
    "PUBLICIP='192.168.1.1'" -e "PROXY=192.168.10.1:8080" -e
    "TOKEN=41f8f442c9a30519a058dd3bb9a19c79eb67f34a8816270dc4a384493988863a" -e
    "CONSOLE=tenant2.eu1-rs.adallom.com" -e "COLLECTOR=MyLogCollector" --security-opt
    apparmor:unconfined --cap-add=SYS_ADMIN -dt microsoft/caslogcollector starter`

    ![ubuntu7](./media/ubuntu7.png)

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
[Werken met Cloud Discovery-gegevens](working-with-cloud-discovery-data.md)  
[Ga naar de ondersteuningspagina van Cloud App Security voor technische ondersteuning.](http://support.microsoft.com/oas/default.aspx?prid=16031)  
[Premier-klanten kunnen Cloud App Security ook rechtstreeks vanuit de Premier Portal kiezen](https://premier.microsoft.com/)

