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
ms.openlocfilehash: 6607d5029e45c77754a431c87eb61cd281e013c1
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730727"
---
# <a name="minimum-requirements-for-microsoft-defender-for-endpoint"></a><span data-ttu-id="b24cc-104">Requisiti minimi per Microsoft Defender per Endpoint</span><span class="sxs-lookup"><span data-stu-id="b24cc-104">Minimum requirements for Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b24cc-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b24cc-105">**Applies to:**</span></span>

- [<span data-ttu-id="b24cc-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b24cc-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b24cc-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b24cc-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b24cc-108">Vuoi provare Microsoft Defender per Endpoint?</span><span class="sxs-lookup"><span data-stu-id="b24cc-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b24cc-109">Iscriversi per una versione di valutazione gratuita.</span><span class="sxs-lookup"><span data-stu-id="b24cc-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-minreqs-abovefoldlink)


<span data-ttu-id="b24cc-110">Esistono alcuni requisiti minimi per l'onboarding dei dispositivi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="b24cc-110">There are some minimum requirements for onboarding devices to the service.</span></span> <span data-ttu-id="b24cc-111">Informazioni sulle licenze, i requisiti hardware e software e altre impostazioni di configurazione per eseguire l'onboardment dei dispositivi nel servizio.</span><span class="sxs-lookup"><span data-stu-id="b24cc-111">Learn about the licensing, hardware and software requirements, and other configuration settings to onboard devices to the service.</span></span>

> [!TIP]
> - <span data-ttu-id="b24cc-112">Informazioni sui miglioramenti più recenti in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span><span class="sxs-lookup"><span data-stu-id="b24cc-112">Learn about the latest enhancements in Defender for Endpoint: [Defender for Endpoint Tech Community](https://techcommunity.microsoft.com/t5/Windows-Defender-Advanced-Threat/ct-p/WindowsDefenderAdvanced).</span></span>
> - <span data-ttu-id="b24cc-113">Defender for Endpoint ha dimostrato le funzionalità di ottica e rilevamento leader del settore nella recente valutazione MITRE.</span><span class="sxs-lookup"><span data-stu-id="b24cc-113">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="b24cc-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="b24cc-114">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="b24cc-115">Requisiti di licenza</span><span class="sxs-lookup"><span data-stu-id="b24cc-115">Licensing requirements</span></span>

<span data-ttu-id="b24cc-116">Microsoft Defender for Endpoint richiede una delle seguenti offerte di contratti multilicenza Microsoft:</span><span class="sxs-lookup"><span data-stu-id="b24cc-116">Microsoft Defender for Endpoint requires one of the following Microsoft volume licensing offers:</span></span>

- <span data-ttu-id="b24cc-117">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="b24cc-117">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="b24cc-118">Windows 10 Education A5</span><span class="sxs-lookup"><span data-stu-id="b24cc-118">Windows 10 Education A5</span></span>
- <span data-ttu-id="b24cc-119">Microsoft 365 E5 (M365 E5) che include Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="b24cc-119">Microsoft 365 E5 (M365 E5) which includes Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="b24cc-120">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="b24cc-120">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="b24cc-121">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="b24cc-121">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="b24cc-122">Microsoft 365 A5 Security</span><span class="sxs-lookup"><span data-stu-id="b24cc-122">Microsoft 365 A5 Security</span></span>
- <span data-ttu-id="b24cc-123">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b24cc-123">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="b24cc-124">Gli utenti con licenza idonea possono usare Microsoft Defender per Endpoint su un massimo di cinque dispositivi simultanei.</span><span class="sxs-lookup"><span data-stu-id="b24cc-124">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="b24cc-125">Microsoft Defender for Endpoint è disponibile anche per l'acquisto da un Cloud Solution Provider (CSP).</span><span class="sxs-lookup"><span data-stu-id="b24cc-125">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span>
> <span data-ttu-id="b24cc-126">Le macchine virtuali RDSH non richiedono una licenza di Defender for Endpoint separata.</span><span class="sxs-lookup"><span data-stu-id="b24cc-126">RDSH VMs do not require a separate Defender for Endpoint license.</span></span>

<span data-ttu-id="b24cc-127">Microsoft Defender for Endpoint per i server richiede una delle opzioni di licenza seguenti:</span><span class="sxs-lookup"><span data-stu-id="b24cc-127">Microsoft Defender for Endpoint for servers requires one of the following licensing options:</span></span>

- [<span data-ttu-id="b24cc-128">Centro sicurezza di Azure con Azure Defender abilitato</span><span class="sxs-lookup"><span data-stu-id="b24cc-128">Azure Security Center with Azure Defender enabled</span></span>](https://docs.microsoft.com/azure/security-center/security-center-pricing)
- <span data-ttu-id="b24cc-129">Microsoft Defender for Endpoint for Server (uno per server coperto)</span><span class="sxs-lookup"><span data-stu-id="b24cc-129">Microsoft Defender for Endpoint for Server (one per covered server)</span></span>

> [!NOTE]
> <span data-ttu-id="b24cc-130">I clienti possono acquisire licenze server (una per server OSE)) per Microsoft Defender for Endpoint for Servers se hanno un minimo combinato di 50 licenze per una o più delle licenze utente seguenti:</span><span class="sxs-lookup"><span data-stu-id="b24cc-130">Customers may acquire server licenses (one per covered server Operating System Environment (OSE)) for Microsoft Defender for Endpoint for Servers if they have a combined minimum of 50 licenses for one or more of the following user licenses:</span></span>
>
> * <span data-ttu-id="b24cc-131">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b24cc-131">Microsoft Defender for Endpoint</span></span>
> * <span data-ttu-id="b24cc-132">Windows E5/A5</span><span class="sxs-lookup"><span data-stu-id="b24cc-132">Windows E5/A5</span></span>
> * <span data-ttu-id="b24cc-133">Microsoft 365 E5/A5</span><span class="sxs-lookup"><span data-stu-id="b24cc-133">Microsoft 365 E5/A5</span></span>
> * <span data-ttu-id="b24cc-134">Microsoft 365 E5/A5 Security</span><span class="sxs-lookup"><span data-stu-id="b24cc-134">Microsoft 365 E5/A5 Security</span></span>

<span data-ttu-id="b24cc-135">Per informazioni dettagliate sulle licenze, vedere il sito [condizioni](https://www.microsoft.com/licensing/terms/) del prodotto e collaborare con il team dell'account per ulteriori informazioni sui termini e le condizioni.</span><span class="sxs-lookup"><span data-stu-id="b24cc-135">For detailed licensing information, see the [Product Terms site](https://www.microsoft.com/licensing/terms/) and work with your account team to learn more about the terms and conditions.</span></span>

<span data-ttu-id="b24cc-136">Per ulteriori informazioni sulla matrice di funzionalità nelle Windows 10, vedere [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span><span class="sxs-lookup"><span data-stu-id="b24cc-136">For more information on the array of features in Windows 10 editions, see [Compare Windows 10 editions](https://www.microsoft.com/windowsforbusiness/compare).</span></span>

<span data-ttu-id="b24cc-137">Per una tabella di confronto dettagliata di Windows 10 edizione commerciale, vedere il [PDF di confronto](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span><span class="sxs-lookup"><span data-stu-id="b24cc-137">For a detailed comparison table of Windows 10 commercial edition comparison, see the [comparison PDF](https://wfbdevicemanagementprod.blob.core.windows.net/windowsforbusiness/Windows10_CommercialEdition_Comparison.pdf).</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="b24cc-138">Requisiti per il browser</span><span class="sxs-lookup"><span data-stu-id="b24cc-138">Browser requirements</span></span>

<span data-ttu-id="b24cc-139">L'accesso a Defender for Endpoint viene eseguito tramite un browser, che supporta i browser seguenti:</span><span class="sxs-lookup"><span data-stu-id="b24cc-139">Access to Defender for Endpoint is done through a browser, supporting the following browsers:</span></span>

- <span data-ttu-id="b24cc-140">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="b24cc-140">Microsoft Edge</span></span>
- <span data-ttu-id="b24cc-141">Google Chrome</span><span class="sxs-lookup"><span data-stu-id="b24cc-141">Google Chrome</span></span>

> [!NOTE]
> <span data-ttu-id="b24cc-142">Mentre altri browser potrebbero funzionare, i browser menzionati sono quelli supportati.</span><span class="sxs-lookup"><span data-stu-id="b24cc-142">While other browsers might work, the mentioned browsers are the ones supported.</span></span>


## <a name="hardware-and-software-requirements"></a><span data-ttu-id="b24cc-143">Requisiti hardware e software</span><span class="sxs-lookup"><span data-stu-id="b24cc-143">Hardware and software requirements</span></span>

### <a name="supported-windows-versions"></a><span data-ttu-id="b24cc-144">Versioni Windows supportate</span><span class="sxs-lookup"><span data-stu-id="b24cc-144">Supported Windows versions</span></span>

- <span data-ttu-id="b24cc-145">Windows 7 SP1 Enterprise ([Richiede ESU per il supporto](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq). )</span><span class="sxs-lookup"><span data-stu-id="b24cc-145">Windows 7 SP1 Enterprise ([Requires ESU for support](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="b24cc-146">Windows 7 SP1 Pro ([Richiede ESU per il supporto](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span><span class="sxs-lookup"><span data-stu-id="b24cc-146">Windows 7 SP1 Pro ([Requires ESU for support](/troubleshoot/windows-client/windows-7-eos-faq/windows-7-extended-security-updates-faq).)</span></span>
- <span data-ttu-id="b24cc-147">Windows 8.1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b24cc-147">Windows 8.1 Enterprise</span></span>
- <span data-ttu-id="b24cc-148">Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="b24cc-148">Windows 8.1 Pro</span></span>
- <span data-ttu-id="b24cc-149">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b24cc-149">Windows 10 Enterprise</span></span>
- [<span data-ttu-id="b24cc-150">Windows 10 Enterprise LTSC 2016 (o versione successiva)</span><span class="sxs-lookup"><span data-stu-id="b24cc-150">Windows 10 Enterprise LTSC 2016 (or later)</span></span>](/windows/whats-new/ltsc/)
- <span data-ttu-id="b24cc-151">Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="b24cc-151">Windows 10 Education</span></span>
- <span data-ttu-id="b24cc-152">Windows 10 Pro</span><span class="sxs-lookup"><span data-stu-id="b24cc-152">Windows 10 Pro</span></span>
- <span data-ttu-id="b24cc-153">Windows 10 Pro Education</span><span class="sxs-lookup"><span data-stu-id="b24cc-153">Windows 10 Pro Education</span></span>
- <span data-ttu-id="b24cc-154">Windows server</span><span class="sxs-lookup"><span data-stu-id="b24cc-154">Windows server</span></span>
  - <span data-ttu-id="b24cc-155">Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="b24cc-155">Windows Server 2008 R2 SP1</span></span>
  - <span data-ttu-id="b24cc-156">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="b24cc-156">Windows Server 2012 R2</span></span>
  - <span data-ttu-id="b24cc-157">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="b24cc-157">Windows Server 2016</span></span>
  - <span data-ttu-id="b24cc-158">Windows Server, versione 1803 o successiva</span><span class="sxs-lookup"><span data-stu-id="b24cc-158">Windows Server, version 1803 or later</span></span>
  - <span data-ttu-id="b24cc-159">Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="b24cc-159">Windows Server 2019</span></span>
- <span data-ttu-id="b24cc-160">Desktop virtuale Windows</span><span class="sxs-lookup"><span data-stu-id="b24cc-160">Windows Virtual Desktop</span></span>

<span data-ttu-id="b24cc-161">I dispositivi nella rete devono eseguire una di queste edizioni.</span><span class="sxs-lookup"><span data-stu-id="b24cc-161">Devices on your network must be running one of these editions.</span></span>

<span data-ttu-id="b24cc-162">I requisiti hardware per Defender per Endpoint nei dispositivi sono gli stessi per le edizioni supportate.</span><span class="sxs-lookup"><span data-stu-id="b24cc-162">The hardware requirements for Defender for Endpoint on devices are the same for the supported editions.</span></span>

> [!NOTE]
> <span data-ttu-id="b24cc-163">I computer che eseguono versioni per dispositivi mobili di Windows (ad esempio Windows CE e Windows 10 Mobile) non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="b24cc-163">Machines running mobile versions of Windows (such as Windows CE and Windows 10 Mobile) aren't supported.</span></span>
>
> <span data-ttu-id="b24cc-164">Le macchine virtuali che Windows 10 Enterprise 2016 LTSB possono riscontrare problemi di prestazioni se eseguite su piattaforme di virtualizzazione non Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b24cc-164">Virtual Machines running Windows 10 Enterprise 2016 LTSB may encounter performance issues if run on non-Microsoft virtualization platforms.</span></span>
>
> <span data-ttu-id="b24cc-165">Per gli ambienti virtuali, è consigliabile usare Windows 10 Enterprise LTSC 2019 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="b24cc-165">For virtual environments, we recommend using Windows 10 Enterprise LTSC 2019 or later.</span></span>


### <a name="other-supported-operating-systems"></a><span data-ttu-id="b24cc-166">Altri sistemi operativi supportati</span><span class="sxs-lookup"><span data-stu-id="b24cc-166">Other supported operating systems</span></span>

- [<span data-ttu-id="b24cc-167">Android</span><span class="sxs-lookup"><span data-stu-id="b24cc-167">Android</span></span>](microsoft-defender-endpoint-android.md)
- [<span data-ttu-id="b24cc-168">iOS</span><span class="sxs-lookup"><span data-stu-id="b24cc-168">iOS</span></span>](microsoft-defender-endpoint-ios.md)
- [<span data-ttu-id="b24cc-169">Linux</span><span class="sxs-lookup"><span data-stu-id="b24cc-169">Linux</span></span>](microsoft-defender-endpoint-linux.md)
- [<span data-ttu-id="b24cc-170">macOS</span><span class="sxs-lookup"><span data-stu-id="b24cc-170">macOS</span></span>](microsoft-defender-endpoint-mac.md)

> [!NOTE]
> <span data-ttu-id="b24cc-171">Dovrai verificare che le distribuzioni Linux e le versioni di Android, iOS e macOS siano compatibili con Defender for Endpoint per il funzionamento dell'integrazione.</span><span class="sxs-lookup"><span data-stu-id="b24cc-171">You'll need to confirm the Linux distributions and versions of Android, iOS, and macOS are compatible with Defender for Endpoint for the integration to work.</span></span>



### <a name="network-and-data-storage-and-configuration-requirements"></a><span data-ttu-id="b24cc-172">Requisiti di archiviazione e configurazione di rete e dati</span><span class="sxs-lookup"><span data-stu-id="b24cc-172">Network and data storage and configuration requirements</span></span>

<span data-ttu-id="b24cc-173">Quando esegui l'onboarding guidato per la prima volta, devi scegliere dove archiviare le informazioni relative a Microsoft Defender for Endpoint: nell'Unione Europea, nel Regno Unito o nel datacenter degli Stati Uniti.</span><span class="sxs-lookup"><span data-stu-id="b24cc-173">When you run the onboarding wizard for the first time, you must choose where your Microsoft Defender for Endpoint-related information is stored: in the European Union, the United Kingdom, or the United States datacenter.</span></span>

> [!NOTE]
> - <span data-ttu-id="b24cc-174">Non è possibile modificare il percorso di archiviazione dei dati dopo la prima installazione.</span><span class="sxs-lookup"><span data-stu-id="b24cc-174">You cannot change your data storage location after the first-time setup.</span></span>
> - <span data-ttu-id="b24cc-175">Per altre [informazioni su dove](data-storage-privacy.md) e come Microsoft archivia i dati, consulta Microsoft Defender per l'archiviazione e la privacy dei dati degli endpoint.</span><span class="sxs-lookup"><span data-stu-id="b24cc-175">Review the [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md) for more information on where and how Microsoft stores your data.</span></span>


### <a name="diagnostic-data-settings"></a><span data-ttu-id="b24cc-176">Impostazioni dei dati di diagnostica</span><span class="sxs-lookup"><span data-stu-id="b24cc-176">Diagnostic data settings</span></span>

> [!NOTE]
> <span data-ttu-id="b24cc-177">Microsoft Defender for Endpoint non richiede alcun livello di diagnostica specifico purché sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="b24cc-177">Microsoft Defender for Endpoint doesn't require any specific diagnostic level as long as it's enabled.</span></span>

<span data-ttu-id="b24cc-178">Verificare che il servizio dati di diagnostica sia abilitato in tutti i dispositivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="b24cc-178">Make sure that the diagnostic data service is enabled on all the devices in your organization.</span></span>
<span data-ttu-id="b24cc-179">Per impostazione predefinita, questo servizio è abilitato.</span><span class="sxs-lookup"><span data-stu-id="b24cc-179">By default, this service is enabled.</span></span> <span data-ttu-id="b24cc-180">È consigliabile verificare che i dati dei sensori siano da essi.</span><span class="sxs-lookup"><span data-stu-id="b24cc-180">It's good practice to check to ensure that you'll get sensor data from them.</span></span>

<span data-ttu-id="b24cc-181">**Utilizzare la riga di comando per controllare il tipo** Windows 10 di avvio del servizio dati di diagnostica:</span><span class="sxs-lookup"><span data-stu-id="b24cc-181">**Use the command line to check the Windows 10 diagnostic data service startup type**:</span></span>

1. <span data-ttu-id="b24cc-182">Apri un prompt della riga di comando con privilegi elevati nel dispositivo:</span><span class="sxs-lookup"><span data-stu-id="b24cc-182">Open an elevated command-line prompt on the device:</span></span>

   1.  <span data-ttu-id="b24cc-183">Passare a **Start** e digitare **cmd**.</span><span class="sxs-lookup"><span data-stu-id="b24cc-183">Go to **Start** and type **cmd**.</span></span>

   1.  <span data-ttu-id="b24cc-184">Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="b24cc-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="b24cc-185">Immettere il comando seguente e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="b24cc-185">Enter the following command, and press **Enter**:</span></span>

   ```console
   sc qc diagtrack
   ```

   <span data-ttu-id="b24cc-186">Se il servizio è abilitato, il risultato dovrebbe essere simile allo screenshot seguente:</span><span class="sxs-lookup"><span data-stu-id="b24cc-186">If the service is enabled, then the result should look like the following screenshot:</span></span>

   ![Risultato del comando sc query per diagtrack](images/windefatp-sc-qc-diagtrack.png)


<span data-ttu-id="b24cc-188">Dovrai impostare l'avvio automatico del servizio  se il START_TYPE non è impostato su **AUTO_START**.</span><span class="sxs-lookup"><span data-stu-id="b24cc-188">You'll need to set the service to automatically start if the **START_TYPE** isn't set to **AUTO_START**.</span></span>


<span data-ttu-id="b24cc-189">**Utilizzare la riga di comando per impostare l'avvio Windows 10 servizio dati di diagnostica:**</span><span class="sxs-lookup"><span data-stu-id="b24cc-189">**Use the command line to set the Windows 10 diagnostic data service to automatically start:**</span></span>

1.  <span data-ttu-id="b24cc-190">Aprire un prompt della riga di comando con privilegi elevati nell'endpoint:</span><span class="sxs-lookup"><span data-stu-id="b24cc-190">Open an elevated command-line prompt on the endpoint:</span></span>

    1. <span data-ttu-id="b24cc-191">Passare a **Start** e digitare **cmd**.</span><span class="sxs-lookup"><span data-stu-id="b24cc-191">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="b24cc-192">Fare clic con il pulsante destro del mouse su **Prompt dei comandi** e scegliere **Esegui come amministratore**.</span><span class="sxs-lookup"><span data-stu-id="b24cc-192">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2.  <span data-ttu-id="b24cc-193">Immettere il comando seguente e premere **INVIO**:</span><span class="sxs-lookup"><span data-stu-id="b24cc-193">Enter the following command, and press **Enter**:</span></span>

    ```console
    sc config diagtrack start=auto
    ```

3.  <span data-ttu-id="b24cc-194">Viene visualizzato un messaggio di esito positivo.</span><span class="sxs-lookup"><span data-stu-id="b24cc-194">A success message is displayed.</span></span> <span data-ttu-id="b24cc-195">Verificare la modifica immettendo il comando seguente e premere **INVIO:**</span><span class="sxs-lookup"><span data-stu-id="b24cc-195">Verify the change by entering the following command, and press **Enter**:</span></span>

    ```console
    sc qc diagtrack
    ```


#### <a name="internet-connectivity"></a><span data-ttu-id="b24cc-196">Connessione Internet</span><span class="sxs-lookup"><span data-stu-id="b24cc-196">Internet connectivity</span></span>

<span data-ttu-id="b24cc-197">La connettività Internet nei dispositivi è necessaria direttamente o tramite proxy.</span><span class="sxs-lookup"><span data-stu-id="b24cc-197">Internet connectivity on devices is required either directly or through proxy.</span></span>

<span data-ttu-id="b24cc-198">Il sensore Defender for Endpoint può usare una larghezza di banda media giornaliera di 5 MB per comunicare con il servizio cloud Defender for Endpoint e segnalare i dati informatici.</span><span class="sxs-lookup"><span data-stu-id="b24cc-198">The Defender for Endpoint sensor can use a daily average bandwidth of 5 MB to communicate with the Defender for Endpoint cloud service and report cyber data.</span></span> <span data-ttu-id="b24cc-199">Le attività una-off come i caricamenti di file e la raccolta di pacchetti di analisi non sono incluse in questa larghezza di banda media giornaliera.</span><span class="sxs-lookup"><span data-stu-id="b24cc-199">One-off activities such as file uploads and investigation package collection aren't included in this daily average bandwidth.</span></span>

<span data-ttu-id="b24cc-200">Per ulteriori informazioni sulle impostazioni di configurazione del proxy aggiuntive, vedere [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span><span class="sxs-lookup"><span data-stu-id="b24cc-200">For more information on additional proxy configuration settings, see [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

<span data-ttu-id="b24cc-201">Prima di eseguire l'onboard di dispositivi, è necessario che il servizio dati di diagnostica sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="b24cc-201">Before you onboard devices, the diagnostic data service must be enabled.</span></span> <span data-ttu-id="b24cc-202">Il servizio è abilitato per impostazione predefinita in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b24cc-202">The service is enabled by default in Windows 10.</span></span>


## <a name="microsoft-defender-antivirus-configuration-requirement"></a><span data-ttu-id="b24cc-203">Antivirus Microsoft Defender di configurazione</span><span class="sxs-lookup"><span data-stu-id="b24cc-203">Microsoft Defender Antivirus configuration requirement</span></span>

<span data-ttu-id="b24cc-204">L'agente Defender for Endpoint dipende dalla capacità Antivirus Microsoft Defender di analizzare i file e fornire informazioni su di essi.</span><span class="sxs-lookup"><span data-stu-id="b24cc-204">The Defender for Endpoint agent depends on the ability of Microsoft Defender Antivirus to scan files and provide information about them.</span></span>

<span data-ttu-id="b24cc-205">Configura gli aggiornamenti di Security intelligence nel Defender per i dispositivi endpoint Antivirus Microsoft Defender è l'antimalware attivo o meno.</span><span class="sxs-lookup"><span data-stu-id="b24cc-205">Configure Security intelligence updates on the Defender for Endpoint devices whether Microsoft Defender Antivirus is the active antimalware or not.</span></span> <span data-ttu-id="b24cc-206">Per ulteriori informazioni, vedere [Manage Antivirus Microsoft Defender updates and apply baselines](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="b24cc-206">For more information, see [Manage Microsoft Defender Antivirus updates and apply baselines](/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="b24cc-207">Quando Antivirus Microsoft Defender non è l'antimalware attivo nell'organizzazione e usi defender per il servizio endpoint, Antivirus Microsoft Defender attiva la modalità passiva.</span><span class="sxs-lookup"><span data-stu-id="b24cc-207">When Microsoft Defender Antivirus isn't the active antimalware in your organization and you use the Defender for Endpoint service, Microsoft Defender Antivirus goes on passive mode.</span></span>

<span data-ttu-id="b24cc-208">Se l'organizzazione ha disattivato Antivirus Microsoft Defender tramite Criteri di gruppo o altri metodi, i dispositivi di cui è stato fatto l'onboarded devono essere esclusi da questi criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="b24cc-208">If your organization has turned off Microsoft Defender Antivirus through group policy or other methods, devices that are onboarded must be excluded from this group policy.</span></span>

<span data-ttu-id="b24cc-209">Se si stanno onboarding dei server e Antivirus Microsoft Defender non è l'antimalware attivo nei server, Antivirus Microsoft Defender dovrà essere configurato per passare alla modalità passiva o disinstallato.</span><span class="sxs-lookup"><span data-stu-id="b24cc-209">If you're onboarding servers and Microsoft Defender Antivirus isn't the active antimalware on your servers, Microsoft Defender Antivirus will either need to be configured to go on passive mode or uninstalled.</span></span> <span data-ttu-id="b24cc-210">La configurazione dipende dalla versione del server.</span><span class="sxs-lookup"><span data-stu-id="b24cc-210">The configuration is dependent on the server version.</span></span> <span data-ttu-id="b24cc-211">Per ulteriori informazioni, vedere [Antivirus Microsoft Defender compatibilità.](/security/defender-endpoint/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="b24cc-211">For more information, see [Microsoft Defender Antivirus compatibility](/security/defender-endpoint/microsoft-defender-antivirus-compatibility).</span></span>

> [!NOTE]
> <span data-ttu-id="b24cc-212">I criteri di gruppo normali non si applicano a Protezione da manomissione e le modifiche alle impostazioni Antivirus Microsoft Defender verranno ignorate quando Protezione manomissione è impostata su Protezione da manomissione.</span><span class="sxs-lookup"><span data-stu-id="b24cc-212">Your regular group policy doesn't apply to Tamper Protection, and changes to Microsoft Defender Antivirus settings will be ignored when Tamper Protection is on.</span></span>


## <a name="microsoft-defender-antivirus-early-launch-antimalware-elam-driver-is-enabled"></a><span data-ttu-id="b24cc-213">Antivirus Microsoft Defender Il driver antimalware ad avvio anticipato (ELAM) è abilitato</span><span class="sxs-lookup"><span data-stu-id="b24cc-213">Microsoft Defender Antivirus Early Launch Antimalware (ELAM) driver is enabled</span></span>

<span data-ttu-id="b24cc-214">Se stai eseguendo Antivirus Microsoft Defender come prodotto antimalware principale nei dispositivi, l'onboard dell'agente Defender for Endpoint verrà eseguito correttamente.</span><span class="sxs-lookup"><span data-stu-id="b24cc-214">If you're running Microsoft Defender Antivirus as the primary antimalware product on your devices, the Defender for Endpoint agent will successfully onboard.</span></span>

<span data-ttu-id="b24cc-215">Se stai eseguendo un client antimalware di terze parti e usi soluzioni di gestione dei dispositivi mobili o Microsoft Endpoint Manager (ramo corrente), dovrai assicurarti che il driver ELAM Antivirus Microsoft Defender sia abilitato.</span><span class="sxs-lookup"><span data-stu-id="b24cc-215">If you're running a third-party antimalware client and use Mobile Device Management solutions or Microsoft Endpoint Manager (current branch), you'll need to ensure the Microsoft Defender Antivirus ELAM driver is enabled.</span></span> <span data-ttu-id="b24cc-216">Per ulteriori informazioni, vedere [Ensure that Antivirus Microsoft Defender is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span><span class="sxs-lookup"><span data-stu-id="b24cc-216">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>


## <a name="related-topics"></a><span data-ttu-id="b24cc-217">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b24cc-217">Related topics</span></span>

- [<span data-ttu-id="b24cc-218">Configurare Microsoft Defender per la distribuzione degli endpoint</span><span class="sxs-lookup"><span data-stu-id="b24cc-218">Set up Microsoft Defender for Endpoint deployment</span></span>](production-deployment.md)
- [<span data-ttu-id="b24cc-219">Eseguire l'onboarding dei dispositivi</span><span class="sxs-lookup"><span data-stu-id="b24cc-219">Onboard devices</span></span>](onboard-configure.md)
