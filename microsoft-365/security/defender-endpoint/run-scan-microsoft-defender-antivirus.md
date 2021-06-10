---
title: Eseguire e personalizzare le analisi su richiesta in Antivirus Microsoft Defender
description: Eseguire e configurare analisi su richiesta tramite PowerShell, Windows Management Instrumentation o singolarmente sugli endpoint con l'app Sicurezza di Windows
keywords: analisi, su richiesta, dos, intune, analisi istantanea
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/04/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: fdca059633ab0993e07b5b1be0c6f33cfe327fcf
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/06/2021
ms.locfileid: "52789172"
---
# <a name="configure-and-run-on-demand-microsoft-defender-antivirus-scans"></a><span data-ttu-id="ba3a5-104">Configurare ed eseguire analisi di Microsoft Defender Antivirus su richiesta</span><span class="sxs-lookup"><span data-stu-id="ba3a5-104">Configure and run on-demand Microsoft Defender Antivirus scans</span></span>

<span data-ttu-id="ba3a5-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ba3a5-105">**Applies to:**</span></span>

- [<span data-ttu-id="ba3a5-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="ba3a5-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ba3a5-107">È possibile eseguire un'analisi su richiesta su singoli endpoint.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-107">You can run an on-demand scan on individual endpoints.</span></span> <span data-ttu-id="ba3a5-108">Queste analisi verranno avviate immediatamente ed è possibile definire i parametri per l'analisi, ad esempio la posizione o il tipo.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-108">These scans will start immediately, and you can define parameters for the scan, such as the location or type.</span></span>

## <a name="quick-scan-versus-full-scan"></a><span data-ttu-id="ba3a5-109">Analisi rapida e analisi completa</span><span class="sxs-lookup"><span data-stu-id="ba3a5-109">Quick scan versus full scan</span></span>

<span data-ttu-id="ba3a5-110">L'analisi rapida esamina tutti i percorsi in cui potrebbe essere registrato malware per iniziare con il sistema, ad esempio le chiavi del Registro di sistema e le cartelle di avvio Windows note.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-110">Quick scan looks at all the locations where there could be malware registered to start with the system, such as registry keys and known Windows startup folders.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ba3a5-111">Antivirus Microsoft Defender viene eseguito nel contesto dell'account [LocalSystem](/windows/win32/services/localsystem-account) quando si esegue un'analisi locale.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-111">Microsoft Defender Antivirus runs in the context of the [LocalSystem](/windows/win32/services/localsystem-account) account when performing a local scan.</span></span> <span data-ttu-id="ba3a5-112">Per le analisi di rete, usa il contesto dell'account del dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-112">For network scans, it uses the context of the device account.</span></span> <span data-ttu-id="ba3a5-113">Se l'account del dispositivo di dominio non dispone delle autorizzazioni appropriate per accedere alla condivisione, l'analisi non funzionerà.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-113">If the domain device account doesn't have appropriate permissions to access the share, the scan won't work.</span></span> <span data-ttu-id="ba3a5-114">Assicurati che il dispositivo abbia le autorizzazioni per la condivisione di rete di accesso.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-114">Ensure that the device has permissions to the access network share.</span></span>

<span data-ttu-id="ba3a5-115">In combinazione con la funzionalità di protezione in [tempo](configure-real-time-protection-microsoft-defender-antivirus.md)reale sempre in uso, un'analisi rapida consente di fornire una copertura avanzata sia per il malware che inizia con il sistema che con il malware a livello di kernel.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-115">Combined with [always-on real-time protection capability](configure-real-time-protection-microsoft-defender-antivirus.md), a quick scan helps provide strong coverage both for malware that starts with the system and kernel-level malware.</span></span> <span data-ttu-id="ba3a5-116">La protezione sempre in tempo reale rivede i file quando vengono aperti e chiusi e ogni volta che un utente passa a una cartella.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-116">Always-on, real-time protection reviews files when they're opened and closed, and whenever a user navigates to a folder.</span></span> <span data-ttu-id="ba3a5-117">Per impostazione predefinita, le analisi rapide vengono eseguite su dispositivi rimovibili montati, ad esempio unità USB.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-117">By default, quick scans run on mounted removable devices, such as USB drives.</span></span> <span data-ttu-id="ba3a5-118">Nella maggior parte dei casi, un'analisi rapida è adeguata per individuare malware non raccolto dalla protezione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-118">In most instances, a quick scan is adequate to find malware that wasn't picked up by real-time protection.</span></span>

<span data-ttu-id="ba3a5-119">Un'analisi completa può essere utile quando una minaccia malware viene segnalata in un endpoint.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-119">A full scan can be useful when a malware threat is reported on an endpoint.</span></span> <span data-ttu-id="ba3a5-120">L'analisi può identificare se sono presenti componenti inattivi che richiedono una pulizia più approfondita.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-120">The scan can identify whether there are any inactive components that require a more thorough clean-up.</span></span> <span data-ttu-id="ba3a5-121">Tuttavia, Microsoft consiglia in genere di utilizzare analisi rapide anziché analisi complete.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-121">However, Microsoft generally recommends using quick scans instead of full scans.</span></span> <span data-ttu-id="ba3a5-122">Il completamento di un'analisi completa può richiedere alcune ore o giorni, a seconda della quantità e del tipo di dati da analizzare.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-122">A full scan can take a few hours or days to complete, depending on the amount and type of data that needs to be scanned.</span></span> 

> [!TIP]
> <span data-ttu-id="ba3a5-123">Per ulteriori informazioni sulle differenze tra analisi rapida e completa, vedere Analisi rapida e analisi [completa e analisi personalizzata.](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan)</span><span class="sxs-lookup"><span data-stu-id="ba3a5-123">To learn more about the differences between quick and full scans, see [Quick scan versus full scan and custom scan](scheduled-catch-up-scans-microsoft-defender-antivirus.md#quick-scan-versus-full-scan-and-custom-scan).</span></span>

## <a name="use-microsoft-endpoint-manager-to-run-a-scan"></a><span data-ttu-id="ba3a5-124">Utilizzare Microsoft Endpoint Manager per eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="ba3a5-124">Use Microsoft Endpoint Manager to run a scan</span></span>

1. <span data-ttu-id="ba3a5-125">Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="ba3a5-126">Scegliere **Endpoint security**  >  **Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-126">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="ba3a5-127">Nell'elenco di schede selezionare **Windows 10 endpoint non integri.**</span><span class="sxs-lookup"><span data-stu-id="ba3a5-127">In the list of tabs, select **Windows 10 unhealthy endpoints**.</span></span>
4. <span data-ttu-id="ba3a5-128">Nell'elenco delle azioni fornite, selezionare **Analisi rapida** o **Analisi completa.**</span><span class="sxs-lookup"><span data-stu-id="ba3a5-128">From the list of actions provided, select **Quick Scan** or **Full Scan**.</span></span>

<span data-ttu-id="ba3a5-129">[![IMAGE ](images/mem-antivirus-scan-on-demand.png)](images/mem-antivirus-scan-on-demand.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="ba3a5-129">[ ![IMAGE](images/mem-antivirus-scan-on-demand.png) ](images/mem-antivirus-scan-on-demand.png#lightbox)</span></span>

> [!TIP]
> <span data-ttu-id="ba3a5-130">Per ulteriori informazioni sull'Microsoft Endpoint Manager per eseguire un'analisi, vedere [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span><span class="sxs-lookup"><span data-stu-id="ba3a5-130">For more information about using Microsoft Endpoint Manager to run a scan, see [Antimalware and firewall tasks: How to perform an on-demand scan](/configmgr/protect/deploy-use/endpoint-antimalware-firewall#how-to-perform-an-on-demand-scan-of-computers).</span></span>

## <a name="use-the-mpcmdrunexe-command-line-utility-to-run-a-scan"></a><span data-ttu-id="ba3a5-131">Utilizzare l'mpcmdrun.exe da riga di comando per eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="ba3a5-131">Use the mpcmdrun.exe command-line utility to run a scan</span></span>

<span data-ttu-id="ba3a5-132">Utilizzare il parametro `-scan` seguente:</span><span class="sxs-lookup"><span data-stu-id="ba3a5-132">Use the following `-scan` parameter:</span></span>

```console
mpcmdrun.exe -scan -scantype 1
```

<span data-ttu-id="ba3a5-133">Per ulteriori informazioni su come utilizzare lo strumento e parametri aggiuntivi, tra cui l'avvio di un'analisi completa o la definizione di percorsi, vedere [Use the mpcmdrun.exe commandline tool to configure and manage Antivirus Microsoft Defender](command-line-arguments-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="ba3a5-133">For more information about how to use the tool and additional parameters, including starting a full scan, or defining paths, see [Use the mpcmdrun.exe commandline tool to configure and manage Microsoft Defender Antivirus](command-line-arguments-microsoft-defender-antivirus.md).</span></span>

## <a name="use-microsoft-intune-to-run-a-scan"></a><span data-ttu-id="ba3a5-134">Utilizzare Microsoft Intune per eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="ba3a5-134">Use Microsoft Intune to run a scan</span></span>

1. <span data-ttu-id="ba3a5-135">Accedere all'Microsoft Endpoint Manager di amministrazione ( [https://endpoint.microsoft.com](https://endpoint.microsoft.com) ) ed eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-135">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="ba3a5-136">Nella barra laterale seleziona Dispositivi > **Tutti i dispositivi** e scegli il dispositivo che vuoi analizzare.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-136">From the sidebar, select **Devices > All Devices** and choose the device you want to scan.</span></span>
3. <span data-ttu-id="ba3a5-137">Selezionare **... Altro**.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-137">Select **...More**.</span></span> <span data-ttu-id="ba3a5-138">Nelle opzioni selezionare **Analisi rapida o** Analisi **completa.**</span><span class="sxs-lookup"><span data-stu-id="ba3a5-138">From the options, select **Quick Scan** or **Full Scan**.</span></span>

## <a name="use-the-windows-security-app-to-run-a-scan"></a><span data-ttu-id="ba3a5-139">Usare l'app Sicurezza di Windows per eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="ba3a5-139">Use the Windows Security app to run a scan</span></span>

<span data-ttu-id="ba3a5-140">Vedi [Eseguire un'analisi nell'app Sicurezza di Windows per](microsoft-defender-security-center-antivirus.md) istruzioni sull'esecuzione di un'analisi su singoli endpoint.</span><span class="sxs-lookup"><span data-stu-id="ba3a5-140">See [Run a scan in the Windows Security app](microsoft-defender-security-center-antivirus.md) for instructions on running a scan on individual endpoints.</span></span>

## <a name="use-powershell-cmdlets-to-run-a-scan"></a><span data-ttu-id="ba3a5-141">Utilizzare i cmdlet di PowerShell per eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="ba3a5-141">Use PowerShell cmdlets to run a scan</span></span>

<span data-ttu-id="ba3a5-142">Utilizzare il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="ba3a5-142">Use the following cmdlet:</span></span>

```PowerShell
Start-MpScan
```

<span data-ttu-id="ba3a5-143">Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per configurare ed eseguire Antivirus Microsoft Defender [e i cmdlet defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="ba3a5-143">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span>

## <a name="use-windows-management-instruction-wmi-to-run-a-scan"></a><span data-ttu-id="ba3a5-144">Utilizzare Windows Management Instruction (WMI) per eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="ba3a5-144">Use Windows Management Instruction (WMI) to run a scan</span></span>

<span data-ttu-id="ba3a5-145">Utilizzare il [ **metodo Start**](/previous-versions/windows/desktop/defender/start-msft-mpscan) della **classe MSFT_MpScan.**</span><span class="sxs-lookup"><span data-stu-id="ba3a5-145">Use the [**Start** method](/previous-versions/windows/desktop/defender/start-msft-mpscan) of the **MSFT_MpScan** class.</span></span>

<span data-ttu-id="ba3a5-146">Per altre informazioni sui parametri consentiti, [Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="ba3a5-146">For more information about which parameters are allowed, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="related-articles"></a><span data-ttu-id="ba3a5-147">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="ba3a5-147">Related articles</span></span>

- [<span data-ttu-id="ba3a5-148">Configurare le opzioni di analisi di Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="ba3a5-148">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ba3a5-149">Configurare le Antivirus Microsoft Defender pianificate</span><span class="sxs-lookup"><span data-stu-id="ba3a5-149">Configure scheduled Microsoft Defender Antivirus scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ba3a5-150">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="ba3a5-150">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)