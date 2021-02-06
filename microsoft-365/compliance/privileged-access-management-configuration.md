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
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: Usare questo articolo per altre informazioni sull'abilitazione e la configurazione della gestione degli accessi con privilegi in Office 365.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126533"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="65cff-103">Introduzione alla gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="65cff-103">Get started with privileged access management</span></span>

<span data-ttu-id="65cff-104">Questo argomento illustra come abilitare e configurare la gestione degli accessi con privilegi nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="65cff-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="65cff-105">È possibile utilizzare l'interfaccia di amministrazione di Microsoft 365 o Exchange Management PowerShell per gestire e utilizzare l'accesso con privilegi.</span><span class="sxs-lookup"><span data-stu-id="65cff-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="65cff-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="65cff-106">Before you begin</span></span>

<span data-ttu-id="65cff-107">Prima di iniziare a usare la gestione degli accessi con privilegi, è consigliabile confermare l'abbonamento a [Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) e gli eventuali componenti aggiuntivi.</span><span class="sxs-lookup"><span data-stu-id="65cff-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="65cff-108">Per accedere e usare la gestione degli accessi con privilegi, l'organizzazione deve disporre di uno dei seguenti abbonamenti o componenti aggiuntivi:</span><span class="sxs-lookup"><span data-stu-id="65cff-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="65cff-109">Abbonamento a Microsoft 365 E5 (versione di valutazione o a pagamento)</span><span class="sxs-lookup"><span data-stu-id="65cff-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="65cff-110">Abbonamento a Microsoft 365 E3 (o abbonamento a Office 365 E3 + Abbonamento Enterprise Mobility and Security E3) + componente aggiuntivo Conformità Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="65cff-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="65cff-111">Qualsiasi abbonamento a Microsoft 365, Office 365, Exchange, SharePoint o OneDrive for Business + il componente aggiuntivo Microsoft 365 E5 Insider Risk Management</span><span class="sxs-lookup"><span data-stu-id="65cff-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="65cff-112">Abbonamento a Microsoft 365 A5 (versione di valutazione o a pagamento)</span><span class="sxs-lookup"><span data-stu-id="65cff-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="65cff-113">Abbonamento a Microsoft 365 A3 (o abbonamento a Office 365 A3 + Abbonamento Enterprise Mobility and Security A3) + componente aggiuntivo Conformità Microsoft A5</span><span class="sxs-lookup"><span data-stu-id="65cff-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="65cff-114">Qualsiasi abbonamento a Microsoft 365, Office 365, Exchange, SharePoint o OneDrive for Education + il componente aggiuntivo Microsoft 365 A5 Insider Risk Management</span><span class="sxs-lookup"><span data-stu-id="65cff-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="65cff-115">Abbonamento a Office 365 Enterprise E5 (versione di valutazione o a pagamento)</span><span class="sxs-lookup"><span data-stu-id="65cff-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="65cff-116">Abbonamento a Office 365 Enterprise E3 + componente aggiuntivo Office 365 Advanced Compliance (non più disponibile per i nuovi abbonamenti, vedere la nota)</span><span class="sxs-lookup"><span data-stu-id="65cff-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="65cff-117">Agli utenti che inviano e rispondono alle richieste di gestione degli accessi privilegiati deve essere assegnata una delle licenze precedenti.</span><span class="sxs-lookup"><span data-stu-id="65cff-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="65cff-118">Office 365 Advanced Compliance non viene più venduto come abbonamento autonomo.</span><span class="sxs-lookup"><span data-stu-id="65cff-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="65cff-119">Quando le sottoscrizioni correnti scadono, i clienti devono passare a una delle sottoscrizioni precedenti, che contengono le stesse o funzionalità di conformità aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="65cff-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="65cff-120">Se non si dispone di un piano Office 365 Enterprise E5 esistente e si vuole provare la gestione degli accessi con privilegi, è possibile aggiungere [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) all'abbonamento a Office 365 esistente o iscriversi [per](https://www.microsoft.com/microsoft-365/enterprise) una versione di valutazione di Microsoft 365 Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="65cff-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="65cff-121">Abilitare e configurare la gestione degli accessi con privilegi</span><span class="sxs-lookup"><span data-stu-id="65cff-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="65cff-122">Seguire questa procedura per configurare e usare l'accesso con privilegi nell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="65cff-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="65cff-123">Passaggio 1: Creare un gruppo di responsabili approvazione</span><span class="sxs-lookup"><span data-stu-id="65cff-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="65cff-124">Prima di iniziare a utilizzare l'accesso con privilegi, determinare chi necessita dell'autorità di approvazione per le richieste in arrivo di accesso alle attività con privilegi e con privilegi elevati.</span><span class="sxs-lookup"><span data-stu-id="65cff-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="65cff-125">Qualsiasi utente che fa parte del gruppo dei responsabili approvazione può approvare le richieste di accesso.</span><span class="sxs-lookup"><span data-stu-id="65cff-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="65cff-126">Questo gruppo viene abilitato creando un gruppo di sicurezza abilitato alla posta elettronica in Office 365.</span><span class="sxs-lookup"><span data-stu-id="65cff-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="65cff-127">Passaggio 2: abilitare l'accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="65cff-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="65cff-128">L'accesso con privilegi deve essere abilitato in modo esplicito in Office 365 con il gruppo di responsabili approvazione predefinito, incluso un set di account di sistema che si desidera escludere dal controllo di accesso per la gestione degli accessi con privilegi.</span><span class="sxs-lookup"><span data-stu-id="65cff-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="65cff-129">Passaggio 3: Creare un criterio di accesso</span><span class="sxs-lookup"><span data-stu-id="65cff-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="65cff-130">La creazione di un criterio di approvazione consente di definire i requisiti di approvazione specifici nell'ambito delle singole attività.</span><span class="sxs-lookup"><span data-stu-id="65cff-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="65cff-131">Le opzioni del tipo di approvazione **sono Automatico** o **Manuale.**</span><span class="sxs-lookup"><span data-stu-id="65cff-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="65cff-132">Passaggio 4: inviare/approvare le richieste di accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="65cff-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="65cff-133">Una volta abilitato, l'accesso con privilegi richiede l'approvazione per qualsiasi attività a cui è associato un criterio di approvazione definito.</span><span class="sxs-lookup"><span data-stu-id="65cff-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="65cff-134">Per le attività incluse in un criterio di approvazione, gli utenti devono richiedere e ottenere l'approvazione dell'accesso per disporre delle autorizzazioni necessarie per eseguire l'attività.</span><span class="sxs-lookup"><span data-stu-id="65cff-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="65cff-135">Una volta concessa l'approvazione, l'utente richiedente può eseguire l'attività prevista e l'accesso privilegiato autorizzerà ed eseguirà l'attività per conto dell'utente.</span><span class="sxs-lookup"><span data-stu-id="65cff-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="65cff-136">L'approvazione rimane valida per la durata richiesta (la durata predefinita è 4 ore), durante la quale il richiedente può eseguire l'attività prevista più volte.</span><span class="sxs-lookup"><span data-stu-id="65cff-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="65cff-137">Tutte queste esecuzioni vengono registrate e rese disponibili per il controllo della sicurezza e della conformità.</span><span class="sxs-lookup"><span data-stu-id="65cff-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="65cff-138">Se si desidera utilizzare Exchange Management PowerShell per abilitare e configurare l'accesso con privilegi, seguire la procedura descritta in Connettersi a [PowerShell di Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) utilizzando l'autenticazione a più fattori per connettersi a PowerShell di Exchange Online con le credenziali di Office 365.</span><span class="sxs-lookup"><span data-stu-id="65cff-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="65cff-139">Non è necessario abilitare l'autenticazione a più fattori per l'organizzazione per utilizzare la procedura per abilitare l'accesso con privilegi durante la connessione a PowerShell di Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="65cff-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="65cff-140">La connessione con l'autenticazione a più fattori crea un token OAuth utilizzato dall'accesso con privilegi per firmare le richieste.</span><span class="sxs-lookup"><span data-stu-id="65cff-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="65cff-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="65cff-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="65cff-142">Passaggio 1: Creare un gruppo di responsabili approvazione</span><span class="sxs-lookup"><span data-stu-id="65cff-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="65cff-143">Accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) usando le credenziali per un account amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="65cff-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="65cff-144">Nell'interfaccia di amministrazione passare a **Gruppi**  >  **Aggiungere un gruppo.**</span><span class="sxs-lookup"><span data-stu-id="65cff-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="65cff-145">Selezionare **il gruppo di sicurezza abilitato alla posta** elettronica  e quindi completare i campi **Nome,** Indirizzo **di** posta elettronica del gruppo e Descrizione per il nuovo gruppo.</span><span class="sxs-lookup"><span data-stu-id="65cff-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="65cff-146">Salvare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="65cff-146">Save the group.</span></span> <span data-ttu-id="65cff-147">La configurazione completa del gruppo e la visualizzazione nell'interfaccia di amministrazione di Microsoft 365 potrebbero richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="65cff-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="65cff-148">Selezionare il gruppo del nuovo responsabile approvazione e selezionare **Modifica** per aggiungere utenti al gruppo.</span><span class="sxs-lookup"><span data-stu-id="65cff-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="65cff-149">Salvare il gruppo.</span><span class="sxs-lookup"><span data-stu-id="65cff-149">Save the group.</span></span>

<span data-ttu-id="65cff-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="65cff-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="65cff-151">Passaggio 2: abilitare l'accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="65cff-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65cff-152">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65cff-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="65cff-153">Accedere [all'interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) usando le credenziali di un account amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="65cff-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="65cff-154">Nell'interfaccia di amministrazione passare **a** Impostazioni organizzazione  >  **Impostazioni** sicurezza &  >  **accesso con privilegi**  >  **di privacy.**</span><span class="sxs-lookup"><span data-stu-id="65cff-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65cff-155">Abilitare il **controllo Richiedi approvazione per le attività con** privilegi.</span><span class="sxs-lookup"><span data-stu-id="65cff-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="65cff-156">Assegnare il gruppo di responsabili approvazione creato nel passaggio 1 come **gruppo responsabili approvazione predefiniti.**</span><span class="sxs-lookup"><span data-stu-id="65cff-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="65cff-157">**Salva** e **chiudi.**</span><span class="sxs-lookup"><span data-stu-id="65cff-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65cff-158">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65cff-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65cff-159">Per abilitare l'accesso con privilegi e assegnare il gruppo del responsabile approvazione, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="65cff-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="65cff-160">Esempio:</span><span class="sxs-lookup"><span data-stu-id="65cff-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="65cff-161">La funzionalità degli account di sistema viene resa disponibile per garantire che determinate automazioni all'interno delle organizzazioni possano funzionare senza dipendenze dall'accesso privilegiato, tuttavia è consigliabile che tali esclusioni siano eccezionali e che quelle consentite debbano essere approvate e verificate regolarmente.</span><span class="sxs-lookup"><span data-stu-id="65cff-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="65cff-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="65cff-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="65cff-163">Passaggio 3: Creare un criterio di accesso</span><span class="sxs-lookup"><span data-stu-id="65cff-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="65cff-164">È possibile creare e configurare fino a 30 criteri di accesso con privilegi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="65cff-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65cff-165">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65cff-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="65cff-166">Accedere [all'interfaccia di amministrazione di Microsoft 365](https://admin.microsoft.com) usando le credenziali di un account amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="65cff-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="65cff-167">Nell'interfaccia di amministrazione passare **a** Impostazioni organizzazione  >  **Impostazioni** sicurezza &  >  **accesso con privilegi**  >  **di privacy.**</span><span class="sxs-lookup"><span data-stu-id="65cff-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65cff-168">Selezionare **Gestisci criteri di accesso e richieste.**</span><span class="sxs-lookup"><span data-stu-id="65cff-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="65cff-169">Selezionare **Configura criteri** e selezionare Aggiungi un **criterio.**</span><span class="sxs-lookup"><span data-stu-id="65cff-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="65cff-170">Nei campi a discesa selezionare i valori appropriati per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="65cff-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="65cff-171">**Tipo di criterio:** attività, ruolo o gruppo di ruoli</span><span class="sxs-lookup"><span data-stu-id="65cff-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="65cff-172">**Ambito dei criteri**: Exchange</span><span class="sxs-lookup"><span data-stu-id="65cff-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="65cff-173">**Nome criterio**: Seleziona uno dei criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="65cff-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="65cff-174">**Tipo di approvazione**: Manuale o Automatico</span><span class="sxs-lookup"><span data-stu-id="65cff-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="65cff-175">**Gruppo di approvazione:** selezionare il gruppo di responsabili approvazione creato nel passaggio 1</span><span class="sxs-lookup"><span data-stu-id="65cff-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="65cff-176">Selezionare **Crea** e quindi **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="65cff-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="65cff-177">La configurazione e l'a attivazione completa del criterio potrebbero richiedere alcuni minuti.</span><span class="sxs-lookup"><span data-stu-id="65cff-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65cff-178">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65cff-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65cff-179">Per creare e definire un criterio di approvazione, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="65cff-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="65cff-180">Esempio:</span><span class="sxs-lookup"><span data-stu-id="65cff-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="65cff-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="65cff-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="65cff-182">Passaggio 4: inviare/approvare le richieste di accesso con privilegi</span><span class="sxs-lookup"><span data-stu-id="65cff-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="65cff-183">Richiesta dell'autorizzazione di elevazione per l'esecuzione di attività privilegiate</span><span class="sxs-lookup"><span data-stu-id="65cff-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="65cff-184">Le richieste di accesso con privilegi sono valide fino a 24 ore dopo l'invio della richiesta.</span><span class="sxs-lookup"><span data-stu-id="65cff-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="65cff-185">Se non approvate o negate, le richieste scadono e l'accesso non viene approvato.</span><span class="sxs-lookup"><span data-stu-id="65cff-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65cff-186">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65cff-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="65cff-187">Accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) usando le credenziali.</span><span class="sxs-lookup"><span data-stu-id="65cff-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="65cff-188">Nell'interfaccia di amministrazione passare **a** Impostazioni organizzazione  >  **Impostazioni** sicurezza &  >  **accesso con privilegi**  >  **di privacy.**</span><span class="sxs-lookup"><span data-stu-id="65cff-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65cff-189">Selezionare **Gestisci criteri di accesso e richieste.**</span><span class="sxs-lookup"><span data-stu-id="65cff-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="65cff-190">Selezionare **Nuova richiesta.**</span><span class="sxs-lookup"><span data-stu-id="65cff-190">Select **New request**.</span></span> <span data-ttu-id="65cff-191">Nei campi a discesa selezionare i valori appropriati per l'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="65cff-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="65cff-192">**Tipo di richiesta:** attività, ruolo o gruppo di ruoli</span><span class="sxs-lookup"><span data-stu-id="65cff-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="65cff-193">**Ambito richiesta**: Exchange</span><span class="sxs-lookup"><span data-stu-id="65cff-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="65cff-194">**Richiesta per:** selezionare uno dei criteri disponibili</span><span class="sxs-lookup"><span data-stu-id="65cff-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="65cff-195">**Durata (ore):** numero di ore di accesso richiesto.</span><span class="sxs-lookup"><span data-stu-id="65cff-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="65cff-196">Non esiste un limite per il numero di ore che possono essere richieste.</span><span class="sxs-lookup"><span data-stu-id="65cff-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="65cff-197">**Commenti**: campo di testo per i commenti correlati alla richiesta di accesso</span><span class="sxs-lookup"><span data-stu-id="65cff-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="65cff-198">Selezionare **Salva** e quindi **Chiudi.**</span><span class="sxs-lookup"><span data-stu-id="65cff-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="65cff-199">La richiesta verrà inviata al gruppo del responsabile approvazione tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="65cff-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65cff-200">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65cff-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65cff-201">Eseguire il comando seguente in PowerShell di Exchange Online per creare e inviare una richiesta di approvazione al gruppo del responsabile approvazione:</span><span class="sxs-lookup"><span data-stu-id="65cff-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="65cff-202">Esempio:</span><span class="sxs-lookup"><span data-stu-id="65cff-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="65cff-203">Visualizzare lo stato delle richieste di elevazione</span><span class="sxs-lookup"><span data-stu-id="65cff-203">View status of elevation requests</span></span>

<span data-ttu-id="65cff-204">Dopo aver creato una richiesta di approvazione, lo stato della richiesta di elevazione può essere esaminato nell'interfaccia di amministrazione o in Exchange Management PowerShell utilizzando l'ID della richiesta associato.</span><span class="sxs-lookup"><span data-stu-id="65cff-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65cff-205">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65cff-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="65cff-206">Accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="65cff-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="65cff-207">Nell'interfaccia di amministrazione passare **a** Impostazioni organizzazione  >  **Impostazioni** sicurezza &  >  **accesso con privilegi**  >  **di privacy.**</span><span class="sxs-lookup"><span data-stu-id="65cff-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65cff-208">Selezionare **Gestisci criteri di accesso e richieste.**</span><span class="sxs-lookup"><span data-stu-id="65cff-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="65cff-209">Selezionare **Visualizza per** filtrare le richieste inviate in base allo stato **In** **sospeso,** **Approvato,** Rifiutato o **Customer Lockbox.**</span><span class="sxs-lookup"><span data-stu-id="65cff-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65cff-210">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65cff-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65cff-211">Eseguire il seguente comando in PowerShell di Exchange Online per visualizzare lo stato di una richiesta di approvazione per un ID richiesta specifico:</span><span class="sxs-lookup"><span data-stu-id="65cff-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="65cff-212">Esempio:</span><span class="sxs-lookup"><span data-stu-id="65cff-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="65cff-213">Approvazione di una richiesta di autorizzazione di elevazione</span><span class="sxs-lookup"><span data-stu-id="65cff-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="65cff-214">Quando viene creata una richiesta di approvazione, i membri del gruppo di responsabili approvazione pertinente ricevono una notifica tramite posta elettronica e possono approvare la richiesta associata all'ID richiesta.</span><span class="sxs-lookup"><span data-stu-id="65cff-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="65cff-215">Il richiedente viene informato dell'approvazione o della negazione della richiesta tramite un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="65cff-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65cff-216">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65cff-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="65cff-217">Accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) con le credenziali.</span><span class="sxs-lookup"><span data-stu-id="65cff-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="65cff-218">Nell'interfaccia di amministrazione passare **a** Impostazioni organizzazione  >  **Impostazioni** sicurezza &  >  **accesso con privilegi**  >  **di privacy.**</span><span class="sxs-lookup"><span data-stu-id="65cff-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65cff-219">Selezionare **Gestisci criteri di accesso e richieste.**</span><span class="sxs-lookup"><span data-stu-id="65cff-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="65cff-220">Selezionare una richiesta elencata per visualizzare i dettagli ed eseguire un'azione sulla richiesta.</span><span class="sxs-lookup"><span data-stu-id="65cff-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="65cff-221">Selezionare **Approva** per approvare la richiesta o **Nega** per rifiutare la richiesta.</span><span class="sxs-lookup"><span data-stu-id="65cff-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="65cff-222">Le richieste approvate in precedenza possono avere accesso revocato selezionando **Revoca.**</span><span class="sxs-lookup"><span data-stu-id="65cff-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65cff-223">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65cff-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65cff-224">Per approvare una richiesta di autorizzazione di elevazione, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="65cff-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="65cff-225">Esempio:</span><span class="sxs-lookup"><span data-stu-id="65cff-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="65cff-226">Per negare una richiesta di autorizzazione di elevazione, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="65cff-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="65cff-227">Esempio:</span><span class="sxs-lookup"><span data-stu-id="65cff-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="65cff-228">Eliminare un criterio di accesso con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="65cff-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="65cff-229">Se non è più necessario nell'organizzazione, è possibile eliminare un criterio di accesso con privilegi.</span><span class="sxs-lookup"><span data-stu-id="65cff-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65cff-230">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65cff-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="65cff-231">Accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) usando le credenziali per un account amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="65cff-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="65cff-232">Nell'interfaccia di amministrazione passare **a** Impostazioni organizzazione  >  **Impostazioni** sicurezza &  >  **accesso con privilegi**  >  **di privacy.**</span><span class="sxs-lookup"><span data-stu-id="65cff-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65cff-233">Selezionare **Gestisci criteri di accesso e richieste.**</span><span class="sxs-lookup"><span data-stu-id="65cff-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="65cff-234">Selezionare **Configura criteri.**</span><span class="sxs-lookup"><span data-stu-id="65cff-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="65cff-235">Selezionare il criterio che si desidera eliminare, quindi **selezionare Rimuovi criterio.**</span><span class="sxs-lookup"><span data-stu-id="65cff-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="65cff-236">Selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="65cff-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65cff-237">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65cff-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65cff-238">Per eliminare un criterio di accesso con privilegi, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="65cff-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="65cff-239">Disabilitare l'accesso con privilegi in Office 365</span><span class="sxs-lookup"><span data-stu-id="65cff-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="65cff-240">Se necessario, è possibile disabilitare la gestione degli accessi con privilegi per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="65cff-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="65cff-241">La disabilitazione dell'accesso con privilegi non elimina i criteri di approvazione o i gruppi di responsabili approvazione associati.</span><span class="sxs-lookup"><span data-stu-id="65cff-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="65cff-242">Nell'interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="65cff-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="65cff-243">Accedere all'interfaccia di amministrazione di [Microsoft 365](https://admin.microsoft.com) con le credenziali per un account amministratore nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="65cff-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="65cff-244">Nell'interfaccia di amministrazione passare **a** Impostazioni organizzazione  >  **Impostazioni** sicurezza &  >  **accesso con privilegi**  >  **di privacy.**</span><span class="sxs-lookup"><span data-stu-id="65cff-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="65cff-245">Abilitare **l'opzione Richiedi approvazioni per il controllo degli accessi con** privilegi.</span><span class="sxs-lookup"><span data-stu-id="65cff-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="65cff-246">In Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="65cff-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="65cff-247">Per disabilitare l'accesso con privilegi, eseguire il comando seguente in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="65cff-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
