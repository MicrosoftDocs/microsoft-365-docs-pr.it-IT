---
title: Applicare gli aggiornamenti di Microsoft Defender Antivirus dopo determinati eventi
description: Gestire il modo in cui Microsoft Defender Antivirus applica gli aggiornamenti di intelligence per la sicurezza dopo l'avvio o la ricezione di report di rilevamento recapitati nel cloud.
keywords: aggiornamenti, protezione, forzare gli aggiornamenti, eventi, avvio, controllare la presenza di più recenti, notifiche
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/17/2018
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 78a04105fce0a3a1f9f7ea3f9ee993dd53750f3f
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764556"
---
# <a name="manage-event-based-forced-updates"></a><span data-ttu-id="96164-104">Gestire gli aggiornamenti forzati basati su eventi</span><span class="sxs-lookup"><span data-stu-id="96164-104">Manage event-based forced updates</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="96164-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="96164-105">**Applies to:**</span></span>

- [<span data-ttu-id="96164-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="96164-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="96164-107">Microsoft Defender Antivirus consente di determinare se gli aggiornamenti devono verificarsi (o meno) dopo determinati eventi, ad esempio all'avvio o dopo la ricezione di report specifici dal servizio di protezione fornito dal cloud.</span><span class="sxs-lookup"><span data-stu-id="96164-107">Microsoft Defender Antivirus allows you to determine if updates should (or should not) occur after certain events, such as at startup or after receiving specific reports from the cloud-delivered protection service.</span></span>

## <a name="check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="96164-108">Verificare la disponibilità di aggiornamenti della protezione prima di eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="96164-108">Check for protection updates before running a scan</span></span>

<span data-ttu-id="96164-109">È possibile utilizzare Microsoft Endpoint Configuration Manager, Criteri di gruppo, cmdlet di PowerShell e WMI per forzare Microsoft Defender Antivirus a controllare e scaricare gli aggiornamenti di protezione prima di eseguire un'analisi pianificata.</span><span class="sxs-lookup"><span data-stu-id="96164-109">You can use Microsoft Endpoint Configuration Manager, Group Policy, PowerShell cmdlets, and WMI to force Microsoft Defender Antivirus to check and download protection updates before running a scheduled scan.</span></span>

### <a name="use-configuration-manager-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="96164-110">Usare Configuration Manager per verificare la disponibilità di aggiornamenti della protezione prima di eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="96164-110">Use Configuration Manager to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="96164-111">Nella console di Microsoft Endpoint Manager apri i criteri antimalware che vuoi modificare (fai clic su Asset  **e** conformità nel riquadro di spostamento a sinistra, quindi espandi l'albero fino a Panoramica criteri  >    >  **antimalware** di Endpoint Protection)</span><span class="sxs-lookup"><span data-stu-id="96164-111">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2. <span data-ttu-id="96164-112">Vai alla sezione **Analisi pianificate** e imposta Verifica la disponibilità degli ultimi aggiornamenti delle funzionalità di intelligence per la sicurezza **prima di eseguire un'analisi** su **Sì.**</span><span class="sxs-lookup"><span data-stu-id="96164-112">Go to the **Scheduled scans** section and set **Check for the latest security intelligence updates before running a scan** to **Yes**.</span></span>

3. <span data-ttu-id="96164-113">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="96164-113">Click **OK**.</span></span>

4. <span data-ttu-id="96164-114">[Distribuire il criterio aggiornato come al solito.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="96164-114">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="96164-115">Utilizzare Criteri di gruppo per verificare la disponibilità di aggiornamenti della protezione prima di eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="96164-115">Use Group Policy to check for protection updates before running a scan</span></span>

1. <span data-ttu-id="96164-116">Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="96164-116">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="96164-117">Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="96164-117">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="96164-118">Fare **clic su Criteri** e quindi su Modelli **amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="96164-118">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="96164-119">Espandere l'albero fino **ai componenti di Windows** Microsoft Defender  >  **Antivirus**  >  **Scan.**</span><span class="sxs-lookup"><span data-stu-id="96164-119">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Scan**.</span></span>

5. <span data-ttu-id="96164-120">Fare doppio clic **su Controlla le definizioni più** recenti di virus e spyware prima di eseguire un'analisi pianificata e impostare l'opzione su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="96164-120">Double-click **Check for the latest virus and spyware definitions before running a scheduled scan** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="96164-121">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="96164-121">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="96164-122">Utilizzare i cmdlet di PowerShell per verificare la disponibilità di aggiornamenti della protezione prima di eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="96164-122">Use PowerShell cmdlets to check for protection updates before running a scan</span></span>

<span data-ttu-id="96164-123">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="96164-123">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="96164-124">Per ulteriori informazioni, vedere [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Defender [cmdlets](/powershell/module/defender/index).</span><span class="sxs-lookup"><span data-stu-id="96164-124">For more information, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index).</span></span>

### <a name="use-windows-management-instruction-wmi-to-check-for-protection-updates-before-running-a-scan"></a><span data-ttu-id="96164-125">Utilizzare Windows Management Instruction (WMI) per verificare la disponibilità di aggiornamenti della protezione prima di eseguire un'analisi</span><span class="sxs-lookup"><span data-stu-id="96164-125">Use Windows Management Instruction (WMI) to check for protection updates before running a scan</span></span>

<span data-ttu-id="96164-126">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="96164-126">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
CheckForSignaturesBeforeRunningScan
```

<span data-ttu-id="96164-127">Per altre informazioni, [vedi Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="96164-127">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

## <a name="check-for-protection-updates-on-startup"></a><span data-ttu-id="96164-128">Verificare la disponibilità di aggiornamenti della protezione all'avvio</span><span class="sxs-lookup"><span data-stu-id="96164-128">Check for protection updates on startup</span></span>

<span data-ttu-id="96164-129">Puoi usare Criteri di gruppo per forzare Microsoft Defender Antivirus a controllare e scaricare gli aggiornamenti di protezione all'avvio del computer.</span><span class="sxs-lookup"><span data-stu-id="96164-129">You can use Group Policy to force Microsoft Defender Antivirus to check and download protection updates when the machine is started.</span></span>

1. <span data-ttu-id="96164-130">Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="96164-130">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="96164-131">Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="96164-131">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="96164-132">Fare **clic su Criteri** e quindi su Modelli **amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="96164-132">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="96164-133">Espandere l'albero fino **ai componenti di Windows** Microsoft Defender  >  **Antivirus** Security  >  **Intelligence Updates**.</span><span class="sxs-lookup"><span data-stu-id="96164-133">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="96164-134">Fare doppio clic **su Controlla le definizioni più** recenti di virus e spyware all'avvio e impostare l'opzione su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="96164-134">Double-click **Check for the latest virus and spyware definitions on startup** and set the option to **Enabled**.</span></span> 

6. <span data-ttu-id="96164-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="96164-135">Click **OK**.</span></span>

<span data-ttu-id="96164-136">È inoltre possibile utilizzare Criteri di gruppo, PowerShell o WMI per configurare Microsoft Defender Antivirus per verificare la disponibilità di aggiornamenti all'avvio anche quando non è in esecuzione.</span><span class="sxs-lookup"><span data-stu-id="96164-136">You can also use Group Policy, PowerShell, or WMI to configure Microsoft Defender Antivirus to check for updates at startup even when it is not running.</span></span>

### <a name="use-group-policy-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="96164-137">Usare Criteri di gruppo per scaricare gli aggiornamenti quando Microsoft Defender Antivirus non è presente</span><span class="sxs-lookup"><span data-stu-id="96164-137">Use Group Policy to download updates when Microsoft Defender Antivirus is not present</span></span>

1. <span data-ttu-id="96164-138">Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="96164-138">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="96164-139">Utilizzando **l'Editor Gestione Criteri di gruppo,** passare a **Configurazione computer**.</span><span class="sxs-lookup"><span data-stu-id="96164-139">Using the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="96164-140">Fare **clic su Criteri** e quindi su Modelli **amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="96164-140">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="96164-141">Espandere l'albero fino **ai componenti di Windows** Microsoft Defender  >  **Antivirus** Security  >  **Intelligence Updates**.</span><span class="sxs-lookup"><span data-stu-id="96164-141">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="96164-142">Fare doppio clic su **Avvia aggiornamento intelligence per la sicurezza all'avvio** e impostare l'opzione su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="96164-142">Double-click **Initiate security intelligence update on startup** and set the option to **Enabled**.</span></span>

6. <span data-ttu-id="96164-143">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="96164-143">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="96164-144">Usare i cmdlet di PowerShell per scaricare gli aggiornamenti quando Microsoft Defender Antivirus non è presente</span><span class="sxs-lookup"><span data-stu-id="96164-144">Use PowerShell cmdlets to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="96164-145">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="96164-145">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="96164-146">Per ulteriori informazioni, vedere Utilizzare i cmdlet di [PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) per gestire i cmdlet di Microsoft Defender Antivirus e [Defender](/powershell/module/defender/index) per ulteriori informazioni su come usare PowerShell con Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="96164-146">For more information, see [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/index) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-download-updates-when-microsoft-defender-antivirus-is-not-present"></a><span data-ttu-id="96164-147">Usare Windows Management Instruction (WMI) per scaricare gli aggiornamenti quando Microsoft Defender Antivirus non è presente</span><span class="sxs-lookup"><span data-stu-id="96164-147">Use Windows Management Instruction (WMI) to download updates when Microsoft Defender Antivirus is not present</span></span>

<span data-ttu-id="96164-148">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="96164-148">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureDisableUpdateOnStartupWithoutEngine
```

<span data-ttu-id="96164-149">Per altre informazioni, [vedi Windows Defender API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span><span class="sxs-lookup"><span data-stu-id="96164-149">For more information, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal).</span></span>

<a id="cloud-report-updates"></a>

## <a name="allow-ad-hoc-changes-to-protection-based-on-cloud-delivered-protection"></a><span data-ttu-id="96164-150">Consentire modifiche ad hoc alla protezione basata sulla protezione basata sul cloud</span><span class="sxs-lookup"><span data-stu-id="96164-150">Allow ad hoc changes to protection based on cloud-delivered protection</span></span>

<span data-ttu-id="96164-151">Microsoft Defender AV può apportare modifiche alla protezione in base alla protezione basata sul cloud.</span><span class="sxs-lookup"><span data-stu-id="96164-151">Microsoft Defender AV can make changes to its protection based on cloud-delivered protection.</span></span> <span data-ttu-id="96164-152">Tali modifiche possono verificarsi al di fuori degli aggiornamenti di protezione normali o pianificati.</span><span class="sxs-lookup"><span data-stu-id="96164-152">Such changes can occur outside of normal or scheduled protection updates.</span></span>

<span data-ttu-id="96164-153">Se è stata abilitata la protezione basata sul cloud, Microsoft Defender AV invierà file sospetti al cloud Windows Defender cloud.</span><span class="sxs-lookup"><span data-stu-id="96164-153">If you have enabled cloud-delivered protection, Microsoft Defender AV will send files it is suspicious about to the Windows Defender cloud.</span></span> <span data-ttu-id="96164-154">Se il servizio cloud segnala che il file è dannoso e il file viene rilevato in un aggiornamento di protezione recente, è possibile utilizzare Criteri di gruppo per configurare Microsoft Defender AV per ricevere automaticamente tale aggiornamento di protezione.</span><span class="sxs-lookup"><span data-stu-id="96164-154">If the cloud service reports that the file is malicious, and the file is detected in a recent protection update, you can use Group Policy to configure Microsoft Defender AV to automatically receive that protection update.</span></span> <span data-ttu-id="96164-155">È inoltre possibile applicare altri importanti aggiornamenti della protezione.</span><span class="sxs-lookup"><span data-stu-id="96164-155">Other important protection updates can also be applied.</span></span>

### <a name="use-group-policy-to-automatically-download-recent-updates-based-on-cloud-delivered-protection"></a><span data-ttu-id="96164-156">Usare Criteri di gruppo per scaricare automaticamente gli aggiornamenti recenti in base alla protezione consegnata dal cloud</span><span class="sxs-lookup"><span data-stu-id="96164-156">Use Group Policy to automatically download recent updates based on cloud-delivered protection</span></span>

1. <span data-ttu-id="96164-157">Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="96164-157">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="96164-158">Utilizzando **l'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="96164-158">Using the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="96164-159">Fare **clic su Criteri** e quindi su Modelli **amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="96164-159">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="96164-160">Espandere l'albero fino **ai componenti di Windows** Microsoft Defender  >  **Antivirus** Security  >  **Intelligence Updates**.</span><span class="sxs-lookup"><span data-stu-id="96164-160">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Security Intelligence Updates**.</span></span>

5. <span data-ttu-id="96164-161">Fare doppio clic **su Consenti aggiornamenti delle** funzionalità di intelligence per la sicurezza in tempo reale in base ai report di Microsoft MAPS e impostare l'opzione su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="96164-161">Double-click **Allow real-time security intelligence updates based on reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="96164-162">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="96164-162">Then click **OK**.</span></span>

6. <span data-ttu-id="96164-163">**Consenti alle notifiche di disabilitare i report basati sulle definizioni in Microsoft MAPS** e imposta l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="96164-163">**Allow notifications to disable definitions-based reports to Microsoft MAPS** and set the option to **Enabled**.</span></span> <span data-ttu-id="96164-164">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="96164-164">Then click **OK**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="96164-165">**Consenti notifiche per disabilitare i report basati sulle** definizioni consente a Microsoft MAPS di disabilitare tali definizioni note per causare report falsi positivi.</span><span class="sxs-lookup"><span data-stu-id="96164-165">**Allow notifications to disable definitions based reports** enables Microsoft MAPS to disable those definitions known to cause false-positive reports.</span></span> <span data-ttu-id="96164-166">È necessario configurare il computer per l'aggiunta a Microsoft MAPS per il funzionamento di questa funzione.</span><span class="sxs-lookup"><span data-stu-id="96164-166">You must configure your computer to join Microsoft MAPS for this function to work.</span></span>

## <a name="see-also"></a><span data-ttu-id="96164-167">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="96164-167">See also</span></span>

- [<span data-ttu-id="96164-168">Distribuire Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="96164-168">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="96164-169">Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base</span><span class="sxs-lookup"><span data-stu-id="96164-169">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="96164-170">Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="96164-170">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="96164-171">Gestire gli aggiornamenti per gli endpoint non aggiornati</span><span class="sxs-lookup"><span data-stu-id="96164-171">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="96164-172">Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali</span><span class="sxs-lookup"><span data-stu-id="96164-172">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="96164-173">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="96164-173">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)