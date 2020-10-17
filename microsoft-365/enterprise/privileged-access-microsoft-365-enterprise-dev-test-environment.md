---
title: Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 per l'organizzazione
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Utilizzare questa guida del laboratorio di testing per abilitare la gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365.
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487589"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="84efb-103">Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="84efb-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="84efb-104">*Questa guida del laboratorio di testing può essere utilizzata per ambienti di testing Microsoft 365 per Enterprise e Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="84efb-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="84efb-105">In questo articolo viene descritto come configurare la gestione degli accessi con privilegi per aumentare la sicurezza nell'ambiente di testing di Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84efb-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="84efb-106">La configurazione della gestione degli accessi di privilegiato comporta tre fasi:</span><span class="sxs-lookup"><span data-stu-id="84efb-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="84efb-107">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="84efb-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="84efb-108">Fase 2: configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="84efb-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="84efb-109">Fase 3: verificare che l'approvazione sia necessaria per le attività con privilegi elevati e</span><span class="sxs-lookup"><span data-stu-id="84efb-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Guide al lab di test per il cloud Microsoft](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="84efb-111">Per una mappa visiva su tutti gli articoli della guida del laboratorio di testing di Microsoft 365 for Enterprise, accedere a [microsoft 365 per la guida dello stack del laboratorio di testing dell'organizzazione](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="84efb-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="84efb-112">Fase 1: creare l'ambiente di testing di Microsoft 365 per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="84efb-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="84efb-113">Se si desidera configurare la gestione degli accessi con privilegi in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="84efb-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="84efb-114">Se si desidera configurare la gestione degli accessi con privilegi in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="84efb-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="84efb-115">Se si verifica la gestione degli accessi con privilegi non è necessario l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="84efb-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="84efb-116">È disponibile come opzione in modo che sia possibile testare la gestione degli accessi con privilegi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="84efb-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="84efb-117">Fase 2: configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="84efb-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="84efb-118">In questa fase, configurare un gruppo responsabili approvazione e abilitare la gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84efb-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="84efb-119">Per ulteriori informazioni e una panoramica della gestione degli accessi con privilegi, vedere [Privileged Access Management](../compliance/privileged-access-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="84efb-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="84efb-120">Per impostare e utilizzare l'accesso con privilegi nell'organizzazione, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="84efb-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="84efb-121">Passaggio 1: creare un gruppo del responsabile approvazione</span><span class="sxs-lookup"><span data-stu-id="84efb-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="84efb-122">Prima di iniziare a utilizzare l'accesso con privilegi, determinare chi avrà l'autorità di approvazione per le richieste in arrivo per l'accesso alle attività con privilegi elevati e di privilegio.</span><span class="sxs-lookup"><span data-stu-id="84efb-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="84efb-123">Tutti gli utenti che fanno parte del gruppo responsabili approvazione possono approvare le richieste di accesso.</span><span class="sxs-lookup"><span data-stu-id="84efb-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="84efb-124">Per utilizzare l'accesso con privilegi, è necessario creare un gruppo di sicurezza abilitato alla posta elettronica in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="84efb-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="84efb-125">Nell'ambiente di testing, denominare il nuovo gruppo di sicurezza "responsabili approvazione accesso privilegiato" e aggiungere "User 3" creato in precedenza nei passaggi precedenti della guida del laboratorio di testing.</span><span class="sxs-lookup"><span data-stu-id="84efb-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="84efb-126">Passaggio 2: abilitare l'accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="84efb-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="84efb-127">L'accesso privilegiato deve essere attivato in modo esplicito in Microsoft 365 con il gruppo di approvazione predefinito e deve includere un set di account di sistema che si desidera escludere dal controllo di accesso alla gestione degli accessi con privilegi.</span><span class="sxs-lookup"><span data-stu-id="84efb-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="84efb-128">Assicurarsi di abilitare l'accesso privilegiato nell'organizzazione prima di iniziare la fase 3 di questa guida.</span><span class="sxs-lookup"><span data-stu-id="84efb-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="84efb-129">Fase 3: verificare che l'approvazione sia necessaria per le attività con privilegi elevati e</span><span class="sxs-lookup"><span data-stu-id="84efb-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="84efb-130">In questa fase, verificare che il criterio di accesso privilegiato funzioni e che gli utenti dispongano dell'approvazione per l'esecuzione di attività definite con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="84efb-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="84efb-131">Testare la possibilità di eseguire un'attività non definita in un criterio di accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="84efb-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="84efb-132">Innanzitutto, connettersi a Exchange Management PowerShell con le credenziali di un utente configurato come amministratore globale nell'ambiente di testing e tentare di creare una nuova regola del journal.</span><span class="sxs-lookup"><span data-stu-id="84efb-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="84efb-133">L'attività [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) non è attualmente definita in un criterio di accesso con privilegi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="84efb-133">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="84efb-134">Nel computer locale, aprire e accedere al modulo Exchange Online Remote PowerShell nel modulo di PowerShell remoto Microsoft **Corporation**  >  **Microsoft Exchange Online** utilizzando l'account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="84efb-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="84efb-135">In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="84efb-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="84efb-136">Visualizzare la nuova regola del journal in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84efb-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="84efb-137">Creare un nuovo criterio di accesso privilegiato per l'attività di New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="84efb-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="84efb-138">Se non sono già stati completati i passaggi 1 e 2 della fase 2 della guida, seguire la procedura seguente per creare un gruppo del responsabile approvazione denominato "revisori di accesso Privilege" per abilitare l'accesso privilegiato nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="84efb-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="84efb-139">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali dell'account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="84efb-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="84efb-140">Nell'interfaccia di amministrazione, andare a **Impostazioni**di  >  **sicurezza & privacy**  >  **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="84efb-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="84efb-141">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="84efb-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="84efb-142">Selezionare **Configure policies**, quindi selezionare **Aggiungi un criterio**.</span><span class="sxs-lookup"><span data-stu-id="84efb-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="84efb-143">Nei campi a discesa selezionare o immettere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="84efb-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="84efb-144">**Tipo di criterio**: attività</span><span class="sxs-lookup"><span data-stu-id="84efb-144">**Policy type**: Task</span></span>

    <span data-ttu-id="84efb-145">**Ambito di criteri**: Exchange</span><span class="sxs-lookup"><span data-stu-id="84efb-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="84efb-146">**Nome criterio**: nuova regola del Journal</span><span class="sxs-lookup"><span data-stu-id="84efb-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="84efb-147">**Tipo di approvazione**: Manual</span><span class="sxs-lookup"><span data-stu-id="84efb-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="84efb-148">**Gruppo di approvazione**: responsabili approvazione accesso privilegiato</span><span class="sxs-lookup"><span data-stu-id="84efb-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="84efb-149">Selezionare **Crea**e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="84efb-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="84efb-150">È possibile che i criteri siano completamente configurati e abilitati per alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="84efb-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="84efb-151">Assicurarsi che il criterio venga abilitato completamente prima di testare il requisito di approvazione nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="84efb-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="84efb-152">Requisiti di approvazione del test per l'attività di New-JournalRule definita in un criterio di accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="84efb-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="84efb-153">Nel computer locale, aprire e accedere al modulo Exchange Online Remote PowerShell nel modulo di PowerShell remoto Microsoft **Corporation**  >  **Microsoft Exchange Online** utilizzando un account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="84efb-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="84efb-154">In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="84efb-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="84efb-155">Visualizzazione dell'errore "autorizzazioni insufficienti" in Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="84efb-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="84efb-156">Richiedere l'accesso per creare una nuova regola del journal utilizzando l'attività New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="84efb-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="84efb-157">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando l'account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="84efb-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="84efb-158">Nell'interfaccia di amministrazione, andare a **Impostazioni**di  >  **sicurezza & privacy**  >  **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="84efb-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="84efb-159">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="84efb-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="84efb-160">Selezionare **nuova richiesta**.</span><span class="sxs-lookup"><span data-stu-id="84efb-160">Select **New request**.</span></span> <span data-ttu-id="84efb-161">Nei campi a discesa selezionare i valori corretti per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="84efb-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="84efb-162">**Tipo di richiesta**: attività</span><span class="sxs-lookup"><span data-stu-id="84efb-162">**Request type**: Task</span></span>

    <span data-ttu-id="84efb-163">**Ambito delle richieste**: Exchange</span><span class="sxs-lookup"><span data-stu-id="84efb-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="84efb-164">**Richiesta per**: nuova regola del Journal</span><span class="sxs-lookup"><span data-stu-id="84efb-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="84efb-165">**Durata (ore)**: 2</span><span class="sxs-lookup"><span data-stu-id="84efb-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="84efb-166">**Commenti**: richiedere l'autorizzazione per la creazione di una nuova regola del Journal</span><span class="sxs-lookup"><span data-stu-id="84efb-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="84efb-167">Selezionare **Salva**e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="84efb-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="84efb-168">La richiesta verrà inviata al gruppo del responsabile dell'approvazione tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="84efb-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="84efb-169">Approva la richiesta di accesso privilegiato per la creazione di una nuova regola di Journal</span><span class="sxs-lookup"><span data-stu-id="84efb-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="84efb-170">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per l'utente 3 nell'ambiente di testing (membro del gruppo di sicurezza "responsabili approvazione accesso privilegiato" nell'ambiente di testing).</span><span class="sxs-lookup"><span data-stu-id="84efb-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="84efb-171">Nell'interfaccia di amministrazione, andare a **Impostazioni**di  >  **sicurezza & privacy**  >  **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="84efb-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="84efb-172">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="84efb-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="84efb-173">Selezionare la richiesta in sospeso, quindi selezionare **approva** per concedere l'accesso all'account di amministratore globale per creare una nuova regola del journal.</span><span class="sxs-lookup"><span data-stu-id="84efb-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="84efb-174">L'account di amministratore globale (l'utente richiedente) riceverà una conferma tramite posta elettronica che è stata concessa l'approvazione.</span><span class="sxs-lookup"><span data-stu-id="84efb-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="84efb-175">Testare la creazione di una nuova regola del journal con accesso privilegiato approvato per l'attività New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="84efb-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="84efb-176">Nel computer locale, aprire e accedere al modulo Exchange Online Remote PowerShell nel modulo di PowerShell remoto Microsoft **Corporation**  >  **Microsoft Exchange Online** utilizzando l'account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="84efb-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="84efb-177">In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="84efb-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="84efb-178">Visualizzare la nuova regola del journal in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84efb-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="84efb-179">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="84efb-179">Next step</span></span>

<span data-ttu-id="84efb-180">Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="84efb-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="84efb-181">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="84efb-181">See also</span></span>

[<span data-ttu-id="84efb-182">Guide ai lab di test di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="84efb-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="84efb-183">Panoramica di Microsoft 365 per le aziende</span><span class="sxs-lookup"><span data-stu-id="84efb-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="84efb-184">Microsoft 365 per la documentazione relativa all'organizzazione</span><span class="sxs-lookup"><span data-stu-id="84efb-184">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
