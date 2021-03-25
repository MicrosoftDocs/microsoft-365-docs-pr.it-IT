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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 06611c19994ba34c4b59eb1a32b9ab9fd91cc1aa
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066909"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-linux-with-puppet"></a><span data-ttu-id="21393-104">Distribuire Microsoft Defender per Endpoint per Linux con Puppet</span><span class="sxs-lookup"><span data-stu-id="21393-104">Deploy Microsoft Defender for Endpoint for Linux with Puppet</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="21393-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="21393-105">**Applies to:**</span></span>
- [<span data-ttu-id="21393-106">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="21393-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="21393-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="21393-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="21393-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="21393-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="21393-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="21393-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="21393-110">Questo articolo descrive come distribuire Defender for Endpoint per Linux usando Puppet.</span><span class="sxs-lookup"><span data-stu-id="21393-110">This article describes how to deploy Defender for Endpoint for Linux using Puppet.</span></span> <span data-ttu-id="21393-111">Una distribuzione corretta richiede il completamento di tutte le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="21393-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="21393-112">Scaricare il pacchetto di onboarding</span><span class="sxs-lookup"><span data-stu-id="21393-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="21393-113">Creare il manifesto di Pupazzo</span><span class="sxs-lookup"><span data-stu-id="21393-113">Create Puppet manifest</span></span>](#create-a-puppet-manifest)
- [<span data-ttu-id="21393-114">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="21393-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="21393-115">Controllare lo stato di onboarding</span><span class="sxs-lookup"><span data-stu-id="21393-115">Check onboarding status</span></span>](#check-onboarding-status)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="21393-116">Prerequisiti e requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="21393-116">Prerequisites and system requirements</span></span>

 <span data-ttu-id="21393-117">Per una descrizione dei prerequisiti e dei requisiti di sistema per la versione software corrente, vedi [la pagina principale di Defender per Endpoint per Linux.](microsoft-defender-endpoint-linux.md)</span><span class="sxs-lookup"><span data-stu-id="21393-117">For a description of prerequisites and system requirements for the current software version, see [the main Defender for Endpoint for Linux page](microsoft-defender-endpoint-linux.md).</span></span>

<span data-ttu-id="21393-118">Inoltre, per la distribuzione di Puppet, devi avere familiarità con le attività di amministrazione di Puppet, avere Configurato Pupazzo e sapere come distribuire i pacchetti.</span><span class="sxs-lookup"><span data-stu-id="21393-118">In addition, for Puppet deployment, you need to be familiar with Puppet administration tasks, have Puppet configured, and know how to deploy packages.</span></span> <span data-ttu-id="21393-119">Puppet ha molti modi per completare la stessa attività.</span><span class="sxs-lookup"><span data-stu-id="21393-119">Puppet has many ways to complete the same task.</span></span> <span data-ttu-id="21393-120">Queste istruzioni presuppongono la disponibilità dei moduli di Pupazzo supportati, ad esempio *apt* per facilitare la distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="21393-120">These instructions assume availability of supported Puppet modules, such as *apt* to help deploy the package.</span></span> <span data-ttu-id="21393-121">L'organizzazione potrebbe utilizzare un flusso di lavoro diverso.</span><span class="sxs-lookup"><span data-stu-id="21393-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="21393-122">Per informazioni dettagliate, fai riferimento alla documentazione [di Puppet.](https://puppet.com/docs)</span><span class="sxs-lookup"><span data-stu-id="21393-122">Refer to the [Puppet documentation](https://puppet.com/docs) for details.</span></span>

## <a name="download-the-onboarding-package"></a><span data-ttu-id="21393-123">Scaricare il pacchetto di onboarding</span><span class="sxs-lookup"><span data-stu-id="21393-123">Download the onboarding package</span></span>

<span data-ttu-id="21393-124">Scaricare il pacchetto di onboarding da Microsoft Defender Security Center:</span><span class="sxs-lookup"><span data-stu-id="21393-124">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="21393-125">In Microsoft Defender Security Center, vai a **Impostazioni > Gestione dispositivi > onboarding**.</span><span class="sxs-lookup"><span data-stu-id="21393-125">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="21393-126">Nel primo menu a discesa seleziona **Linux Server** come sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="21393-126">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="21393-127">Nel secondo menu a discesa seleziona Lo strumento di gestione della **configurazione Linux preferito** come metodo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="21393-127">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="21393-128">Seleziona **Scarica pacchetto di onboarding.**</span><span class="sxs-lookup"><span data-stu-id="21393-128">Select **Download onboarding package**.</span></span> <span data-ttu-id="21393-129">Salvare il file come WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="21393-129">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Screenshot di Microsoft Defender Security Center](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="21393-131">Da un prompt dei comandi, verificare di disporre del file.</span><span class="sxs-lookup"><span data-stu-id="21393-131">From a command prompt, verify that you have the file.</span></span> 

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
5. <span data-ttu-id="21393-132">Estrarre il contenuto dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="21393-132">Extract the contents of the archive.</span></span>
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-a-puppet-manifest"></a><span data-ttu-id="21393-133">Creare un manifesto di Pupazzo</span><span class="sxs-lookup"><span data-stu-id="21393-133">Create a Puppet manifest</span></span>

<span data-ttu-id="21393-134">Devi creare un manifesto di Pupazzo per la distribuzione di Defender per Endpoint per Linux nei dispositivi gestiti da un server Puppet.</span><span class="sxs-lookup"><span data-stu-id="21393-134">You need to create a Puppet manifest for deploying Defender for Endpoint for Linux to devices managed by a Puppet server.</span></span> <span data-ttu-id="21393-135">Questo esempio usa i moduli *apt* e *yumrepo* disponibili da puppetlabs e presuppone che i moduli siano stati installati nel server Puppet.</span><span class="sxs-lookup"><span data-stu-id="21393-135">This example makes use of the *apt* and *yumrepo* modules available from puppetlabs, and assumes that the modules have been installed on your Puppet server.</span></span>

<span data-ttu-id="21393-136">Crea le cartelle *install_mdatp/file* *e install_mdatp/manifesti* nella cartella dei moduli dell'installazione di Puppet.</span><span class="sxs-lookup"><span data-stu-id="21393-136">Create the folders *install_mdatp/files* and *install_mdatp/manifests* under the modules folder of your Puppet installation.</span></span> <span data-ttu-id="21393-137">Questa cartella si trova in genere in */etc/puppetlabs/code/environments/production/modules* sul server Puppet.</span><span class="sxs-lookup"><span data-stu-id="21393-137">This folder is typically located in */etc/puppetlabs/code/environments/production/modules* on your Puppet server.</span></span> <span data-ttu-id="21393-138">Copiare mdatp_onboard.jsfile creato in precedenza *nella cartella install_mdatp/files.*</span><span class="sxs-lookup"><span data-stu-id="21393-138">Copy the mdatp_onboard.json file created above to the *install_mdatp/files* folder.</span></span> <span data-ttu-id="21393-139">Creare un *file init.pp*</span><span class="sxs-lookup"><span data-stu-id="21393-139">Create an *init.pp*</span></span> <span data-ttu-id="21393-140">contenente le istruzioni di distribuzione:</span><span class="sxs-lookup"><span data-stu-id="21393-140">file that contains the deployment instructions:</span></span>

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

### <a name="contents-of-install_mdatpmanifestsinitpp"></a><span data-ttu-id="21393-141">Contenuto di `install_mdatp/manifests/init.pp`</span><span class="sxs-lookup"><span data-stu-id="21393-141">Contents of `install_mdatp/manifests/init.pp`</span></span>

<span data-ttu-id="21393-142">Defender per Endpoint per Linux può essere distribuito da uno dei seguenti canali (indicato di seguito come *[canale]*): *insiders-fast,* *insiders-slow* o *prod*. Ognuno di questi canali corrisponde a un archivio software Linux.</span><span class="sxs-lookup"><span data-stu-id="21393-142">Defender for Endpoint for Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

<span data-ttu-id="21393-143">La scelta del canale determina il tipo e la frequenza degli aggiornamenti offerti al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="21393-143">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="21393-144">I dispositivi *in Insiders-fast* sono i primi a ricevere aggiornamenti e nuove funzionalità, seguiti successivamente da *insider lenti* e infine *da prod*.</span><span class="sxs-lookup"><span data-stu-id="21393-144">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="21393-145">Per visualizzare in anteprima le nuove funzionalità e fornire feedback anticipato, è consigliabile configurare alcuni dispositivi nell'organizzazione per l'uso di *insiders-fast* o *insiders-slow*.</span><span class="sxs-lookup"><span data-stu-id="21393-145">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="21393-146">Il cambio di canale dopo l'installazione iniziale richiede la reinstallazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="21393-146">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="21393-147">Per cambiare il canale del prodotto: disinstalla il pacchetto esistente, ri-configura il dispositivo per l'uso del nuovo canale e segui i passaggi in questo documento per installare il pacchetto dal nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="21393-147">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

<span data-ttu-id="21393-148">Annotare la distribuzione e la versione e identificare la voce più vicina in `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="21393-148">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

<span data-ttu-id="21393-149">Nei comandi seguenti sostituisci *[distro]* e *[versione]* con le informazioni identificate:</span><span class="sxs-lookup"><span data-stu-id="21393-149">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

> [!NOTE]
> <span data-ttu-id="21393-150">Nel caso di RedHat, Oracle EL e CentOS 8, sostituisci *[distro]* con "rhel".</span><span class="sxs-lookup"><span data-stu-id="21393-150">In case of RedHat, Oracle EL, and CentOS 8, replace *[distro]* with 'rhel'.</span></span>

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

## <a name="deployment"></a><span data-ttu-id="21393-151">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="21393-151">Deployment</span></span>

<span data-ttu-id="21393-152">Includere il manifesto precedente nel sito.pp</span><span class="sxs-lookup"><span data-stu-id="21393-152">Include the above manifest in your site.pp</span></span> <span data-ttu-id="21393-153">file:</span><span class="sxs-lookup"><span data-stu-id="21393-153">file:</span></span>

```bash
cat /etc/puppetlabs/code/environments/production/manifests/site.pp
```
```Output
node "default" {
    include install_mdatp
}
```

<span data-ttu-id="21393-154">I dispositivi agente registrati esempre periodicamente il polling del server Di pupazzo e installano nuovi profili e criteri di configurazione non appena vengono rilevati.</span><span class="sxs-lookup"><span data-stu-id="21393-154">Enrolled agent devices periodically poll the Puppet Server and install new configuration profiles and policies as soon as they are detected.</span></span>

## <a name="monitor-puppet-deployment"></a><span data-ttu-id="21393-155">Monitorare la distribuzione di Puppet</span><span class="sxs-lookup"><span data-stu-id="21393-155">Monitor Puppet deployment</span></span>

<span data-ttu-id="21393-156">Nel dispositivo agente puoi anche controllare lo stato di onboarding eseguendo:</span><span class="sxs-lookup"><span data-stu-id="21393-156">On the agent device, you can also check the onboarding status by running:</span></span>

```bash
mdatp health
```
```Output
...
licensed                                : true
org_id                                  : "[your organization identifier]"
...
```

- <span data-ttu-id="21393-157">**licensed**: questo conferma che il dispositivo è legato all'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21393-157">**licensed**: This confirms that the device is tied to your organization.</span></span>

- <span data-ttu-id="21393-158">**orgId:** questo è l'identificatore dell'organizzazione Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="21393-158">**orgId**: This is your Defender for Endpoint organization identifier.</span></span>

## <a name="check-onboarding-status"></a><span data-ttu-id="21393-159">Controllare lo stato di onboarding</span><span class="sxs-lookup"><span data-stu-id="21393-159">Check onboarding status</span></span>

<span data-ttu-id="21393-160">Puoi verificare che i dispositivi siano stati correttamente onboarded creando uno script.</span><span class="sxs-lookup"><span data-stu-id="21393-160">You can check that devices have been correctly onboarded by creating a script.</span></span> <span data-ttu-id="21393-161">Ad esempio, lo script seguente controlla lo stato di onboarding nei dispositivi registrati:</span><span class="sxs-lookup"><span data-stu-id="21393-161">For example, the following script checks enrolled devices for onboarding status:</span></span>

```bash
mdatp health --field healthy
```

<span data-ttu-id="21393-162">Il comando precedente viene stampato `1` se il prodotto è onboarding e funziona come previsto.</span><span class="sxs-lookup"><span data-stu-id="21393-162">The above command prints `1` if the product is onboarded and functioning as expected.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="21393-163">Quando il prodotto viene avviato per la prima volta, scarica le definizioni antimalware più recenti.</span><span class="sxs-lookup"><span data-stu-id="21393-163">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="21393-164">A seconda della connessione Internet, l'operazione può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="21393-164">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="21393-165">Durante questo periodo di tempo il comando precedente restituisce il valore `0` .</span><span class="sxs-lookup"><span data-stu-id="21393-165">During this time the above command returns a value of `0`.</span></span>

<span data-ttu-id="21393-166">Se il prodotto non è integro, il codice di uscita (che può essere controllato `echo $?` tramite ) indica il problema:</span><span class="sxs-lookup"><span data-stu-id="21393-166">If the product is not healthy, the exit code (which can be checked through `echo $?`) indicates the problem:</span></span>

- <span data-ttu-id="21393-167">1 se il dispositivo non è ancora stato onboarded.</span><span class="sxs-lookup"><span data-stu-id="21393-167">1 if the device isn't onboarded yet.</span></span>
- <span data-ttu-id="21393-168">3 se non è possibile stabilire la connessione al daemon.</span><span class="sxs-lookup"><span data-stu-id="21393-168">3 if the connection to the daemon cannot be established.</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="21393-169">Registrare i problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="21393-169">Log installation issues</span></span>

 <span data-ttu-id="21393-170">Per ulteriori informazioni su come trovare il registro generato automaticamente creato dal programma di installazione quando si verifica un errore, vedere [Log installation issues](linux-resources.md#log-installation-issues).</span><span class="sxs-lookup"><span data-stu-id="21393-170">For more information on how to find the automatically generated log that is created by the installer when an error occurs, see [Log installation issues](linux-resources.md#log-installation-issues).</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="21393-171">Aggiornamenti del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="21393-171">Operating system upgrades</span></span>

<span data-ttu-id="21393-172">Durante l'aggiornamento del sistema operativo a una nuova versione principale, devi prima disinstallare Defender per Endpoint per Linux, installare l'aggiornamento e infine riconfigurare Defender per Endpoint per Linux nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="21393-172">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint for Linux, install the upgrade, and finally reconfigure Defender for Endpoint for Linux on your device.</span></span>

## <a name="uninstallation"></a><span data-ttu-id="21393-173">Disinstallazione</span><span class="sxs-lookup"><span data-stu-id="21393-173">Uninstallation</span></span>

<span data-ttu-id="21393-174">Creare un modulo *remove_mdatp* simile *a install_mdatp* con il contenuto seguente in *init.pp*</span><span class="sxs-lookup"><span data-stu-id="21393-174">Create a module *remove_mdatp* similar to *install_mdatp* with the following contents in *init.pp*</span></span> <span data-ttu-id="21393-175">file:</span><span class="sxs-lookup"><span data-stu-id="21393-175">file:</span></span>

```bash
class remove_mdatp {
    package { 'mdatp':
        ensure => 'purged',
    }
}
```
