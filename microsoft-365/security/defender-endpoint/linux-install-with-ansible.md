---
title: Distribuire Microsoft Defender ATP per Linux con Ansible
ms.reviewer: ''
description: Descrive come distribuire Microsoft Defender ATP per Linux usando Ansible.
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
ms.openlocfilehash: eca9727676fec9b716724719c182ca958b22ec85
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187806"
---
# <a name="deploy-microsoft-defender-for-endpoint-for-linux-with-ansible"></a><span data-ttu-id="98cdc-104">Distribuire Microsoft Defender per Endpoint per Linux con Ansible</span><span class="sxs-lookup"><span data-stu-id="98cdc-104">Deploy Microsoft Defender for Endpoint for Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="98cdc-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="98cdc-105">**Applies to:**</span></span>
- [<span data-ttu-id="98cdc-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="98cdc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="98cdc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98cdc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="98cdc-108">Vuoi provare Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="98cdc-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="98cdc-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="98cdc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="98cdc-110">Questo articolo descrive come distribuire Defender for Endpoint per Linux usando Ansible.</span><span class="sxs-lookup"><span data-stu-id="98cdc-110">This article describes how to deploy Defender for Endpoint for Linux using Ansible.</span></span> <span data-ttu-id="98cdc-111">Una distribuzione corretta richiede il completamento di tutte le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="98cdc-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="98cdc-112">Scaricare il pacchetto di onboarding</span><span class="sxs-lookup"><span data-stu-id="98cdc-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="98cdc-113">Creare file YAML ansible</span><span class="sxs-lookup"><span data-stu-id="98cdc-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="98cdc-114">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="98cdc-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="98cdc-115">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="98cdc-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="98cdc-116">Prerequisiti e requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="98cdc-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="98cdc-117">Prima di iniziare, vedi la [pagina principale di Defender per Endpoint per Linux](microsoft-defender-endpoint-linux.md) per una descrizione dei prerequisiti e dei requisiti di sistema per la versione software corrente.</span><span class="sxs-lookup"><span data-stu-id="98cdc-117">Before you get started, see [the main Defender for Endpoint for Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="98cdc-118">Inoltre, per la distribuzione di Ansible, devi avere familiarità con le attività di amministrazione di Ansible, avere Ansible configurato e sapere come distribuire playbook e attività.</span><span class="sxs-lookup"><span data-stu-id="98cdc-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="98cdc-119">Ansible ha molti modi per completare la stessa attività.</span><span class="sxs-lookup"><span data-stu-id="98cdc-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="98cdc-120">Queste istruzioni presuppongono la disponibilità di moduli ansible supportati, ad esempio *apt* e *unarchive* per facilitare la distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="98cdc-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="98cdc-121">L'organizzazione potrebbe utilizzare un flusso di lavoro diverso.</span><span class="sxs-lookup"><span data-stu-id="98cdc-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="98cdc-122">Per informazioni dettagliate, fare riferimento alla documentazione relativa a [Ansible.](https://docs.ansible.com/)</span><span class="sxs-lookup"><span data-stu-id="98cdc-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="98cdc-123">Ansible deve essere installato in almeno un computer (lo chiameremo computer primario).</span><span class="sxs-lookup"><span data-stu-id="98cdc-123">Ansible needs to be installed on at least one computer (we will call it the primary computer).</span></span>
- <span data-ttu-id="98cdc-124">SSH deve essere configurato per un account amministratore tra il computer primario e tutti i client ed è consigliabile configurarlo con l'autenticazione a chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="98cdc-124">SSH must be configured for an administrator account between the primary computer and all clients, and it is recommended be configured with public key authentication.</span></span>
- <span data-ttu-id="98cdc-125">In tutti i client deve essere installato il software seguente:</span><span class="sxs-lookup"><span data-stu-id="98cdc-125">The following software must be installed on all clients:</span></span>
  - <span data-ttu-id="98cdc-126">curl</span><span class="sxs-lookup"><span data-stu-id="98cdc-126">curl</span></span>
  - <span data-ttu-id="98cdc-127">python-apt</span><span class="sxs-lookup"><span data-stu-id="98cdc-127">python-apt</span></span>

- <span data-ttu-id="98cdc-128">Tutti gli host devono essere elencati nel formato seguente nel `/etc/ansible/hosts` file o pertinente:</span><span class="sxs-lookup"><span data-stu-id="98cdc-128">All hosts must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="98cdc-129">Test ping:</span><span class="sxs-lookup"><span data-stu-id="98cdc-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="98cdc-130">Scaricare il pacchetto di onboarding</span><span class="sxs-lookup"><span data-stu-id="98cdc-130">Download the onboarding package</span></span>

<span data-ttu-id="98cdc-131">Scaricare il pacchetto di onboarding da Microsoft Defender Security Center:</span><span class="sxs-lookup"><span data-stu-id="98cdc-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="98cdc-132">In Microsoft Defender Security Center, vai a **Impostazioni > Gestione dispositivi > onboarding**.</span><span class="sxs-lookup"><span data-stu-id="98cdc-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="98cdc-133">Nel primo menu a discesa seleziona **Linux Server** come sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="98cdc-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="98cdc-134">Nel secondo menu a discesa seleziona Lo strumento di gestione della **configurazione Linux preferito** come metodo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="98cdc-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="98cdc-135">Seleziona **Scarica pacchetto di onboarding.**</span><span class="sxs-lookup"><span data-stu-id="98cdc-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="98cdc-136">Salvare il file come WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="98cdc-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Screenshot di Microsoft Defender Security Center](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="98cdc-138">Da un prompt dei comandi, verificare di disporre del file.</span><span class="sxs-lookup"><span data-stu-id="98cdc-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="98cdc-139">Estrarre il contenuto dell'archivio:</span><span class="sxs-lookup"><span data-stu-id="98cdc-139">Extract the contents of the archive:</span></span>

    ```bash
    ls -l
    ```
    ```Output
    total 8
    -rw-r--r-- 1 test  staff  4984 Feb 18 11:22 WindowsDefenderATPOnboardingPackage.zip
    ```
    ```bash
    unzip WindowsDefenderATPOnboardingPackage.zip
    ```
    ```Output
    Archive:  WindowsDefenderATPOnboardingPackage.zip
    inflating: mdatp_onboard.json
    ```

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="98cdc-140">Creare file YAML ansible</span><span class="sxs-lookup"><span data-stu-id="98cdc-140">Create Ansible YAML files</span></span>

<span data-ttu-id="98cdc-141">Crea una sottoattività o file di ruolo che contribuiscono a un playbook o a un'attività.</span><span class="sxs-lookup"><span data-stu-id="98cdc-141">Create a subtask or role files that contribute to an playbook or task.</span></span>

- <span data-ttu-id="98cdc-142">Creare l'attività di onboarding: `onboarding_setup.yml`</span><span class="sxs-lookup"><span data-stu-id="98cdc-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

    ```bash
    - name: Create MDATP directories
      file:
        path: /etc/opt/microsoft/mdatp/
        recurse: true
        state: directory
        mode: 0755
        owner: root
        group: root

    - name: Register mdatp_onboard.json
      stat:
        path: /etc/opt/microsoft/mdatp/mdatp_onboard.json
      register: mdatp_onboard

    - name: Extract WindowsDefenderATPOnboardingPackage.zip into /etc/opt/microsoft/mdatp
      unarchive:
        src: WindowsDefenderATPOnboardingPackage.zip
        dest: /etc/opt/microsoft/mdatp
        mode: 0600
        owner: root
        group: root
      when: not mdatp_onboard.stat.exists
    ```

- <span data-ttu-id="98cdc-143">Aggiungi il repository e la chiave defender per endpoint.</span><span class="sxs-lookup"><span data-stu-id="98cdc-143">Add the Defender for Endpoint repository and key.</span></span>

    <span data-ttu-id="98cdc-144">Defender per Endpoint per Linux può essere distribuito da uno dei seguenti canali (indicato di seguito come *[canale]*): *insiders-fast,* *insiders-slow* o *prod*. Ognuno di questi canali corrisponde a un archivio software Linux.</span><span class="sxs-lookup"><span data-stu-id="98cdc-144">Defender for Endpoint for Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="98cdc-145">La scelta del canale determina il tipo e la frequenza degli aggiornamenti offerti al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98cdc-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="98cdc-146">I dispositivi *in Insiders-fast* sono i primi a ricevere aggiornamenti e nuove funzionalità, seguiti successivamente da *insider lenti* e infine *da prod*.</span><span class="sxs-lookup"><span data-stu-id="98cdc-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="98cdc-147">Per visualizzare in anteprima le nuove funzionalità e fornire feedback anticipato, è consigliabile configurare alcuni dispositivi nell'organizzazione per l'uso di *insiders-fast* o *insiders-slow*.</span><span class="sxs-lookup"><span data-stu-id="98cdc-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="98cdc-148">Il cambio di canale dopo l'installazione iniziale richiede la reinstallazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="98cdc-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="98cdc-149">Per cambiare il canale del prodotto: disinstalla il pacchetto esistente, ri-configura il dispositivo per l'uso del nuovo canale e segui i passaggi in questo documento per installare il pacchetto dal nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="98cdc-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="98cdc-150">Annotare la distribuzione e la versione e identificare la voce più vicina in `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="98cdc-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="98cdc-151">Nei comandi seguenti sostituisci *[distro]* e *[versione]* con le informazioni identificate.</span><span class="sxs-lookup"><span data-stu-id="98cdc-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="98cdc-152">Nel caso di Oracle Linux, sostituisci *[distro]* con "rhel".</span><span class="sxs-lookup"><span data-stu-id="98cdc-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

  ```bash
  - name: Add Microsoft APT key
    apt_key:
      keyserver: https://packages.microsoft.com/
      id: BC528686B50D79E339D3721CEB3E94ADBE1229CF
    when: ansible_os_family == "Debian"

  - name: Add Microsoft apt repository for MDATP
    apt_repository:
      repo: deb [arch=arm64,armhf,amd64] https://packages.microsoft.com/[distro]/[version]/prod [channel] main
      update_cache: yes
      state: present
      filename: microsoft-[channel].list
    when: ansible_os_family == "Debian"

  - name: Add Microsoft DNF/YUM key
    rpm_key:
      state: present
      key: https://packages.microsoft.com/keys/microsoft.asc
    when: ansible_os_family == "RedHat"

  - name: Add  Microsoft yum repository for MDATP
    yum_repository:
      name: packages-microsoft-com-prod-[channel]
      description: Microsoft Defender for Endpoint
      file: microsoft-[channel]
      baseurl: https://packages.microsoft.com/[distro]/[version]/[channel]/
      gpgcheck: yes
      enabled: Yes
  when: ansible_os_family == "RedHat"
  ```

- <span data-ttu-id="98cdc-153">Creare i file YAML di installazione e disinstallazione di Ansible.</span><span class="sxs-lookup"><span data-stu-id="98cdc-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="98cdc-154">Per le distribuzioni basate su apt usa il file YAML seguente:</span><span class="sxs-lookup"><span data-stu-id="98cdc-154">For apt-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - apt:
                name: mdatp
                state: latest
                update_cache: yes
        ```

        ```bash
        cat uninstall_mdatp.yml
        ```
        ```Output
        - hosts: servers
        tasks:
            - apt:
                name: mdatp
                state: absent
        ```

    - <span data-ttu-id="98cdc-155">Per le distribuzioni basate su yum utilizzare il file YAML seguente:</span><span class="sxs-lookup"><span data-stu-id="98cdc-155">For yum-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp_yum.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - yum:
              name: mdatp
              state: latest
              enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_yum.yml
        ```
        ```Output
        - hosts: servers
        tasks:
            - yum:
               name: mdatp
                state: absent
        ```

## <a name="deployment"></a><span data-ttu-id="98cdc-156">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="98cdc-156">Deployment</span></span>

<span data-ttu-id="98cdc-157">Eseguire ora i file delle attività nella `/etc/ansible/playbooks/` directory o nella directory pertinente.</span><span class="sxs-lookup"><span data-stu-id="98cdc-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="98cdc-158">Installazione:</span><span class="sxs-lookup"><span data-stu-id="98cdc-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="98cdc-159">Quando il prodotto viene avviato per la prima volta, scarica le definizioni antimalware più recenti.</span><span class="sxs-lookup"><span data-stu-id="98cdc-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="98cdc-160">A seconda della connessione Internet, l'operazione può richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="98cdc-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="98cdc-161">Convalida/configurazione:</span><span class="sxs-lookup"><span data-stu-id="98cdc-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="98cdc-162">Disinstallazione:</span><span class="sxs-lookup"><span data-stu-id="98cdc-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="98cdc-163">Registrare i problemi di installazione</span><span class="sxs-lookup"><span data-stu-id="98cdc-163">Log installation issues</span></span>

<span data-ttu-id="98cdc-164">Vedere [Registrare i problemi](linux-resources.md#log-installation-issues) di installazione per ulteriori informazioni su come trovare il registro generato automaticamente creato dal programma di installazione quando si verifica un errore.</span><span class="sxs-lookup"><span data-stu-id="98cdc-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="98cdc-165">Aggiornamenti del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="98cdc-165">Operating system upgrades</span></span>

<span data-ttu-id="98cdc-166">Durante l'aggiornamento del sistema operativo a una nuova versione principale, devi prima disinstallare Defender per Endpoint per Linux, installare l'aggiornamento e infine riconfigurare Defender per Endpoint per Linux nel dispositivo.</span><span class="sxs-lookup"><span data-stu-id="98cdc-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint for Linux, install the upgrade, and finally reconfigure Defender for Endpoint for Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="98cdc-167">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="98cdc-167">References</span></span>

- [<span data-ttu-id="98cdc-168">Aggiungere o rimuovere archivi YUM</span><span class="sxs-lookup"><span data-stu-id="98cdc-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/2.3/yum_repository_module.html)

- [<span data-ttu-id="98cdc-169">Gestire i pacchetti con gestione pacchetti yum</span><span class="sxs-lookup"><span data-stu-id="98cdc-169">Manage packages with the yum package manager</span></span>](https://docs.ansible.com/ansible/latest/modules/yum_module.html)

- [<span data-ttu-id="98cdc-170">Aggiungere e rimuovere archivi APT</span><span class="sxs-lookup"><span data-stu-id="98cdc-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/modules/apt_repository_module.html)

- [<span data-ttu-id="98cdc-171">Gestire i pacchetti apt</span><span class="sxs-lookup"><span data-stu-id="98cdc-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/modules/apt_module.html)
