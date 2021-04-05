---
title: Distribuire Microsoft Defender ATP per Linux con Puppet
ms.reviewer: ''
description: Descrive come distribuire Microsoft Defender ATP per Linux usando Puppet.
keywords: microsoft, defender, atp, linux, installazione, distribuire, disinstallazione, pupazzo, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 424f08c525ef7f4b80c21812970921613320f4cd
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587660"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-linux-with-puppet"></a>Distribuire Microsoft Defender per Endpoint per Linux con Puppet

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Si applica a:**
- [Microsoft Defender per endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Vuoi provare Defender per Endpoint? [Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Questo articolo descrive come distribuire Defender for Endpoint per Linux usando Puppet. Una distribuzione corretta richiede il completamento di tutte le attività seguenti:

- [Scaricare il pacchetto di onboarding](#download-the-onboarding-package)
- [Creare il manifesto di Pupazzo](#create-a-puppet-manifest)
- [Distribuzione](#deployment)
- [Controllare lo stato di onboarding](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a>Prerequisiti e requisiti di sistema

 Per una descrizione dei prerequisiti e dei requisiti di sistema per la versione software corrente, vedi [la pagina principale di Defender per Endpoint per Linux.](microsoft-defender-endpoint-linux.md)

Inoltre, per la distribuzione di Puppet, devi avere familiarità con le attività di amministrazione di Puppet, avere Configurato Pupazzo e sapere come distribuire i pacchetti. Puppet ha molti modi per completare la stessa attività. Queste istruzioni presuppongono la disponibilità dei moduli di Pupazzo supportati, ad esempio *apt* per facilitare la distribuzione del pacchetto. L'organizzazione potrebbe utilizzare un flusso di lavoro diverso. Per informazioni dettagliate, fai riferimento alla documentazione [di Puppet.](https://puppet.com/docs)

## <a name="download-the-onboarding-package"></a>Scaricare il pacchetto di onboarding

Scaricare il pacchetto di onboarding da Microsoft Defender Security Center:

1. In Microsoft Defender Security Center, vai a **Impostazioni > Gestione dispositivi > onboarding**.
2. Nel primo menu a discesa seleziona **Linux Server** come sistema operativo. Nel secondo menu a discesa seleziona Lo strumento di gestione della **configurazione Linux preferito** come metodo di distribuzione.
3. Seleziona **Scarica pacchetto di onboarding.** Salvare il file come WindowsDefenderATPOnboardingPackage.zip.

    ![Screenshot di Microsoft Defender Security Center](images/atp-portal-onboarding-linux-2.png)

4. Da un prompt dei comandi, verificare di disporre del file. 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. Estrarre il contenuto dell'archivio.
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a>Creare un manifesto di Pupazzo

Devi creare un manifesto di Pupazzo per la distribuzione di Defender per Endpoint per Linux nei dispositivi gestiti da un server Puppet. Questo esempio usa i moduli *apt* e *yumrepo* disponibili da puppetlabs e presuppone che i moduli siano stati installati nel server Puppet.

Crea le cartelle *install_mdatp/file* *e install_mdatp/manifesti* nella cartella dei moduli dell'installazione di Puppet. Questa cartella si trova in genere in */etc/puppetlabs/code/environments/production/modules* sul server Puppet. Copiare mdatp_onboard.jsfile creato in precedenza *nella cartella install_mdatp/files.* Creare un *file init.pp* contenente le istruzioni di distribuzione:

```bash
pwd
```
```Output
/etc/puppetlabs/code/environments/production/modules
```

```bash
tree install_mdatp
```
```Output
install_mdatp
├── files
│   └── mdatp_onboard.json
└── manifests
    └── init.pp
```

### <a name="contents-of-install_mdatpmanifestsinitpp"></a>Contenuto di `install_mdatp/manifests/init.pp`

Defender per Endpoint per Linux può essere distribuito da uno dei seguenti canali (indicato di seguito come *[canale]*): *insiders-fast,* *insiders-slow* o *prod*. Ognuno di questi canali corrisponde a un archivio software Linux.

La scelta del canale determina il tipo e la frequenza degli aggiornamenti offerti al dispositivo. I dispositivi *in Insiders-fast* sono i primi a ricevere aggiornamenti e nuove funzionalità, seguiti successivamente da *insider lenti* e infine *da prod*.

Per visualizzare in anteprima le nuove funzionalità e fornire feedback anticipato, è consigliabile configurare alcuni dispositivi nell'organizzazione per l'uso di *insiders-fast* o *insiders-slow*.

> [!WARNING]
> Il cambio di canale dopo l'installazione iniziale richiede la reinstallazione del prodotto. Per cambiare il canale del prodotto: disinstalla il pacchetto esistente, ri-configura il dispositivo per l'uso del nuovo canale e segui i passaggi in questo documento per installare il pacchetto dal nuovo percorso.

Annotare la distribuzione e la versione e identificare la voce più vicina in `https://packages.microsoft.com/config/` .

Nei comandi seguenti sostituisci *[distro]* e *[versione]* con le informazioni identificate:

> [!NOTE]
> Nel caso di RedHat, Oracle EL e CentOS 8, sostituisci *[distro]* con "rhel".

```puppet
# Puppet manifest to install Microsoft Defender ATP.
# @param channel The release channel based on your environment, insider-fast or prod.
# @param distro The Linux distribution in lowercase. In case of RedHat, Oracle EL, and CentOS 8, the distro variable should be 'rhel'.
# @param version The Linux distribution release number, e.g. 7.4.

class install_mdatp (
$channel = 'insiders-fast',
$distro = undef,
$version = undef
){
    case $::osfamily {
        'Debian' : {
            apt::source { 'microsoftpackages' :
                location => "https://packages.microsoft.com/${distro}/${version}/prod",
                release  => $channel,
                repos    => 'main',
                key      => {
                    'id'     => 'BC528686B50D79E339D3721CEB3E94ADBE1229CF',
                    'server' => 'keyserver.ubuntu.com',
                },
            }
        }
        'RedHat' : {
            yumrepo { 'microsoftpackages' :
                baseurl  => "https://packages.microsoft.com/${distro}/${version}/${channel}",
                descr    => "packages-microsoft-com-prod-${channel}",
                enabled  => 1,
                gpgcheck => 1,
                gpgkey   => 'https://packages.microsoft.com/keys/microsoft.asc'
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }

    case $::osfamily {
        /(Debian|RedHat)/: {
            file { ['/etc/opt', '/etc/opt/microsoft', '/etc/opt/microsoft/mdatp']:
                ensure => directory,
                owner  => root,
                group  => root,
                mode   => '0755'
            }

            file { '/etc/opt/microsoft/mdatp/mdatp_onboard.json':
                source  => 'puppet:///modules/install_mdatp/mdatp_onboard.json',
                owner   => root,
                group   => root,
                mode    => '0600',
                require => File['/etc/opt/microsoft/mdatp']
            }

            package { 'mdatp':
                ensure  => 'installed',
                require => File['/etc/opt/microsoft/mdatp/mdatp_onboard.json']
            }
        }
        default : { fail("${::osfamily} is currently not supported.") }
    }
}
```

## <a name="deployment"></a>Distribuzione

Includere il manifesto precedente nel sito.pp file:

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

I dispositivi agente registrati esempre periodicamente il polling del server Di pupazzo e installano nuovi profili e criteri di configurazione non appena vengono rilevati.

## <a name="monitor-puppet-deployment"></a>Monitorare la distribuzione di Puppet

Nel dispositivo agente puoi anche controllare lo stato di onboarding eseguendo:

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- **licensed**: questo conferma che il dispositivo è legato all'organizzazione.

- **orgId:** questo è l'identificatore dell'organizzazione Defender for Endpoint.

## <a name="check-onboarding-status"></a>Controllare lo stato di onboarding

Puoi verificare che i dispositivi siano stati correttamente onboarded creando uno script. Ad esempio, lo script seguente controlla lo stato di onboarding nei dispositivi registrati:

```bash
mdatp health --field healthy
```

Il comando precedente viene stampato `1` se il prodotto è onboarding e funziona come previsto.

> [!IMPORTANT]
> Quando il prodotto viene avviato per la prima volta, scarica le definizioni antimalware più recenti. A seconda della connessione Internet, l'operazione può richiedere alcuni minuti. Durante questo periodo di tempo il comando precedente restituisce il valore `0` .

Se il prodotto non è integro, il codice di uscita (che può essere controllato `echo $?` tramite ) indica il problema:

- 1 se il dispositivo non è ancora stato onboarded.
- 3 se non è possibile stabilire la connessione al daemon.

## <a name="log-installation-issues"></a>Registrare i problemi di installazione

 Per ulteriori informazioni su come trovare il registro generato automaticamente creato dal programma di installazione quando si verifica un errore, vedere [Log installation issues](linux-resources.md#log-installation-issues).

## <a name="operating-system-upgrades"></a>Aggiornamenti del sistema operativo

Durante l'aggiornamento del sistema operativo a una nuova versione principale, devi prima disinstallare Defender per Endpoint per Linux, installare l'aggiornamento e infine riconfigurare Defender per Endpoint per Linux nel dispositivo.

## <a name="uninstallation"></a>Disinstallazione

Creare un modulo *remove_mdatp* simile *a install_mdatp* con il contenuto seguente in *init.pp* file:

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
