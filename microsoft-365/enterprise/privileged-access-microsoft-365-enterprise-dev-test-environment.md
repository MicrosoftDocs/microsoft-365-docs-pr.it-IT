---
title: Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 Enterprise
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
description: Utilizzare questa guida del laboratorio di testing per abilitare la gestione degli accessi con privilegi nell'ambiente di testing Microsoft 365 Enterprise.
ms.openlocfilehash: 7e6a2ddea341f49c737409d8586bd9e70c9b2b79
ms.sourcegitcommit: c5ca71d6feb0f033b50ccd4de816fd59b0925007
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/04/2019
ms.locfileid: "39831817"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="afb60-103">Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="afb60-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="afb60-104">*Questa guida al lab di test può essere usata sia per ambienti di testing di Microsoft 365 Enterprise che Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="afb60-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="afb60-105">Con le istruzioni riportate in questo articolo, è possibile configurare la gestione degli accessi con privilegi per aumentare la sicurezza nell'ambiente di testing Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="afb60-105">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="afb60-107">Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="afb60-107">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="afb60-108">Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="afb60-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="afb60-109">Se si desidera configurare la gestione degli accessi con privilegi in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="afb60-109">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="afb60-110">Se si desidera configurare la gestione degli accessi con privilegi in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="afb60-110">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="afb60-111">Se si verifica la gestione degli accessi con privilegi non è necessario l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di AD DS.</span><span class="sxs-lookup"><span data-stu-id="afb60-111">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="afb60-112">Viene fornito come opzione in modo che sia possibile testare la gestione degli accessi con privilegi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="afb60-112">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="afb60-113">Fase 2: configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="afb60-113">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="afb60-114">In questa fase, è possibile configurare un gruppo responsabili approvazione e abilitare la gestione degli accessi con privilegi per l'ambiente di testing Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="afb60-114">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="afb60-115">Per ulteriori informazioni e una panoramica della gestione degli accessi con privilegi, vedere [gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="afb60-115">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="afb60-116">Seguire questa procedura per configurare e usare l'accesso privilegiato nell'organizzazione di Office 365:</span><span class="sxs-lookup"><span data-stu-id="afb60-116">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="afb60-117">Passaggio 1: creare un gruppo del responsabile approvazione</span><span class="sxs-lookup"><span data-stu-id="afb60-117">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="afb60-118">Prima di iniziare a utilizzare l'accesso ai privilegi, determinare chi avrà l'autorità di approvazione per le richieste in arrivo per l'accesso a attività con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="afb60-118">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="afb60-119">Qualsiasi utente che fa parte del gruppo responsabili approvazione sarà in grado di approvare le richieste di accesso.</span><span class="sxs-lookup"><span data-stu-id="afb60-119">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="afb60-120">Questa impostazione viene abilitata creando un gruppo di sicurezza abilitato alla posta elettronica in Office 365.</span><span class="sxs-lookup"><span data-stu-id="afb60-120">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="afb60-121">Creare un nuovo gruppo di sicurezza denominato "revisori accesso privilegiato" nell'ambiente di testing e aggiungere "User 3" precedentemente creato nei passaggi precedenti della guida del laboratorio di testing.</span><span class="sxs-lookup"><span data-stu-id="afb60-121">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="afb60-122">Passaggio 2: abilitare l'accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="afb60-122">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="afb60-123">L'accesso privilegiato deve essere attivato in modo esplicito in Office 365 con il gruppo di approvazione predefinito e includendo un set di account di sistema che si desidera escludere dal controllo di accesso a gestione accesso privilegiato.</span><span class="sxs-lookup"><span data-stu-id="afb60-123">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="afb60-124">Assicurarsi di abilitare l'accesso con privilegi nell'organizzazione di Office 365 prima di iniziare la fase 3 di questa guida.</span><span class="sxs-lookup"><span data-stu-id="afb60-124">Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="afb60-125">Fase 3: verificare che l'approvazione sia necessaria per le attività con privilegi elevati e</span><span class="sxs-lookup"><span data-stu-id="afb60-125">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="afb60-126">In questa fase, è possibile verificare che il criterio di accesso privilegiato funzioni e che gli utenti dispongano dell'approvazione per l'esecuzione di attività definite con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="afb60-126">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="afb60-127">Provare la possibilità di eseguire un'attività non definita in un criterio di accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="afb60-127">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="afb60-128">Innanzitutto, connettersi a Exchange Management PowerShell con le credenziali di un utente configurato come amministratore globale nell'ambiente di testing e tentare di creare una nuova regola del journal.</span><span class="sxs-lookup"><span data-stu-id="afb60-128">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="afb60-129">L'attività [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) non è attualmente definita in un criterio di accesso con privilegi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="afb60-129">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="afb60-130">Nel computer locale, aprire e accedere al modulo Exchange Online Remote PowerShell nel modulo di PowerShell remoto di Microsoft **Corporation** > **Microsoft Exchange Online** utilizzando l'account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="afb60-130">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="afb60-131">In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="afb60-131">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="afb60-132">Visualizzare la nuova regola del journal in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afb60-132">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="afb60-133">Creare un nuovo criterio di accesso privilegiato per l'attività New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="afb60-133">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="afb60-134">Se non sono già stati completati i passaggi 1 e 2 della fase 2 della guida, seguire la procedura seguente per creare un gruppo del responsabile approvazione denominato "revisori di accesso Privilege" e per abilitare l'accesso con privilegi nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="afb60-134">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="afb60-135">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali dell'account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="afb60-135">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="afb60-136">Nell'interfaccia di amministrazione, andare a **Impostazioni** > di**sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="afb60-136">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="afb60-137">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="afb60-137">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="afb60-138">Selezionare **Configure policies** e selezionare **Add a Policy**.</span><span class="sxs-lookup"><span data-stu-id="afb60-138">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="afb60-139">Nei campi a discesa selezionare o immettere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="afb60-139">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="afb60-140">**Tipo di criterio**: attività</span><span class="sxs-lookup"><span data-stu-id="afb60-140">**Policy type**: Task</span></span>

    <span data-ttu-id="afb60-141">**Ambito di criteri**: Exchange</span><span class="sxs-lookup"><span data-stu-id="afb60-141">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="afb60-142">**Nome criterio**: nuova regola del Journal</span><span class="sxs-lookup"><span data-stu-id="afb60-142">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="afb60-143">**Tipo di approvazione**: Manual</span><span class="sxs-lookup"><span data-stu-id="afb60-143">**Approval type**: Manual</span></span>

    <span data-ttu-id="afb60-144">**Gruppo di approvazione**: responsabili approvazione accesso privilegiato</span><span class="sxs-lookup"><span data-stu-id="afb60-144">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="afb60-145">Selezionare **Crea** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="afb60-145">Select **Create** and then **Close**.</span></span> <span data-ttu-id="afb60-146">È possibile che i criteri siano completamente configurati e abilitati per alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="afb60-146">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="afb60-147">Assicurarsi che il criterio venga abilitato completamente prima di testare il requisito di approvazione nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="afb60-147">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="afb60-148">Requisiti di approvazione del test per l'attività New-JournalRule definita in un criterio di accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="afb60-148">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="afb60-149">Nel computer locale, aprire e accedere al modulo Exchange Online Remote PowerShell nel modulo di PowerShell remoto di Microsoft **Corporation** > **Microsoft Exchange Online** utilizzando un account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="afb60-149">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="afb60-150">In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="afb60-150">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="afb60-151">Visualizzazione dell'errore "autorizzazioni insufficienti" in Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="afb60-151">View "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="afb60-152">Richiedere l'accesso per creare una nuova regola del journal utilizzando l'attività New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="afb60-152">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="afb60-153">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando l'account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="afb60-153">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="afb60-154">Nell'interfaccia di amministrazione, andare a **Impostazioni** > di**sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="afb60-154">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="afb60-155">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="afb60-155">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="afb60-156">Selezionare **nuova richiesta**.</span><span class="sxs-lookup"><span data-stu-id="afb60-156">Select **New request**.</span></span> <span data-ttu-id="afb60-157">Nei campi a discesa selezionare i valori corretti per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="afb60-157">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="afb60-158">**Tipo di richiesta**: attività</span><span class="sxs-lookup"><span data-stu-id="afb60-158">**Request type**: Task</span></span>

    <span data-ttu-id="afb60-159">**Ambito delle richieste**: Exchange</span><span class="sxs-lookup"><span data-stu-id="afb60-159">**Request scope**: Exchange</span></span>

    <span data-ttu-id="afb60-160">**Richiesta per**: nuova regola del Journal</span><span class="sxs-lookup"><span data-stu-id="afb60-160">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="afb60-161">**Durata (ore)**: 2</span><span class="sxs-lookup"><span data-stu-id="afb60-161">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="afb60-162">**Commenti**: richiedere l'autorizzazione per la creazione di una nuova regola del Journal</span><span class="sxs-lookup"><span data-stu-id="afb60-162">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="afb60-163">Selezionare **Salva** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="afb60-163">Select **Save** and then **Close**.</span></span> <span data-ttu-id="afb60-164">La richiesta verrà inviata al gruppo del responsabile dell'approvazione tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="afb60-164">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="afb60-165">Approva la richiesta di accesso privilegiato per la creazione di una nuova regola di Journal</span><span class="sxs-lookup"><span data-stu-id="afb60-165">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="afb60-166">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per l'utente 3 nell'ambiente di testing (membro del gruppo di sicurezza "responsabili approvazione accesso privilegiato" nell'ambiente di testing).</span><span class="sxs-lookup"><span data-stu-id="afb60-166">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="afb60-167">Nell'interfaccia di amministrazione, andare a **Impostazioni** > di**sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="afb60-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="afb60-168">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="afb60-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="afb60-169">Selezionare la richiesta in sospeso e selezionare **approva** per concedere l'accesso all'account di amministratore globale per creare una nuova regola del journal.</span><span class="sxs-lookup"><span data-stu-id="afb60-169">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="afb60-170">Un messaggio di posta elettronica di notifica che conferma che l'approvazione è stata concessa verrà inviata all'account di amministratore globale (l'utente richiedente).</span><span class="sxs-lookup"><span data-stu-id="afb60-170">A notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="afb60-171">Testare la creazione di una nuova regola del journal con accesso privilegiato approvato per l'attività New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="afb60-171">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="afb60-172">Nel computer locale, aprire e accedere al modulo Exchange Online Remote PowerShell nel modulo di PowerShell remoto di Microsoft **Corporation** > **Microsoft Exchange Online** utilizzando l'account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="afb60-172">On your local computer, open and sign into the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="afb60-173">In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="afb60-173">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="afb60-174">Visualizzare la nuova regola del journal in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="afb60-174">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="afb60-175">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="afb60-175">Next step</span></span>

<span data-ttu-id="afb60-176">Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="afb60-176">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="afb60-177">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="afb60-177">See also</span></span>

[<span data-ttu-id="afb60-178">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="afb60-178">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="afb60-179">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="afb60-179">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="afb60-180">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="afb60-180">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)