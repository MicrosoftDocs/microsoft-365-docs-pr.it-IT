---
title: Microsoft Defender Offline in Windows 10
description: Puoi usare Microsoft Defender Offline direttamente dall'app Windows Defender Antivirus app. È inoltre possibile gestire la modalità di distribuzione nella rete.
keywords: analisi, defender, offline
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a25a2ec513cd7c25f9f6ddf3d5e328928837bf2d
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275145"
---
# <a name="run-and-review-the-results-of-a-microsoft-defender-offline-scan"></a><span data-ttu-id="53079-105">Eseguire e rivedere i risultati di un’analisi Microsoft Defender Offline</span><span class="sxs-lookup"><span data-stu-id="53079-105">Run and review the results of a Microsoft Defender Offline scan</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="53079-106">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="53079-106">**Applies to:**</span></span>

- [<span data-ttu-id="53079-107">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="53079-107">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="53079-108">Microsoft Defender Offline è uno strumento di analisi antimalware che consente di avviare ed eseguire un'analisi da un ambiente attendibile.</span><span class="sxs-lookup"><span data-stu-id="53079-108">Microsoft Defender Offline is an antimalware scanning tool that lets you boot and run a scan from a trusted environment.</span></span> <span data-ttu-id="53079-109">L'analisi viene eseguita dall'esterno del normale kernel di Windows in modo che possa essere mirato al malware che tenta di ignorare la shell di Windows, ad esempio virus e rootkit che infettano o sovrascrivono il record di avvio master (MBR).</span><span class="sxs-lookup"><span data-stu-id="53079-109">The scan runs from outside the normal Windows kernel so it can target malware that attempts to bypass the Windows shell, such as viruses and rootkits that infect or overwrite the master boot record (MBR).</span></span>

<span data-ttu-id="53079-110">È possibile utilizzare Microsoft Defender Offline se si sospetta un'infezione da malware o si desidera confermare una pulizia completa dell'endpoint dopo un'epidemia di malware.</span><span class="sxs-lookup"><span data-stu-id="53079-110">You can use Microsoft Defender Offline if you suspect a malware infection, or you want to confirm a thorough clean of the endpoint after a malware outbreak.</span></span>

<span data-ttu-id="53079-111">In Windows 10, Microsoft Defender Offline può essere eseguito con un solo clic direttamente [dall'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="53079-111">In Windows 10, Microsoft Defender Offline can be run with one click directly from the [Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> <span data-ttu-id="53079-112">Nelle versioni precedenti di Windows, un utente doveva installare Microsoft Defender Offline su supporti di avvio, riavviare l'endpoint e caricare il supporto di avvio.</span><span class="sxs-lookup"><span data-stu-id="53079-112">In previous versions of Windows, a user had to install Microsoft Defender Offline to bootable media, restart the endpoint, and load the bootable media.</span></span>

## <a name="prerequisites-and-requirements"></a><span data-ttu-id="53079-113">prerequisiti e requisiti</span><span class="sxs-lookup"><span data-stu-id="53079-113">prerequisites and requirements</span></span>

<span data-ttu-id="53079-114">Microsoft Defender Offline in Windows 10 ha gli stessi requisiti hardware di Windows 10.</span><span class="sxs-lookup"><span data-stu-id="53079-114">Microsoft Defender Offline in Windows 10 has the same hardware requirements as Windows 10.</span></span> 

<span data-ttu-id="53079-115">Per ulteriori informazioni sui Windows 10, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="53079-115">For more information about Windows 10 requirements, see the following topics:</span></span>

- [<span data-ttu-id="53079-116">Requisiti hardware minimi</span><span class="sxs-lookup"><span data-stu-id="53079-116">Minimum hardware requirements</span></span>](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)

- [<span data-ttu-id="53079-117">Linee guida per i componenti hardware</span><span class="sxs-lookup"><span data-stu-id="53079-117">Hardware component guidelines</span></span>](/windows-hardware/design/component-guidelines/components)

> [!NOTE]
> <span data-ttu-id="53079-118">Microsoft Defender Offline non è supportato nei computer con processori ARM o Windows Server Stock Keeping Units.</span><span class="sxs-lookup"><span data-stu-id="53079-118">Microsoft Defender Offline is not supported on machines with ARM processors, or on Windows Server Stock Keeping Units.</span></span>

<span data-ttu-id="53079-119">Per eseguire Microsoft Defender Offline dall'endpoint, l'utente deve essere connesso con privilegi di amministratore.</span><span class="sxs-lookup"><span data-stu-id="53079-119">To run Microsoft Defender Offline from the endpoint, the user must be logged in with administrator privileges.</span></span>
 
## <a name="microsoft-defender-offline-updates"></a><span data-ttu-id="53079-120">Microsoft Defender Offline aggiornamenti</span><span class="sxs-lookup"><span data-stu-id="53079-120">Microsoft Defender Offline updates</span></span>

<span data-ttu-id="53079-121">Microsoft Defender Offline vengono utilizzati gli aggiornamenti di protezione più recenti disponibili nell'endpoint. viene aggiornato ogni volta Windows Defender Antivirus viene aggiornato.</span><span class="sxs-lookup"><span data-stu-id="53079-121">Microsoft Defender Offline uses the most recent protection updates available on the endpoint; it's updated whenever Windows Defender Antivirus is updated.</span></span> 

> [!NOTE]
> <span data-ttu-id="53079-122">Prima di eseguire un'analisi offline, è consigliabile tentare di aggiornare la protezione di Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="53079-122">Before running an offline scan, you should attempt to update Microsoft Defender AV protection.</span></span> <span data-ttu-id="53079-123">È possibile forzare un aggiornamento con Criteri di gruppo o, in genere, distribuire gli aggiornamenti agli endpoint oppure scaricare e installare manualmente gli aggiornamenti di protezione più recenti [dal Microsoft Malware Protection Center](https://www.microsoft.com/security/portal/definitions/adl.aspx).</span><span class="sxs-lookup"><span data-stu-id="53079-123">You can either force an update with Group Policy or however you normally deploy updates to endpoints, or you can manually download and install the latest protection updates from the [Microsoft Malware Protection Center](https://www.microsoft.com/security/portal/definitions/adl.aspx).</span></span>

<span data-ttu-id="53079-124">Per ulteriori [informazioni, vedere l'argomento Manage Antivirus Microsoft Defender Security intelligence updates.](manage-protection-updates-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="53079-124">See the [Manage Microsoft Defender Antivirus Security intelligence  updates](manage-protection-updates-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="usage-scenarios"></a><span data-ttu-id="53079-125">Scenari di utilizzo</span><span class="sxs-lookup"><span data-stu-id="53079-125">Usage scenarios</span></span>

<span data-ttu-id="53079-126">In Windows 10 versione 1607, è possibile forzare manualmente un'analisi offline.</span><span class="sxs-lookup"><span data-stu-id="53079-126">In Windows 10, version 1607, you can manually force an offline scan.</span></span> <span data-ttu-id="53079-127">In alternativa, se Windows Defender che Microsoft Defender Offline necessario eseguire, verrà richiesto all'utente nell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="53079-127">Alternatively, if Windows Defender determines that Microsoft Defender Offline needs to run, it will prompt the user on the endpoint.</span></span> 

<span data-ttu-id="53079-128">La necessità di eseguire un'analisi offline verrà inoltre rivelata Microsoft Endpoint Manager se si usa per gestire gli endpoint.</span><span class="sxs-lookup"><span data-stu-id="53079-128">The need to perform an offline scan will also be revealed in Microsoft Endpoint Manager if you're using it to manage your endpoints.</span></span>

<span data-ttu-id="53079-129">Il prompt può verificarsi tramite una notifica, simile alla seguente:</span><span class="sxs-lookup"><span data-stu-id="53079-129">The prompt can occur via a notification, similar to the following:</span></span>

![Windows notifica che mostra il requisito per l'esecuzione Microsoft Defender Offline](images/defender/notification.png)

<span data-ttu-id="53079-131">L'utente riceverà anche una notifica all'interno del client Windows Defender client.</span><span class="sxs-lookup"><span data-stu-id="53079-131">The user will also be notified within the Windows Defender client.</span></span>

<span data-ttu-id="53079-132">In Configuration Manager è possibile identificare lo stato degli endpoint accedendo a Monitoraggio > Panoramica > Sicurezza > Endpoint Protection stato > System Center Endpoint Protection **Stato**.</span><span class="sxs-lookup"><span data-stu-id="53079-132">In Configuration Manager, you can identify the status of endpoints by navigating to **Monitoring > Overview > Security > Endpoint Protection Status > System Center Endpoint Protection Status**.</span></span> 

<span data-ttu-id="53079-133">Microsoft Defender Offline analisi sono indicate in **Stato** correzione malware come **Analisi offline necessaria.**</span><span class="sxs-lookup"><span data-stu-id="53079-133">Microsoft Defender Offline scans are indicated under **Malware remediation status** as **Offline scan required**.</span></span>

![Microsoft Endpoint Manager che indica che è necessaria Microsoft Defender Offline'analisi](images/defender/sccm-wdo.png)

## <a name="configure-notifications"></a><span data-ttu-id="53079-135">Configurare le notifiche</span><span class="sxs-lookup"><span data-stu-id="53079-135">Configure notifications</span></span>

<span data-ttu-id="53079-136">Microsoft Defender Offline le notifiche vengono configurate nella stessa impostazione dei criteri di altre notifiche di Microsoft Defender AV.</span><span class="sxs-lookup"><span data-stu-id="53079-136">Microsoft Defender Offline notifications are configured in the same policy setting as other Microsoft Defender AV notifications.</span></span>

<span data-ttu-id="53079-137">Per altre informazioni sulle notifiche in Windows Defender, vedi l'argomento [Configurare le notifiche visualizzate negli endpoint.](configure-notifications-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="53079-137">For more information about notifications in Windows Defender, see the [Configure the notifications that appear on endpoints](configure-notifications-microsoft-defender-antivirus.md) topic.</span></span>

## <a name="run-a-scan"></a><span data-ttu-id="53079-138">Eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="53079-138">Run a scan</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="53079-139">Prima di utilizzare Microsoft Defender Offline, assicurarsi di salvare i file e arrestare i programmi in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="53079-139">Before you use Microsoft Defender Offline, make sure you save any files and shut down running programs.</span></span> <span data-ttu-id="53079-140">L Microsoft Defender Offline intervaio richiede circa 15 minuti.</span><span class="sxs-lookup"><span data-stu-id="53079-140">The Microsoft Defender Offline scan takes about 15 minutes to run.</span></span> <span data-ttu-id="53079-141">L'endpoint verrà riavviato al termine dell'analisi.</span><span class="sxs-lookup"><span data-stu-id="53079-141">It will restart the endpoint when the scan is complete.</span></span> <span data-ttu-id="53079-142">L'analisi viene eseguita al di fuori dell'ambiente Windows normale.</span><span class="sxs-lookup"><span data-stu-id="53079-142">The scan is performed outside of the usual Windows operating environment.</span></span> <span data-ttu-id="53079-143">L'interfaccia utente sarà diversa da una normale analisi eseguita da Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="53079-143">The user interface will appear different to a normal scan performed by Windows Defender.</span></span> <span data-ttu-id="53079-144">Al termine dell'analisi, l'endpoint verrà riavviato e Windows verrà caricato normalmente.</span><span class="sxs-lookup"><span data-stu-id="53079-144">After the scan is completed, the endpoint will be restarted and Windows will load normally.</span></span>

<span data-ttu-id="53079-145">È possibile eseguire un'Microsoft Defender Offline di analisi con le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="53079-145">You can run a Microsoft Defender Offline scan with the following:</span></span>

- <span data-ttu-id="53079-146">PowerShell</span><span class="sxs-lookup"><span data-stu-id="53079-146">PowerShell</span></span>
- <span data-ttu-id="53079-147">Strumentazione gestione Windows (WMI)</span><span class="sxs-lookup"><span data-stu-id="53079-147">Windows Management Instrumentation (WMI)</span></span>
- <span data-ttu-id="53079-148">L Sicurezza di Windows app</span><span class="sxs-lookup"><span data-stu-id="53079-148">The Windows Security app</span></span>



### <a name="use-powershell-cmdlets-to-run-an-offline-scan"></a><span data-ttu-id="53079-149">Utilizzare i cmdlet di PowerShell per eseguire un'analisi offline</span><span class="sxs-lookup"><span data-stu-id="53079-149">Use PowerShell cmdlets to run an offline scan</span></span>

<span data-ttu-id="53079-150">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="53079-150">Use the following cmdlets:</span></span>

```PowerShell
Start-MpWDOScan
```

<span data-ttu-id="53079-151">Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Use [PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Antivirus Microsoft Defender run Antivirus Microsoft Defender and [Defender cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="53079-151">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-run-an-offline-scan"></a><span data-ttu-id="53079-152">Utilizzare Windows Management Instruction (WMI) per eseguire un'analisi offline</span><span class="sxs-lookup"><span data-stu-id="53079-152">Use Windows Management Instruction (WMI) to run an offline scan</span></span>

<span data-ttu-id="53079-153">Utilizzare la [**classe MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per eseguire un'analisi offline.</span><span class="sxs-lookup"><span data-stu-id="53079-153">Use the [**MSFT_MpWDOScan**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class to run an offline scan.</span></span>

<span data-ttu-id="53079-154">Il frammento di script WMI seguente eseguirà immediatamente un'analisi Microsoft Defender Offline, che causerà il riavvio dell'endpoint, l'esecuzione dell'analisi offline e quindi il riavvio e l'avvio in Windows.</span><span class="sxs-lookup"><span data-stu-id="53079-154">The following WMI script snippet will immediately run a Microsoft Defender Offline scan, which will cause the endpoint to restart, run the offline scan, and then restart and boot into Windows.</span></span>

```console
wmic /namespace:\\root\Microsoft\Windows\Defender path MSFT_MpWDOScan call Start 
```

<span data-ttu-id="53079-155">Per ulteriori informazioni, vedere:</span><span class="sxs-lookup"><span data-stu-id="53079-155">See the following for more information:</span></span>
- [<span data-ttu-id="53079-156">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="53079-156">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-the-windows-defender-security-app-to-run-an-offline-scan"></a><span data-ttu-id="53079-157">Usare l'app Windows Defender Security per eseguire un'analisi offline</span><span class="sxs-lookup"><span data-stu-id="53079-157">Use the Windows Defender Security app to run an offline scan</span></span>

1. <span data-ttu-id="53079-158">Apri l Sicurezza di Windows app facendo clic sull'icona scudo nella barra delle applicazioni o cercando Defender nel menu **Start.**</span><span class="sxs-lookup"><span data-stu-id="53079-158">Open the Windows Security app by clicking the shield icon in the task bar or searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="53079-159">Fai clic **sul riquadro Protezione da &** virus (o sull'icona scudo sulla barra dei menu sinistra) e quindi sull'etichetta **Analisi** avanzata:</span><span class="sxs-lookup"><span data-stu-id="53079-159">Click the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Advanced scan** label:</span></span>
    
3. <span data-ttu-id="53079-160">Selezionare **Microsoft Defender Offline analisi e** fare clic su Analizza **ora.**</span><span class="sxs-lookup"><span data-stu-id="53079-160">Select **Microsoft Defender Offline scan** and click **Scan now**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="53079-161">In Windows 10 versione 1607, l'analisi offline potrebbe essere eseguita da **Windows Impostazioni** Update & security Windows Defender o dal  >    >   client Windows Defender.</span><span class="sxs-lookup"><span data-stu-id="53079-161">In Windows 10, version 1607, the offline scan could be run from under **Windows Settings** > **Update & security** > **Windows Defender** or from the Windows Defender client.</span></span>


## <a name="review-scan-results"></a><span data-ttu-id="53079-162">Esaminare i risultati dell'analisi</span><span class="sxs-lookup"><span data-stu-id="53079-162">Review scan results</span></span>

<span data-ttu-id="53079-163">Microsoft Defender Offline risultati dell'analisi verranno elencati nella sezione [Cronologia analisi dell'app Sicurezza di Windows.](microsoft-defender-security-center-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="53079-163">Microsoft Defender Offline scan results will be listed in the [Scan history section of the Windows Security app](microsoft-defender-security-center-antivirus.md).</span></span> 


## <a name="related-articles"></a><span data-ttu-id="53079-164">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="53079-164">Related articles</span></span>

- [<span data-ttu-id="53079-165">Personalizzare, avviare ed esaminare i risultati delle analisi e delle correzioni</span><span class="sxs-lookup"><span data-stu-id="53079-165">Customize, initiate, and review the results of scans and remediation</span></span>](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="53079-166">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="53079-166">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)