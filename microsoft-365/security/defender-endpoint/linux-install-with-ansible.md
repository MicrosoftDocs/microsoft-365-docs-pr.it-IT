---
title: Distribuire Microsoft Defender per Endpoint su Linux con Ansible
ms.reviewer: ''
description: Descrive come distribuire Microsoft Defender per Endpoint su Linux utilizzando Ansible.
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
ms.openlocfilehash: 36095f14ad3ed71c6a8d4707522c08c07ea738c4
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572730"
---
# <a name="deploy-microsoft-defender-for-endpoint-on-linux-with-ansible"></a><span data-ttu-id="5166d-104">Distribuire Microsoft Defender per Endpoint su Linux con Ansible</span><span class="sxs-lookup"><span data-stu-id="5166d-104">Deploy Microsoft Defender for Endpoint on Linux with Ansible</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5166d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="5166d-105">**Applies to:**</span></span>
- [<span data-ttu-id="5166d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="5166d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5166d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5166d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="5166d-108">Vuoi provare Defender for Endpoint?</span><span class="sxs-lookup"><span data-stu-id="5166d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5166d-109">Iscriviti per una prova gratuita.</span><span class="sxs-lookup"><span data-stu-id="5166d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="5166d-110">In questo articolo viene descritto come distribuire Defender for Endpoint su Linux utilizzando Ansible.</span><span class="sxs-lookup"><span data-stu-id="5166d-110">This article describes how to deploy Defender for Endpoint on Linux using Ansible.</span></span> <span data-ttu-id="5166d-111">Una distribuzione riuscita richiede il completamento di tutte le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5166d-111">A successful deployment requires the completion of all of the following tasks:</span></span>

- [<span data-ttu-id="5166d-112">Scarica il pacchetto onboarding</span><span class="sxs-lookup"><span data-stu-id="5166d-112">Download the onboarding package</span></span>](#download-the-onboarding-package)
- [<span data-ttu-id="5166d-113">Creare file YAML ansibili</span><span class="sxs-lookup"><span data-stu-id="5166d-113">Create Ansible YAML files</span></span>](#create-ansible-yaml-files)
- [<span data-ttu-id="5166d-114">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="5166d-114">Deployment</span></span>](#deployment)
- [<span data-ttu-id="5166d-115">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="5166d-115">References</span></span>](#references)

## <a name="prerequisites-and-system-requirements"></a><span data-ttu-id="5166d-116">Prerequisiti e requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="5166d-116">Prerequisites and system requirements</span></span>

<span data-ttu-id="5166d-117">Prima di iniziare, vedere la [pagina Defender for Endpoint principale su Linux per](microsoft-defender-endpoint-linux.md) una descrizione dei prerequisiti e dei requisiti di sistema per la versione software corrente.</span><span class="sxs-lookup"><span data-stu-id="5166d-117">Before you get started, see [the main Defender for Endpoint on Linux page](microsoft-defender-endpoint-linux.md) for a description of prerequisites and system requirements for the current software version.</span></span>

<span data-ttu-id="5166d-118">Inoltre, per la distribuzione Ansible, è necessario avere familiarità con le attività di amministrazione ansible, configurare Ansible e sapere come distribuire playbook e attività.</span><span class="sxs-lookup"><span data-stu-id="5166d-118">In addition, for Ansible deployment, you need to be familiar with Ansible administration tasks, have Ansible configured, and know how to deploy playbooks and tasks.</span></span> <span data-ttu-id="5166d-119">Ansible ha molti modi per completare la stessa attività.</span><span class="sxs-lookup"><span data-stu-id="5166d-119">Ansible has many ways to complete the same task.</span></span> <span data-ttu-id="5166d-120">Queste istruzioni presuppongono la disponibilità di moduli Ansible supportati, *ad esempio apt* *e unarchive per* facilitare la distribuzione del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="5166d-120">These instructions assume availability of supported Ansible modules, such as *apt* and *unarchive* to help deploy the package.</span></span> <span data-ttu-id="5166d-121">L'organizzazione potrebbe usare un flusso di lavoro diverso.</span><span class="sxs-lookup"><span data-stu-id="5166d-121">Your organization might use a different workflow.</span></span> <span data-ttu-id="5166d-122">Per ulteriori [informazioni, fare riferimento alla documentazione ansible.](https://docs.ansible.com/)</span><span class="sxs-lookup"><span data-stu-id="5166d-122">Refer to the [Ansible documentation](https://docs.ansible.com/) for details.</span></span>

- <span data-ttu-id="5166d-123">Ansible deve essere installato in almeno un computer (Ansible chiama questo nodo di controllo).</span><span class="sxs-lookup"><span data-stu-id="5166d-123">Ansible needs to be installed on at least one computer (Ansible calls this the control node).</span></span>
- <span data-ttu-id="5166d-124">SSH deve essere configurato per un account amministratore tra il nodo di controllo e tutti i nodi gestiti (dispositivi in cui sarà installato Defender for Endpoint) ed è consigliabile configurarlo con l'autenticazione a chiave pubblica.</span><span class="sxs-lookup"><span data-stu-id="5166d-124">SSH must be configured for an administrator account between the control node and all managed nodes (devices that will have Defender for Endpoint installed on them), and it is recommended to be configured with public key authentication.</span></span>
- <span data-ttu-id="5166d-125">In tutti i nodi gestiti deve essere installato il software seguente:</span><span class="sxs-lookup"><span data-stu-id="5166d-125">The following software must be installed on all managed nodes:</span></span>
  - <span data-ttu-id="5166d-126">ricciolo</span><span class="sxs-lookup"><span data-stu-id="5166d-126">curl</span></span>
  - <span data-ttu-id="5166d-127">pitone-apt</span><span class="sxs-lookup"><span data-stu-id="5166d-127">python-apt</span></span>

- <span data-ttu-id="5166d-128">Tutti i nodi gestiti devono essere elencati nel formato seguente nel `/etc/ansible/hosts` file o nel file pertinente:</span><span class="sxs-lookup"><span data-stu-id="5166d-128">All managed nodes must be listed in the following format in the `/etc/ansible/hosts` or relevant file:</span></span>

    ```bash
    [servers]
    host1 ansible_ssh_host=10.171.134.39
    host2 ansible_ssh_host=51.143.50.51
    ```

- <span data-ttu-id="5166d-129">Test ping:</span><span class="sxs-lookup"><span data-stu-id="5166d-129">Ping test:</span></span>

    ```bash
    ansible -m ping all
    ```

## <a name="download-the-onboarding-package"></a><span data-ttu-id="5166d-130">Scarica il pacchetto onboarding</span><span class="sxs-lookup"><span data-stu-id="5166d-130">Download the onboarding package</span></span>

<span data-ttu-id="5166d-131">Scarica il pacchetto di onboarding da Microsoft Defender Security Center:</span><span class="sxs-lookup"><span data-stu-id="5166d-131">Download the onboarding package from Microsoft Defender Security Center:</span></span>

1. <span data-ttu-id="5166d-132">In Microsoft Defender Security Center passare a **Gestione Impostazioni > dispositivi > onboarding**.</span><span class="sxs-lookup"><span data-stu-id="5166d-132">In Microsoft Defender Security Center, go to **Settings > Device Management > Onboarding**.</span></span>
2. <span data-ttu-id="5166d-133">Nel primo menu a discesa, selezionare **Linux Server** come sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="5166d-133">In the first drop-down menu, select **Linux Server** as the operating system.</span></span> <span data-ttu-id="5166d-134">Nel secondo menu a discesa selezionare Lo strumento **di gestione della configurazione Linux preferito** come metodo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="5166d-134">In the second drop-down menu, select **Your preferred Linux configuration management tool** as the deployment method.</span></span>
3. <span data-ttu-id="5166d-135">Selezionare **Scarica pacchetto onboarding**.</span><span class="sxs-lookup"><span data-stu-id="5166d-135">Select **Download onboarding package**.</span></span> <span data-ttu-id="5166d-136">Salvare il file come WindowsDefenderATPOnboardingPackage.zip.</span><span class="sxs-lookup"><span data-stu-id="5166d-136">Save the file as WindowsDefenderATPOnboardingPackage.zip.</span></span>

    ![Microsoft Defender Security Center schermata](images/atp-portal-onboarding-linux-2.png)

4. <span data-ttu-id="5166d-138">Dal prompt dei comandi verificare di avere il file.</span><span class="sxs-lookup"><span data-stu-id="5166d-138">From a command prompt, verify that you have the file.</span></span> <span data-ttu-id="5166d-139">Estrarre il contenuto dell'archivio:</span><span class="sxs-lookup"><span data-stu-id="5166d-139">Extract the contents of the archive:</span></span>

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

## <a name="create-ansible-yaml-files"></a><span data-ttu-id="5166d-140">Creare file YAML ansibili</span><span class="sxs-lookup"><span data-stu-id="5166d-140">Create Ansible YAML files</span></span>

<span data-ttu-id="5166d-141">Creare una sottoattività o file di ruolo che contribuiscano a un playbook o a un'attività.</span><span class="sxs-lookup"><span data-stu-id="5166d-141">Create a subtask or role files that contribute to a playbook or task.</span></span>

- <span data-ttu-id="5166d-142">Creare l'attività di onboarding: `onboarding_setup.yml`</span><span class="sxs-lookup"><span data-stu-id="5166d-142">Create the onboarding task, `onboarding_setup.yml`:</span></span>

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

- <span data-ttu-id="5166d-143">Aggiungere il repository e la chiave Defender for `add_apt_repo.yml` Endpoint:</span><span class="sxs-lookup"><span data-stu-id="5166d-143">Add the Defender for Endpoint repository and key, `add_apt_repo.yml`:</span></span>

    <span data-ttu-id="5166d-144">Defender for Endpoint su Linux può essere distribuito da uno dei seguenti canali (indicato di seguito come *[channel]*): *insiders-fast*, *insiders-slow* o *prod*. Ognuno di questi canali corrisponde a un repository software Linux.</span><span class="sxs-lookup"><span data-stu-id="5166d-144">Defender for Endpoint on Linux can be deployed from one of the following channels (denoted below as *[channel]*): *insiders-fast*, *insiders-slow*, or *prod*. Each of these channels corresponds to a Linux software repository.</span></span>

    <span data-ttu-id="5166d-145">La scelta del canale determina il tipo e la frequenza degli aggiornamenti offerti al dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5166d-145">The choice of the channel determines the type and frequency of updates that are offered to your device.</span></span> <span data-ttu-id="5166d-146">I dispositivi *in tempi privilegiati sono* i primi a ricevere aggiornamenti e nuove funzionalità, seguiti in seguito da *insider-slow* e infine da *prod*.</span><span class="sxs-lookup"><span data-stu-id="5166d-146">Devices in *insiders-fast* are the first ones to receive updates and new features, followed later by *insiders-slow* and lastly by *prod*.</span></span>

    <span data-ttu-id="5166d-147">Per visualizzare in anteprima le nuove funzionalità e fornire un feedback tempestivo, è consigliabile configurare alcuni dispositivi dell'azienda in modo che *utilizzi insider veloci* o *i partecipanti al programma Insider-slow*.</span><span class="sxs-lookup"><span data-stu-id="5166d-147">In order to preview new features and provide early feedback, it is recommended that you configure some devices in your enterprise to use either *insiders-fast* or *insiders-slow*.</span></span>

    > [!WARNING]
    > <span data-ttu-id="5166d-148">Il cambio di canale dopo l'installazione iniziale richiede la reinstallazione del prodotto.</span><span class="sxs-lookup"><span data-stu-id="5166d-148">Switching the channel after the initial installation requires the product to be reinstalled.</span></span> <span data-ttu-id="5166d-149">Per cambiare canale prodotto: disinstallare il pacchetto esistente, riconfigurare il dispositivo per l'utilizzo del nuovo canale e seguire i passaggi descritti in questo documento per installare il pacchetto dal nuovo percorso.</span><span class="sxs-lookup"><span data-stu-id="5166d-149">To switch the product channel: uninstall the existing package, re-configure your device to use the new channel, and follow the steps in this document to install the package from the new location.</span></span>

    <span data-ttu-id="5166d-150">Prendere nota della distribuzione e della versione e identificare la voce più vicina in `https://packages.microsoft.com/config/` .</span><span class="sxs-lookup"><span data-stu-id="5166d-150">Note your distribution and version and identify the closest entry for it under `https://packages.microsoft.com/config/`.</span></span>

    <span data-ttu-id="5166d-151">Nei comandi seguenti sostituire *[distro]* *e [version]* con le informazioni identificate.</span><span class="sxs-lookup"><span data-stu-id="5166d-151">In the following commands, replace *[distro]* and *[version]* with the information you've identified.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5166d-152">Nel caso di Oracle Linux, sostituire *[distro]* con "rhel".</span><span class="sxs-lookup"><span data-stu-id="5166d-152">In case of Oracle Linux, replace *[distro]* with “rhel”.</span></span>

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

- <span data-ttu-id="5166d-153">Creare i file YAML di installazione e disinstallazione ansible.</span><span class="sxs-lookup"><span data-stu-id="5166d-153">Create the Ansible install and uninstall YAML files.</span></span>

    - <span data-ttu-id="5166d-154">Per le distribuzioni basate su apt utilizzare il seguente file YAML:</span><span class="sxs-lookup"><span data-stu-id="5166d-154">For apt-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_apt_repo.yml
            - name: Install MDATP
              apt:
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
            - name: Uninstall MDATP
              apt:
                name: mdatp
                state: absent
        ```

    - <span data-ttu-id="5166d-155">Per le distribuzioni basate su dnf utilizzare il seguente file YAML:</span><span class="sxs-lookup"><span data-stu-id="5166d-155">For dnf-based distributions use the following YAML file:</span></span>

        ```bash
        cat install_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - include: ../roles/onboarding_setup.yml
            - include: ../roles/add_yum_repo.yml
            - name: Install MDATP
              dnf:
                name: mdatp
                state: latest
                enablerepo: packages-microsoft-com-prod-[channel]
        ```

        ```bash
        cat uninstall_mdatp_dnf.yml
        ```
        ```Output
        - hosts: servers
          tasks:
            - name: Uninstall MDATP
              dnf:
                name: mdatp
                state: absent
        ```

## <a name="deployment"></a><span data-ttu-id="5166d-156">Distribuzione</span><span class="sxs-lookup"><span data-stu-id="5166d-156">Deployment</span></span>

<span data-ttu-id="5166d-157">Ora esegui i file delle attività in `/etc/ansible/playbooks/` o nella directory pertinente.</span><span class="sxs-lookup"><span data-stu-id="5166d-157">Now run the tasks files under `/etc/ansible/playbooks/` or relevant directory.</span></span>

- <span data-ttu-id="5166d-158">installazione:</span><span class="sxs-lookup"><span data-stu-id="5166d-158">Installation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/install_mdatp.yml -i /etc/ansible/hosts
    ```

> [!IMPORTANT]
> <span data-ttu-id="5166d-159">Quando il prodotto inizia per la prima volta, scarica le più recenti definizioni di antimalware.</span><span class="sxs-lookup"><span data-stu-id="5166d-159">When the product starts for the first time, it downloads the latest antimalware definitions.</span></span> <span data-ttu-id="5166d-160">A seconda della connessione Internet, possono essere disponibili fino a pochi minuti.</span><span class="sxs-lookup"><span data-stu-id="5166d-160">Depending on your Internet connection, this can take up to a few minutes.</span></span>

- <span data-ttu-id="5166d-161">Convalida/configurazione:</span><span class="sxs-lookup"><span data-stu-id="5166d-161">Validation/configuration:</span></span>

    ```bash
    ansible -m shell -a 'mdatp connectivity test' all
    ```
    ```bash
    ansible -m shell -a 'mdatp health' all
    ```

- <span data-ttu-id="5166d-162">Disinstallazione:</span><span class="sxs-lookup"><span data-stu-id="5166d-162">Uninstallation:</span></span>

    ```bash
    ansible-playbook /etc/ansible/playbooks/uninstall_mdatp.yml -i /etc/ansible/hosts
    ```

## <a name="log-installation-issues"></a><span data-ttu-id="5166d-163">Problemi di installazione dei registri</span><span class="sxs-lookup"><span data-stu-id="5166d-163">Log installation issues</span></span>

<span data-ttu-id="5166d-164">Per [ulteriori informazioni su](linux-resources.md#log-installation-issues) come trovare il registro generato automaticamente creato dal programma di installazione quando si verifica un errore, vedere Problemi di installazione del registro.</span><span class="sxs-lookup"><span data-stu-id="5166d-164">See [Log installation issues](linux-resources.md#log-installation-issues) for more information on how to find the automatically generated log that is created by the installer when an error occurs.</span></span>

## <a name="operating-system-upgrades"></a><span data-ttu-id="5166d-165">Aggiornamenti del sistema operativo</span><span class="sxs-lookup"><span data-stu-id="5166d-165">Operating system upgrades</span></span>

<span data-ttu-id="5166d-166">Quando si aggiorna il sistema operativo a una nuova versione principale, è necessario prima disinstallare Defender for Endpoint su Linux, installare l'aggiornamento e infine riconfigurare Defender for Endpoint su Linux sul dispositivo.</span><span class="sxs-lookup"><span data-stu-id="5166d-166">When upgrading your operating system to a new major version, you must first uninstall Defender for Endpoint on Linux, install the upgrade, and finally reconfigure Defender for Endpoint on Linux on your device.</span></span>

## <a name="references"></a><span data-ttu-id="5166d-167">Riferimenti</span><span class="sxs-lookup"><span data-stu-id="5166d-167">References</span></span>

- [<span data-ttu-id="5166d-168">Aggiungere o rimuovere repository YUM</span><span class="sxs-lookup"><span data-stu-id="5166d-168">Add or remove YUM repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/yum_repository_module.html)

- [<span data-ttu-id="5166d-169">Gestire i pacchetti con il gestore pacchetti dnf</span><span class="sxs-lookup"><span data-stu-id="5166d-169">Manage packages with the dnf package manager</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/dnf_module.html)

- [<span data-ttu-id="5166d-170">Aggiungere e rimuovere repository APT</span><span class="sxs-lookup"><span data-stu-id="5166d-170">Add and remove APT repositories</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_repository_module.html)

- [<span data-ttu-id="5166d-171">Gestire i pacchetti apt</span><span class="sxs-lookup"><span data-stu-id="5166d-171">Manage apt-packages</span></span>](https://docs.ansible.com/ansible/latest/collections/ansible/builtin/apt_module.html)

## <a name="see-also"></a><span data-ttu-id="5166d-172">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5166d-172">See also</span></span>
- [<span data-ttu-id="5166d-173">Esaminare i problemi di integrità dell'agente</span><span class="sxs-lookup"><span data-stu-id="5166d-173">Investigate agent health issues</span></span>](health-status.md)
