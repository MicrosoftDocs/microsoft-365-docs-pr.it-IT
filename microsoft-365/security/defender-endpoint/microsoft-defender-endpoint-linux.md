---
title: Microsoft Defender per endpoint su Linux
ms.reviewer: ''
description: Descrive come installare e usare Microsoft Defender per Endpoint in Linux.
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 008263bfb948d1a2c52031635d074aca323e6764
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256892"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="7121e-104">Microsoft Defender per endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="7121e-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7121e-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="7121e-105">**Applies to:**</span></span>
- [<span data-ttu-id="7121e-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="7121e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="7121e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7121e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7121e-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="7121e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7121e-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="7121e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="7121e-110">Questo argomento descrive come installare, configurare, aggiornare e usare Microsoft Defender per Endpoint in Linux.</span><span class="sxs-lookup"><span data-stu-id="7121e-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="7121e-111">L'esecuzione di altri prodotti di protezione degli endpoint di terze parti insieme a Microsoft Defender for Endpoint su Linux può causare problemi di prestazioni ed effetti collaterali imprevedibili.</span><span class="sxs-lookup"><span data-stu-id="7121e-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="7121e-112">Se la protezione degli endpoint non Microsoft è un requisito assoluto nell'ambiente, puoi comunque sfruttare in modo sicuro la funzionalità Defender for Endpoint in Linux EDR dopo aver configurato la funzionalità antivirus per l'esecuzione in [modalità passiva.](linux-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="7121e-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="7121e-113">Come installare Microsoft Defender per Endpoint in Linux</span><span class="sxs-lookup"><span data-stu-id="7121e-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="7121e-114">Prerequisiti</span><span class="sxs-lookup"><span data-stu-id="7121e-114">Prerequisites</span></span>

- <span data-ttu-id="7121e-115">Accesso al Microsoft Defender Security Center portale</span><span class="sxs-lookup"><span data-stu-id="7121e-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="7121e-116">Distribuzione Linux con [systemd](https://systemd.io/) system manager</span><span class="sxs-lookup"><span data-stu-id="7121e-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="7121e-117">Esperienza a livello di principiante in script Linux e BASH</span><span class="sxs-lookup"><span data-stu-id="7121e-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="7121e-118">Privilegi amministrativi nel dispositivo (in caso di distribuzione manuale)</span><span class="sxs-lookup"><span data-stu-id="7121e-118">Administrative privileges on the device (in case of manual deployment)</span></span>

> [!NOTE]
>  <span data-ttu-id="7121e-119">Microsoft Defender per l'agente Endpoint su Linux è indipendente [dall'agente OMS.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="7121e-119">Microsoft Defender for Endpoint on Linux agent is independent from [OMS agent](/azure/azure-monitor/agents/agents-overview#log-analytics-agent).</span></span> <span data-ttu-id="7121e-120">Microsoft Defender for Endpoint si basa sulla propria pipeline di telemetria indipendente.</span><span class="sxs-lookup"><span data-stu-id="7121e-120">Microsoft Defender for Endpoint relies on its own independent telemetry pipeline.</span></span>
> 
> <span data-ttu-id="7121e-121">Microsoft Defender per Endpoint su Linux non è ancora integrato nel Centro sicurezza di Azure.</span><span class="sxs-lookup"><span data-stu-id="7121e-121">Microsoft Defender for Endpoint on Linux is not yet integrated into Azure Security Center.</span></span>



### <a name="installation-instructions"></a><span data-ttu-id="7121e-122">Istruzioni di installazione</span><span class="sxs-lookup"><span data-stu-id="7121e-122">Installation instructions</span></span>

<span data-ttu-id="7121e-123">Esistono diversi metodi e strumenti di distribuzione che puoi usare per installare e configurare Microsoft Defender per Endpoint in Linux.</span><span class="sxs-lookup"><span data-stu-id="7121e-123">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="7121e-124">In generale, è necessario eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="7121e-124">In general you need to take the following steps:</span></span>

- <span data-ttu-id="7121e-125">Assicurati di avere un abbonamento a Microsoft Defender for Endpoint e di avere accesso al [portale di Microsoft Defender for Endpoint.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="7121e-125">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="7121e-126">Distribuire Microsoft Defender per Endpoint su Linux usando uno dei metodi di distribuzione seguenti:</span><span class="sxs-lookup"><span data-stu-id="7121e-126">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="7121e-127">Lo strumento da riga di comando:</span><span class="sxs-lookup"><span data-stu-id="7121e-127">The command-line tool:</span></span>
    - [<span data-ttu-id="7121e-128">Distribuzione manuale</span><span class="sxs-lookup"><span data-stu-id="7121e-128">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="7121e-129">Strumenti di gestione di terze parti:</span><span class="sxs-lookup"><span data-stu-id="7121e-129">Third-party management tools:</span></span>
    - [<span data-ttu-id="7121e-130">Distribuire con lo strumento di gestione della configurazione di Puppet</span><span class="sxs-lookup"><span data-stu-id="7121e-130">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="7121e-131">Distribuire con lo strumento di gestione della configurazione di Ansible</span><span class="sxs-lookup"><span data-stu-id="7121e-131">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)
    - [<span data-ttu-id="7121e-132">Distribuire con lo strumento di gestione della configurazione di Chef</span><span class="sxs-lookup"><span data-stu-id="7121e-132">Deploy using Chef configuration management tool</span></span>](linux-deploy-defender-for-endpoint-with-chef.md)
    
<span data-ttu-id="7121e-133">Se si verificano errori di installazione, fare riferimento a Risoluzione dei problemi di installazione [in Microsoft Defender per Endpoint su Linux.](linux-support-install.md)</span><span class="sxs-lookup"><span data-stu-id="7121e-133">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>



### <a name="system-requirements"></a><span data-ttu-id="7121e-134">Requisiti di sistema</span><span class="sxs-lookup"><span data-stu-id="7121e-134">System requirements</span></span>

- <span data-ttu-id="7121e-135">Distribuzioni di server Linux supportate e versioni x64 (AMD64/EM64T):</span><span class="sxs-lookup"><span data-stu-id="7121e-135">Supported Linux server distributions and x64 (AMD64/EM64T) versions:</span></span>

  - <span data-ttu-id="7121e-136">Red Hat Enterprise Linux 7.2 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="7121e-136">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="7121e-137">CentOS 7.2 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="7121e-137">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="7121e-138">Ubuntu 16,04 LTS o superiore</span><span class="sxs-lookup"><span data-stu-id="7121e-138">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="7121e-139">Debian 9 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="7121e-139">Debian 9 or higher</span></span>
  - <span data-ttu-id="7121e-140">SUSE Linux Enterprise Server 12 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="7121e-140">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="7121e-141">Oracle Linux 7.2 o versione successiva</span><span class="sxs-lookup"><span data-stu-id="7121e-141">Oracle Linux 7.2 or higher</span></span>

    > [!NOTE]
    > <span data-ttu-id="7121e-142">Le distribuzioni e le versioni non elencate in modo esplicito non sono supportate (anche se derivano dalle distribuzioni ufficialmente supportate).</span><span class="sxs-lookup"><span data-stu-id="7121e-142">Distributions and version that are not explicitly listed are unsupported (even if they are derived from the officially supported distributions).</span></span>


- <span data-ttu-id="7121e-143">Versione kernel minima 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="7121e-143">Minimum kernel version 3.10.0-327</span></span>

- <span data-ttu-id="7121e-144">`fanotify`L'opzione kernel deve essere abilitata</span><span class="sxs-lookup"><span data-stu-id="7121e-144">The `fanotify` kernel option must be enabled</span></span>

  > [!CAUTION]
  > <span data-ttu-id="7121e-145">L'esecuzione di Defender per Endpoint su Linux affiancata ad altre soluzioni di sicurezza basate su base non `fanotify` è supportata.</span><span class="sxs-lookup"><span data-stu-id="7121e-145">Running Defender for Endpoint on Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="7121e-146">Può portare a risultati imprevedibili, tra cui l'sospensione del sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7121e-146">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="7121e-147">Spazio su disco: 1 GB</span><span class="sxs-lookup"><span data-stu-id="7121e-147">Disk space: 1 GB</span></span>

- <span data-ttu-id="7121e-148">/opt/microsoft/mdatp/sbin/wdavdaemon richiede l'autorizzazione eseguibile.</span><span class="sxs-lookup"><span data-stu-id="7121e-148">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="7121e-149">Per ulteriori informazioni, vedere "Verificare che il daemon abbia l'autorizzazione eseguibile" in Risolvere i problemi di installazione di [Microsoft Defender per Endpoint su Linux.](/microsoft-365/security/defender-endpoint/linux-support-install)</span><span class="sxs-lookup"><span data-stu-id="7121e-149">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>

- <span data-ttu-id="7121e-150">Core: minimo 2, 4 preferiti</span><span class="sxs-lookup"><span data-stu-id="7121e-150">Cores: 2 minimum, 4 preferred</span></span>

- <span data-ttu-id="7121e-151">Memoria: minimo 1 GB, 4 preferiti</span><span class="sxs-lookup"><span data-stu-id="7121e-151">Memory: 1 GB minimum, 4 preferred</span></span>

    > [!NOTE]
    > <span data-ttu-id="7121e-152">Assicurati di avere spazio libero su disco in /var.</span><span class="sxs-lookup"><span data-stu-id="7121e-152">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="7121e-153">La soluzione attualmente offre protezione in tempo reale per i tipi di file system seguenti:</span><span class="sxs-lookup"><span data-stu-id="7121e-153">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="7121e-154">Dopo aver abilitato il servizio, potrebbe essere necessario configurare la rete o il firewall per consentire le connessioni in uscita tra il servizio e gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="7121e-154">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="7121e-155">Il framework di controllo ( `auditd` ) deve essere abilitato.</span><span class="sxs-lookup"><span data-stu-id="7121e-155">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="7121e-156">Gli eventi di sistema acquisiti dalle regole aggiunte a verranno aggiunti a (s) e potrebbero influire sul controllo `/etc/audit/rules.d/` `audit.log` dell'host e sulla raccolta a monte.</span><span class="sxs-lookup"><span data-stu-id="7121e-156">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="7121e-157">Gli eventi aggiunti da Microsoft Defender per Endpoint su Linux saranno contrassegnati con `mdatp` la chiave.</span><span class="sxs-lookup"><span data-stu-id="7121e-157">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="7121e-158">Connessioni di rete</span><span class="sxs-lookup"><span data-stu-id="7121e-158">Network connections</span></span>

<span data-ttu-id="7121e-159">Nel seguente foglio di calcolo scaricabile sono elencati i servizi e gli URL associati a cui la rete deve essere in grado di connettersi.</span><span class="sxs-lookup"><span data-stu-id="7121e-159">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="7121e-160">È consigliabile assicurarsi che non siano presenti regole di filtro di rete o firewall che negherebbero l'accesso a questi URL.</span><span class="sxs-lookup"><span data-stu-id="7121e-160">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="7121e-161">In caso contrario, potrebbe essere necessario creare una regola *di* autorizzazione specifica per loro.</span><span class="sxs-lookup"><span data-stu-id="7121e-161">If there are, you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="7121e-162">Foglio di calcolo dell'elenco dei domini</span><span class="sxs-lookup"><span data-stu-id="7121e-162">Spreadsheet of domains list</span></span> | <span data-ttu-id="7121e-163">Descrizione</span><span class="sxs-lookup"><span data-stu-id="7121e-163">Description</span></span> |
|:-----|:-----|
|![Immagine di scorrimento per il foglio di calcolo degli URL di Microsoft Defender for Endpoint](images/mdatp-urls.png)<br/>  | <span data-ttu-id="7121e-165">Foglio di calcolo di record DNS specifici per le posizioni dei servizi, le posizioni geografiche e il sistema operativo.</span><span class="sxs-lookup"><span data-stu-id="7121e-165">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="7121e-166">Scaricare il foglio di calcolo qui.</span><span class="sxs-lookup"><span data-stu-id="7121e-166">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="7121e-167">Per un elenco di URL più specifico, vedere [Configure proxy and internet connectivity settings](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="7121e-167">For a more specific URL list, see [Configure proxy and internet connectivity settings](/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="7121e-168">Defender for Endpoint può individuare un server proxy utilizzando i metodi di individuazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="7121e-168">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="7121e-169">Proxy trasparente</span><span class="sxs-lookup"><span data-stu-id="7121e-169">Transparent proxy</span></span>
- <span data-ttu-id="7121e-170">Configurazione manuale del proxy statico</span><span class="sxs-lookup"><span data-stu-id="7121e-170">Manual static proxy configuration</span></span>

<span data-ttu-id="7121e-171">Se un proxy o un firewall blocca il traffico anonimo, assicurati che il traffico anonimo sia consentito negli URL elencati in precedenza.</span><span class="sxs-lookup"><span data-stu-id="7121e-171">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="7121e-172">Per i proxy trasparenti, non è necessaria alcuna configurazione aggiuntiva per Defender per Endpoint.</span><span class="sxs-lookup"><span data-stu-id="7121e-172">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="7121e-173">Per il proxy statico, seguire i passaggi descritti in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="7121e-173">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="7121e-174">PAC, WPAD e proxy autenticati non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="7121e-174">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="7121e-175">Verificare che sia in uso solo un proxy statico o trasparente.</span><span class="sxs-lookup"><span data-stu-id="7121e-175">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="7121e-176">Anche l'ispezione e l'intercettazione dei proxy SSL non sono supportati per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="7121e-176">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="7121e-177">Configura un'eccezione per l'ispezione SSL e il server proxy per passare direttamente i dati da Defender per Endpoint su Linux agli URL rilevanti senza intercettazione.</span><span class="sxs-lookup"><span data-stu-id="7121e-177">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="7121e-178">L'aggiunta del certificato di intercettazione all'archivio globale non consentirà l'intercettazione.</span><span class="sxs-lookup"><span data-stu-id="7121e-178">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="7121e-179">Per la procedura di risoluzione dei problemi, vedi Risolvere i problemi [di connettività cloud per Microsoft Defender per Endpoint su Linux.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="7121e-179">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="7121e-180">Come aggiornare Microsoft Defender per Endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="7121e-180">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="7121e-181">Microsoft pubblica regolarmente aggiornamenti software per migliorare le prestazioni, la sicurezza e offrire nuove funzionalità.</span><span class="sxs-lookup"><span data-stu-id="7121e-181">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="7121e-182">Per aggiornare Microsoft Defender per Endpoint su Linux, fare riferimento [a Distribuire gli aggiornamenti per Microsoft Defender per Endpoint su Linux.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="7121e-182">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="7121e-183">Come configurare Microsoft Defender per endpoint su Linux</span><span class="sxs-lookup"><span data-stu-id="7121e-183">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="7121e-184">Le indicazioni su come configurare il prodotto in ambienti aziendali sono disponibili in Impostare le preferenze [per Microsoft Defender per Endpoint su Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="7121e-184">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="7121e-185">Risorse</span><span class="sxs-lookup"><span data-stu-id="7121e-185">Resources</span></span>

- <span data-ttu-id="7121e-186">Per ulteriori informazioni sulla registrazione, la disinstallazione o altri argomenti, vedere [Resources](linux-resources.md).</span><span class="sxs-lookup"><span data-stu-id="7121e-186">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
