---
title: Pianificare Antivirus Microsoft Defender aggiornamenti della protezione
description: Pianificare il giorno, l'ora e l'intervallo per il download degli aggiornamenti della protezione
keywords: aggiornamenti, linee di base della sicurezza, pianificare gli aggiornamenti
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
search.appverid: met150
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: pahuijbr
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 26b88b8677c27a5d6615776a371326e37034afd4
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275037"
---
# <a name="manage-the-schedule-for-when-protection-updates-should-be-downloaded-and-applied"></a><span data-ttu-id="ebed4-104">Gestire la pianificazione del momento in cui devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="ebed4-104">Manage the schedule for when protection updates should be downloaded and applied</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ebed4-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="ebed4-105">**Applies to:**</span></span>

- [<span data-ttu-id="ebed4-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="ebed4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="ebed4-107">Antivirus Microsoft Defender consente di determinare quando cercare e scaricare gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="ebed4-107">Microsoft Defender Antivirus lets you determine when it should look for and download updates.</span></span>

<span data-ttu-id="ebed4-108">Puoi pianificare gli aggiornamenti per gli endpoint:</span><span class="sxs-lookup"><span data-stu-id="ebed4-108">You can schedule updates for your endpoints by:</span></span> 

- <span data-ttu-id="ebed4-109">Specifica del giorno della settimana per la verifica della disponibilità di aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="ebed4-109">Specifying the day of the week to check for protection updates</span></span> 
- <span data-ttu-id="ebed4-110">Specifica dell'intervallo per la verifica della disponibilità di aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="ebed4-110">Specifying the interval to check for protection updates</span></span>
- <span data-ttu-id="ebed4-111">Specifica del tempo necessario per verificare la disponibilità di aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="ebed4-111">Specifying the time to check for protection updates</span></span>

<span data-ttu-id="ebed4-112">È inoltre possibile impostare in modo casuale i tempi in cui ogni endpoint controlla e scarica gli aggiornamenti della protezione.</span><span class="sxs-lookup"><span data-stu-id="ebed4-112">You can also randomize the times when each endpoint checks and downloads protection updates.</span></span> <span data-ttu-id="ebed4-113">Per ulteriori [informazioni, vedere l'argomento](scheduled-catch-up-scans-microsoft-defender-antivirus.md) Pianifica analisi.</span><span class="sxs-lookup"><span data-stu-id="ebed4-113">See the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic for more information.</span></span>

## <a name="use-configuration-manager-to-schedule-protection-updates"></a><span data-ttu-id="ebed4-114">Utilizzare Configuration Manager per pianificare gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="ebed4-114">Use Configuration Manager to schedule protection updates</span></span>

1.  <span data-ttu-id="ebed4-115">Nella console Microsoft Endpoint Manager, aprire il criterio antimalware che si desidera modificare (fare clic su Asset **e** conformità nel riquadro di spostamento a sinistra, quindi espandere l'albero fino a Panoramica Endpoint Protection  >    >  **Criteri antimalware**)</span><span class="sxs-lookup"><span data-stu-id="ebed4-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="ebed4-116">Passare alla sezione **Aggiornamenti di Intelligence per la sicurezza.**</span><span class="sxs-lookup"><span data-stu-id="ebed4-116">Go to the **Security intelligence updates** section.</span></span>

3. <span data-ttu-id="ebed4-117">Per controllare e scaricare gli aggiornamenti in un determinato momento:</span><span class="sxs-lookup"><span data-stu-id="ebed4-117">To check and download updates at a certain time:</span></span>
      1. <span data-ttu-id="ebed4-118">Impostare Verifica disponibilità Endpoint Protection aggiornamenti delle funzionalità di intelligence per la **sicurezza a un intervallo specifico...** su **0**.</span><span class="sxs-lookup"><span data-stu-id="ebed4-118">Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to **0**.</span></span>
      2. <span data-ttu-id="ebed4-119">Imposta **Verifica disponibilità Endpoint Protection aggiornamenti delle funzionalità di intelligence** per la sicurezza ogni giorno all'ora in cui devono essere controllati gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="ebed4-119">Set **Check for Endpoint Protection security intelligence updates daily at...** to the time when updates should be checked.</span></span>
      <span data-ttu-id="ebed4-120">3</span><span class="sxs-lookup"><span data-stu-id="ebed4-120">3</span></span>
4. <span data-ttu-id="ebed4-121">Per controllare e scaricare gli aggiornamenti a intervalli continui, impostare Verifica disponibilità aggiornamenti di intelligence per la sicurezza Endpoint Protection un intervallo **specifico...** sul numero di ore che devono verificarsi tra gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="ebed4-121">To check and download updates on a continual interval, Set **Check for Endpoint Protection security intelligence updates at a specific interval...** to the number of hours that should occur between updates.</span></span>

5.  <span data-ttu-id="ebed4-122">[Distribuire il criterio aggiornato come al solito.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="ebed4-122">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="use-group-policy-to-schedule-protection-updates"></a><span data-ttu-id="ebed4-123">Utilizzare Criteri di gruppo per pianificare gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="ebed4-123">Use Group Policy to schedule protection updates</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ebed4-124">Per impostazione predefinita, Antivirus Microsoft Defender un aggiornamento 15 minuti prima dell'ora di qualsiasi analisi pianificata.</span><span class="sxs-lookup"><span data-stu-id="ebed4-124">By default, Microsoft Defender Antivirus will check for an update 15 minutes before the time of any scheduled scans.</span></span> <span data-ttu-id="ebed4-125">L'abilitazione di queste impostazioni avrà la precedenza su quella predefinita.</span><span class="sxs-lookup"><span data-stu-id="ebed4-125">Enabling these settings will override that default.</span></span>

1.  <span data-ttu-id="ebed4-126">Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="ebed4-126">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="ebed4-127">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="ebed4-127">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="ebed4-128">Fare **clic su Criteri** e quindi su Modelli **amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="ebed4-128">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="ebed4-129">Espandere l'albero per **Windows componenti**  >  **Antivirus Microsoft Defender**  >  **aggiornamenti di Signature Intelligence** e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ebed4-129">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Signature Intelligence Updates** and configure the following settings:</span></span>

    1. <span data-ttu-id="ebed4-130">Fare doppio clic **sull'impostazione Specifica il giorno della** settimana per verificare la disponibilità di aggiornamenti delle funzionalità di intelligence per la sicurezza e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="ebed4-130">Double-click the **Specify the day of the week to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="ebed4-131">Immettere il giorno della settimana per verificare la disponibilità di aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="ebed4-131">Enter the day of the week to check for updates.</span></span> <span data-ttu-id="ebed4-132">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ebed4-132">Click **OK**.</span></span>
    2. <span data-ttu-id="ebed4-133">Fare doppio clic **sull'impostazione Specifica l'intervallo per controllare la** disponibilità di aggiornamenti delle funzionalità di intelligence per la sicurezza e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="ebed4-133">Double-click the **Specify the interval to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="ebed4-134">Immettere il numero di ore tra gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="ebed4-134">Enter the number of hours between updates.</span></span> <span data-ttu-id="ebed4-135">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ebed4-135">Click **OK**.</span></span>
    3. <span data-ttu-id="ebed4-136">Fare doppio clic **sull'impostazione Specifica il tempo di** verifica della disponibilità di aggiornamenti delle funzionalità di intelligence per la sicurezza e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="ebed4-136">Double-click the **Specify the time to check for security intelligence updates** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="ebed4-137">Immettere l'ora in cui controllare gli aggiornamenti.</span><span class="sxs-lookup"><span data-stu-id="ebed4-137">Enter the time when updates should be checked.</span></span> <span data-ttu-id="ebed4-138">L'ora è basata sull'ora locale dell'endpoint.</span><span class="sxs-lookup"><span data-stu-id="ebed4-138">The time is based on the local time of the endpoint.</span></span> <span data-ttu-id="ebed4-139">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="ebed4-139">Click **OK**.</span></span>


## <a name="use-powershell-cmdlets-to-schedule-protection-updates"></a><span data-ttu-id="ebed4-140">Utilizzare i cmdlet di PowerShell per pianificare gli aggiornamenti di protezione</span><span class="sxs-lookup"><span data-stu-id="ebed4-140">Use PowerShell cmdlets to schedule protection updates</span></span>

<span data-ttu-id="ebed4-141">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="ebed4-141">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureScheduleDay
Set-MpPreference -SignatureScheduleTime
Set-MpPreference -SignatureUpdateInterval
```

<span data-ttu-id="ebed4-142">Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Use [PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Antivirus Microsoft Defender run Antivirus Microsoft Defender and [Defender cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="ebed4-142">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

## <a name="use-windows-management-instruction-wmi-to-schedule-protection-updates"></a><span data-ttu-id="ebed4-143">Utilizzare Windows Management Instruction (WMI) per pianificare gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="ebed4-143">Use Windows Management Instruction (WMI) to schedule protection updates</span></span>

<span data-ttu-id="ebed4-144">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="ebed4-144">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureScheduleDay
SignatureScheduleTime
SignatureUpdateInterval
```

<span data-ttu-id="ebed4-145">Per ulteriori informazioni e parametri consentiti, vedere:</span><span class="sxs-lookup"><span data-stu-id="ebed4-145">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="ebed4-146">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="ebed4-146">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="related-articles"></a><span data-ttu-id="ebed4-147">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="ebed4-147">Related articles</span></span>

- [<span data-ttu-id="ebed4-148">Distribuire Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="ebed4-148">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ebed4-149">Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base</span><span class="sxs-lookup"><span data-stu-id="ebed4-149">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ebed4-150">Gestire gli aggiornamenti per gli endpoint non aggiornati</span><span class="sxs-lookup"><span data-stu-id="ebed4-150">Manage updates for endpoints that are out of date</span></span>](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ebed4-151">Gestire gli aggiornamenti forzati basati su eventi</span><span class="sxs-lookup"><span data-stu-id="ebed4-151">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ebed4-152">Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)</span><span class="sxs-lookup"><span data-stu-id="ebed4-152">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="ebed4-153">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="ebed4-153">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)