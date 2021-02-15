---
title: Chiudere il proprio account
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
search.appverid:
- MET150
description: Scopri come chiudere l'account con Microsoft.
ms.openlocfilehash: bdcf4408ddc9c198fab1d68b4c096fad9059b975
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376318"
---
# <a name="close-your-account"></a><span data-ttu-id="dfe97-103">Chiudere il proprio account</span><span class="sxs-lookup"><span data-stu-id="dfe97-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="dfe97-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="dfe97-104">The admin center is changing.</span></span> <span data-ttu-id="dfe97-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="dfe97-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="dfe97-106">Quando si chiude l'account con Microsoft, verranno eliminate tutte le informazioni correlate all'account.</span><span class="sxs-lookup"><span data-stu-id="dfe97-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="dfe97-107">Queste informazioni includono abbonamenti, licenze, modalità di pagamento, utenti e dati utente.</span><span class="sxs-lookup"><span data-stu-id="dfe97-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="dfe97-108">Informazioni preliminari</span><span class="sxs-lookup"><span data-stu-id="dfe97-108">Before you begin</span></span>

<span data-ttu-id="dfe97-109">Prima di iniziare questo processo, assicurarsi di eseguire il backup dei dati che si vogliono conservare.</span><span class="sxs-lookup"><span data-stu-id="dfe97-109">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="dfe97-110">Per eseguire le attività di questo articolo, è necessario essere un amministratore globale o di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="dfe97-110">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="dfe97-111">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="dfe97-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="dfe97-112">Passaggio 1: eliminare gli utenti</span><span class="sxs-lookup"><span data-stu-id="dfe97-112">Step 1: Delete users</span></span>

<span data-ttu-id="dfe97-113">Eliminare tutti gli utenti ad eccezione di un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="dfe97-113">Delete all users except for one global administrator.</span></span> <span data-ttu-id="dfe97-114">L'amministratore globale completa i passaggi per chiudere l'account.</span><span class="sxs-lookup"><span data-stu-id="dfe97-114">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="dfe97-115">Prima di eliminare la directory al termine di questo processo, è necessario eliminare tutti gli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="dfe97-115">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="dfe97-116">Se gli utenti vengono sincronizzati dall'ambiente locale, disattivare prima la sincronizzazione, quindi eliminare gli utenti nella directory cloud utilizzando il portale di Azure o i cmdlet di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dfe97-116">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="dfe97-117">Per eliminare gli utenti, vedere <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">Amministratore gestione utenti: Eliminare uno o più utenti.</a></span><span class="sxs-lookup"><span data-stu-id="dfe97-117">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="dfe97-118">È inoltre possibile utilizzare il cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> di PowerShell per eliminare gli utenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="dfe97-118">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="dfe97-119">Se l'organizzazione usa Active Directory che si sincronizza con Microsoft Azure Active Directory (Azure AD), elimina invece l'account utente da Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dfe97-119">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="dfe97-120">Per istruzioni, vedere <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Eliminare in blocco gli utenti in Azure Active Directory.</a></span><span class="sxs-lookup"><span data-stu-id="dfe97-120">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="dfe97-121">Passaggio 2: Annullare tutte le sottoscrizioni attive</span><span class="sxs-lookup"><span data-stu-id="dfe97-121">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="dfe97-122">Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="dfe97-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="dfe97-123">Nella scheda **Prodotti** trovare un abbonamento attivo.</span><span class="sxs-lookup"><span data-stu-id="dfe97-123">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="dfe97-124">Selezionare **Altre azioni** (tre puntini), quindi selezionare **Annulla l’abbonamento**.</span><span class="sxs-lookup"><span data-stu-id="dfe97-124">Select **More actions** (three dots), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="dfe97-125">Nel riquadro **Annulla abbonamento** scegliere un motivo per cui si vuole annullare l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="dfe97-125">In the **Cancel subscription** pane, choose a reason why you're canceling.</span></span> <span data-ttu-id="dfe97-126">Se si vuole, inviare un feedback.</span><span class="sxs-lookup"><span data-stu-id="dfe97-126">Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="dfe97-127">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="dfe97-127">Select **Save**.</span></span>
5. <span data-ttu-id="dfe97-128">Ripetere i passaggi da 1 a 4 per annullare tutte le sottoscrizioni attive.</span><span class="sxs-lookup"><span data-stu-id="dfe97-128">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="dfe97-129">Passaggio 3: Eliminare tutte le sottoscrizioni disabilitate</span><span class="sxs-lookup"><span data-stu-id="dfe97-129">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="dfe97-130">Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="dfe97-130">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="dfe97-131">Nella scheda **Prodotti** selezionare una sottoscrizione disabilitata.</span><span class="sxs-lookup"><span data-stu-id="dfe97-131">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="dfe97-132">Nella sezione Impostazioni sottoscrizione e pagamento della pagina dei dettagli **dell'abbonamento** selezionare **Elimina sottoscrizione.**</span><span class="sxs-lookup"><span data-stu-id="dfe97-132">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="dfe97-133">Nel riquadro **Elimina sottoscrizione** selezionare **Elimina sottoscrizione.**</span><span class="sxs-lookup"><span data-stu-id="dfe97-133">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="dfe97-134">Nella finestra **di dialogo Elimina** sottoscrizione selezionare **Sì.**</span><span class="sxs-lookup"><span data-stu-id="dfe97-134">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="dfe97-135">Per ogni sottoscrizione disabilitata, ripetere i passaggi da 3 a 5 fino a eliminare tutte le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="dfe97-135">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="dfe97-136">Se non è possibile eliminare immediatamente una sottoscrizione disabilitata, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contattare il supporto tecnico</a></span><span class="sxs-lookup"><span data-stu-id="dfe97-136">If you're unable to immediately delete a disabled subscription, <a href="https://go.microsoft.com/fwlink/p/?linkid=518322" target="_blank">contact support</a></span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="dfe97-137">Passaggio 4: Disabilitare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="dfe97-137">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="dfe97-138">Accedere all'interfaccia di amministrazione con un account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="dfe97-138">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="dfe97-139">Per verificare i ruoli di cui si dispone, vedere [Controllare i ruoli di amministratore nell'organizzazione.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="dfe97-139">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="dfe97-140">Passare alla **pagina Utenti**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">attivi.</a></span><span class="sxs-lookup"><span data-stu-id="dfe97-140">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="dfe97-141">Scegliere **Autenticazione a più fattori.**</span><span class="sxs-lookup"><span data-stu-id="dfe97-141">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="dfe97-142">Nella pagina Autenticazione a più fattori disabilitare tutti gli account ad eccezione dell'account amministratore globale attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="dfe97-142">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="dfe97-143">È inoltre possibile <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">utilizzare PowerShell per disabilitare l'autenticazione</a>a più fattori per più utenti.</span><span class="sxs-lookup"><span data-stu-id="dfe97-143">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="dfe97-144">Passaggio 5: eliminare la directory in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="dfe97-144">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="dfe97-145">Accedere all'interfaccia <a href="https://aad.portal.azure.com/" target="_blank">di amministrazione di Azure AD</a> con un account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="dfe97-145">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="dfe97-146">Selezionare **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="dfe97-146">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="dfe97-147">Passare all'organizzazione che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="dfe97-147">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="dfe97-148">Selezionare **Elimina tenant.**</span><span class="sxs-lookup"><span data-stu-id="dfe97-148">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="dfe97-149">Se l'organizzazione non supera uno o più controlli, viene visualizzato un collegamento a ulteriori informazioni su come superare i controlli.</span><span class="sxs-lookup"><span data-stu-id="dfe97-149">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="dfe97-150">Dopo aver superato tutti i controlli, selezionare **Elimina** per completare il processo.</span><span class="sxs-lookup"><span data-stu-id="dfe97-150">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="dfe97-151">Dopo aver completato questo passaggio finale, l'account con Microsoft viene chiuso ed eliminato.</span><span class="sxs-lookup"><span data-stu-id="dfe97-151">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>