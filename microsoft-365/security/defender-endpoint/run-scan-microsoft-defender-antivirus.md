---
title: Eseguire e personalizzare le analisi su richiesta in Antivirus Microsoft Defender
description: Eseguire e configurare analisi su richiesta tramite PowerShell, Windows Management Instrumentation o singolarmente sugli endpoint con l'app Sicurezza di Windows
keywords: analisi, su richiesta, dos, intune, analisi istantanea
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/05/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 8b6889a2eabcfb777983be79d78060165497de72
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246345"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="83b89-104">Configurare ed eseguire analisi di Microsoft Defender Antivirus su richiesta</span><span class="sxs-lookup"><span data-stu-id="83b89-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="83b89-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="83b89-105">**Applies to:**</span></span>

- [<span data-ttu-id="83b89-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="83b89-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="83b89-107">È possibile eseguire un'analisi su richiesta su singoli endpoint.</span><span class="sxs-lookup"><span data-stu-id="83b89-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="83b89-108">Queste analisi verranno avviate immediatamente ed è possibile definire i parametri per l'analisi, ad esempio la posizione o il tipo.</span><span class="sxs-lookup"><span data-stu-id="83b89-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="83b89-109">Analisi rapida e analisi completa</span><span class="sxs-lookup"><span data-stu-id="83b89-109">Quick scan versus full scan</span></span>

<span data-ttu-id="83b89-110">L'analisi rapida esamina tutti i percorsi in cui potrebbe essere registrato malware per iniziare con il sistema, ad esempio le chiavi del Registro di sistema e le cartelle di avvio Windows note.</span><span class="sxs-lookup"><span data-stu-id="83b89-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83b89-111">Antivirus Microsoft Defender viene eseguito nel contesto dell'account [LocalSystem](/windows/win32/services/localsystem-account) quando si esegue un'analisi locale.</span><span class="sxs-lookup"><span data-stu-id="83b89-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="83b89-112">Per le analisi di rete, usa il contesto dell'account del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="83b89-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="83b89-113">Se l'account del dispositivo di dominio non dispone delle autorizzazioni appropriate per accedere alla condivisione, l'analisi non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="83b89-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="83b89-114">Assicurati che il dispositivo abbia le autorizzazioni per la condivisione di rete di accesso.</span><span class="sxs-lookup"><span data-stu-id="83b89-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="83b89-115">In [](configure-real-time-protection-microsoft-defender-antivirus.md)combinazione con la funzionalità di protezione sempre in tempo reale, che rivede i file quando vengono aperti e chiusi e ogni volta che un utente passa a una cartella, un'analisi rapida consente di fornire una copertura avanzata sia per il malware che inizia con il sistema che con il malware a livello di kernel.</span><span class="sxs-lookup"><span data-stu-id="83b89-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md)--which reviews files when they're opened and closed, and whenever a user navigates to a folder--a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span>  

<span data-ttu-id="83b89-116">Nella maggior parte dei casi, un'analisi rapida è adeguata per individuare malware non raccolto dalla protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="83b89-116">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="83b89-117">Un'analisi completa può essere utile per gli endpoint che hanno segnalato una minaccia malware.</span><span class="sxs-lookup"><span data-stu-id="83b89-117">A full scan can be useful on endpoints that have reported a malware threat.</span></span> <span data-ttu-id="83b89-118">L'analisi può identificare se sono presenti componenti inattivi che richiedono una pulizia più approfondita.</span><span class="sxs-lookup"><span data-stu-id="83b89-118">The scan can identify if there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="83b89-119">Questo è l'ideale se l'organizzazione esegue analisi su richiesta.</span><span class="sxs-lookup"><span data-stu-id="83b89-119">This is  ideal if your organization is running on-demand scans.</span></span>

> [!NOTE]
> <span data-ttu-id="83b89-120">Per impostazione predefinita, le analisi rapide vengono eseguite su dispositivi rimovibili montati, ad esempio unità USB.</span><span class="sxs-lookup"><span data-stu-id="83b89-120">By default, quick scans run on mounted removable devices, such as USB drives.</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="83b89-121">Utilizzare Microsoft Endpoint Manager per eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="83b89-121">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="83b89-122">Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="83b89-122">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="83b89-123">Scegliere **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="83b89-123">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="83b89-124">Nell'elenco di schede selezionare **Windows 10 endpoint non integri.**</span><span class="sxs-lookup"><span data-stu-id="83b89-124">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="83b89-125">Nell'elenco delle azioni fornite, selezionare **Analisi rapida** o **Analisi completa.**</span><span class="sxs-lookup"><span data-stu-id="83b89-125">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="83b89-126">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="83b89-126">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="83b89-127">Per ulteriori informazioni sull'Microsoft Endpoint Manager per eseguire un'analisi, vedere [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span><span class="sxs-lookup"><span data-stu-id="83b89-127">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="83b89-128">Utilizzare l'mpcmdrun.exe da riga di comando per eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="83b89-128">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="83b89-129">Utilizzare il parametro `-scan` seguente:</span><span class="sxs-lookup"><span data-stu-id="83b89-129">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="83b89-130">Per ulteriori informazioni su come utilizzare lo strumento e parametri aggiuntivi, tra cui l'avvio di un'analisi completa o la definizione di percorsi, vedere [Use the mpcmdrun.exe commandline tool to configure and manage Antivirus Microsoft Defender](command-line-arguments-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="83b89-130">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="83b89-131">Utilizzare Microsoft Intune per eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="83b89-131">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="83b89-132">Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="83b89-132">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="83b89-133">Nella barra laterale seleziona Dispositivi > **Tutti i dispositivi** e scegli il dispositivo che vuoi analizzare.</span><span class="sxs-lookup"><span data-stu-id="83b89-133">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="83b89-134">Selezionare **... Altro**.</span><span class="sxs-lookup"><span data-stu-id="83b89-134">Select **...More**.</span></span> <span data-ttu-id="83b89-135">Nelle opzioni selezionare **Analisi rapida o** Analisi **completa.**</span><span class="sxs-lookup"><span data-stu-id="83b89-135">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="83b89-136">Usare l'app Sicurezza di Windows per eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="83b89-136">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="83b89-137">Vedi [Eseguire un'analisi nell'app Sicurezza di Windows per](microsoft-defender-security-center-antivirus.md) istruzioni sull'esecuzione di un'analisi su singoli endpoint.</span><span class="sxs-lookup"><span data-stu-id="83b89-137">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="83b89-138">Utilizzare i cmdlet di PowerShell per eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="83b89-138">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="83b89-139">Utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="83b89-139">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="83b89-140">Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per configurare ed eseguire Antivirus Microsoft Defender [e i cmdlet defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="83b89-140">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="83b89-141">Utilizzare Windows Management Instruction (WMI) per eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="83b89-141">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="83b89-142">Utilizzare il [ **metodo Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) della **classe MSFT_MpScan.**</span><span class="sxs-lookup"><span data-stu-id="83b89-142">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="83b89-143">Per altre informazioni sui parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="83b89-143">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="83b89-144">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="83b89-144">Related articles</span></span>

- [<span data-ttu-id="83b89-145">Configurare le opzioni di analisi di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="83b89-145">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="83b89-146">Configurare le Antivirus Microsoft Defender pianificate</span><span class="sxs-lookup"><span data-stu-id="83b89-146">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="83b89-147">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="83b89-147">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)