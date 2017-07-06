---
title: Cloud App Security externe DLP-integratie via beveiligde ICAP | Microsoft Docs
description: Dit onderwerp bevat de stappen die nodig zijn voor het configureren van de verbinding ICAP in de Cloud App Security en stunnel setup opnieuw uit.
keywords: 
author: rkarlin
ms.author: rkarlin
manager: mbaldwin
ms.date: 6/26/2017
ms.topic: article
ms.prod: 
ms.service: cloud-app-security
ms.technology: 
ms.assetid: 9656f6c6-7dd4-4c4c-a0eb-f22afce78071
ms.reviewer: reutam
ms.suite: ems
ms.openlocfilehash: b9931f11e50285c1bc6a0053fe0c8ad820851a08
ms.sourcegitcommit: 38e3c6749e3c746ab73b8da96cd81219781a7998
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/04/2017
---
# <a name="external-dlp-integration"></a>Externe DLP-integratie

> [!NOTE] 
> Deze functie is in preview.

Cloud App Security kunt integreren met bestaande DLP-oplossingen voor deze besturingselementen naar de cloud uitbreiden behoud een consistente en uniform beleid on-premises en in de cloud activiteiten. Eenvoudig te gebruiken interfaces, met inbegrip van REST-API en ICAP, doordat integratie met classificatieregel systemen zoals Symantec preventie van gegevensverlies (voorheen Vontu preventie van gegevensverlies) of Forcepoint DLP exporteert u het platform. 

Integratie wordt bereikt door het gebruik van het standaard ICAP-protocol, een http-achtige-protocol dat wordt beschreven in [RFC 3507](https://tools.ietf.org/html/rfc3507). Om te kunnen beveiligen ICAP voor de overdracht van uw gegevens, is het vereist voor het instellen van een beveiligde SSL-tunnel (stunnel) tussen de DLP-oplossing en Cloud App Security. Setup stunnel biedt functionaliteit voor TLS-versleuteling voor uw gegevens doorheen tussen uw DLP-server en de Cloud App Security. 

Deze handleiding bevat de stappen die nodig zijn voor het configureren van de verbinding ICAP in de Cloud App Security en stunnel setup opnieuw uit om communicatie via deze te beveiligen.

## <a name="architecture"></a>Architectuur
Cloud App Security scant uw cloudomgeving en op basis van uw bestand beleidsconfiguratie bepaald of het bestand met de interne DLP-engine of de externe DLP te scannen. Als externe DLP-scan wordt toegepast, het bestand wordt verzonden via een beveiligde tunnel naar de klantomgeving waar deze is doorgegeven aan het toestel ICAP voor de eindconclusie DLP: toegestaan/geblokkeerd. Antwoorden worden verzonden naar Cloud App Security via de stunnel waar deze wordt gebruikt door het beleid om te bepalen van de volgende acties zoals het meldingen, quarantaine en delen.

![Stunnel-architectuur](./media/icap-architecture-stunnel.png)

Aangezien Cloud App Security wordt uitgevoerd in Azure, resulteert in een implementatie in Azure betere prestaties. Andere opties, waaronder andere Clouds en On-Premises implementatie worden echter ondersteund. In andere omgevingen implementeert, kan dit leiden tot verminderde prestaties als gevolg van hogere latentie en lagere doorvoer. De server ICAP en stunnel moeten samen worden geïmplementeerd op hetzelfde netwerk om ervoor te zorgen dat het verkeer wordt gecodeerd.

## <a name="prerequisites"></a>Vereisten
Open in de volgorde voor Cloud App Security gegevens via uw stunnel verzenden naar uw server ICAP uw firewall DMZ kan het externe IP-adressen die door Cloud App Security gebruikt met een dynamische bronpoortnummer of bereik. 

1.  Adressen van bron: Raadpleeg [verbinding maken met apps, onder vereisten](enable-instant-visibility-protection-and-governance-actions-for-your-apps.md#prerequisites)
2.  TCP-bronpoort: dynamische
3.  Bestemming adres(sen): één of twee IP-adres van de stunnel verbonden met de externe ICAP-server die u in de volgende stappen configureert
4.  Doel-TCP-poort: zoals gedefinieerd in uw netwerk

## <a name="step-1--set-up-icap-server"></a>STAP 1: ICAP server instellen

Een server ICAP, u het poortnummer instellen en zorg ervoor dat u instelt **modus** naar **blokkeren**. Blokkerende modus Hiermee stelt u de server ICAP om door te sturen de classificatie eindconclusie terug naar de Cloud App Security.

Raadpleeg de productdocumentatie van uw externe DLP voor instructies om dit te bereiken. Zie bijvoorbeeld [bijlage A: Forcepoint ICAP server setup](#forcepoint).

## <a name="step-2--set-up-your-stunnel-server"></a>STAP 2: Uw stunnel-server instellen 

In deze stap stelt u de stunnel verbonden met uw ICAP-server. 

>[!NOTE]
> Hoewel ten zeerste aangeraden, wordt deze stap is optioneel en op testwerkbelastingen worden overgeslagen. 

### <a name="install-stunnel-on-a-server"></a>Stunnel installeren op een server

**Vereisten**

- **Een server** -een Windows Server of Linux-server is gebaseerd op een primaire distributiepunt.

Raadpleeg de [stunnel website](https://www.stunnel.org/index.html) voor meer informatie over de typen servers die ondersteuning bieden voor stunnel-installatie. Als u van Linux gebruikmaakt, kunt u uw Linux-Distributiebeheer om deze te installeren.

#### <a name="install-stunnel-on-windows"></a>Stunnel op Windows installeren

1. [Download de meest recente installatie van Windows Server](https://www.stunnel.org/downloads.html) (dit moet werken op een recente versie van Windows Server).
(standaardinstallatie)

2. Tijdens de installatie, maak een nieuw zelfondertekend certificaat geen, maakt u een certificaat in een later stadium.

3. Klik op **server na de installatie Start**.

4. Maak een certificaat met een van de volgende manieren:

   -    De beheerserver van uw certificaat gebruiken voor het maken van een SSL-certificaat op uw server ICAP en de sleutels vervolgens naar de server die u hebt voorbereid voor de installatie stunnel kopiëren.
   -    Of op de server stunnel, kunt u de volgende OpenSSL-opdrachten gebruiken om een persoonlijke sleutel en een zelfondertekend certificaat te genereren. Vervang deze variabelen:
       -    **Key.PEM** met de naam van uw persoonlijke sleutel
       -    **CERT.PEM** met de naam van uw certificaat
       -    **stunnel sleutel** met de naam van de zojuist gemaakte sleutel

5. Open de configuratiemap onder uw installatiepad stunnel. Dit is standaard: c:\Program bestanden (x86) \stunnel\config\
6. Voer de opdrachtregel met administratorbevoegdheden:`..\bin\openssl.exe genrsa -out ey.pem 2048 `
      
     ` ..\bin\openssl.exe  req -new -x509 -config ".\openssl.cnf" -key key.pem -out .\cert.pem -days 1095`

8. Samenvoegen van de cert.pem en key.pem en deze opslaan op het bestand:`cat cert.pem key.pem >> stunnel-key.pem`

9. [Downloaden van de openbare sleutel](https://adaprodconsole.blob.core.windows.net/icap/publicCert.pem) en sla deze op deze locatie **C:\Program Files (x86)\stunnel\config\CAfile.pem**.

10. Voeg de volgende regels om te openen van de poort in de Windows firewall:

        rem Open TCP Port 11344 inbound and outbound
        netsh advfirewall firewall add rule name="Secure ICAP TCP Port 11344" dir=in action=allow protocol=TCP localport=11344
        netsh advfirewall firewall add rule name=" Secure ICAP Port 11344" dir=out action=allow protocol=TCP localport=11344

11. Voer: `c:\Program Files (x86)\stunnel\bin\stunnel.exe` om de toepassing stunnel te openen. 

12. Klik op **configuratie** en vervolgens **bewerken configuratie**.

   ![Windows Server-configuratie bewerken](./media/stunnel-windows.png)
 
13. Open het bestand en plak de volgende regels in de configuratie van server, waarbij **DLP Server-IP** het IP-adres van uw server ICAP **stunnel sleutel** is de sleutel die u in de vorige stap hebt gemaakt en **CAfile** is het openbare certificaat van de Cloud App Security stunnel-client. Ook Verwijder eventuele van de voorbeeldtekst die is geïmplementeerd (in het voorbeeld Gmail tekst wordt weergegeven) en het volgende in het bestand cop:

        [microsoft-Cloud App Security]
        accept = 0.0.0.0:11344
        connect = **ICAP Server IP**:1344
        cert = C:\Program Files (x86)\stunnel\config\**stunnel-key**.pem
        CAfile = C:\Program Files (x86)\stunnel\config\**CAfile**.pem
        TIMEOUTclose = 0

12. Sla het bestand en klik vervolgens op **opnieuw laden configuratie**.

13. Voer het volgende als u wilt valideren dat alles werkt zoals verwacht, vanaf een opdrachtprompt:`netstat -nao  | findstr 11344`
 

#### <a name="install-stunnel-on-ubuntu"></a>Stunnel op Ubuntu installeren

Het volgende voorbeeld is gebaseerd op de installatie van een virtuele Ubuntu server wanneer u bent aangemeld als hoofdgebruiker - voor andere servers parallelle opdrachten gebruiken. 

Op de server voorbereid, download en installeer de nieuwste versie van stunnel met de volgende opdracht op uw Ubuntu server die u stunnel en OpenSSL installeert:

    apt-get update
    apt-get install openssl -y
    apt-get install stunnel4 -y
Controleer of dat deze stunnel door te voeren van de volgende opdracht vanaf een console is geïnstalleerd. U moet het versienummer en een lijst met configuratieopties krijgen:

    stunnel-version

### <a name="generate-certificates"></a>Genereren van certificaten

De ICAP-server en de Cloud App Security gebruiken een persoonlijke sleutel en het openbare certificaat voor de verificatie en serverversleuteling in de stunnel. Zorg ervoor dat u de persoonlijke sleutel zonder een wachtwoordzin maken zodat stunnel kan worden uitgevoerd als een achtergrondservice. Stel ook de machtiging voor de bestanden naar **leesbare** voor de eigenaar stunnel en zo de **geen** voor alle andere.

U kunt de certificaten in een van de volgende manieren maken:
-   De beheerserver van uw certificaat gebruiken voor het maken van een SSL-certificaat op uw server ICAP en de sleutels vervolgens naar de server die u hebt voorbereid voor de installatie stunnel kopiëren. 
-   Of op de server stunnel, kunt u de volgende OpenSSL-opdrachten gebruiken om een persoonlijke sleutel en een zelfondertekend certificaat te genereren. Vervang deze variabelen:
    - **'key.pem'** met de naam van uw persoonlijke sleutel
    - **'cert.pem'** met de naam van uw certificaat
    - **'stunnel-sleutel'** met de naam van de zojuist gemaakte sleutel
       
            openssl genrsa -out key.pem 2048
            openssl req -new -x509 -key key.pem -out cert.pem -days 1095
            cat key.pem cert.pem >> /etc/ssl/private/stunnel-key.pem

### <a name="download-the-cloud-app-security-stunnel-client-public-key"></a>De openbare sleutel voor Cloud App Security stunnel client downloaden

Downloaden van de openbare sleutel van deze locatie: https://adaprodconsole.blob.core.windows.net/icap/publicCert.pem en sla deze op deze locatie: **/etc/ssl/certs/CAfile.pem**

### <a name="configure-stunnel"></a>Stunnel configureren 

De configuratie stunnel is ingesteld in het bestand stunnel.conf.

1. Het bestand stunnel.conf maken in de volgende map: **vim /etc/stunnel/stunnel.conf**

3.  Open het bestand en plak de volgende regels in de configuratie van server, waarbij **DLP Server-IP** het IP-adres van uw server ICAP **stunnel sleutel** is de sleutel die u in de vorige stap hebt gemaakt en **CAfile** is het openbare certificaat van de Cloud App Security stunnel client:

        [microsoft-Cloud App Security]
         accept = 0.0.0.0:11344
         connect = **ICAP Server IP**:1344
          cert = /etc/ssl/private/**stunnel-key**.pem
          CAfile = /etc/ssl/certs/**CAfile**.pem
          TIMEOUTclose = 1

> [!NOTE] 
> Het poortnummer stunnel is standaard ingesteld op 11344. U kunt dit wijzigen in een andere poort, indien nodig, maar zorg ervoor dat het nieuwe poortnummer Noteer - u moet invoeren in de volgende stap.

### <a name="update-your-ip-table"></a>Uw IP-tabel bijwerken
Uw IP-adrestabel bijwerken met de volgende regel in de route:
   
    iptables -I INPUT -p tcp --dport 11344 -j ACCEPT

De update naar uw IP-tabel permanente gebruik de volgende opdrachten maken:

     sudo apt-get install iptables-persistent
     sudo /sbin/iptables-save > /etc/iptables/rules.v4
 

### <a name="run-stunnel"></a>Stunnel uitvoeren
1.  Op uw server stunnel, voert u het volgende:

        vim /etc/default/stunnel4

2.  Wijzig de variabele ENABLED in op 1:

        ENABLED=1

3.  De service voor de configuratie van kracht te laten opnieuw starten:

        /etc/init.d/stunnel4 restart

4.  Voer de volgende opdrachten om te controleren of de stunnel correct wordt uitgevoerd:

        ps -A | grep stunnel

    en dat deze op de poort vermeld luistert:

        netstat -anp | grep 11344

5. Zorg ervoor dat het netwerk waarin de stunnel server werd geïmplementeerd overeenkomt met de netwerk-vereisten zoals eerder vermeld. Dit is vereist voor het toestaan van binnenkomende verbindingen van Cloud App Security is de server te bereiken.

Als het proces nog steeds niet wordt uitgevoerd, raadpleegt u de [stunnel documentatie](https://www.stunnel.org/docs.html) om op te lossen.


## <a name="step-3--connect-to-cloud-app-security"></a>STAP 3: Verbinding maken met Cloud App Security

1. In de Cloud App Security onder **instellingen** Selecteer **Security extensions** en selecteer de **externe DLP** tabblad.

2. Klik op het plusteken om toe te voegen, een nieuwe verbinding. 

3. In de **toevoegen van nieuwe externe DLP** wizard bieden een **verbindingsnaam** (voor een voorbeeld van mijn Forcepoint connector) die worden gebruikt voor het identificeren van de connector.

4. Selecteer de **verbindingstype**:
    - **Symantec Vontu** – Selecteer deze optie met de aangepaste integratie voor Vontu DLP-apparaten
    - **Forcepoint DLP** – Selecteer deze optie met de aangepaste integratie voor Forcepoint DLP-apparaten
    - **Algemene ICAP – REQMOD** - voor andere DLP-apparaten die gebruikmaken van [wijziging aanvragen](https://tools.ietf.org/html/rfc3507)
    - **Algemene ICAP – RESPMOD** - voor andere DLP-apparaten die gebruikmaken van [antwoord wijziging](https://tools.ietf.org/html/rfc3507)
    ![Cloud App Security ICAP verbinding](./media/icap-wizard1.png)

4. Ga naar de openbare basis-CA van uw stunnel gebruiken om te verbinden met uw stunnel en klikt u op **volgende**.

   > [!NOTE]
   > Het is raadzaam om te controleren de **gebruik secure ICAP** vak voor het instellen van een versleutelde stunnel-gateway. Als voor het testen van doeleinden of als u een server stunnel geen hebt, u dit rechtstreeks te integreren met uw DLP-server uitschakelen kunt. 

5. In de **serverconfiguratie** scherm, bieden de **IP-adres** en **poort** van de stunnel-server die u in stap 2 hebt ingesteld. Voor de load balancer doeleinden kunt u de **IP-adres** en **poort** van een extra server. De opgegeven IP-adressen moet de externe statische IP-adressen van uw servers.

   ![Cloud App Security ICAP verbinding](./media/icap-wizard2.png)
6. Klik op **Volgende**. Cloud App Security wordt testen van verbinding met de server die u hebt geconfigureerd. Als u een foutbericht ontvangt, raadpleegt u de instructies en netwerkinstellingen. Nadat deze is verbonden, kunt u **afsluiten**.

7. Nu aan de verkeer omleiden naar deze externe DLP-server bij het maken van een **Bestandsbeleid**onder **methode voor inhoudscontrole**, selecteert u de verbinding die u zojuist hebt gemaakt. Lees meer over [maken van een bestandsbeleid](data-protection-policies.md).


## Bijlage A: ForcePoint ICAP server setup<a name="forcepoint"></a>

In ForcePoint, stelt u uw apparaat met de volgende stappen:

1.  Ga in uw toestel DLP naar **implementatie** > **System Modules**. 

    ![ICAP-implementatie](./media/icap-system-modules.png)

2.  In de **algemene** tabblad, controleert u of **ICAP Server** is **ingeschakeld** en de standaardinstelling **poort** is ingesteld op **1344**. Bovendien onder **verbinding met deze Server ICAP van de volgende IP-adressen toestaan**, selecteer **elk IP-adres**.
 
    ![ICAP configuratie](./media/icap-ip-address.png)

3.  Controleer of in te stellen in het tabblad HTTP/HTTPS **modus** naar **blokkeren**.
 
    ![ICAP blokkeren](./media/icap-blocking.png)
 




