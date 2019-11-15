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
ms.openlocfilehash: cd90aadd2e473668d8c7f634d3edc777c3380dfb
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639766"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="2eacd-103">Gestione degli accessi con privilegi per l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2eacd-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="2eacd-104">Con le istruzioni riportate in questo articolo, è possibile configurare la gestione degli accessi con privilegi per aumentare la sicurezza nell'ambiente di testing Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2eacd-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Guide al lab di test per il cloud Microsoft](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="2eacd-106">Fare clic [qui](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) per consultare una mappa di tutti gli articoli relativi alla guida al lab test di Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2eacd-106">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="2eacd-107">Fase 1: Creare l'ambiente di testing di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2eacd-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="2eacd-108">Se si desidera configurare la gestione degli accessi con privilegi in modo semplice con i requisiti minimi, seguire le istruzioni contenute in [Lightweight base Configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="2eacd-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="2eacd-109">Se si desidera configurare la gestione degli accessi con privilegi in un'azienda simulata, seguire le istruzioni riportate nell' [autenticazione pass-through](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="2eacd-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="2eacd-110">Se si verifica la gestione degli accessi con privilegi non è necessario l'ambiente di testing dell'organizzazione simulata, che include una rete Intranet simulata connessa a Internet e la sincronizzazione della directory per una foresta di AD DS.</span><span class="sxs-lookup"><span data-stu-id="2eacd-110">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="2eacd-111">Viene fornito come opzione in modo che sia possibile testare la gestione degli accessi con privilegi e sperimentarla in un ambiente che rappresenta un'organizzazione tipica.</span><span class="sxs-lookup"><span data-stu-id="2eacd-111">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="2eacd-112">Fase 2: configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="2eacd-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="2eacd-113">In questa fase, è possibile configurare un gruppo responsabili approvazione e abilitare la gestione degli accessi con privilegi per l'ambiente di testing Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="2eacd-113">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="2eacd-114">Per ulteriori informazioni e una panoramica della gestione degli accessi con privilegi, vedere [gestione degli accessi con privilegi in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="2eacd-114">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="2eacd-115">Seguire questa procedura per configurare e usare l'accesso privilegiato nell'organizzazione di Office 365:</span><span class="sxs-lookup"><span data-stu-id="2eacd-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="2eacd-116">Passaggio 1: creare un gruppo del responsabile approvazione</span><span class="sxs-lookup"><span data-stu-id="2eacd-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-1-create-an-approvers-group)

    <span data-ttu-id="2eacd-117">Prima di iniziare a utilizzare l'accesso ai privilegi, determinare chi avrà l'autorità di approvazione per le richieste in arrivo per l'accesso a attività con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="2eacd-117">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="2eacd-118">Qualsiasi utente che fa parte del gruppo responsabili approvazione sarà in grado di approvare le richieste di accesso.</span><span class="sxs-lookup"><span data-stu-id="2eacd-118">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="2eacd-119">Questa impostazione viene abilitata creando un gruppo di sicurezza abilitato alla posta elettronica in Office 365.</span><span class="sxs-lookup"><span data-stu-id="2eacd-119">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="2eacd-120">Creare un nuovo gruppo di sicurezza denominato "revisori accesso privilegiato" nell'ambiente di testing e aggiungere "User 3" precedentemente creato nei passaggi precedenti della guida del laboratorio di testing.</span><span class="sxs-lookup"><span data-stu-id="2eacd-120">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="2eacd-121">Passaggio 2: abilitare l'accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="2eacd-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/microsoft-365/compliance/privileged-access-management-configuration#step-2-enable-privileged-access)

    <span data-ttu-id="2eacd-122">L'accesso privilegiato deve essere attivato in modo esplicito in Office 365 con il gruppo di approvazione predefinito e includendo un set di account di sistema che si desidera escludere dal controllo di accesso a gestione accesso privilegiato.</span><span class="sxs-lookup"><span data-stu-id="2eacd-122">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="2eacd-123">Assicurarsi di abilitare l'accesso con privilegi nell'organizzazione di Office 365 prima di iniziare la fase 3 di questa guida.</span><span class="sxs-lookup"><span data-stu-id="2eacd-123">Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="2eacd-124">Fase 3: verificare che l'approvazione sia necessaria per le attività con privilegi elevati e</span><span class="sxs-lookup"><span data-stu-id="2eacd-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="2eacd-125">In questa fase, è possibile verificare che il criterio di accesso privilegiato funzioni e che gli utenti dispongano dell'approvazione per l'esecuzione di attività definite con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="2eacd-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="2eacd-126">Provare la possibilità di eseguire un'attività non definita in un criterio di accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="2eacd-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="2eacd-127">Innanzitutto, connettersi a Exchange Management PowerShell con le credenziali di un utente configurato come amministratore globale nell'ambiente di testing e tentare di creare una nuova regola del journal.</span><span class="sxs-lookup"><span data-stu-id="2eacd-127">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="2eacd-128">L'attività [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) non è attualmente definita in un criterio di accesso con privilegi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2eacd-128">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="2eacd-129">Nel computer locale, aprire e accedere al modulo Exchange Online Remote PowerShell nel modulo di PowerShell remoto di **Microsoft Corporation** > **Microsoft Exchange Online** utilizzando l'account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="2eacd-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2eacd-130">In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="2eacd-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```

4. <span data-ttu-id="2eacd-131">Visualizzare la nuova regola del journal in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2eacd-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="2eacd-132">Creare un nuovo criterio di accesso privilegiato per l'attività New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="2eacd-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="2eacd-133">Se non sono già stati completati i passaggi 1 e 2 della fase 2 della guida, seguire la procedura seguente per creare un gruppo del responsabile approvazione denominato "revisori di accesso Privilege" e per abilitare l'accesso con privilegi nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="2eacd-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="2eacd-134">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali dell'account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="2eacd-134">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2eacd-135">Nell'interfaccia di amministrazione, andare a **Impostazioni** > di**sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="2eacd-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="2eacd-136">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="2eacd-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="2eacd-137">Selezionare **Configure policies** e selezionare **Add a Policy**.</span><span class="sxs-lookup"><span data-stu-id="2eacd-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="2eacd-138">Nei campi a discesa selezionare o immettere i valori seguenti:</span><span class="sxs-lookup"><span data-stu-id="2eacd-138">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="2eacd-139">**Tipo di criterio**: attività</span><span class="sxs-lookup"><span data-stu-id="2eacd-139">**Policy type**: Task</span></span>

    <span data-ttu-id="2eacd-140">**Ambito di criteri**: Exchange</span><span class="sxs-lookup"><span data-stu-id="2eacd-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="2eacd-141">**Nome criterio**: nuova regola del Journal</span><span class="sxs-lookup"><span data-stu-id="2eacd-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="2eacd-142">**Tipo di approvazione**: Manual</span><span class="sxs-lookup"><span data-stu-id="2eacd-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="2eacd-143">**Gruppo di approvazione**: responsabili approvazione accesso privilegiato</span><span class="sxs-lookup"><span data-stu-id="2eacd-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="2eacd-144">Selezionare **Crea** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="2eacd-144">Select **Create** and then **Close**.</span></span> <span data-ttu-id="2eacd-145">È possibile che i criteri siano completamente configurati e abilitati per alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="2eacd-145">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="2eacd-146">Assicurarsi che il criterio venga abilitato completamente prima di testare il requisito di approvazione nel passaggio successivo.</span><span class="sxs-lookup"><span data-stu-id="2eacd-146">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="2eacd-147">Requisiti di approvazione del test per l'attività New-JournalRule definita in un criterio di accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="2eacd-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="2eacd-148">Nel computer locale, aprire e accedere al modulo Exchange Online Remote PowerShell nel modulo di PowerShell remoto Microsoft **Corporation** > **Microsoft Exchange Online** utilizzando un account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="2eacd-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2eacd-149">In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="2eacd-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="2eacd-150">Visualizzazione dell'errore "autorizzazioni Insuffient" in Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2eacd-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```ExchangeManagementPowerShell
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="2eacd-151">Richiedere l'accesso per creare una nuova regola del journal utilizzando l'attività New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="2eacd-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="2eacd-152">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando l'account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="2eacd-152">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2eacd-153">Nell'interfaccia di amministrazione, andare a **Impostazioni** > di**sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="2eacd-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="2eacd-154">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="2eacd-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="2eacd-155">Selezionare **nuova richiesta**.</span><span class="sxs-lookup"><span data-stu-id="2eacd-155">Select **New request**.</span></span> <span data-ttu-id="2eacd-156">Nei campi a discesa selezionare i valori corretti per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="2eacd-156">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="2eacd-157">**Tipo di richiesta**: attività</span><span class="sxs-lookup"><span data-stu-id="2eacd-157">**Request type**: Task</span></span>

    <span data-ttu-id="2eacd-158">**Ambito delle richieste**: Exchange</span><span class="sxs-lookup"><span data-stu-id="2eacd-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="2eacd-159">**Richiesta per**: nuova regola del Journal</span><span class="sxs-lookup"><span data-stu-id="2eacd-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="2eacd-160">**Durata (ore)**: 2</span><span class="sxs-lookup"><span data-stu-id="2eacd-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="2eacd-161">**Commenti**: richiedere l'autorizzazione per la creazione di una nuova regola del Journal</span><span class="sxs-lookup"><span data-stu-id="2eacd-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="2eacd-162">Selezionare **Salva** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="2eacd-162">Select **Save** and then **Close**.</span></span> <span data-ttu-id="2eacd-163">La richiesta verrà inviata al gruppo del responsabile dell'approvazione tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="2eacd-163">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="2eacd-164">Approva la richiesta di accesso privilegiato per la creazione di una nuova regola di Journal</span><span class="sxs-lookup"><span data-stu-id="2eacd-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="2eacd-165">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per l'utente 3 nell'ambiente di testing (membro del gruppo di sicurezza "responsabili approvazione accesso privilegiato" nell'ambiente di testing).</span><span class="sxs-lookup"><span data-stu-id="2eacd-165">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="2eacd-166">Nell'interfaccia di amministrazione, andare a **Impostazioni** > di**sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="2eacd-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="2eacd-167">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="2eacd-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="2eacd-168">Selezionare la richiesta in sospeso e selezionare **approva** per concedere l'accesso all'account di amministratore globale per creare una nuova regola del journal.</span><span class="sxs-lookup"><span data-stu-id="2eacd-168">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="2eacd-169">Un messaggio di posta elettronica di notifica che conferma che l'approvazione è stata concessa verrà inviata all'account di amministratore globale (l'utente richiedente).</span><span class="sxs-lookup"><span data-stu-id="2eacd-169">An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="2eacd-170">Testare la creazione di una nuova regola del journal con accesso privilegiato approvato per l'attività New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="2eacd-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="2eacd-171">Nel computer locale, aprire e accedere al modulo Exchange Online Remote PowerShell nel modulo di PowerShell remoto di **Microsoft Corporation** > **Microsoft Exchange Online** utilizzando l'account di amministratore globale per l'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="2eacd-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="2eacd-172">In Exchange Management PowerShell, creare una nuova regola del journal per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="2eacd-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```ExchangeManagementPowerShell
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```

3. <span data-ttu-id="2eacd-173">Visualizzare la nuova regola del journal in Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2eacd-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="2eacd-174">Passaggio successivo</span><span class="sxs-lookup"><span data-stu-id="2eacd-174">Next step</span></span>

<span data-ttu-id="2eacd-175">Esplorare le funzionalità e le funzionalità di [protezione delle informazioni](m365-enterprise-test-lab-guides.md#information-protection) aggiuntive nell'ambiente di testing.</span><span class="sxs-lookup"><span data-stu-id="2eacd-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="2eacd-176">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2eacd-176">See also</span></span>

[<span data-ttu-id="2eacd-177">Guide al lab di test di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2eacd-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="2eacd-178">Distribuzione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2eacd-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="2eacd-179">Documentazione di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="2eacd-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)