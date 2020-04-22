---
title: Introduzione alla gestione degli accessi con privilegi
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Utilizzare questo argomento per ulteriori informazioni sulla configurazione della gestione degli accessi con privilegi.
ms.openlocfilehash: 196685eda6818b399c778363ee458f6f2792a33a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626512"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="c1834-103">Introduzione alla gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="c1834-103">Get started with privileged access management</span></span>

<span data-ttu-id="c1834-104">In questo argomento viene illustrata la possibilità di abilitare e configurare la gestione degli accessi con privilegi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1834-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="c1834-105">È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o Exchange Management PowerShell per gestire e utilizzare accesso privilegiato.</span><span class="sxs-lookup"><span data-stu-id="c1834-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c1834-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="c1834-106">Before you begin</span></span>

<span data-ttu-id="c1834-107">Prima di iniziare a utilizzare la gestione degli accessi con privilegi, è necessario confermare la [sottoscrizione Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e gli eventuali componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="c1834-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="c1834-108">Per accedere e utilizzare la gestione degli accessi con privilegi, è necessario che l'organizzazione disponga di una delle sottoscrizioni o dei componenti aggiuntivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c1834-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="c1834-109">Sottoscrizione Microsoft 365 E5 (a pagamento o versione di valutazione)</span><span class="sxs-lookup"><span data-stu-id="c1834-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="c1834-110">Sottoscrizione Microsoft 365 E3 (o abbonamento a Office 365 E3 + sottoscrizione Enterprise Mobility and Security E3) + componente aggiuntivo Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="c1834-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="c1834-111">Qualsiasi sottoscrizione Microsoft 365, Office 365, Exchange, SharePoint o OneDrive for Business + Microsoft 365 E5 Insider Risk Management Add-on</span><span class="sxs-lookup"><span data-stu-id="c1834-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="c1834-112">Sottoscrizione Microsoft 365 a5 (a pagamento o versione di valutazione)</span><span class="sxs-lookup"><span data-stu-id="c1834-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="c1834-113">Sottoscrizione Microsoft 365 a3 (o abbonamento a Office 365 a3 + sottoscrizione Enterprise Mobility and Security a3) + componente aggiuntivo Microsoft a5 Compliance</span><span class="sxs-lookup"><span data-stu-id="c1834-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="c1834-114">Qualsiasi componente aggiuntivo Microsoft 365, Office 365, Exchange, SharePoint o OneDrive for Education + Microsoft 365 a5 Insider Risk Management Add-on</span><span class="sxs-lookup"><span data-stu-id="c1834-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="c1834-115">Abbonamento a Office 365 Enterprise E5 (a pagamento o versione di valutazione)</span><span class="sxs-lookup"><span data-stu-id="c1834-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="c1834-116">Abbonamento a Office 365 Enterprise E3 + il componente aggiuntivo Office 365 Advanced Compliance (non più disponibile per le nuove sottoscrizioni, vedere note)</span><span class="sxs-lookup"><span data-stu-id="c1834-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="c1834-117">Gli utenti che inviano e rispondono alle richieste di gestione degli accessi con privilegi devono essere assegnati a una delle licenze precedenti.</span><span class="sxs-lookup"><span data-stu-id="c1834-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="c1834-118">La conformità avanzata di Office 365 non viene più venduta come sottoscrizione autonoma.</span><span class="sxs-lookup"><span data-stu-id="c1834-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="c1834-119">Quando le sottoscrizioni correnti scadono, i clienti devono passare a una delle sottoscrizioni precedenti, che contengono le stesse funzionalità di conformità o aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="c1834-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="c1834-120">Se non si dispone di un piano Office 365 Enterprise E5 esistente e si desidera tentare la gestione degli accessi con privilegi, è possibile [aggiungere microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) alla propria sottoscrizione a Office 365 esistente oppure [iscriversi per una versione di valutazione](https://www.microsoft.com/microsoft-365/enterprise) di Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="c1834-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="c1834-121">Abilitare e configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="c1834-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="c1834-122">Eseguire la procedura seguente per configurare e usare l'accesso privilegiato nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="c1834-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="c1834-123">Passaggio 1: creare un gruppo del responsabile approvazione</span><span class="sxs-lookup"><span data-stu-id="c1834-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="c1834-124">Prima di iniziare a utilizzare l'accesso ai privilegi, determinare chi deve disporre dell'autorizzazione di approvazione per le richieste in arrivo per l'accesso a attività con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="c1834-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="c1834-125">Qualsiasi utente che fa parte del gruppo responsabili approvazione è in grado di approvare le richieste di accesso.</span><span class="sxs-lookup"><span data-stu-id="c1834-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="c1834-126">Questo gruppo è abilitato mediante la creazione di un gruppo di sicurezza abilitato alla posta elettronica in Office 365.</span><span class="sxs-lookup"><span data-stu-id="c1834-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="c1834-127">Passaggio 2: abilitare l'accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="c1834-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="c1834-128">L'accesso con privilegi deve essere abilitato in modo esplicito in Office 365 con il gruppo di approvazione predefinito, incluso un set di account di sistema che si desidera escludere dal controllo di accesso alla gestione degli accessi con privilegi.</span><span class="sxs-lookup"><span data-stu-id="c1834-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="c1834-129">Passaggio 3: creare un criterio di accesso</span><span class="sxs-lookup"><span data-stu-id="c1834-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="c1834-130">La creazione di un criterio di approvazione consente di definire i requisiti di approvazione specifici con ambito a singole attività.</span><span class="sxs-lookup"><span data-stu-id="c1834-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="c1834-131">Le opzioni relative al tipo di approvazione sono **automatiche** o **manuali**.</span><span class="sxs-lookup"><span data-stu-id="c1834-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="c1834-132">Passaggio 4: invio/approvazione delle richieste di accesso privilegiate</span><span class="sxs-lookup"><span data-stu-id="c1834-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="c1834-133">Una volta abilitata, l'accesso con privilegi richiede le approvazioni per qualsiasi attività in cui sia stato definito un criterio di approvazione associato.</span><span class="sxs-lookup"><span data-stu-id="c1834-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="c1834-134">Per le attività incluse in un criterio di approvazione, è necessario che gli utenti dispongano dell'autorizzazione di accesso e che dispongano delle autorizzazioni necessarie per eseguire l'attività.</span><span class="sxs-lookup"><span data-stu-id="c1834-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="c1834-135">Dopo aver concesso l'approvazione, l'utente richiedente può eseguire l'attività desiderata e l'accesso privilegiato autorizzerà ed eseguirà l'attività per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="c1834-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="c1834-136">L'approvazione rimane valida per la durata richiesta (la durata predefinita è di 4 ore), durante la quale il richiedente può eseguire l'attività desiderata più volte.</span><span class="sxs-lookup"><span data-stu-id="c1834-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="c1834-137">Tutte queste esecuzioni vengono registrate e rese disponibili per il controllo di sicurezza e conformità.</span><span class="sxs-lookup"><span data-stu-id="c1834-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="c1834-138">Se si desidera utilizzare Exchange Management PowerShell per abilitare e configurare l'accesso con privilegi, seguire la procedura descritta in [Connect to Exchange Online PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to Connect to Exchange Online PowerShell with your Office 365 Credentials.</span><span class="sxs-lookup"><span data-stu-id="c1834-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="c1834-139">Non è necessario abilitare l'autenticazione a più fattori per l'organizzazione per l'utilizzo dei passaggi per abilitare l'accesso privilegiato durante la connessione a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c1834-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="c1834-140">La connessione con l'autenticazione a più fattori consente di creare un token OAuth utilizzato dall'accesso privilegiato per la firma delle richieste.</span><span class="sxs-lookup"><span data-stu-id="c1834-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="c1834-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="c1834-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="c1834-142">Passaggio 1: creare un gruppo del responsabile approvazione</span><span class="sxs-lookup"><span data-stu-id="c1834-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="c1834-143">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1834-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="c1834-144">Nell'interfaccia di amministrazione, andare a **gruppi** > **aggiungere un gruppo**.</span><span class="sxs-lookup"><span data-stu-id="c1834-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="c1834-145">Selezionare **gruppo di sicurezza abilitato alla posta elettronica** e quindi completare il **nome**, l' **indirizzo di posta elettronica del gruppo**e i campi **Descrizione** per il nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="c1834-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="c1834-146">Salvare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="c1834-146">Save the group.</span></span> <span data-ttu-id="c1834-147">Il gruppo può richiedere alcuni minuti completamente configurati e comparire nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c1834-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="c1834-148">Selezionare il gruppo del nuovo responsabile approvazione e selezionare **modifica** per aggiungere gli utenti al gruppo.</span><span class="sxs-lookup"><span data-stu-id="c1834-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="c1834-149">Salvare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="c1834-149">Save the group.</span></span>

<span data-ttu-id="c1834-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="c1834-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="c1834-151">Passaggio 2: abilitare l'accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="c1834-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="c1834-152">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c1834-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="c1834-153">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1834-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="c1834-154">Nell'interfaccia di amministrazione, passare a **Impostazioni > impostazioni > sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="c1834-154">In the Admin Center, go to **Settings > Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="c1834-155">Abilitare il controllo **Richiedi approvazioni per le attività privilegiate** .</span><span class="sxs-lookup"><span data-stu-id="c1834-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="c1834-156">Assegnare il gruppo del responsabile approvazione creato nel passaggio 1 come **gruppo dei responsabili approvazione predefiniti**.</span><span class="sxs-lookup"><span data-stu-id="c1834-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="c1834-157">**Salva** e **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c1834-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="c1834-158">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1834-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="c1834-159">Per abilitare l'accesso con privilegi e assegnare il gruppo del responsabile dell'approvazione, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="c1834-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="c1834-160">Esempio:</span><span class="sxs-lookup"><span data-stu-id="c1834-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="c1834-161">La funzionalità account di sistema è disponibile per garantire che alcuni automatismi all'interno delle organizzazioni possano funzionare senza dipendenza dall'accesso privilegiato, tuttavia è consigliabile che tali esclusioni siano eccezionali e quelle consentite debbano essere approvate e controllate regolarmente.</span><span class="sxs-lookup"><span data-stu-id="c1834-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="c1834-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="c1834-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="c1834-163">Passaggio 3: creare un criterio di accesso</span><span class="sxs-lookup"><span data-stu-id="c1834-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="c1834-164">È possibile creare e configurare fino a 30 criteri di accesso privilegiato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1834-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="c1834-165">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c1834-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="c1834-166">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1834-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="c1834-167">Nell'interfaccia di amministrazione, andare a **Impostazioni** > di**sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="c1834-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="c1834-168">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="c1834-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="c1834-169">Selezionare **Configure policies** e selezionare **Add a Policy**.</span><span class="sxs-lookup"><span data-stu-id="c1834-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="c1834-170">Nei campi a discesa selezionare i valori corretti per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="c1834-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="c1834-171">**Tipo di criterio**: attività, ruolo o gruppo di ruoli</span><span class="sxs-lookup"><span data-stu-id="c1834-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="c1834-172">**Ambito di criteri**: Exchange</span><span class="sxs-lookup"><span data-stu-id="c1834-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="c1834-173">**Nome criterio**: scegliere tra i criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="c1834-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="c1834-174">**Tipo di approvazione**: manuale o automatico</span><span class="sxs-lookup"><span data-stu-id="c1834-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="c1834-175">**Gruppo di approvazione**: selezionare il gruppo responsabili approvazione creato nel passaggio 1</span><span class="sxs-lookup"><span data-stu-id="c1834-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="c1834-176">Selezionare **Crea** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c1834-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="c1834-177">È possibile che i criteri siano completamente configurati e abilitati per alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="c1834-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="c1834-178">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1834-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="c1834-179">Per creare e definire un criterio di approvazione, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="c1834-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="c1834-180">Esempio:</span><span class="sxs-lookup"><span data-stu-id="c1834-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="c1834-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="c1834-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="c1834-182">Passaggio 4: invio/approvazione delle richieste di accesso privilegiate</span><span class="sxs-lookup"><span data-stu-id="c1834-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="c1834-183">Richiesta di autorizzazione all'elevazione per l'esecuzione di attività privilegiate</span><span class="sxs-lookup"><span data-stu-id="c1834-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="c1834-184">Le richieste di accesso con privilegi sono valide per un massimo di 24 ore dopo l'invio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="c1834-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="c1834-185">Se non è stato approvato o negato, le richieste scadono e Access non è approvato.</span><span class="sxs-lookup"><span data-stu-id="c1834-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="c1834-186">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c1834-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="c1834-187">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="c1834-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="c1834-188">Nell'interfaccia di amministrazione, andare a **Impostazioni** > di**sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="c1834-188">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="c1834-189">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="c1834-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="c1834-190">Selezionare **nuova richiesta**.</span><span class="sxs-lookup"><span data-stu-id="c1834-190">Select **New request**.</span></span> <span data-ttu-id="c1834-191">Nei campi a discesa selezionare i valori corretti per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="c1834-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="c1834-192">**Tipo di richiesta**: attività, ruolo o gruppo di ruoli</span><span class="sxs-lookup"><span data-stu-id="c1834-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="c1834-193">**Ambito delle richieste**: Exchange</span><span class="sxs-lookup"><span data-stu-id="c1834-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="c1834-194">**Richiesta per**: selezionare i criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="c1834-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="c1834-195">**Durata (ore)**: numero di ore di accesso richiesto.</span><span class="sxs-lookup"><span data-stu-id="c1834-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="c1834-196">Non è previsto un limite per il numero di ore che è possibile richiedere.</span><span class="sxs-lookup"><span data-stu-id="c1834-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="c1834-197">**Commenti**: campo di testo per i commenti relativi alla richiesta di accesso</span><span class="sxs-lookup"><span data-stu-id="c1834-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="c1834-198">Selezionare **Salva** e quindi **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c1834-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="c1834-199">La richiesta verrà inviata al gruppo del responsabile dell'approvazione tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c1834-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="c1834-200">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1834-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="c1834-201">Eseguire il seguente comando in PowerShell di Exchange Online per creare e inviare una richiesta di approvazione al gruppo del responsabile dell'approvazione:</span><span class="sxs-lookup"><span data-stu-id="c1834-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="c1834-202">Esempio:</span><span class="sxs-lookup"><span data-stu-id="c1834-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="c1834-203">Visualizzare lo stato delle richieste di elevazione</span><span class="sxs-lookup"><span data-stu-id="c1834-203">View status of elevation requests</span></span>

<span data-ttu-id="c1834-204">Dopo la creazione di una richiesta di approvazione, lo stato della richiesta di elevazione può essere esaminato nell'interfaccia di amministrazione o in Exchange Management PowerShell utilizzando l'ID della richiesta associato.</span><span class="sxs-lookup"><span data-stu-id="c1834-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="c1834-205">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c1834-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="c1834-206">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) con le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="c1834-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="c1834-207">Nell'interfaccia di amministrazione, andare a **Impostazioni** > di**sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="c1834-207">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="c1834-208">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="c1834-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="c1834-209">Selezionare **Visualizza** per filtrare le richieste inviate mediante lo stato **in sospeso**, **approvato**, **negato**o **protetto dall'archivio dei clienti** .</span><span class="sxs-lookup"><span data-stu-id="c1834-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="c1834-210">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1834-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="c1834-211">Eseguire il seguente comando in PowerShell di Exchange Online per visualizzare lo stato di una richiesta di approvazione per un ID di richiesta specifico:</span><span class="sxs-lookup"><span data-stu-id="c1834-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="c1834-212">Esempio:</span><span class="sxs-lookup"><span data-stu-id="c1834-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="c1834-213">Approvazione di una richiesta di autorizzazione elevazione</span><span class="sxs-lookup"><span data-stu-id="c1834-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="c1834-214">Quando viene creata una richiesta di approvazione, i membri del gruppo di approvazione pertinente ricevono una notifica tramite posta elettronica e possono approvare la richiesta associata all'ID della richiesta.</span><span class="sxs-lookup"><span data-stu-id="c1834-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="c1834-215">Il richiedente riceve una notifica dell'approvazione o della negazione della richiesta tramite il messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c1834-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="c1834-216">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c1834-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="c1834-217">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) con le proprie credenziali.</span><span class="sxs-lookup"><span data-stu-id="c1834-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="c1834-218">Nell'interfaccia di amministrazione, andare a **Impostazioni** > di**sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="c1834-218">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="c1834-219">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="c1834-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="c1834-220">Selezionare una richiesta elencata per visualizzare i dettagli e per eseguire l'azione sulla richiesta.</span><span class="sxs-lookup"><span data-stu-id="c1834-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="c1834-221">Selezionare **approva** per approvare la richiesta oppure selezionare **Nega** per rifiutare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="c1834-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="c1834-222">Le richieste approvate in precedenza possono avere accesso revocato selezionando **revoca**.</span><span class="sxs-lookup"><span data-stu-id="c1834-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="c1834-223">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1834-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="c1834-224">Per approvare una richiesta di autorizzazione elevazione, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="c1834-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="c1834-225">Esempio:</span><span class="sxs-lookup"><span data-stu-id="c1834-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="c1834-226">Per rifiutare una richiesta di autorizzazione elevazione, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="c1834-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="c1834-227">Esempio:</span><span class="sxs-lookup"><span data-stu-id="c1834-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="c1834-228">Eliminare un criterio di accesso con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="c1834-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="c1834-229">Se non è più necessario nell'organizzazione, è possibile eliminare un criterio di accesso con privilegi.</span><span class="sxs-lookup"><span data-stu-id="c1834-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="c1834-230">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c1834-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="c1834-231">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) utilizzando le credenziali per un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1834-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="c1834-232">Nell'interfaccia di amministrazione, andare a **Impostazioni** > di**sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="c1834-232">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="c1834-233">Selezionare **Gestisci criteri di accesso e richieste**.</span><span class="sxs-lookup"><span data-stu-id="c1834-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="c1834-234">Selezionare **Configure policies**.</span><span class="sxs-lookup"><span data-stu-id="c1834-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="c1834-235">Selezionare il criterio che si desidera eliminare, quindi selezionare **Rimuovi criterio**.</span><span class="sxs-lookup"><span data-stu-id="c1834-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="c1834-236">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="c1834-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="c1834-237">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1834-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="c1834-238">Per eliminare un criterio di accesso con privilegi, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="c1834-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="c1834-239">Disabilitare l'accesso con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="c1834-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="c1834-240">Se necessario, è possibile disabilitare la gestione degli accessi con privilegi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1834-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="c1834-241">La disabilitazione dell'accesso con privilegi non comporta l'eliminazione di criteri di approvazione associati o gruppi di approvatori.</span><span class="sxs-lookup"><span data-stu-id="c1834-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="c1834-242">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c1834-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="c1834-243">Accedere all'interfaccia di [amministrazione di Microsoft 365](https://admin.microsoft.com) con le credenziali di un account di amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c1834-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="c1834-244">Nell'interfaccia di amministrazione, andare a **Impostazioni** > di**sicurezza & privacy** > **accesso privilegiato**.</span><span class="sxs-lookup"><span data-stu-id="c1834-244">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="c1834-245">Abilitare le **autorizzazioni necessarie per il controllo di accesso privilegiato** .</span><span class="sxs-lookup"><span data-stu-id="c1834-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="c1834-246">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="c1834-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="c1834-247">Per disabilitare l'accesso con privilegi, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="c1834-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
