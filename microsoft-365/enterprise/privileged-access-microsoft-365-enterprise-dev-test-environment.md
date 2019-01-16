---
title: Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 Enterprise
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: Utilizzare questa guida dei laboratori di testing per abilitare la gestione degli accessi privilegiato l'ambiente di testing Microsoft 365 Enterprise.
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868287"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="58c28-103">Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="58c28-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="58c28-104">Con le istruzioni riportate in questo articolo, configurare la gestione dei privilegi di accesso per aumentare la protezione dell'ambiente di test Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="58c28-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="58c28-106">Fare clic [qui](https://aka.ms/m365etlgstack) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="58c28-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="58c28-107">Fase 1: Preparare l'ambiente di testing Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="58c28-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="58c28-108">Se si desidera configurare la gestione dei privilegi di accesso in un modo semplice con i requisiti minimi, seguire le istruzioni di [configurazione di base semplificata](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="58c28-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="58c28-109">Se si desidera configurare l'accesso con privilegi management in un'azienda simulata, seguire le istruzioni [nell'autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="58c28-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="58c28-p101">Test di gestione con privilegi di accesso non richiede l'ambiente di testing simulato enterprise, che include una rete intranet simulata connessione a Internet e la sincronizzazione delle directory per una foresta Windows Server Active Directory. Di seguito viene fornito come opzione in modo che è possibile testare con privilegi accedere a gestione e sperimentare in un ambiente che rappresenta una tipica organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58c28-p101">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="58c28-112">Fase 2: Configurare la gestione dei privilegi di accesso</span><span class="sxs-lookup"><span data-stu-id="58c28-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="58c28-p102">In questa fase, configurare un gruppo di responsabili approvazione e abilitare la gestione dell'accesso con privilegi per l'ambiente di testing Microsoft 365 Enterprise. Per ulteriori dettagli e una panoramica dei privilegi di accesso gestione, vedere [accesso privilegiato management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="58c28-p102">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment. For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="58c28-115">Eseguire la procedura seguente per configurare e utilizzare i privilegi di accesso nella propria organizzazione Office 365:</span><span class="sxs-lookup"><span data-stu-id="58c28-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="58c28-116">Passaggio 1: Creare il gruppo del revisore</span><span class="sxs-lookup"><span data-stu-id="58c28-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    <span data-ttu-id="58c28-p103">Prima di iniziare a utilizzare accesso privilegi, determinare chi avrà autorità approvazione delle richieste in ingresso per l'accesso alle attività con privilegi elevate e privilegiata. Qualsiasi utente che fa parte del gruppo dei responsabili approvazione saranno in grado di approvare le richieste di accesso. Questa opzione è attivata mediante la creazione di un gruppo di protezione abilitati alla posta elettronica in Office 365. Creare un nuovo gruppo di sicurezza denominato "Revisori con privilegi di accesso" nell'ambiente di testing e aggiungere il "utente 3" creato in precedenza nei passaggi Guida laboratorio di testing precedente.</span><span class="sxs-lookup"><span data-stu-id="58c28-p103">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365. Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="58c28-121">Passaggio 2: Abilitare l'accesso con privilegiato</span><span class="sxs-lookup"><span data-stu-id="58c28-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    <span data-ttu-id="58c28-p104">Accesso privilegiato deve essere attivata in modo esplicito in Office 365 gruppo responsabile approvazione predefinito, incluso un set di account di sistema che si desidera vengano esclusi dal controllo dell'accesso Gestione accesso privilegiato. È necessario abilitare l'accesso con privilegiato nella propria organizzazione Office 365 prima di avviare fase 3 della presente Guida.</span><span class="sxs-lookup"><span data-stu-id="58c28-p104">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control. Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="58c28-124">Fase 3: Verificare che l'approvazione è necessaria per le attività con privilegi elevate e privilegiata</span><span class="sxs-lookup"><span data-stu-id="58c28-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>
<span data-ttu-id="58c28-125">In questa fase, verificare che sia attivo il criterio di accesso con privilegi e gli utenti richiedono l'approvazione di eseguire attività con privilegi elevate e privilegiata definita.</span><span class="sxs-lookup"><span data-stu-id="58c28-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="58c28-126">Possibilità di eseguire un'attività non è definita nei criteri di accesso con privilegi di testing</span><span class="sxs-lookup"><span data-stu-id="58c28-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="58c28-p105">Per prima cosa, connettersi a PowerShell per Exchange Management con le credenziali di un utente configurato come amministratore globale nell'ambiente di testing e tenta di creare una nuova regola del Journal. L'attività [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) non è attualmente definito nei criteri di accesso con privilegi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="58c28-p105">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule. The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="58c28-129">Nel computer locale, aprire e accedere ai di Exchange Online Remote PowerShell Module presso **Microsoft Corporation** > **Microsoft Exchange Online PowerShell modulo remoto** tramite Amministratore globale per gli account per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="58c28-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="58c28-130">In Exchange Management Powershell, creare una nuova regola del Journal dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="58c28-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. <span data-ttu-id="58c28-131">Visualizzazione in cui è stata correttamente la nuova regola di Journal creata in Exchange PowerShell Management.</span><span class="sxs-lookup"><span data-stu-id="58c28-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="58c28-132">Creare un nuovo criterio di accesso con privilegi per l'attività New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="58c28-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="58c28-133">Se non sono già stati completati i passaggi 1 e 2 della fase 2 della presente Guida, essere certi segui i passaggi per creare gruppo un responsabile dell'approvazione denominato "Principio dei privilegi responsabili approvazione accesso" e consentire l'accesso con privilegiato nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="58c28-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="58c28-134">Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali l'account amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="58c28-134">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="58c28-135">Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="58c28-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="58c28-136">Selezionare **le richieste e gestire i criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="58c28-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="58c28-137">Selezionare **Configura criteri** e selezionare **Aggiungi un criterio**.</span><span class="sxs-lookup"><span data-stu-id="58c28-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="58c28-138">Dai campi a discesa, selezionare o immettere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="58c28-138">From the drop-down fields, select or enter the following values:</span></span>
    
    <span data-ttu-id="58c28-139">**Tipo di criterio**: attività</span><span class="sxs-lookup"><span data-stu-id="58c28-139">**Policy type**: Task</span></span>

    <span data-ttu-id="58c28-140">**Ambito dei criteri**: Exchange</span><span class="sxs-lookup"><span data-stu-id="58c28-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="58c28-141">**Nome del criterio**: nuova regola di Journal</span><span class="sxs-lookup"><span data-stu-id="58c28-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="58c28-142">**Tipo di approvazione**: manuale</span><span class="sxs-lookup"><span data-stu-id="58c28-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="58c28-143">**Gruppo di approvazione**: responsabili approvazione con privilegi di accesso</span><span class="sxs-lookup"><span data-stu-id="58c28-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="58c28-p106">Selezionare **Crea** e quindi **Chiudi**. Potrebbe richiedere alcuni minuti per il criterio da configurare e abilitare completamente. Assicurarsi di concedere il tempo per il criterio da abilitare completamente prima di verificare la richiesta di approvazione nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="58c28-p106">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled. Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="58c28-147">Richiesta di approvazione per l'attività New-JournalRule definito nei criteri di accesso con privilegi di testing</span><span class="sxs-lookup"><span data-stu-id="58c28-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="58c28-148">Nel computer locale, aprire e accedere ai di Exchange Online Remote PowerShell Module presso **Microsoft Corporation** > **Microsoft Exchange Online PowerShell modulo remoto** tramite un amministratore globale utilizzando gli account per il test ambiente.</span><span class="sxs-lookup"><span data-stu-id="58c28-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="58c28-149">In Exchange Management Powershell, creare una nuova regola del Journal dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="58c28-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="58c28-150">Visualizza l'errore "Insufficiente autorizzazioni" in Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="58c28-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="58c28-151">Richiedere l'accesso per creare una nuova regola di Journal tramite l'attività New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="58c28-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="58c28-152">Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando l'account amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="58c28-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="58c28-153">Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="58c28-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="58c28-154">Selezionare **le richieste e gestire i criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="58c28-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="58c28-p107">Selezionare **nuova richiesta**. I campi di riepilogo a discesa, selezionare i valori appropriati per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="58c28-p107">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="58c28-157">**Tipo di richiesta**: attività</span><span class="sxs-lookup"><span data-stu-id="58c28-157">**Request type**: Task</span></span>

    <span data-ttu-id="58c28-158">**Richiedere ambito**: Exchange</span><span class="sxs-lookup"><span data-stu-id="58c28-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="58c28-159">**Richiedere per**: nuova regola di Journal</span><span class="sxs-lookup"><span data-stu-id="58c28-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="58c28-160">**Durata (ore)**: 2</span><span class="sxs-lookup"><span data-stu-id="58c28-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="58c28-161">**Commenti**: richiedere l'autorizzazione per creare una nuova regola di Journal</span><span class="sxs-lookup"><span data-stu-id="58c28-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="58c28-p108">Selezionare **Salva** , quindi **Chiudi**. La richiesta verrà inviata al gruppo del revisore tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="58c28-p108">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="58c28-164">Approvare le richieste di accesso con privilegi per la creazione di una nuova regola di Journal</span><span class="sxs-lookup"><span data-stu-id="58c28-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="58c28-165">Accedere a [Microsoft 365 Admin Center](https://portal.office.com) utilizzando le credenziali per l'utente 3 nell'ambiente di testing (membro del gruppo di protezione "Revisori con privilegi di accesso" nell'ambiente di testing).</span><span class="sxs-lookup"><span data-stu-id="58c28-165">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="58c28-166">Nell'interfaccia di amministrazione di accedere alle **Impostazioni** > **sulla Privacy e sicurezza** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="58c28-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="58c28-167">Selezionare **le richieste e gestire i criteri di accesso**.</span><span class="sxs-lookup"><span data-stu-id="58c28-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="58c28-p109">Selezionare la richiesta in sospeso e scegliere **Approva** per concedere l'accesso all'account amministratore globale per creare una nuova regola del Journal. Verrà inviato un messaggio di posta elettronica di notifica per confermare che è stato concesso l'approvazione per l'account amministratore globale (richiedente utente).</span><span class="sxs-lookup"><span data-stu-id="58c28-p109">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule. An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="58c28-170">Crea una nuova regola di Journal con privilegi di accesso approvata per l'attività New-JournalRule test</span><span class="sxs-lookup"><span data-stu-id="58c28-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="58c28-171">Nel computer locale, aprire e accedere ai di Exchange Online Remote PowerShell Module presso **Microsoft Corporation** > **Microsoft Exchange Online PowerShell modulo remoto** tramite Amministratore globale per gli account per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="58c28-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="58c28-172">In Exchange Management Powershell, creare una nuova regola del Journal dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="58c28-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="58c28-173">Visualizzazione in cui è stata correttamente la nuova regola di Journal creata in Exchange PowerShell Management.</span><span class="sxs-lookup"><span data-stu-id="58c28-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="58c28-174">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="58c28-174">Next step</span></span>

<span data-ttu-id="58c28-175">Esplorare le funzionalità aggiuntive [la protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) e le funzionalità nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="58c28-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="58c28-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="58c28-176">See also</span></span>

[<span data-ttu-id="58c28-177">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="58c28-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="58c28-178">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="58c28-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="58c28-179">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="58c28-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)