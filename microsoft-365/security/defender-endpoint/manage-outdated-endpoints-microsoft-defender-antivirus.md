---
title: Applicare gli aggiornamenti della protezione di Microsoft Defender AV agli endpoint non aggiornati
description: Definire quando e come applicare gli aggiornamenti per gli endpoint che non sono stati aggiornati da un po'.
keywords: aggiornamenti, protezione, non aggiornato, obsoleto, vecchio, catch-up
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4199f55488ef0dc5989af88e8be83a3d51190d1f
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275061"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="88915-104">Gestire gli aggiornamenti e le analisi di Microsoft Defender Antivirus per gli endpoint non aggiornati</span><span class="sxs-lookup"><span data-stu-id="88915-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="88915-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="88915-105">**Applies to:**</span></span>

- [<span data-ttu-id="88915-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="88915-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="88915-107">Antivirus Microsoft Defender consente di definire per quanto tempo un endpoint può evitare un aggiornamento o il numero di analisi che può mancare prima di essere necessario per l'aggiornamento e l'analisi.</span><span class="sxs-lookup"><span data-stu-id="88915-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="88915-108">Ciò è particolarmente utile in ambienti in cui i dispositivi non sono spesso connessi a una rete aziendale o esterna o in dispositivi che non vengono utilizzati quotidianamente.</span><span class="sxs-lookup"><span data-stu-id="88915-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="88915-109">Ad esempio, un dipendente che usa un PC specifico è in pausa per tre giorni e non accede al PC durante tale periodo.</span><span class="sxs-lookup"><span data-stu-id="88915-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="88915-110">Quando l'utente torna a lavorare e accede al PC, Antivirus Microsoft Defender controlla immediatamente e scarica gli aggiornamenti di protezione più recenti ed esegue un'analisi.</span><span class="sxs-lookup"><span data-stu-id="88915-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="88915-111">Configurare gli aggiornamenti di protezione da recuperare per gli endpoint che non sono stati aggiornati per un po' di tempo</span><span class="sxs-lookup"><span data-stu-id="88915-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="88915-112">Se Antivirus Microsoft Defender non ha scaricato gli aggiornamenti di protezione per un periodo specificato, è possibile configurarlo per controllare e scaricare automaticamente l'aggiornamento più recente all'accesso successivo.</span><span class="sxs-lookup"><span data-stu-id="88915-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="88915-113">Ciò è utile se all'avvio sono stati disabilitati a livello globale i [download degli aggiornamenti automatici.](manage-event-based-updates-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="88915-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="88915-114">Usare Configuration Manager per configurare gli aggiornamenti di protezione di blocco</span><span class="sxs-lookup"><span data-stu-id="88915-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="88915-115">Nella console Microsoft Endpoint Manager, aprire il criterio antimalware che si desidera modificare (fare clic su Asset **e** conformità nel riquadro di spostamento a sinistra, quindi espandere l'albero fino a Panoramica Endpoint Protection  >    >  **Criteri antimalware**)</span><span class="sxs-lookup"><span data-stu-id="88915-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="88915-116">Passare alla sezione **Aggiornamenti di Intelligence per la** sicurezza e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="88915-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="88915-117">Impostare Forza un aggiornamento della sicurezza intelligence se il computer client è offline per più di **due aggiornamenti pianificati consecutivi** su **Sì.**</span><span class="sxs-lookup"><span data-stu-id="88915-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="88915-118">Per se Configuration Manager viene utilizzato come origine per gli aggiornamenti delle funzionalità di intelligence per la  **sicurezza...**, specificare le ore prima delle quali gli aggiornamenti di protezione recapitati da Configuration Manager devono essere considerati non aggiornati.</span><span class="sxs-lookup"><span data-stu-id="88915-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="88915-119">In questo modo verrà utilizzato il percorso di aggiornamento successivo, in base all'ordine di [origine di fallback definito.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)</span><span class="sxs-lookup"><span data-stu-id="88915-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="88915-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="88915-120">Click **OK**.</span></span>

4.  <span data-ttu-id="88915-121">[Distribuire il criterio aggiornato come al solito.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="88915-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="88915-122">Usare Criteri di gruppo per abilitare e configurare la funzionalità di aggiornamento di blocco</span><span class="sxs-lookup"><span data-stu-id="88915-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="88915-123">Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="88915-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="88915-124">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="88915-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="88915-125">Fare **clic su Criteri** e quindi su Modelli **amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="88915-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="88915-126">Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender > aggiornamenti delle firme**.</span><span class="sxs-lookup"><span data-stu-id="88915-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="88915-127">Fare doppio clic sull'impostazione Definisci il numero di giorni dopo il quale è necessario un aggiornamento **di intelligence** per la sicurezza e impostare l'opzione su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="88915-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="88915-128">Immettere il numero di giorni dopo i quali si desidera che Microsoft Defender AV controlli e scarii il più recente aggiornamento della protezione.</span><span class="sxs-lookup"><span data-stu-id="88915-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="88915-129">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="88915-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="88915-130">Utilizzare i cmdlet di PowerShell per configurare gli aggiornamenti di protezione da recuperare</span><span class="sxs-lookup"><span data-stu-id="88915-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="88915-131">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="88915-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="88915-132">Per ulteriori informazioni su come usare PowerShell con Antivirus Microsoft Defender, vedere Use [PowerShell cmdlets to configure](use-powershell-cmdlets-microsoft-defender-antivirus.md) and Antivirus Microsoft Defender run Antivirus Microsoft Defender and [Defender cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="88915-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="88915-133">Utilizzare Windows Management Instruction (WMI) per configurare gli aggiornamenti di protezione di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="88915-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="88915-134">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="88915-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="88915-135">Per ulteriori informazioni e parametri consentiti, vedere:</span><span class="sxs-lookup"><span data-stu-id="88915-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="88915-136">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="88915-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="88915-137">Impostare il numero di giorni prima che la protezione venga segnalata come non aggiornata</span><span class="sxs-lookup"><span data-stu-id="88915-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="88915-138">È inoltre possibile specificare il numero di giorni dopo i quali la protezione Antivirus Microsoft Defender è considerata precedente o non aggiornata.</span><span class="sxs-lookup"><span data-stu-id="88915-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="88915-139">Dopo il numero di giorni specificato, il client segnala se stesso come non aggiornato e visualizza un errore all'utente del PC.</span><span class="sxs-lookup"><span data-stu-id="88915-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="88915-140">Può anche causare Antivirus Microsoft Defender di tentare di scaricare un aggiornamento da altre origini (in base all'ordine di [origine di fallback](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)definito), ad esempio quando si utilizza MMPC come origine secondaria dopo aver impostato WSUS o Microsoft Update come prima origine.</span><span class="sxs-lookup"><span data-stu-id="88915-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="88915-141">Utilizzare Criteri di gruppo per specificare il numero di giorni prima che la protezione venga considerata non aggiornata</span><span class="sxs-lookup"><span data-stu-id="88915-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="88915-142">Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="88915-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="88915-143">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="88915-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="88915-144">Fare **clic su Criteri** e quindi su Modelli **amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="88915-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="88915-145">Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender > aggiornamenti delle firme** e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="88915-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="88915-146">Fare doppio clic su Definisci il numero di giorni prima che le definizioni **di spyware** siano considerate non aggiornate e impostare l'opzione su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="88915-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="88915-147">Immettere il numero di giorni dopo i quali si desidera che Microsoft Defender AV consideri l'intelligence di sicurezza spyware non aggiornata.</span><span class="sxs-lookup"><span data-stu-id="88915-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="88915-148">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="88915-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="88915-149">Fare doppio clic **su Definisci il numero di giorni** prima che le definizioni di virus siano considerate non aggiornate e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="88915-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="88915-150">Immettere il numero di giorni dopo i quali si desidera che Microsoft Defender AV consideri l'intelligence per la sicurezza antivirus non aggiornata.</span><span class="sxs-lookup"><span data-stu-id="88915-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="88915-151">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="88915-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="88915-152">Configurare le analisi di catch-up per gli endpoint che non sono stati analizzati per un po' di tempo</span><span class="sxs-lookup"><span data-stu-id="88915-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="88915-153">È possibile impostare il numero di analisi pianificate consecutive che possono essere perse prima Antivirus Microsoft Defender forzare un'analisi.</span><span class="sxs-lookup"><span data-stu-id="88915-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="88915-154">Il processo per l'abilitazione di questa funzionalità è il seguente:</span><span class="sxs-lookup"><span data-stu-id="88915-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="88915-155">Configurare almeno un'analisi pianificata (vedere [l'argomento Pianificare le](scheduled-catch-up-scans-microsoft-defender-antivirus.md) analisi).</span><span class="sxs-lookup"><span data-stu-id="88915-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="88915-156">Abilitare la funzionalità di analisi di acquisizione dati.</span><span class="sxs-lookup"><span data-stu-id="88915-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="88915-157">Definire il numero di analisi che possono essere ignorate prima che si verifichi un'analisi di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="88915-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="88915-158">Questa funzionalità può essere abilitata sia per le analisi complete che per le analisi rapide.</span><span class="sxs-lookup"><span data-stu-id="88915-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="88915-159">Utilizzare Criteri di gruppo per abilitare e configurare la funzionalità di analisi di catch-up</span><span class="sxs-lookup"><span data-stu-id="88915-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="88915-160">Assicurarsi di aver configurato almeno un'analisi pianificata.</span><span class="sxs-lookup"><span data-stu-id="88915-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="88915-161">Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="88915-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="88915-162">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="88915-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="88915-163">Fare **clic su Criteri** e quindi su Modelli **amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="88915-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="88915-164">Espandere l'albero per **Windows componenti > Antivirus Microsoft Defender > analisi** e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="88915-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="88915-165">Se sono state impostate analisi rapide pianificate, fare doppio clic sull'impostazione Attiva analisi rapida di acquisizione e impostare l'opzione su **Abilitato.** </span><span class="sxs-lookup"><span data-stu-id="88915-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="88915-166">Se sono state impostate analisi complete pianificate, fare doppio clic sull'impostazione Attiva analisi completa di acquisizione completa e impostare l'opzione su **Abilitato.** </span><span class="sxs-lookup"><span data-stu-id="88915-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="88915-167">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="88915-167">Click **OK**.</span></span>
    3. <span data-ttu-id="88915-168">Fare doppio clic sull'impostazione Definisci il numero di giorni dopo i quali viene forzata un'analisi di **catch-up** e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="88915-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="88915-169">Immetti il numero di analisi che possono essere perse prima che un'analisi venga eseguita automaticamente quando l'utente accede al PC.</span><span class="sxs-lookup"><span data-stu-id="88915-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="88915-170">Il tipo di analisi eseguito è determinato dall'argomento Specificare il tipo di analisi da **utilizzare** per un'analisi pianificata (vedere l'argomento [Pianifica](scheduled-catch-up-scans-microsoft-defender-antivirus.md) analisi).</span><span class="sxs-lookup"><span data-stu-id="88915-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="88915-171">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="88915-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="88915-172">Il titolo dell'impostazione di Criteri di gruppo fa riferimento al numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="88915-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="88915-173">L'impostazione, tuttavia, viene applicata al numero di analisi (non giorni) prima dell'esecuzione dell'analisi di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="88915-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="88915-174">Utilizzare i cmdlet di PowerShell per configurare le analisi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="88915-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="88915-175">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="88915-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="88915-176">Per ulteriori informazioni su come usare [PowerShell con Antivirus Microsoft Defender,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Usare i cmdlet di Power Antivirus Microsoft Defender Shell per gestire i cmdlet di Antivirus Microsoft Defender e [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="88915-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="88915-177">Utilizzare Windows Management Instruction (WMI) per configurare le analisi di catch-up</span><span class="sxs-lookup"><span data-stu-id="88915-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="88915-178">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="88915-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="88915-179">Per ulteriori informazioni e parametri consentiti, vedere:</span><span class="sxs-lookup"><span data-stu-id="88915-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="88915-180">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="88915-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="88915-181">Usare Configuration Manager per configurare le analisi di catch-up</span><span class="sxs-lookup"><span data-stu-id="88915-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="88915-182">Nella console Microsoft Endpoint Manager, aprire il criterio antimalware che si desidera modificare (fare clic su Asset **e** conformità nel riquadro di spostamento a sinistra, quindi espandere l'albero fino a Panoramica Endpoint Protection  >    >  **Criteri antimalware**)</span><span class="sxs-lookup"><span data-stu-id="88915-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="88915-183">Passare alla sezione **Analisi pianificate** e **Forzare un'analisi** del tipo di analisi selezionato se il computer client è offline... su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="88915-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="88915-184">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="88915-184">Click **OK**.</span></span>

4.  <span data-ttu-id="88915-185">[Distribuire il criterio aggiornato come al solito.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="88915-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="88915-186">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="88915-186">Related articles</span></span>

- [<span data-ttu-id="88915-187">Distribuire Antivirus Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="88915-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="88915-188">Gestire Antivirus Microsoft Defender aggiornamenti e applicare linee di base</span><span class="sxs-lookup"><span data-stu-id="88915-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="88915-189">Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="88915-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="88915-190">Gestire gli aggiornamenti forzati basati su eventi</span><span class="sxs-lookup"><span data-stu-id="88915-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="88915-191">Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali (VMS)</span><span class="sxs-lookup"><span data-stu-id="88915-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="88915-192">Antivirus Microsoft Defender in Windows 10</span><span class="sxs-lookup"><span data-stu-id="88915-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)