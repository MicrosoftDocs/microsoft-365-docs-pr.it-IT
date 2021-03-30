---
title: Microsoft Defender ATP per Linux
ms.reviewer: ''
description: Descrive come installare e usare Microsoft Defender ATP per Linux.
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
ms.openlocfilehash: 08bb4c73cb9df429c4b07194f1c7615f44d745d8
ms.sourcegitcommit: c75aac39ee8d93218a79585113ef6b36f47c9ddf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/29/2021
ms.locfileid: "51408338"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="006a6-104">Microsoft Defender per endpoint per Linux</span><span class="sxs-lookup"><span data-stu-id="006a6-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="006a6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="006a6-105">**Applies to:**</span></span>
- [<span data-ttu-id="006a6-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="006a6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="006a6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="006a6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="006a6-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="006a6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="006a6-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="006a6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="006a6-110">Questo argomento descrive come installare, configurare, aggiornare e usare Microsoft Defender per Endpoint per Linux.</span><span class="sxs-lookup"><span data-stu-id="006a6-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="006a6-111">L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Microsoft Defender for Endpoint per Linux può causare problemi di prestazioni ed errori di sistema imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="006a6-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to cause performance problems and unpredictable system errors.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="006a6-112">Come installare Microsoft Defender per Endpoint per Linux</span><span class="sxs-lookup"><span data-stu-id="006a6-112">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="006a6-113">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="006a6-113">Prerequisites</span></span>

- <span data-ttu-id="006a6-114">Accesso al portale di Microsoft Defender Security Center</span><span class="sxs-lookup"><span data-stu-id="006a6-114">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="006a6-115">Distribuzione Linux con [systemd](https://systemd.io/) system manager</span><span class="sxs-lookup"><span data-stu-id="006a6-115">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="006a6-116">Esperienza a livello di principiante in script Linux e BASH</span><span class="sxs-lookup"><span data-stu-id="006a6-116">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="006a6-117">Privilegi amministrativi nel dispositivo (in caso di distribuzione manuale)</span><span class="sxs-lookup"><span data-stu-id="006a6-117">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="006a6-118">Istruzioni di installazione</span><span class="sxs-lookup"><span data-stu-id="006a6-118">Installation instructions</span></span>

<span data-ttu-id="006a6-119">Esistono diversi metodi e strumenti di distribuzione che puoi usare per installare e configurare Microsoft Defender per Endpoint per Linux.</span><span class="sxs-lookup"><span data-stu-id="006a6-119">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="006a6-120">In generale, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="006a6-120">In general you need to take the following steps:</span></span>

- <span data-ttu-id="006a6-121">Assicurati di avere un abbonamento a Microsoft Defender for Endpoint e di avere accesso al [portale di Microsoft Defender for Endpoint.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="006a6-121">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="006a6-122">Distribuire Microsoft Defender per Endpoint per Linux usando uno dei metodi di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="006a6-122">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="006a6-123">Lo strumento da riga di comando:</span><span class="sxs-lookup"><span data-stu-id="006a6-123">The command-line tool:</span></span>
    - [<span data-ttu-id="006a6-124">Distribuzione manuale</span><span class="sxs-lookup"><span data-stu-id="006a6-124">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="006a6-125">Strumenti di gestione di terze parti:</span><span class="sxs-lookup"><span data-stu-id="006a6-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="006a6-126">Distribuire con lo strumento di gestione della configurazione di Puppet</span><span class="sxs-lookup"><span data-stu-id="006a6-126">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="006a6-127">Distribuire con lo strumento di gestione della configurazione di Ansible</span><span class="sxs-lookup"><span data-stu-id="006a6-127">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="006a6-128">Se si verificano errori di installazione, fare riferimento a Risoluzione dei problemi di installazione [in Microsoft Defender per Endpoint per Linux](linux-support-install.md).</span><span class="sxs-lookup"><span data-stu-id="006a6-128">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="006a6-129">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="006a6-129">System requirements</span></span>

- <span data-ttu-id="006a6-130">Distribuzioni e versioni supportate del server Linux:</span><span class="sxs-lookup"><span data-stu-id="006a6-130">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="006a6-131">Red Hat Enterprise Linux 7.2 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="006a6-131">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="006a6-132">CentOS 7.2 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="006a6-132">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="006a6-133">Ubuntu 16,04 LTS o superiore</span><span class="sxs-lookup"><span data-stu-id="006a6-133">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="006a6-134">Debian 9 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="006a6-134">Debian 9 or higher</span></span>
  - <span data-ttu-id="006a6-135">SUSE Linux Enterprise Server 12 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="006a6-135">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="006a6-136">Oracle Linux 7.2 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="006a6-136">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="006a6-137">Versione kernel minima 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="006a6-137">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="006a6-138">`fanotify`L'opzione kernel deve essere abilitata</span><span class="sxs-lookup"><span data-stu-id="006a6-138">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="006a6-139">L'esecuzione di Defender per Endpoint per Linux affiancata ad altre soluzioni di sicurezza basate su base non `fanotify` è supportata.</span><span class="sxs-lookup"><span data-stu-id="006a6-139">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="006a6-140">Può portare a risultati imprevedibili, tra cui l'sospensione del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="006a6-140">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="006a6-141">Spazio su disco: 1 GB</span><span class="sxs-lookup"><span data-stu-id="006a6-141">Disk space: 1GB</span></span>
- <span data-ttu-id="006a6-142">/opt/microsoft/mdatp/sbin/wdavdaemon richiede l'autorizzazione eseguibile.</span><span class="sxs-lookup"><span data-stu-id="006a6-142">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="006a6-143">Per ulteriori informazioni, vedere "Verificare che il daemon abbia l'autorizzazione eseguibile" in Risolvere i problemi di installazione [per Microsoft Defender ATP per Linux.](/microsoft-365/security/defender-endpoint/linux-support-install)</span><span class="sxs-lookup"><span data-stu-id="006a6-143">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender ATP for Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>
- <span data-ttu-id="006a6-144">Memoria: 1 GB</span><span class="sxs-lookup"><span data-stu-id="006a6-144">Memory: 1GB</span></span>
    > [!NOTE]
    > <span data-ttu-id="006a6-145">Assicurati di avere spazio libero su disco in /var.</span><span class="sxs-lookup"><span data-stu-id="006a6-145">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="006a6-146">La soluzione attualmente offre protezione in tempo reale per i tipi di file system seguenti:</span><span class="sxs-lookup"><span data-stu-id="006a6-146">The solution currently provides real-time protection for the following file system types:</span></span>

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

<span data-ttu-id="006a6-147">Dopo aver abilitato il servizio, potrebbe essere necessario configurare la rete o il firewall per consentire le connessioni in uscita tra il servizio e gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="006a6-147">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="006a6-148">Il framework di controllo ( `auditd` ) deve essere abilitato.</span><span class="sxs-lookup"><span data-stu-id="006a6-148">Audit framework (`auditd`) must be enabled.</span></span>
  >[!NOTE]
  > <span data-ttu-id="006a6-149">Gli eventi di sistema acquisiti dalle regole aggiunte a verranno aggiunti ai log di controllo e potrebbero influire sul `audit.logs` controllo dell'host e sulla raccolta a monte.</span><span class="sxs-lookup"><span data-stu-id="006a6-149">System events captured by rules added to `audit.logs` will add to audit logs and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="006a6-150">Gli eventi aggiunti da Microsoft Defender per Endopoint per Linux saranno contrassegnati con `mdatp` la chiave.</span><span class="sxs-lookup"><span data-stu-id="006a6-150">Events added by Microsoft Defender for Endopoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="006a6-151">Connessioni di rete</span><span class="sxs-lookup"><span data-stu-id="006a6-151">Network connections</span></span>

<span data-ttu-id="006a6-152">Nel seguente foglio di calcolo scaricabile sono elencati i servizi e gli URL associati a cui la rete deve essere in grado di connettersi.</span><span class="sxs-lookup"><span data-stu-id="006a6-152">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="006a6-153">È consigliabile assicurarsi che non siano presenti regole di filtro di rete o firewall che negherebbero l'accesso a questi URL.</span><span class="sxs-lookup"><span data-stu-id="006a6-153">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="006a6-154">In caso contrario, potrebbe essere necessario creare una regola *di* autorizzazione specifica per loro.</span><span class="sxs-lookup"><span data-stu-id="006a6-154">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="006a6-155">**Foglio di calcolo dell'elenco dei domini**</span><span class="sxs-lookup"><span data-stu-id="006a6-155">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="006a6-156">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="006a6-156">**Description**</span></span>|
|:-----|:-----|
|![Immagine di scorrimento per il foglio di calcolo degli URL di Microsoft Defender for Endpoint](images/mdatp-urls.png)<br/>  | <span data-ttu-id="006a6-158">Foglio di calcolo di record DNS specifici per le posizioni dei servizi, le posizioni geografiche e il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="006a6-158">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="006a6-159">Scaricare il foglio di calcolo qui.</span><span class="sxs-lookup"><span data-stu-id="006a6-159">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="006a6-160">Per un elenco di URL più specifico, vedere [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="006a6-160">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="006a6-161">Defender for Endpoint può individuare un server proxy utilizzando i metodi di individuazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="006a6-161">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="006a6-162">Proxy trasparente</span><span class="sxs-lookup"><span data-stu-id="006a6-162">Transparent proxy</span></span>
- <span data-ttu-id="006a6-163">Configurazione manuale del proxy statico</span><span class="sxs-lookup"><span data-stu-id="006a6-163">Manual static proxy configuration</span></span>

<span data-ttu-id="006a6-164">Se un proxy o un firewall blocca il traffico anonimo, assicurati che il traffico anonimo sia consentito negli URL elencati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="006a6-164">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="006a6-165">Per i proxy trasparenti, non è necessaria alcuna configurazione aggiuntiva per Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="006a6-165">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="006a6-166">Per il proxy statico, seguire i passaggi descritti in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="006a6-166">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="006a6-167">PAC, WPAD e proxy autenticati non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="006a6-167">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="006a6-168">Verificare che sia in uso solo un proxy statico o trasparente.</span><span class="sxs-lookup"><span data-stu-id="006a6-168">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="006a6-169">Anche l'ispezione e l'intercettazione dei proxy SSL non sono supportati per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="006a6-169">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="006a6-170">Configura un'eccezione per l'ispezione SSL e il server proxy per passare direttamente i dati da Defender per Endpoint per Linux agli URL rilevanti senza intercettazione.</span><span class="sxs-lookup"><span data-stu-id="006a6-170">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="006a6-171">L'aggiunta del certificato di intercettazione all'archivio globale non consentirà l'intercettazione.</span><span class="sxs-lookup"><span data-stu-id="006a6-171">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="006a6-172">Per la procedura di risoluzione dei problemi, vedi Risolvere i [problemi di connettività cloud per Microsoft Defender per Endpoint per Linux.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="006a6-172">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="006a6-173">Come aggiornare Microsoft Defender per Endpoint per Linux</span><span class="sxs-lookup"><span data-stu-id="006a6-173">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="006a6-174">Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="006a6-174">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="006a6-175">Per aggiornare Microsoft Defender per Endpoint per Linux, vedere [Distribuire gli aggiornamenti per Microsoft Defender per Endpoint per Linux.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="006a6-175">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="006a6-176">Come configurare Microsoft Defender per Endpoint per Linux</span><span class="sxs-lookup"><span data-stu-id="006a6-176">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="006a6-177">Le indicazioni su come configurare il prodotto in ambienti aziendali sono disponibili in Impostare le preferenze [per Microsoft Defender per Endpoint per Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="006a6-177">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="006a6-178">Risorse</span><span class="sxs-lookup"><span data-stu-id="006a6-178">Resources</span></span>

- <span data-ttu-id="006a6-179">Per ulteriori informazioni sulla registrazione, la disinstallazione o altri argomenti, vedere [Resources](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="006a6-179">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
