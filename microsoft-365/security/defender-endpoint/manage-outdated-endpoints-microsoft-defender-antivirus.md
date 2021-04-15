---
title: Applicare gli aggiornamenti della protezione di Microsoft Defender AV agli endpoint non aggiornati
description: Definire quando e come applicare gli aggiornamenti per gli endpoint che non sono stati aggiornati da un po'.
keywords: aggiornamenti, protezione, non aggiornato, obsoleto, vecchio, catch-up
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 81c7fb2bb7cd20fea3f343097811078ed744c3eb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765372"
---
# <a name="manage-microsoft-defender-antivirus-updates-and-scans-for-endpoints-that-are-out-of-date"></a><span data-ttu-id="b556d-104">Gestire gli aggiornamenti e le analisi di Microsoft Defender Antivirus per gli endpoint non aggiornati</span><span class="sxs-lookup"><span data-stu-id="b556d-104">Manage Microsoft Defender Antivirus updates and scans for endpoints that are out of date</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b556d-105">**Si applica a:**</span><span class="sxs-lookup"><span data-stu-id="b556d-105">**Applies to:**</span></span>

- [<span data-ttu-id="b556d-106">Microsoft Defender per endpoint</span><span class="sxs-lookup"><span data-stu-id="b556d-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b556d-107">Microsoft Defender Antivirus consente di definire per quanto tempo un endpoint può evitare un aggiornamento o il numero di analisi che può perdere prima di essere necessario per l'aggiornamento e l'analisi stessa.</span><span class="sxs-lookup"><span data-stu-id="b556d-107">Microsoft Defender Antivirus lets you define how long an endpoint can avoid an update or how many scans it can miss before it is required to update and scan itself.</span></span> <span data-ttu-id="b556d-108">Ciò è particolarmente utile in ambienti in cui i dispositivi non sono spesso connessi a una rete aziendale o esterna o in dispositivi che non vengono utilizzati quotidianamente.</span><span class="sxs-lookup"><span data-stu-id="b556d-108">This is especially useful in environments where devices are not often connected to a corporate or external network, or devices that are not used on a daily basis.</span></span>

<span data-ttu-id="b556d-109">Ad esempio, un dipendente che usa un PC specifico è in pausa per tre giorni e non accede al PC durante tale periodo.</span><span class="sxs-lookup"><span data-stu-id="b556d-109">For example, an employee that uses a particular PC is on break for three days and does not log on to their PC during that time.</span></span>

<span data-ttu-id="b556d-110">Quando l'utente torna a lavorare e accede al PC, Microsoft Defender Antivirus controllera' immediatamente e scarichi gli aggiornamenti di protezione più recenti ed eseguirà un'analisi.</span><span class="sxs-lookup"><span data-stu-id="b556d-110">When the user returns to work and logs on to their PC, Microsoft Defender Antivirus will immediately check and download the latest protection updates, and run a scan.</span></span>

## <a name="set-up-catch-up-protection-updates-for-endpoints-that-havent-updated-for-a-while"></a><span data-ttu-id="b556d-111">Configurare gli aggiornamenti di protezione da recuperare per gli endpoint che non sono stati aggiornati per un po' di tempo</span><span class="sxs-lookup"><span data-stu-id="b556d-111">Set up catch-up protection updates for endpoints that haven't updated for a while</span></span>

<span data-ttu-id="b556d-112">Se Microsoft Defender Antivirus non ha scaricato gli aggiornamenti di protezione per un periodo specificato, è possibile configurarlo per controllare e scaricare automaticamente l'aggiornamento più recente al successivo accesso.</span><span class="sxs-lookup"><span data-stu-id="b556d-112">If Microsoft Defender Antivirus did not download protection updates for a specified period, you can set it up to automatically check and download the latest update at the next log on.</span></span> <span data-ttu-id="b556d-113">Ciò è utile se all'avvio sono stati disabilitati a livello globale i [download degli aggiornamenti automatici.](manage-event-based-updates-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b556d-113">This is useful if you have [globally disabled automatic update downloads on startup](manage-event-based-updates-microsoft-defender-antivirus.md).</span></span>

### <a name="use-configuration-manager-to-configure-catch-up-protection-updates"></a><span data-ttu-id="b556d-114">Usare Configuration Manager per configurare gli aggiornamenti di protezione di blocco</span><span class="sxs-lookup"><span data-stu-id="b556d-114">Use Configuration Manager to configure catch-up protection updates</span></span>

1.  <span data-ttu-id="b556d-115">Nella console di Microsoft Endpoint Manager apri i criteri antimalware che vuoi modificare (fai clic su Asset  **e** conformità nel riquadro di spostamento a sinistra, quindi espandi l'albero fino a Panoramica criteri  >    >  **antimalware** di Endpoint Protection)</span><span class="sxs-lookup"><span data-stu-id="b556d-115">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="b556d-116">Passare alla sezione **Aggiornamenti di Intelligence per la** sicurezza e configurare le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b556d-116">Go to the **Security intelligence updates** section and configure the following settings:</span></span>

    1. <span data-ttu-id="b556d-117">Impostare Forza un aggiornamento della sicurezza intelligence se il computer client è offline per più di **due aggiornamenti pianificati consecutivi** su **Sì.**</span><span class="sxs-lookup"><span data-stu-id="b556d-117">Set **Force a security intelligence update if the client computer is offline for more than two consecutive scheduled updates** to **Yes**.</span></span>
    2. <span data-ttu-id="b556d-118">Per se Configuration Manager viene utilizzato come origine per gli aggiornamenti delle funzionalità di intelligence per la  **sicurezza...**, specificare le ore prima delle quali gli aggiornamenti di protezione recapitati da Configuration Manager devono essere considerati non aggiornati.</span><span class="sxs-lookup"><span data-stu-id="b556d-118">For the  **If Configuration Manager is used as a source for security intelligence updates...**, specify the hours before which the protection updates delivered by Configuration Manager should be considered out-of-date.</span></span> <span data-ttu-id="b556d-119">In questo modo verrà utilizzato il percorso di aggiornamento successivo, in base all'ordine di [origine di fallback definito.](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)</span><span class="sxs-lookup"><span data-stu-id="b556d-119">This will cause the next update location to be used, based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order).</span></span>

3. <span data-ttu-id="b556d-120">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b556d-120">Click **OK**.</span></span>

4.  <span data-ttu-id="b556d-121">[Distribuire il criterio aggiornato come al solito.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="b556d-121">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-update-feature"></a><span data-ttu-id="b556d-122">Usare Criteri di gruppo per abilitare e configurare la funzionalità di aggiornamento di blocco</span><span class="sxs-lookup"><span data-stu-id="b556d-122">Use Group Policy to enable and configure the catch-up update feature</span></span>

1. <span data-ttu-id="b556d-123">Nel computer di gestione di Criteri di gruppo, aprire console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b556d-123">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

2. <span data-ttu-id="b556d-124">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="b556d-124">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

3. <span data-ttu-id="b556d-125">Fare **clic su Criteri** e quindi su Modelli **amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="b556d-125">Click **Policies** then **Administrative templates**.</span></span>

4. <span data-ttu-id="b556d-126">Espandi l'albero **fino ai componenti di Windows > Microsoft Defender Antivirus > aggiornamenti delle firme**.</span><span class="sxs-lookup"><span data-stu-id="b556d-126">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates**.</span></span>

5. <span data-ttu-id="b556d-127">Fare doppio clic sull'impostazione Definisci il numero di giorni dopo il quale è necessario un aggiornamento **di intelligence** per la sicurezza e impostare l'opzione su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="b556d-127">Double-click the **Define the number of days after which a catch-up security intelligence update is required** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="b556d-128">Immettere il numero di giorni dopo i quali si desidera che Microsoft Defender AV controlli e scarii il più recente aggiornamento della protezione.</span><span class="sxs-lookup"><span data-stu-id="b556d-128">Enter the number of days after which you want Microsoft Defender AV to check for and download the latest protection update.</span></span>

6. <span data-ttu-id="b556d-129">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b556d-129">Click **OK**.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-protection-updates"></a><span data-ttu-id="b556d-130">Utilizzare i cmdlet di PowerShell per configurare gli aggiornamenti di protezione da recuperare</span><span class="sxs-lookup"><span data-stu-id="b556d-130">Use PowerShell cmdlets to configure catch-up protection updates</span></span>

<span data-ttu-id="b556d-131">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="b556d-131">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -SignatureUpdateCatchupInterval
```

<span data-ttu-id="b556d-132">Per ulteriori informazioni su come usare PowerShell con Microsoft [Defender Antivirus,](use-powershell-cmdlets-microsoft-defender-antivirus.md) vedere Utilizzare i cmdlet di PowerShell per configurare ed eseguire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="b556d-132">See [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-protection-updates"></a><span data-ttu-id="b556d-133">Utilizzare Windows Management Instruction (WMI) per configurare gli aggiornamenti di protezione di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="b556d-133">Use Windows Management Instruction (WMI) to configure catch-up protection updates</span></span>

<span data-ttu-id="b556d-134">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="b556d-134">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
SignatureUpdateCatchupInterval
```

<span data-ttu-id="b556d-135">Per ulteriori informazioni e parametri consentiti, vedere:</span><span class="sxs-lookup"><span data-stu-id="b556d-135">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="b556d-136">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="b556d-136">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


## <a name="set-the-number-of-days-before-protection-is-reported-as-out-of-date"></a><span data-ttu-id="b556d-137">Impostare il numero di giorni prima che la protezione venga segnalata come non aggiornata</span><span class="sxs-lookup"><span data-stu-id="b556d-137">Set the number of days before protection is reported as out-of-date</span></span>

<span data-ttu-id="b556d-138">Puoi anche specificare il numero di giorni dopo i quali la protezione antivirus di Microsoft Defender è considerata vecchia o non aggiornata.</span><span class="sxs-lookup"><span data-stu-id="b556d-138">You can also specify the number of days after which Microsoft Defender Antivirus protection is considered old or out-of-date.</span></span> <span data-ttu-id="b556d-139">Dopo il numero di giorni specificato, il client segnala se stesso come non aggiornato e visualizza un errore all'utente del PC.</span><span class="sxs-lookup"><span data-stu-id="b556d-139">After the specified number of days, the client will report itself as out-of-date, and show an error to the user of the PC.</span></span> <span data-ttu-id="b556d-140">Potrebbe anche causare il tentativo di scaricare un aggiornamento da altre origini (in base all'ordine di origine di [fallback](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)definito), ad esempio quando si usa MMPC come origine secondaria dopo aver impostato WSUS o Microsoft Update come prima origine.</span><span class="sxs-lookup"><span data-stu-id="b556d-140">It may also cause Microsoft Defender Antivirus to attempt to download an update from other sources (based on the defined [fallback source order](manage-protection-updates-microsoft-defender-antivirus.md#fallback-order)), such as when using MMPC as a secondary source after setting WSUS or Microsoft Update as the first source.</span></span>

### <a name="use-group-policy-to-specify-the-number-of-days-before-protection-is-considered-out-of-date"></a><span data-ttu-id="b556d-141">Utilizzare Criteri di gruppo per specificare il numero di giorni prima che la protezione venga considerata non aggiornata</span><span class="sxs-lookup"><span data-stu-id="b556d-141">Use Group Policy to specify the number of days before protection is considered out-of-date</span></span>

1.  <span data-ttu-id="b556d-142">Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b556d-142">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="b556d-143">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="b556d-143">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="b556d-144">Fare **clic su Criteri** e quindi su Modelli **amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="b556d-144">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="b556d-145">Espandi l'albero **fino ai componenti di Windows > Microsoft Defender Antivirus > aggiornamenti** delle firme e configura le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b556d-145">Expand the tree to **Windows components > Microsoft Defender Antivirus > Signature Updates** and configure the following settings:</span></span>

    1.  <span data-ttu-id="b556d-146">Fare doppio clic su Definisci il numero di giorni prima che le definizioni **di spyware** siano considerate non aggiornate e impostare l'opzione su **Abilitato**.</span><span class="sxs-lookup"><span data-stu-id="b556d-146">Double-click **Define the number of days before spyware definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="b556d-147">Immettere il numero di giorni dopo i quali si desidera che Microsoft Defender AV consideri l'intelligence di sicurezza spyware non aggiornata.</span><span class="sxs-lookup"><span data-stu-id="b556d-147">Enter the number of days after which you want Microsoft Defender AV to consider spyware Security intelligence to be out-of-date.</span></span>

    2. <span data-ttu-id="b556d-148">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b556d-148">Click **OK**.</span></span>

    3.  <span data-ttu-id="b556d-149">Fare doppio clic **su Definisci il numero di giorni** prima che le definizioni di virus siano considerate non aggiornate e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="b556d-149">Double-click **Define the number of days before virus definitions are considered out of date** and set the option to **Enabled**.</span></span> <span data-ttu-id="b556d-150">Immettere il numero di giorni dopo i quali si desidera che Microsoft Defender AV consideri l'intelligence per la sicurezza antivirus non aggiornata.</span><span class="sxs-lookup"><span data-stu-id="b556d-150">Enter the number of days after which you want Microsoft Defender AV to consider virus Security intelligence to be out-of-date.</span></span>

    4. <span data-ttu-id="b556d-151">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b556d-151">Click **OK**.</span></span>


## <a name="set-up-catch-up-scans-for-endpoints-that-have-not-been-scanned-for-a-while"></a><span data-ttu-id="b556d-152">Configurare le analisi di catch-up per gli endpoint che non sono stati analizzati per un po' di tempo</span><span class="sxs-lookup"><span data-stu-id="b556d-152">Set up catch-up scans for endpoints that have not been scanned for a while</span></span>

<span data-ttu-id="b556d-153">È possibile impostare il numero di analisi pianificate consecutive che possono essere perse prima che Microsoft Defender Antivirus forza un'analisi.</span><span class="sxs-lookup"><span data-stu-id="b556d-153">You can set the number of consecutive scheduled scans that can be missed before Microsoft Defender Antivirus will force a scan.</span></span>

<span data-ttu-id="b556d-154">Il processo per l'abilitazione di questa funzionalità è il seguente:</span><span class="sxs-lookup"><span data-stu-id="b556d-154">The process for enabling this feature is:</span></span>

1. <span data-ttu-id="b556d-155">Configurare almeno un'analisi pianificata (vedere [l'argomento Pianificare le](scheduled-catch-up-scans-microsoft-defender-antivirus.md) analisi).</span><span class="sxs-lookup"><span data-stu-id="b556d-155">Set up at least one scheduled scan (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span>
2. <span data-ttu-id="b556d-156">Abilitare la funzionalità di analisi di acquisizione dati.</span><span class="sxs-lookup"><span data-stu-id="b556d-156">Enable the catch-up scan feature.</span></span>
3. <span data-ttu-id="b556d-157">Definire il numero di analisi che possono essere ignorate prima che si verifichi un'analisi di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b556d-157">Define the number of scans that can be skipped before a catch-up scan occurs.</span></span>

<span data-ttu-id="b556d-158">Questa funzionalità può essere abilitata sia per le analisi complete che per le analisi rapide.</span><span class="sxs-lookup"><span data-stu-id="b556d-158">This feature can be enabled for both full and quick scans.</span></span>

### <a name="use-group-policy-to-enable-and-configure-the-catch-up-scan-feature"></a><span data-ttu-id="b556d-159">Utilizzare Criteri di gruppo per abilitare e configurare la funzionalità di analisi di catch-up</span><span class="sxs-lookup"><span data-stu-id="b556d-159">Use Group Policy to enable and configure the catch-up scan feature</span></span>

1.  <span data-ttu-id="b556d-160">Assicurarsi di aver configurato almeno un'analisi pianificata.</span><span class="sxs-lookup"><span data-stu-id="b556d-160">Ensure you have set up at least one scheduled scan.</span></span>

2.  <span data-ttu-id="b556d-161">Nel computer di gestione di Criteri di gruppo, aprire Console Gestione Criteri di [gruppo,](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))fare clic con il pulsante destro del mouse sull'oggetto Criteri di gruppo che si desidera configurare e scegliere **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="b556d-161">On your Group Policy management machine, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and click **Edit**.</span></span>

3.  <span data-ttu-id="b556d-162">**Nell'Editor Gestione Criteri di gruppo** passare a Configurazione **computer**.</span><span class="sxs-lookup"><span data-stu-id="b556d-162">In the **Group Policy Management Editor** go to **Computer configuration**.</span></span>

4.  <span data-ttu-id="b556d-163">Fare **clic su Criteri** e quindi su Modelli **amministrativi.**</span><span class="sxs-lookup"><span data-stu-id="b556d-163">Click **Policies** then **Administrative templates**.</span></span>

5.  <span data-ttu-id="b556d-164">Espandi l'albero fino ai componenti **di Windows > Microsoft Defender Antivirus > analisi** e configura le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b556d-164">Expand the tree to **Windows components > Microsoft Defender Antivirus > Scan** and configure the following settings:</span></span>

    1.  <span data-ttu-id="b556d-165">Se sono state impostate analisi rapide pianificate, fare doppio clic sull'impostazione Attiva analisi rapida di acquisizione e impostare l'opzione su **Abilitato.** </span><span class="sxs-lookup"><span data-stu-id="b556d-165">If you have set up scheduled quick scans, double-click the **Turn on catch-up quick scan** setting and set the option to **Enabled**.</span></span> 
    2. <span data-ttu-id="b556d-166">Se sono state impostate analisi complete pianificate, fare doppio clic sull'impostazione Attiva analisi completa di acquisizione completa e impostare l'opzione su **Abilitato.** </span><span class="sxs-lookup"><span data-stu-id="b556d-166">If you have set up scheduled full scans, double-click the **Turn on catch-up full scan** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="b556d-167">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b556d-167">Click **OK**.</span></span>
    3. <span data-ttu-id="b556d-168">Fare doppio clic sull'impostazione Definisci il numero di giorni dopo i quali viene forzata un'analisi di **catch-up** e impostare l'opzione su **Abilitato.**</span><span class="sxs-lookup"><span data-stu-id="b556d-168">Double-click the **Define the number of days after which a catch-up scan is forced** setting and set the option to **Enabled**.</span></span> 
    4. <span data-ttu-id="b556d-169">Immetti il numero di analisi che possono essere perse prima che un'analisi venga eseguita automaticamente quando l'utente accede al PC.</span><span class="sxs-lookup"><span data-stu-id="b556d-169">Enter the number of scans that can be missed before a scan will be automatically run when the user next logs on to the PC.</span></span> <span data-ttu-id="b556d-170">Il tipo di analisi eseguito è determinato dall'argomento Specificare il tipo di analisi da **utilizzare** per un'analisi pianificata (vedere l'argomento [Pianifica](scheduled-catch-up-scans-microsoft-defender-antivirus.md) analisi).</span><span class="sxs-lookup"><span data-stu-id="b556d-170">The type of scan that is run is determined by the **Specify the scan type to use for a scheduled scan** (see the [Schedule scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md) topic).</span></span> <span data-ttu-id="b556d-171">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b556d-171">Click **OK**.</span></span>

> [!NOTE]
> <span data-ttu-id="b556d-172">Il titolo dell'impostazione di Criteri di gruppo fa riferimento al numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="b556d-172">The Group Policy setting title refers to the number of days.</span></span> <span data-ttu-id="b556d-173">L'impostazione, tuttavia, viene applicata al numero di analisi (non giorni) prima dell'esecuzione dell'analisi di aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b556d-173">The setting, however, is applied to the number of scans (not days) before the catch-up scan will be run.</span></span>

### <a name="use-powershell-cmdlets-to-configure-catch-up-scans"></a><span data-ttu-id="b556d-174">Utilizzare i cmdlet di PowerShell per configurare le analisi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="b556d-174">Use PowerShell cmdlets to configure catch-up scans</span></span>

<span data-ttu-id="b556d-175">Utilizzare i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="b556d-175">Use the following cmdlets:</span></span>

```PowerShell
Set-MpPreference -DisableCatchupFullScan
Set-MpPreference -DisableCatchupQuickScan

```

<span data-ttu-id="b556d-176">Per ulteriori informazioni su come usare [PowerShell con](use-powershell-cmdlets-microsoft-defender-antivirus.md) Microsoft Defender Antivirus, vedere Utilizzare i cmdlet di PowerShell per gestire i cmdlet di Microsoft Defender Antivirus e [Defender.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="b556d-176">See [Use PowerShell cmdlets to manage Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md)  and [Defender cmdlets](/powershell/module/defender/) for more information on how to use PowerShell with Microsoft Defender Antivirus.</span></span>

### <a name="use-windows-management-instruction-wmi-to-configure-catch-up-scans"></a><span data-ttu-id="b556d-177">Utilizzare Windows Management Instruction (WMI) per configurare le analisi di aggiornamento</span><span class="sxs-lookup"><span data-stu-id="b556d-177">Use Windows Management Instruction (WMI) to configure catch-up scans</span></span>

<span data-ttu-id="b556d-178">Utilizzare il [ **metodo Set** della **classe MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) per le proprietà seguenti:</span><span class="sxs-lookup"><span data-stu-id="b556d-178">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) class for the following properties:</span></span>

```WMI
DisableCatchupFullScan
DisableCatchupQuickScan
```

<span data-ttu-id="b556d-179">Per ulteriori informazioni e parametri consentiti, vedere:</span><span class="sxs-lookup"><span data-stu-id="b556d-179">See the following for more information and allowed parameters:</span></span>
- [<span data-ttu-id="b556d-180">Windows Defender API WMIv2</span><span class="sxs-lookup"><span data-stu-id="b556d-180">Windows Defender WMIv2 APIs</span></span>](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)


### <a name="use-configuration-manager-to-configure-catch-up-scans"></a><span data-ttu-id="b556d-181">Usare Configuration Manager per configurare le analisi di catch-up</span><span class="sxs-lookup"><span data-stu-id="b556d-181">Use Configuration Manager to configure catch-up scans</span></span>

1.  <span data-ttu-id="b556d-182">Nella console di Microsoft Endpoint Manager apri i criteri antimalware che vuoi modificare (fai clic su Asset  **e** conformità nel riquadro di spostamento a sinistra, quindi espandi l'albero fino a Panoramica criteri  >    >  **antimalware** di Endpoint Protection)</span><span class="sxs-lookup"><span data-stu-id="b556d-182">On your Microsoft Endpoint Manager console, open the antimalware policy you want to change (click **Assets and Compliance** in the navigation pane on the left, then expand the tree to **Overview** > **Endpoint Protection** > **Antimalware Policies**)</span></span>

2.  <span data-ttu-id="b556d-183">Passare alla sezione **Analisi pianificate** e **Forzare un'analisi** del tipo di analisi selezionato se il computer client è offline... su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="b556d-183">Go to the **Scheduled scans** section and **Force a scan of the selected scan type if client computer is offline...** to **Yes**.</span></span> 

3. <span data-ttu-id="b556d-184">Fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="b556d-184">Click **OK**.</span></span>

4.  <span data-ttu-id="b556d-185">[Distribuire il criterio aggiornato come al solito.](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers)</span><span class="sxs-lookup"><span data-stu-id="b556d-185">[Deploy the updated policy as usual](/sccm/protect/deploy-use/endpoint-antimalware-policies#deploy-an-antimalware-policy-to-client-computers).</span></span>

## <a name="related-articles"></a><span data-ttu-id="b556d-186">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="b556d-186">Related articles</span></span>

- [<span data-ttu-id="b556d-187">Distribuire Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="b556d-187">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b556d-188">Gestire gli aggiornamenti di Microsoft Defender Antivirus e applicare le linee di base</span><span class="sxs-lookup"><span data-stu-id="b556d-188">Manage Microsoft Defender Antivirus updates and apply baselines</span></span>](manage-updates-baselines-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b556d-189">Gestire quando devono essere scaricati e applicati gli aggiornamenti della protezione</span><span class="sxs-lookup"><span data-stu-id="b556d-189">Manage when protection updates should be downloaded and applied</span></span>](manage-protection-update-schedule-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b556d-190">Gestire gli aggiornamenti forzati basati su eventi</span><span class="sxs-lookup"><span data-stu-id="b556d-190">Manage event-based forced updates</span></span>](manage-event-based-updates-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b556d-191">Gestire gli aggiornamenti per dispositivi mobili e macchine virtuali</span><span class="sxs-lookup"><span data-stu-id="b556d-191">Manage updates for mobile devices and virtual machines (VMs)</span></span>](manage-updates-mobile-devices-vms-microsoft-defender-antivirus.md)
- [<span data-ttu-id="b556d-192">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="b556d-192">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)