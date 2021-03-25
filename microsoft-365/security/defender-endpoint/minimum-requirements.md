---
title: Requisiti minimi per Microsoft Defender per Endpoint
description: Comprendere i requisiti di licenza e i requisiti per l'onboarding dei dispositivi nel servizio
keywords: requisiti minimi, licenze, tabella di confronto
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: c6afa48fcee80c0b8fb7ed0563264932566b6321
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185792"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="582e6-104">Requisiti minimi per Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="582e6-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="582e6-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="582e6-105">**Applies to:**</span></span>
- [<span data-ttu-id="582e6-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="582e6-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="582e6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="582e6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="582e6-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="582e6-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="582e6-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="582e6-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="582e6-110">Esistono alcuni requisiti minimi per l'onboarding dei dispositivi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="582e6-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="582e6-111">Informazioni sulle licenze, i requisiti hardware e software e altre impostazioni di configurazione per eseguire l'onboardment dei dispositivi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="582e6-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> <span data-ttu-id="582e6-112">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="582e6-112">Want to experience Microsoft Defender for Endpoint?</span></span> <span data-ttu-id="582e6-113">[Iscriversi per una versione di valutazione gratuita.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="582e6-113">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink).</span></span>

> [!TIP]
> - <span data-ttu-id="582e6-114">Informazioni sui miglioramenti più recenti in Defender for Endpoint: [Defender for Endpoint Tech Community.](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced)</span><span class="sxs-lookup"><span data-stu-id="582e6-114">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="582e6-115">Defender for Endpoint ha dimostrato le funzionalità di ottica e rilevamento leader del settore nella recente valutazione MITRE.</span><span class="sxs-lookup"><span data-stu-id="582e6-115">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="582e6-116">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="582e6-116">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="582e6-117">Requisiti per la licenza</span><span class="sxs-lookup"><span data-stu-id="582e6-117">Licensing requirements</span></span>
<span data-ttu-id="582e6-118">Microsoft Defender for Endpoint richiede una delle seguenti offerte di contratti multilicenza Microsoft:</span><span class="sxs-lookup"><span data-stu-id="582e6-118">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="582e6-119">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="582e6-119">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="582e6-120">Windows 10 Education A5</span><span class="sxs-lookup"><span data-stu-id="582e6-120">Windows 10 Education A5</span></span>
- <span data-ttu-id="582e6-121">Microsoft 365 E5 (M365 E5) che include Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="582e6-121">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="582e6-122">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="582e6-122">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="582e6-123">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="582e6-123">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="582e6-124">Microsoft 365 A5 Security</span><span class="sxs-lookup"><span data-stu-id="582e6-124">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="582e6-125">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="582e6-125">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="582e6-126">Gli utenti con licenza idonea possono usare Microsoft Defender per Endpoint su un massimo di cinque dispositivi simultanei.</span><span class="sxs-lookup"><span data-stu-id="582e6-126">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="582e6-127">Microsoft Defender for Endpoint è disponibile anche per l'acquisto da un provider di soluzioni cloud (CSP).</span><span class="sxs-lookup"><span data-stu-id="582e6-127">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>

<span data-ttu-id="582e6-128">Microsoft Defender for Endpoint per i server richiede una delle opzioni di licenza seguenti:</span><span class="sxs-lookup"><span data-stu-id="582e6-128">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="582e6-129">Centro sicurezza di Azure con Azure Defender abilitato</span><span class="sxs-lookup"><span data-stu-id="582e6-129">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="582e6-130">Microsoft Defender for Endpoint for Server (uno per server coperto)</span><span class="sxs-lookup"><span data-stu-id="582e6-130">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="582e6-131">I clienti possono acquisire licenze server (una per server OSE)) per Microsoft Defender for Endpoint for Servers se hanno un minimo combinato di 50 licenze per una o più delle licenze utente seguenti:</span><span class="sxs-lookup"><span data-stu-id="582e6-131">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="582e6-132">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="582e6-132">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="582e6-133">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="582e6-133">Windows E5/A5</span></span>
> * <span data-ttu-id="582e6-134">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="582e6-134">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="582e6-135">Microsoft 365 E5/A5 Security</span><span class="sxs-lookup"><span data-stu-id="582e6-135">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="582e6-136">Per informazioni dettagliate sulle licenze, vedere il sito [condizioni](https://www.microsoft.com/licensing/terms/) del prodotto e collaborare con il team dell'account per ulteriori informazioni sui termini e le condizioni.</span><span class="sxs-lookup"><span data-stu-id="582e6-136">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="582e6-137">Per altre informazioni sulla matrice di funzionalità nelle edizioni di Windows 10, vedi [Confrontare le edizioni di Windows 10.](https://www.microsoft.com/windowsforbusiness/compare)</span><span class="sxs-lookup"><span data-stu-id="582e6-137">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="582e6-138">Per una tabella di confronto dettagliata del confronto delle edizioni commerciali di Windows 10, vedi il [PDF di confronto.](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf)</span><span class="sxs-lookup"><span data-stu-id="582e6-138">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="582e6-139">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="582e6-139">Browser requirements</span></span>
<span data-ttu-id="582e6-140">L'accesso a Defender for Endpoint viene eseguito tramite un browser, che supporta i browser seguenti:</span><span class="sxs-lookup"><span data-stu-id="582e6-140">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="582e6-141">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="582e6-141">Microsoft Edge</span></span>
- <span data-ttu-id="582e6-142">Internet Explorer versione 11</span><span class="sxs-lookup"><span data-stu-id="582e6-142">Internet Explorer version 11</span></span>
- <span data-ttu-id="582e6-143">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="582e6-143">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="582e6-144">Mentre altri browser potrebbero funzionare, i browser menzionati sono quelli supportati.</span><span class="sxs-lookup"><span data-stu-id="582e6-144">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="582e6-145">Requisiti hardware e software</span><span class="sxs-lookup"><span data-stu-id="582e6-145">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="582e6-146">Versioni di Windows supportate</span><span class="sxs-lookup"><span data-stu-id="582e6-146">Supported Windows versions</span></span>
- <span data-ttu-id="582e6-147">Windows 7 SP1 Enterprise ([Richiede ESU per il supporto](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq). )</span><span class="sxs-lookup"><span data-stu-id="582e6-147">Windows 7 SP1 Enterprise ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="582e6-148">Windows 7 SP1 Pro ([Richiede ESU per il supporto](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq). )</span><span class="sxs-lookup"><span data-stu-id="582e6-148">Windows 7 SP1 Pro ([Requires ESU for support](https://docs.microsoft.com/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="582e6-149">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="582e6-149">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="582e6-150">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="582e6-150">Windows 8.1 Pro</span></span>
- <span data-ttu-id="582e6-151">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="582e6-151">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="582e6-152">Windows 10 Enterprise LTSC</span><span class="sxs-lookup"><span data-stu-id="582e6-152">Windows 10 Enterprise LTSC</span></span>](https://docs.microsoft.com/windows/whats-new/ltsc/)
- <span data-ttu-id="582e6-153">Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="582e6-153">Windows 10 Education</span></span>
- <span data-ttu-id="582e6-154">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="582e6-154">Windows 10 Pro</span></span>
- <span data-ttu-id="582e6-155">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="582e6-155">Windows 10 Pro Education</span></span>
- <span data-ttu-id="582e6-156">Windows Server</span><span class="sxs-lookup"><span data-stu-id="582e6-156">Windows server</span></span>
  - <span data-ttu-id="582e6-157">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="582e6-157">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="582e6-158">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="582e6-158">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="582e6-159">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="582e6-159">Windows Server 2016</span></span>
  - <span data-ttu-id="582e6-160">Windows Server, versione 1803 o successiva</span><span class="sxs-lookup"><span data-stu-id="582e6-160">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="582e6-161">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="582e6-161">Windows Server 2019</span></span>
- <span data-ttu-id="582e6-162">Desktop virtuale Windows</span><span class="sxs-lookup"><span data-stu-id="582e6-162">Windows Virtual Desktop</span></span>

<span data-ttu-id="582e6-163">I dispositivi nella rete devono eseguire una di queste edizioni.</span><span class="sxs-lookup"><span data-stu-id="582e6-163">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="582e6-164">I requisiti hardware per Defender per Endpoint nei dispositivi sono gli stessi per le edizioni supportate.</span><span class="sxs-lookup"><span data-stu-id="582e6-164">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="582e6-165">I computer che eseguono versioni per dispositivi mobili di Windows (ad esempio Windows CE e Windows 10 Mobile) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="582e6-165">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) are not supported.</span></span>
>
> <span data-ttu-id="582e6-166">Le macchine virtuali che eseguono Windows 10 Enterprise 2016 LTSB potrebbero riscontrare problemi di prestazioni se eseguite su piattaforme di virtualizzazione non Microsoft.</span><span class="sxs-lookup"><span data-stu-id="582e6-166">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="582e6-167">Per gli ambienti virtuali, ti consigliamo di usare Windows 10 Enterprise LTSC 2019 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="582e6-167">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="582e6-168">Altri sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="582e6-168">Other supported operating systems</span></span>
- <span data-ttu-id="582e6-169">Android</span><span class="sxs-lookup"><span data-stu-id="582e6-169">Android</span></span>
- <span data-ttu-id="582e6-170">Linux</span><span class="sxs-lookup"><span data-stu-id="582e6-170">Linux</span></span>
- <span data-ttu-id="582e6-171">macOS</span><span class="sxs-lookup"><span data-stu-id="582e6-171">macOS</span></span>

> [!NOTE]
> <span data-ttu-id="582e6-172">Per il funzionamento dell'integrazione, dovrai conoscere esattamente le distribuzioni Linux e le versioni di Android e macOS compatibili con Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="582e6-172">You'll need to know the exact Linux distributions and versions of Android and macOS that are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="582e6-173">Requisiti di archiviazione e configurazione di rete e dati</span><span class="sxs-lookup"><span data-stu-id="582e6-173">Network and data storage and configuration requirements</span></span>
<span data-ttu-id="582e6-174">Quando esegui l'onboarding guidato per la prima volta, devi scegliere dove archiviare le informazioni relative a Microsoft Defender for Endpoint: nell'Unione Europea, nel Regno Unito o nel datacenter degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="582e6-174">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="582e6-175">Non è possibile modificare il percorso di archiviazione dei dati dopo la prima installazione.</span><span class="sxs-lookup"><span data-stu-id="582e6-175">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="582e6-176">Per altre [informazioni su dove](data-storage-privacy.md) e come Microsoft archivia i dati, consulta Microsoft Defender per l'archiviazione e la privacy dei dati degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="582e6-176">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="582e6-177">Impostazioni dei dati di diagnostica</span><span class="sxs-lookup"><span data-stu-id="582e6-177">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="582e6-178">Microsoft Defender for Endpoint non richiede alcun livello di diagnostica specifico purché sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="582e6-178">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="582e6-179">Verificare che il servizio dati di diagnostica sia abilitato in tutti i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="582e6-179">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="582e6-180">Per impostazione predefinita, questo servizio è abilitato.</span><span class="sxs-lookup"><span data-stu-id="582e6-180">By default, this service is enabled.</span></span> <span data-ttu-id="582e6-181">È consigliabile verificare che i dati dei sensori siano da essi.</span><span class="sxs-lookup"><span data-stu-id="582e6-181">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="582e6-182">Usa la riga di comando per controllare il tipo di avvio del servizio dati di diagnostica **di Windows 10:**</span><span class="sxs-lookup"><span data-stu-id="582e6-182">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="582e6-183">Apri un prompt della riga di comando con privilegi elevati nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="582e6-183">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="582e6-184">Passare a **Start** e digitare **cmd**.</span><span class="sxs-lookup"><span data-stu-id="582e6-184">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="582e6-185">Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="582e6-185">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="582e6-186">Immettere il comando seguente e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="582e6-186">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="582e6-187">Se il servizio è abilitato, il risultato dovrebbe essere simile allo screenshot seguente:</span><span class="sxs-lookup"><span data-stu-id="582e6-187">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Risultato del comando sc query per diagtrack](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="582e6-189">Dovrai impostare l'avvio automatico del servizio se il START_TYPE **non** è impostato su **AUTO_START**.</span><span class="sxs-lookup"><span data-stu-id="582e6-189">You'll need to set the service to automatically start if the **START_TYPE** is not set to **AUTO_START**.</span></span>


<span data-ttu-id="582e6-190">**Usa la riga di comando per impostare il servizio dati di diagnostica di Windows 10 per l'avvio automatico:**</span><span class="sxs-lookup"><span data-stu-id="582e6-190">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="582e6-191">Aprire un prompt della riga di comando con privilegi elevati nell'endpoint:</span><span class="sxs-lookup"><span data-stu-id="582e6-191">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="582e6-192">Passare a **Start** e digitare **cmd**.</span><span class="sxs-lookup"><span data-stu-id="582e6-192">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="582e6-193">Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="582e6-193">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="582e6-194">Immettere il comando seguente e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="582e6-194">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="582e6-195">Viene visualizzato un messaggio di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="582e6-195">A success message is displayed.</span></span> <span data-ttu-id="582e6-196">Verificare la modifica immettendo il comando seguente e premere **INVIO:**</span><span class="sxs-lookup"><span data-stu-id="582e6-196">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="582e6-197">Connessione Internet</span><span class="sxs-lookup"><span data-stu-id="582e6-197">Internet connectivity</span></span>
<span data-ttu-id="582e6-198">La connettività Internet nei dispositivi è necessaria direttamente o tramite proxy.</span><span class="sxs-lookup"><span data-stu-id="582e6-198">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="582e6-199">Il sensore Defender for Endpoint può utilizzare una larghezza di banda media giornaliera di 5 MB per comunicare con il servizio cloud Defender for Endpoint e segnalare i dati informatici.</span><span class="sxs-lookup"><span data-stu-id="582e6-199">The Defender for Endpoint sensor can utilize a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="582e6-200">Le attività una-off come i caricamenti di file e la raccolta di pacchetti di analisi non sono incluse in questa larghezza di banda media giornaliera.</span><span class="sxs-lookup"><span data-stu-id="582e6-200">One-off activities such as file uploads and investigation package collection are not included in this daily average bandwidth.</span></span>

<span data-ttu-id="582e6-201">Per ulteriori informazioni sulle impostazioni di configurazione del proxy aggiuntive, vedere [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="582e6-201">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="582e6-202">Prima di eseguire l'onboard di dispositivi, è necessario che il servizio dati di diagnostica sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="582e6-202">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="582e6-203">Il servizio è abilitato per impostazione predefinita in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="582e6-203">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="582e6-204">Requisiti di configurazione di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="582e6-204">Microsoft Defender Antivirus configuration requirement</span></span>
<span data-ttu-id="582e6-205">L'agente Defender for Endpoint dipende dalla capacità di Microsoft Defender Antivirus di analizzare i file e fornire informazioni su di essi.</span><span class="sxs-lookup"><span data-stu-id="582e6-205">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="582e6-206">Configura gli aggiornamenti di Security Intelligence nel Defender per i dispositivi endpoint indipendentemente dal fatto che Microsoft Defender Antivirus sia l'antimalware attivo o meno.</span><span class="sxs-lookup"><span data-stu-id="582e6-206">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="582e6-207">Per altre informazioni, vedi [Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="582e6-207">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="582e6-208">Quando Microsoft Defender Antivirus non è l'antimalware attivo nell'organizzazione e usi il servizio Defender for Endpoint, Microsoft Defender Antivirus passa alla modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="582e6-208">When Microsoft Defender Antivirus is not the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="582e6-209">Se l'organizzazione ha disattivato Microsoft Defender Antivirus tramite criteri di gruppo o altri metodi, i dispositivi che sono stati onboarded devono essere esclusi da questo criterio di gruppo.</span><span class="sxs-lookup"><span data-stu-id="582e6-209">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="582e6-210">Se si stanno onboarding server e Microsoft Defender Antivirus non è l'antimalware attivo nei server, Microsoft Defender Antivirus dovrà essere configurato per passare alla modalità passiva o disinstallato.</span><span class="sxs-lookup"><span data-stu-id="582e6-210">If you are onboarding servers and Microsoft Defender Antivirus is not the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="582e6-211">La configurazione dipende dalla versione del server.</span><span class="sxs-lookup"><span data-stu-id="582e6-211">The configuration is dependent on the server version.</span></span> <span data-ttu-id="582e6-212">Per ulteriori informazioni, vedere [Compatibilità con Microsoft Defender Antivirus.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md)</span><span class="sxs-lookup"><span data-stu-id="582e6-212">For more information, see [Microsoft Defender Antivirus compatibility](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus-compatibility.md).</span></span>

> [!NOTE]
> <span data-ttu-id="582e6-213">I criteri di gruppo normali non si applicano a Protezione da manomissione e le modifiche alle impostazioni di Microsoft Defender Antivirus verranno ignorate quando Protezione da manomissione è impostata su Protezione da manomissione.</span><span class="sxs-lookup"><span data-stu-id="582e6-213">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="582e6-214">Il driver Microsoft Defender Antivirus Early Launch Antimalware (ELAM) è abilitato</span><span class="sxs-lookup"><span data-stu-id="582e6-214">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>
<span data-ttu-id="582e6-215">Se si esegue Microsoft Defender Antivirus come prodotto antimalware principale nei dispositivi, l'onboard dell'agente Defender for Endpoint verrà eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="582e6-215">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="582e6-216">Se stai eseguendo un client antimalware di terze parti e usi soluzioni di gestione dei dispositivi mobili o Microsoft Endpoint Manager (current branch), dovrai assicurarti che il driver ELAM di Microsoft Defender Antivirus sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="582e6-216">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure that the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="582e6-217">Per altre informazioni, vedi [Verificare che Microsoft Defender Antivirus non sia disabilitato dai criteri.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="582e6-217">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="582e6-218">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="582e6-218">Related topics</span></span>
- [<span data-ttu-id="582e6-219">Configurare Microsoft Defender per la distribuzione degli endpoint</span><span class="sxs-lookup"><span data-stu-id="582e6-219">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="582e6-220">Dispositivi onboard</span><span class="sxs-lookup"><span data-stu-id="582e6-220">Onboard devices</span></span>](onboard-configure.md)
