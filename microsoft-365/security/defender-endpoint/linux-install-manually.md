---
title: Distribuire manualmente Microsoft Defender per Endpoint su Linux
ms.reviewer: ''
description: Descrive come distribuire Manualmente Microsoft Defender for Endpoint su Linux dalla riga di comando.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, installazione, distribuire, disinstallazione, pupazzo, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 0374c1a44a4d942ea631d97f51fa48df15d3ec13
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2021
ms.locfileid: "51929086"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-manually"></a><span data-ttu-id="d9fde-104">Distribuire manualmente Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="d9fde-104">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d9fde-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="d9fde-105">**Applies to:**</span></span>
- [<span data-ttu-id="d9fde-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="d9fde-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="d9fde-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9fde-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="d9fde-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="d9fde-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="d9fde-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="d9fde-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="d9fde-110">Questo articolo descrive come distribuire Manualmente Microsoft Defender for Endpoint su Linux.</span><span class="sxs-lookup"><span data-stu-id="d9fde-110">This article describes how to deploy Microsoft Defender for Endpoint on Linux manually.</span></span> <span data-ttu-id="d9fde-111">Una distribuzione corretta richiede il completamento di tutte le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="d9fde-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="d9fde-112">Distribuire manualmente Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="d9fde-112">Deploy Microsoft Defender for Endpoint on Linux manually</span></span>](#deploy-microsoft-defender-for-endpoint-on-linux-manually)
  - [<span data-ttu-id="d9fde-113">Prerequisiti e requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="d9fde-113">Prerequisites and system requirements</span></span>](#prerequisites-and-system-requirements)
  - [<span data-ttu-id="d9fde-114">Configurare l'archivio software Linux</span><span class="sxs-lookup"><span data-stu-id="d9fde-114">Configure the Linux software repository</span></span>](#configure-the-linux-software-repository)
    - [<span data-ttu-id="d9fde-115">RHEL e varianti (CentOS e Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="d9fde-115">RHEL and variants (CentOS and Oracle Linux)</span></span>](#rhel-and-variants-centos-and-oracle-linux)
    - [<span data-ttu-id="d9fde-116">SLES e varianti</span><span class="sxs-lookup"><span data-stu-id="d9fde-116">SLES and variants</span></span>](#sles-and-variants)
    - [<span data-ttu-id="d9fde-117">Sistemi Ubuntu e Debian</span><span class="sxs-lookup"><span data-stu-id="d9fde-117">Ubuntu and Debian systems</span></span>](#ubuntu-and-debian-systems)
  - [<span data-ttu-id="d9fde-118">Installazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d9fde-118">Application installation</span></span>](#application-installation)
  - [<span data-ttu-id="d9fde-119">Scaricare il pacchetto di onboarding</span><span class="sxs-lookup"><span data-stu-id="d9fde-119">Download the onboarding package</span></span>](#download-the-onboarding-package)
  - [<span data-ttu-id="d9fde-120">Configurazione client</span><span class="sxs-lookup"><span data-stu-id="d9fde-120">Client configuration</span></span>](#client-configuration)
  - [<span data-ttu-id="d9fde-121">Script del programma di installazione</span><span class="sxs-lookup"><span data-stu-id="d9fde-121">Installer script</span></span>](#installer-script)
  - [<span data-ttu-id="d9fde-122">Registrare i problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="d9fde-122">Log installation issues</span></span>](#log-installation-issues)
  - [<span data-ttu-id="d9fde-123">Aggiornamenti del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="d9fde-123">Operating system upgrades</span></span>](#operating-system-upgrades)
  - [<span data-ttu-id="d9fde-124">Disinstallazione</span><span class="sxs-lookup"><span data-stu-id="d9fde-124">Uninstallation</span></span>](#uninstallation)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="d9fde-125">Prerequisiti e requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="d9fde-125">Prerequisites and system requirements</span></span>

<span data-ttu-id="d9fde-126">Prima di iniziare, vedi [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) per una descrizione dei prerequisiti e dei requisiti di sistema per la versione software corrente.</span><span class="sxs-lookup"><span data-stu-id="d9fde-126">Before you get started, see [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

## <a name="configure-the-linux-software-repository"></a><span data-ttu-id="d9fde-127">Configurare l'archivio software Linux</span><span class="sxs-lookup"><span data-stu-id="d9fde-127">Configure the Linux software repository</span></span>

<span data-ttu-id="d9fde-128">Defender per Endpoint su Linux può essere distribuito da uno dei seguenti canali (indicato di seguito come *[canale]*): *insiders-fast,* *insiders-slow* o *prod*. Ognuno di questi canali corrisponde a un archivio software Linux.</span><span class="sxs-lookup"><span data-stu-id="d9fde-128">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span> <span data-ttu-id="d9fde-129">Le istruzioni per configurare il dispositivo per l'uso di uno di questi archivi sono disponibili di seguito.</span><span class="sxs-lookup"><span data-stu-id="d9fde-129">Instructions for configuring your device to use one of these repositories are provided below.</span></span>

<span data-ttu-id="d9fde-130">La scelta del canale determina il tipo e la frequenza degli aggiornamenti offerti al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9fde-130">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="d9fde-131">I dispositivi *in Insiders-fast* sono i primi a ricevere aggiornamenti e nuove funzionalità, seguiti successivamente da *insider lenti* e infine *da prod*.</span><span class="sxs-lookup"><span data-stu-id="d9fde-131">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

<span data-ttu-id="d9fde-132">Per visualizzare in anteprima le nuove funzionalità e fornire feedback anticipato, è consigliabile configurare alcuni dispositivi nell'organizzazione per l'uso di *insiders-fast* o *insiders-slow*.</span><span class="sxs-lookup"><span data-stu-id="d9fde-132">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

> [!WARNING]
> <span data-ttu-id="d9fde-133">Il cambio di canale dopo l'installazione iniziale richiede la reinstallazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="d9fde-133">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="d9fde-134">Per cambiare il canale del prodotto: disinstalla il pacchetto esistente, ri-configura il dispositivo per l'uso del nuovo canale e segui i passaggi in questo documento per installare il pacchetto dal nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="d9fde-134">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

### <a name="rhel-and-variants-centos-and-oracle-linux"></a><span data-ttu-id="d9fde-135">RHEL e varianti (CentOS e Oracle Linux)</span><span class="sxs-lookup"><span data-stu-id="d9fde-135">RHEL and variants (CentOS and Oracle Linux)</span></span>

- <span data-ttu-id="d9fde-136">Installa `yum-utils` se non è ancora installato:</span><span class="sxs-lookup"><span data-stu-id="d9fde-136">Install `yum-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo yum install yum-utils
    ```

- <span data-ttu-id="d9fde-137">Annotare la distribuzione e la versione e identificare la voce più vicina (in base alla versione principale e secondaria) in `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="d9fde-137">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span> <span data-ttu-id="d9fde-138">Ad esempio, RHEL 7.9 è più vicino a 7,4 rispetto a 8.</span><span class="sxs-lookup"><span data-stu-id="d9fde-138">For instance, RHEL 7.9 is closer to 7.4 than to 8.</span></span>

    <span data-ttu-id="d9fde-139">Nei comandi seguenti sostituisci *[distro]* e *[versione]* con le informazioni identificate:</span><span class="sxs-lookup"><span data-stu-id="d9fde-139">In the below commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    > [!NOTE]
    > <span data-ttu-id="d9fde-140">Nel caso di Oracle Linux, sostituisci *[distro]* con "rhel".</span><span class="sxs-lookup"><span data-stu-id="d9fde-140">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="d9fde-141">Ad esempio, se si esegue CentOS 7 e si desidera distribuire Defender for Endpoint su Linux dal *canale prod:*</span><span class="sxs-lookup"><span data-stu-id="d9fde-141">For example, if you are running CentOS 7 and want to deploy Defender for Endpoint on Linux from the *prod* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/prod.repo
    ```

    <span data-ttu-id="d9fde-142">Oppure, se vuoi esplorare nuove funzionalità su dispositivi selezionati, potresti voler distribuire MDE per Linux nel canale *veloce per i insider:*</span><span class="sxs-lookup"><span data-stu-id="d9fde-142">Or if you wish to explore new features on selected devices, you might want to deploy MDE for Linux to *insiders-fast* channel:</span></span>

    ```bash
    sudo yum-config-manager --add-repo=https://packages.microsoft.com/config/centos/7/insiders-fast.repo
    ```

- <span data-ttu-id="d9fde-143">Installare la chiave pubblica del Gruppo di criteri di gruppo di Microsoft:</span><span class="sxs-lookup"><span data-stu-id="d9fde-143">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

- <span data-ttu-id="d9fde-144">Scarica e rendi utilizzabili tutti i metadati per gli archivi yum attualmente abilitati:</span><span class="sxs-lookup"><span data-stu-id="d9fde-144">Download and make usable all the metadata for the currently enabled yum repositories:</span></span>

    ```bash
    yum makecache
    ```

### <a name="sles-and-variants"></a><span data-ttu-id="d9fde-145">SLES e varianti</span><span class="sxs-lookup"><span data-stu-id="d9fde-145">SLES and variants</span></span>

- <span data-ttu-id="d9fde-146">Annotare la distribuzione e la versione e identificare la voce più vicina(in base alla versione principale e secondaria) in `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="d9fde-146">Note your distribution and version, and identify the closest entry(by major, then minor) for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="d9fde-147">Nei comandi seguenti sostituisci *[distro]* e *[versione]* con le informazioni identificate:</span><span class="sxs-lookup"><span data-stu-id="d9fde-147">In the following commands, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-[channel] https://packages.microsoft.com/config/[distro]/[version]/[channel].repo
    ```

    <span data-ttu-id="d9fde-148">Ad esempio, se si esegue SLES 12 e si desidera distribuire MDE per Linux dal *canale prod:*</span><span class="sxs-lookup"><span data-stu-id="d9fde-148">For example, if you are running SLES 12 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    sudo zypper addrepo -c -f -n microsoft-prod https://packages.microsoft.com/config/sles/12/prod.repo
    ```

- <span data-ttu-id="d9fde-149">Installare la chiave pubblica del Gruppo di criteri di gruppo di Microsoft:</span><span class="sxs-lookup"><span data-stu-id="d9fde-149">Install the Microsoft GPG public key:</span></span>

    ```bash
    sudo rpm --import http://packages.microsoft.com/keys/microsoft.asc
    ```

### <a name="ubuntu-and-debian-systems"></a><span data-ttu-id="d9fde-150">Sistemi Ubuntu e Debian</span><span class="sxs-lookup"><span data-stu-id="d9fde-150">Ubuntu and Debian systems</span></span>

- <span data-ttu-id="d9fde-151">Installa `curl` se non è ancora installato:</span><span class="sxs-lookup"><span data-stu-id="d9fde-151">Install `curl` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install curl
    ```

- <span data-ttu-id="d9fde-152">Installa `libplist-utils` se non è ancora installato:</span><span class="sxs-lookup"><span data-stu-id="d9fde-152">Install `libplist-utils` if it isn't installed yet:</span></span>

    ```bash
    sudo apt-get install libplist-utils
    ```

- <span data-ttu-id="d9fde-153">Annotare la distribuzione e la versione e identificare la voce più vicina (in base alla versione principale e secondaria) in `https://packages.microsoft.com/config` .</span><span class="sxs-lookup"><span data-stu-id="d9fde-153">Note your distribution and version, and identify the closest entry (by major, then minor) for it under `https://packages.microsoft.com/config`.</span></span>

    <span data-ttu-id="d9fde-154">Nel comando seguente sostituisci *[distro]* e *[versione]* con le informazioni identificate:</span><span class="sxs-lookup"><span data-stu-id="d9fde-154">In the below command, replace *[distro]* and *[version]* with the information you've identified:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/[distro]/[version]/[channel].list
    ```

    <span data-ttu-id="d9fde-155">Ad esempio, se si esegue Ubuntu 18.04 e si desidera distribuire MDE per Linux dal *canale prod:*</span><span class="sxs-lookup"><span data-stu-id="d9fde-155">For example, if you are running Ubuntu 18.04 and wish to deploy MDE for Linux from the *prod* channel:</span></span>

    ```bash
    curl -o microsoft.list https://packages.microsoft.com/config/ubuntu/18.04/prod.list
    ```

- <span data-ttu-id="d9fde-156">Installare la configurazione del repository:</span><span class="sxs-lookup"><span data-stu-id="d9fde-156">Install the repository configuration:</span></span>

    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-[channel].list
    ```
    <span data-ttu-id="d9fde-157">Ad esempio, se hai scelto *il canale prod:*</span><span class="sxs-lookup"><span data-stu-id="d9fde-157">For example, if you chose *prod* channel:</span></span>
    
    ```bash
    sudo mv ./microsoft.list /etc/apt/sources.list.d/microsoft-prod.list
    ```   

- <span data-ttu-id="d9fde-158">Installare il `gpg` pacchetto se non è già installato:</span><span class="sxs-lookup"><span data-stu-id="d9fde-158">Install the `gpg` package if not already installed:</span></span>

    ```bash
    sudo apt-get install gpg
    ```

  <span data-ttu-id="d9fde-159">Se `gpg` non è disponibile, installare `gnupg` .</span><span class="sxs-lookup"><span data-stu-id="d9fde-159">If `gpg` is not available, then install `gnupg`.</span></span>

- <span data-ttu-id="d9fde-160">Installare la chiave pubblica del Gruppo di criteri di gruppo di Microsoft:</span><span class="sxs-lookup"><span data-stu-id="d9fde-160">Install the Microsoft GPG public key:</span></span>

    ```bash
    curl https://packages.microsoft.com/keys/microsoft.asc | sudo apt-key add -
    ```

- <span data-ttu-id="d9fde-161">Installare il driver https se non è già presente:</span><span class="sxs-lookup"><span data-stu-id="d9fde-161">Install the https driver if it's not already present:</span></span>

    ```bash
    sudo apt-get install apt-transport-https
    ```

- <span data-ttu-id="d9fde-162">Aggiornare i metadati del repository:</span><span class="sxs-lookup"><span data-stu-id="d9fde-162">Update the repository metadata:</span></span>

    ```bash
    sudo apt-get update
    ```

## <a name="application-installation"></a><span data-ttu-id="d9fde-163">Installazione dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="d9fde-163">Application installation</span></span>

- <span data-ttu-id="d9fde-164">RHEL e varianti (CentOS e Oracle Linux):</span><span class="sxs-lookup"><span data-stu-id="d9fde-164">RHEL and variants (CentOS and Oracle Linux):</span></span>

    ```bash
    sudo yum install mdatp
    ```

    <span data-ttu-id="d9fde-165">Se nel dispositivo sono configurati più archivi Microsoft, è possibile specificare il repository da cui installare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d9fde-165">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="d9fde-166">L'esempio seguente mostra come installare il pacchetto dal canale se nel dispositivo è configurato anche `production` `insiders-fast` il canale repository.</span><span class="sxs-lookup"><span data-stu-id="d9fde-166">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="d9fde-167">Questa situazione può verificarsi se si usano più prodotti Microsoft nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9fde-167">This situation can happen if you are using multiple Microsoft products on your device.</span></span> <span data-ttu-id="d9fde-168">A seconda della distribuzione e della versione del server, l'alias del repository potrebbe essere diverso da quello dell'esempio seguente.</span><span class="sxs-lookup"><span data-stu-id="d9fde-168">Depending on the distribution and the version of your server, the repository alias might be different than the one in the following example.</span></span>

    ```bash
    # list all repositories
    yum repolist
    ```
    ```Output
    ...
    packages-microsoft-com-prod               packages-microsoft-com-prod        316
    packages-microsoft-com-prod-insiders-fast packages-microsoft-com-prod-ins      2
    ...
    ```
    ```bash
    # install the package from the production repository
    sudo yum --enablerepo=packages-microsoft-com-prod install mdatp
    ```

- <span data-ttu-id="d9fde-169">SLES e varianti:</span><span class="sxs-lookup"><span data-stu-id="d9fde-169">SLES and variants:</span></span>

    ```bash
    sudo zypper install mdatp
    ```

    <span data-ttu-id="d9fde-170">Se nel dispositivo sono configurati più archivi Microsoft, è possibile specificare il repository da cui installare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d9fde-170">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="d9fde-171">L'esempio seguente mostra come installare il pacchetto dal canale se nel dispositivo è configurato anche `production` `insiders-fast` il canale repository.</span><span class="sxs-lookup"><span data-stu-id="d9fde-171">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="d9fde-172">Questa situazione può verificarsi se si usano più prodotti Microsoft nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9fde-172">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    zypper repos
    ```

    ```Output
    ...
    #  | Alias | Name | ...
    XX | packages-microsoft-com-insiders-fast | microsoft-insiders-fast | ...
    XX | packages-microsoft-com-prod | microsoft-prod | ...
    ...
    ```
    ```bash
    sudo zypper install packages-microsoft-com-prod:mdatp
    ```

- <span data-ttu-id="d9fde-173">Sistema Ubuntu e Debian:</span><span class="sxs-lookup"><span data-stu-id="d9fde-173">Ubuntu and Debian system:</span></span>

    ```bash
    sudo apt-get install mdatp
    ```

    <span data-ttu-id="d9fde-174">Se nel dispositivo sono configurati più archivi Microsoft, è possibile specificare il repository da cui installare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="d9fde-174">If you have multiple Microsoft repositories configured on your device, you can be specific about which repository to install the package from.</span></span> <span data-ttu-id="d9fde-175">L'esempio seguente mostra come installare il pacchetto dal canale se nel dispositivo è configurato anche `production` `insiders-fast` il canale repository.</span><span class="sxs-lookup"><span data-stu-id="d9fde-175">The following example shows how to install the package from the `production` channel if you also have the `insiders-fast` repository channel configured on this device.</span></span> <span data-ttu-id="d9fde-176">Questa situazione può verificarsi se si usano più prodotti Microsoft nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9fde-176">This situation can happen if you are using multiple Microsoft products on your device.</span></span>

    ```bash
    cat /etc/apt/sources.list.d/*
    ```
    ```Output
    deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/ubuntu/18.04/prod insiders-fast main
    deb [arch=amd64] https://packages.microsoft.com/ubuntu/18.04/prod bionic main
    ```
    ```bash
    sudo apt -t bionic install mdatp
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="d9fde-177">Scaricare il pacchetto di onboarding</span><span class="sxs-lookup"><span data-stu-id="d9fde-177">Download the onboarding package</span></span>

<span data-ttu-id="d9fde-178">Scaricare il pacchetto di onboarding da Microsoft Defender Security Center:</span><span class="sxs-lookup"><span data-stu-id="d9fde-178">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="d9fde-179">In Microsoft Defender Security Center, vai a **Impostazioni > Gestione dispositivi > onboarding**.</span><span class="sxs-lookup"><span data-stu-id="d9fde-179">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="d9fde-180">Nel primo menu a discesa seleziona **Linux Server** come sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="d9fde-180">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="d9fde-181">Nel secondo menu a discesa seleziona Script locale (per un massimo **di 10 dispositivi)** come metodo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d9fde-181">In the second drop-down menu, select **Local Script (for up to 10 devices)** as the deployment method.</span></span>
3. <span data-ttu-id="d9fde-182">Seleziona **Scarica pacchetto di onboarding.**</span><span class="sxs-lookup"><span data-stu-id="d9fde-182">Select **Download onboarding package**.</span></span> <span data-ttu-id="d9fde-183">Salvare il file come WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="d9fde-183">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Screenshot di Microsoft Defender Security Center](images/atp-portal-onboarding-linux.png)

4. <span data-ttu-id="d9fde-185">Da un prompt dei comandi, verificare di disporre del file.</span><span class="sxs-lookup"><span data-stu-id="d9fde-185">From a command prompt, verify that you have the file.</span></span>
    <span data-ttu-id="d9fde-186">Estrarre il contenuto dell'archivio:</span><span class="sxs-lookup"><span data-stu-id="d9fde-186">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```

    ```Output
    total 8
    -rw-r--r-- 1 test  staff  5752 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```

    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: MicrosoftDefenderATPOnboardingLinuxServer.py
    ```


## <a name="client-configuration"></a><span data-ttu-id="d9fde-187">Configurazione client</span><span class="sxs-lookup"><span data-stu-id="d9fde-187">Client configuration</span></span>

1. <span data-ttu-id="d9fde-188">Copia MicrosoftDefenderATPOnboardingLinuxServer.py nel dispositivo di destinazione.</span><span class="sxs-lookup"><span data-stu-id="d9fde-188">Copy MicrosoftDefenderATPOnboardingLinuxServer.py to the target device.</span></span>

    <span data-ttu-id="d9fde-189">Inizialmente il dispositivo client non è associato a un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="d9fde-189">Initially the client device is not associated with an organization.</span></span> <span data-ttu-id="d9fde-190">Si noti che *l'attributo orgId* è vuoto:</span><span class="sxs-lookup"><span data-stu-id="d9fde-190">Note that the *orgId* attribute is blank:</span></span>

    ```bash
    mdatp health --field org_id
    ```

2. <span data-ttu-id="d9fde-191">Esegui MicrosoftDefenderATPOnboardingLinuxServer.py e tieni presente che, per eseguire questo comando, devi aver `python` installato nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="d9fde-191">Run MicrosoftDefenderATPOnboardingLinuxServer.py, and note that, in order to run this command, you must have `python` installed on the device:</span></span>

    ```bash
    python MicrosoftDefenderATPOnboardingLinuxServer.py
    ```

3. <span data-ttu-id="d9fde-192">Verifica che il dispositivo sia ora associato all'organizzazione e segnala un identificatore di organizzazione valido:</span><span class="sxs-lookup"><span data-stu-id="d9fde-192">Verify that the device is now associated with your organization and reports a valid organization identifier:</span></span>

    ```bash
    mdatp health --field org_id
    ```

4. <span data-ttu-id="d9fde-193">Pochi minuti dopo aver completato l'installazione, è possibile visualizzare lo stato eseguendo il comando seguente.</span><span class="sxs-lookup"><span data-stu-id="d9fde-193">A few minutes after you complete the installation, you can see the status by running the following command.</span></span> <span data-ttu-id="d9fde-194">Il valore restituito di `1` indica che il prodotto funziona come previsto:</span><span class="sxs-lookup"><span data-stu-id="d9fde-194">A return value of `1` denotes that the product is functioning as expected:</span></span>

    ```bash
    mdatp health --field healthy
    ```

    > [!IMPORTANT]
    > <span data-ttu-id="d9fde-195">Quando il prodotto viene avviato per la prima volta, scarica le definizioni antimalware più recenti.</span><span class="sxs-lookup"><span data-stu-id="d9fde-195">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="d9fde-196">A seconda della connessione Internet, l'operazione può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="d9fde-196">Depending on your Internet connection, this can take up to a few minutes.</span></span> <span data-ttu-id="d9fde-197">Durante questo periodo di tempo il comando precedente restituisce il valore `false` .</span><span class="sxs-lookup"><span data-stu-id="d9fde-197">During this time the above command returns a value of `false`.</span></span> <span data-ttu-id="d9fde-198">È possibile controllare lo stato dell'aggiornamento delle definizioni utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d9fde-198">You can check the status of the definition update using the following command:</span></span>
    > ```bash
    > mdatp health --field definitions_status
    > ```
    > <span data-ttu-id="d9fde-199">Tenere presente che potrebbe essere necessario configurare un proxy anche dopo aver completato l'installazione iniziale.</span><span class="sxs-lookup"><span data-stu-id="d9fde-199">Please note that you may also need to configure a proxy after completing the initial installation.</span></span> <span data-ttu-id="d9fde-200">Vedi [Configurare Defender per Endpoint su Linux per l'individuazione di proxy statici: configurazione post-installazione.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration)</span><span class="sxs-lookup"><span data-stu-id="d9fde-200">See [Configure Defender for Endpoint on Linux for static proxy discovery: Post-installation configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/linux-static-proxy-configuration#post-installation-configuration).</span></span>

5. <span data-ttu-id="d9fde-201">Eseguire un test di rilevamento per verificare che il dispositivo sia correttamente onboarded e che il servizio sia segnalato.</span><span class="sxs-lookup"><span data-stu-id="d9fde-201">Run a detection test to verify that the device is properly onboarded and reporting to the service.</span></span> <span data-ttu-id="d9fde-202">Eseguire la procedura seguente nel dispositivo appena onboarded:</span><span class="sxs-lookup"><span data-stu-id="d9fde-202">Perform the following steps on the newly onboarded device:</span></span>

    - <span data-ttu-id="d9fde-203">Verificare che la protezione in tempo reale sia abilitata (denotata dall'esecuzione `1` del comando seguente):</span><span class="sxs-lookup"><span data-stu-id="d9fde-203">Ensure that real-time protection is enabled (denoted by a result of `1` from running the following command):</span></span>

        ```bash
        mdatp health --field real_time_protection_enabled
        ```

    - <span data-ttu-id="d9fde-204">Aprire una finestra terminale.</span><span class="sxs-lookup"><span data-stu-id="d9fde-204">Open a Terminal window.</span></span> <span data-ttu-id="d9fde-205">Copiare ed eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="d9fde-205">Copy and execute the following command:</span></span>

        ``` bash
        curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt
        ```

    - <span data-ttu-id="d9fde-206">Il file dovrebbe essere stato messo in quarantena da Defender per Endpoint su Linux.</span><span class="sxs-lookup"><span data-stu-id="d9fde-206">The file should have been quarantined by Defender for Endpoint on Linux.</span></span> <span data-ttu-id="d9fde-207">Utilizzare il comando seguente per elencare tutte le minacce rilevate:</span><span class="sxs-lookup"><span data-stu-id="d9fde-207">Use the following command to list all the detected threats:</span></span>

        ```bash
        mdatp threat list
        ```

## <a name="installer-script"></a><span data-ttu-id="d9fde-208">Script del programma di installazione</span><span class="sxs-lookup"><span data-stu-id="d9fde-208">Installer script</span></span>

<span data-ttu-id="d9fde-209">In alternativa, puoi usare uno script di avvio automatico del [programma](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) di installazione fornito nel repository [GitHub pubblico.](https://github.com/microsoft/mdatp-xplat/)</span><span class="sxs-lookup"><span data-stu-id="d9fde-209">Alternatively, you can use an automated [installer bash script](https://github.com/microsoft/mdatp-xplat/blob/master/linux/installation/mde_installer.sh) provided in our [public GitHub repository](https://github.com/microsoft/mdatp-xplat/).</span></span>
<span data-ttu-id="d9fde-210">Lo script identifica la distribuzione e la versione e configura il dispositivo per estrarre il pacchetto più recente e installarlo.</span><span class="sxs-lookup"><span data-stu-id="d9fde-210">The script identifies the distribution and version, and sets up the device to pull the latest package and install it.</span></span>
<span data-ttu-id="d9fde-211">Puoi anche eseguire l'onboardboard con uno script fornito.</span><span class="sxs-lookup"><span data-stu-id="d9fde-211">You can also onboard with a provided script.</span></span>

```bash
❯ ./mde_installer.sh --help
usage: basename ./mde_installer.sh [OPTIONS]
Options:
-c|--channel      specify the channel from which you want to install. Default: insiders-fast
-i|--install      install the product
-r|--remove       remove the product
-u|--upgrade      upgrade the existing product
-o|--onboard      onboard/offboard the product with <onboarding_script>
-p|--passive-mode set EPP to passive mode
-t|--tag          set a tag by declaring <name> and <value>. ex: -t GROUP Coders
-m|--min_req      enforce minimum requirements
-w|--clean        remove repo from package manager for a specific channel
-v|--version      print out script version
-h|--help         display help
```

<span data-ttu-id="d9fde-212">Per altre [informazioni, vedere](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span><span class="sxs-lookup"><span data-stu-id="d9fde-212">Read more [here](https://github.com/microsoft/mdatp-xplat/tree/master/linux/installation).</span></span>

## <a name="log-installation-issues"></a><span data-ttu-id="d9fde-213">Registrare i problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="d9fde-213">Log installation issues</span></span>

<span data-ttu-id="d9fde-214">Vedere [Registrare i problemi](linux-resources.md#log-installation-issues) di installazione per ulteriori informazioni su come trovare il registro generato automaticamente creato dal programma di installazione quando si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="d9fde-214">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="d9fde-215">Aggiornamenti del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="d9fde-215">Operating system upgrades</span></span>

<span data-ttu-id="d9fde-216">Durante l'aggiornamento del sistema operativo a una nuova versione principale, devi prima disinstallare Defender per Endpoint in Linux, installare l'aggiornamento e infine riconfigurare Defender per Endpoint su Linux nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d9fde-216">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="how-to-migrate-from-insiders-fast-to-production-channel"></a><span data-ttu-id="d9fde-217">Come eseguire la migrazione da Insiders-Fast al canale di produzione</span><span class="sxs-lookup"><span data-stu-id="d9fde-217">How to migrate from Insiders-Fast to Production channel</span></span>

1. <span data-ttu-id="d9fde-218">Disinstallare la versione "Insiders-Fast Channel" di MDE per Linux.</span><span class="sxs-lookup"><span data-stu-id="d9fde-218">Uninstall the “Insiders-Fast channel” version of MDE for Linux.</span></span>

    ``
    sudo yum remove mdatp
    ``

1. <span data-ttu-id="d9fde-219">Disabilitare mdE per Linux Insiders-Fast repo  ``
    sudo yum repolist
    ``</span><span class="sxs-lookup"><span data-stu-id="d9fde-219">Disable the MDE for Linux Insiders-Fast repo  ``
    sudo yum repolist
 ``</span></span>

    > [!NOTE]
    > <span data-ttu-id="d9fde-220">L'output dovrebbe mostrare "packages-microsoft-com-fast-prod".</span><span class="sxs-lookup"><span data-stu-id="d9fde-220">The output should show “packages-microsoft-com-fast-prod”.</span></span>

    ``
    sudo yum-config-manager --disable packages-microsoft-com-fast-prod
    ``
1. <span data-ttu-id="d9fde-221">Ridistribuire MDE per Linux usando il "canale di produzione".</span><span class="sxs-lookup"><span data-stu-id="d9fde-221">Redeploy MDE for Linux using the “Production channel”.</span></span>


## <a name="uninstallation"></a><span data-ttu-id="d9fde-222">Disinstallazione</span><span class="sxs-lookup"><span data-stu-id="d9fde-222">Uninstallation</span></span>

<span data-ttu-id="d9fde-223">Vedi [Disinstallare](linux-resources.md#uninstall) per informazioni dettagliate su come rimuovere Defender per Endpoint su Linux dai dispositivi client.</span><span class="sxs-lookup"><span data-stu-id="d9fde-223">See [Uninstall](linux-resources.md#uninstall) for details on how to remove Defender for Endpoint on Linux from client devices.</span></span>
