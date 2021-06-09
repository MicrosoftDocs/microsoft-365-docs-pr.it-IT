---
title: Chiudere il proprio account
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- fwlink 2133922 to Delete subscription heading
- commerce_subscription
search.appverid: MET150
description: Quando chiudi l'account con Microsoft, tutte le informazioni relative al tuo account vengono eliminate, incluse le licenze, gli utenti e i dati degli utenti.
ms.date: 04/02/2021
ms.openlocfilehash: b212911707b5d6a967ab833a5a06bc76f5ceeb3b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52624326"
---
# <a name="close-your-account"></a><span data-ttu-id="d52f4-103">Chiudere il proprio account</span><span class="sxs-lookup"><span data-stu-id="d52f4-103">Close your account</span></span>

<span data-ttu-id="d52f4-104">Quando si chiude l'account con Microsoft, verranno eliminate tutte le informazioni correlate all'account.</span><span class="sxs-lookup"><span data-stu-id="d52f4-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="d52f4-105">Queste informazioni includono abbonamenti, licenze, modalità di pagamento, utenti e dati utente.</span><span class="sxs-lookup"><span data-stu-id="d52f4-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d52f4-106">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="d52f4-106">Before you begin</span></span>

<span data-ttu-id="d52f4-107">Prima di iniziare questo processo, assicurarsi di eseguire il backup dei dati che si vogliono conservare.</span><span class="sxs-lookup"><span data-stu-id="d52f4-107">Before you start this process, make sure to back up any data that you want to preserve.</span></span>

<span data-ttu-id="d52f4-108">È necessario essere un amministratore globale o un amministratore di fatturazione per eseguire le procedure descritte in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="d52f4-108">You must be a Global or Billing admin to do the tasks in this article.</span></span> <span data-ttu-id="d52f4-109">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore](../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="d52f4-109">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="d52f4-110">Passaggio 1: eliminare gli utenti</span><span class="sxs-lookup"><span data-stu-id="d52f4-110">Step 1: Delete users</span></span>

<span data-ttu-id="d52f4-111">Eliminare tutti gli utenti ad eccezione di un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="d52f4-111">Delete all users except for one global administrator.</span></span> <span data-ttu-id="d52f4-112">L'amministratore globale completa i passaggi per chiudere l'account.</span><span class="sxs-lookup"><span data-stu-id="d52f4-112">The global administrator completes the steps to close the account.</span></span> <span data-ttu-id="d52f4-113">Prima di poter eliminare la directory al termine di questo processo, è necessario eliminare tutti gli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="d52f4-113">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="d52f4-114">Se gli utenti vengono sincronizzati da locale, disattivare prima la sincronizzazione, quindi eliminare gli utenti nella directory cloud utilizzando il portale di Azure o i cmdlet di Azure PowerShell azure.</span><span class="sxs-lookup"><span data-stu-id="d52f4-114">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="d52f4-115">Per eliminare gli utenti, vedere [Amministratore gestione utenti: Eliminare uno o più utenti](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span><span class="sxs-lookup"><span data-stu-id="d52f4-115">To delete users, see [User management admin: Delete one or more users](../admin/add-users/delete-a-user.md#user-management-admin-delete-one-or-more-users-from-office-365).</span></span>

<span data-ttu-id="d52f4-116">È inoltre possibile utilizzare il cmdlet [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell per eliminare gli utenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="d52f4-116">You can also use the [Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="d52f4-117">Se l'organizzazione usa Active Directory che si sincronizza con Microsoft Azure Active Directory (Azure AD), elimina invece l'account utente da Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d52f4-117">If your organization uses Active Directory that synchronizes with Microsoft Azure Active Directory (Azure AD), delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="d52f4-118">Per istruzioni, vedere [Eliminazione in blocco degli utenti in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).</span><span class="sxs-lookup"><span data-stu-id="d52f4-118">For instructions, see [Bulk delete users in Azure Active Directory](/azure/active-directory/users-groups-roles/users-bulk-delete).</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="d52f4-119">Passaggio 2: Annullare tutte le sottoscrizioni attive</span><span class="sxs-lookup"><span data-stu-id="d52f4-119">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="d52f4-120">Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="d52f4-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="d52f4-121">Nella scheda **Prodotti** trovare un abbonamento attivo.</span><span class="sxs-lookup"><span data-stu-id="d52f4-121">On the **Products** tab, find an active subscription.</span></span> <span data-ttu-id="d52f4-122">Selezionare i tre puntini (Altre azioni) e quindi **Annulla abbonamento**.</span><span class="sxs-lookup"><span data-stu-id="d52f4-122">Select the three dots (more actions), then select **Cancel subscription**.</span></span>
3. <span data-ttu-id="d52f4-p106">Nel riquadro **Annulla abbonamento** scegliere un motivo per cui si vuole annullare l'abbonamento. Se si vuole, inviare un feedback.</span><span class="sxs-lookup"><span data-stu-id="d52f4-p106">In the **Cancel subscription** pane, choose a reason why you're canceling. Optionally, provide any feedback.</span></span>
4. <span data-ttu-id="d52f4-125">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d52f4-125">Select **Save**.</span></span>
5. <span data-ttu-id="d52f4-126">Ripetere i passaggi da 1 a 4 per annullare tutte le sottoscrizioni attive.</span><span class="sxs-lookup"><span data-stu-id="d52f4-126">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="d52f4-127">Passaggio 3: Eliminare tutte le sottoscrizioni disabilitate</span><span class="sxs-lookup"><span data-stu-id="d52f4-127">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="d52f4-128">Nell'interfaccia di amministrazione, passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">I tuoi prodotti</a>.</span><span class="sxs-lookup"><span data-stu-id="d52f4-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="d52f4-129">Nella scheda **Prodotti** selezionare una sottoscrizione disabilitata.</span><span class="sxs-lookup"><span data-stu-id="d52f4-129">On the **Products** tab, select a disabled subscription.</span></span>
3. <span data-ttu-id="d52f4-130">Nella sezione Impostazioni sottoscrizione e pagamento della pagina dei dettagli **dell'abbonamento** selezionare **Elimina sottoscrizione.**</span><span class="sxs-lookup"><span data-stu-id="d52f4-130">On the subscription details page, in the **Subscription and payment settings** section, select **Delete subscription**.</span></span>
4. <span data-ttu-id="d52f4-131">Nel riquadro **Elimina sottoscrizione** selezionare **Elimina sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="d52f4-131">In the **Delete subscription** pane, select **Delete subscription**.</span></span>
5. <span data-ttu-id="d52f4-132">Nella finestra **di dialogo** Elimina sottoscrizione selezionare **Sì.**</span><span class="sxs-lookup"><span data-stu-id="d52f4-132">In the **Delete subscription** dialog box, select **Yes**.</span></span>
6. <span data-ttu-id="d52f4-133">Per ogni sottoscrizione disabilitata, ripetere i passaggi da 3 a 5 finché non vengono eliminate tutte le sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="d52f4-133">For each disabled subscription, repeat steps 3 through 5 until all subscriptions are deleted.</span></span>

> [!NOTE]
> <span data-ttu-id="d52f4-134">Se non è possibile eliminare immediatamente una sottoscrizione disabilitata, [contattare il supporto](../business-video/get-help-support.md)tecnico.</span><span class="sxs-lookup"><span data-stu-id="d52f4-134">If you're unable to immediately delete a disabled subscription, [contact support](../business-video/get-help-support.md).</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="d52f4-135">Passaggio 4: Disabilitare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="d52f4-135">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="d52f4-136">Accedi all'interfaccia di amministrazione con un account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="d52f4-136">Sign in to the admin center with a Global administrator account.</span></span> <span data-ttu-id="d52f4-137">Per verificare quali ruoli si hanno, vedere [Controllare i ruoli di amministratore nell'organizzazione.](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="d52f4-137">To verify what roles you have, see [Check admin roles in your organization](../admin/add-users/assign-admin-roles.md#check-admin-roles-in-your-organization).</span></span>
2. <span data-ttu-id="d52f4-138">Passare alla **pagina Utenti**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">utenti</a> attivi.</span><span class="sxs-lookup"><span data-stu-id="d52f4-138">Go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
3. <span data-ttu-id="d52f4-139">Scegliere **Autenticazione a più fattori.**</span><span class="sxs-lookup"><span data-stu-id="d52f4-139">Choose **Multi-factor authentication**.</span></span>
4. <span data-ttu-id="d52f4-140">Nella pagina Autenticazione a più fattori disabilitare tutti gli account ad eccezione dell'account amministratore globale attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="d52f4-140">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="d52f4-141">È inoltre possibile [utilizzare PowerShell per disabilitare l'autenticazione a più fattori per più utenti.](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell)</span><span class="sxs-lookup"><span data-stu-id="d52f4-141">You can also [use PowerShell to disable multi-factor authentication for multiple users](/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell).</span></span>


## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="d52f4-142">Passaggio 5: Eliminare la directory in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d52f4-142">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="d52f4-143">Accedere <a href="https://aad.portal.azure.com/" target="_blank">all'interfaccia di amministrazione di Azure AD</a> con un account amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="d52f4-143">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global administrator account.</span></span>
2. <span data-ttu-id="d52f4-144">Selezionare **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="d52f4-144">Select **Azure Active Directory**.</span></span>
3. <span data-ttu-id="d52f4-145">Passare all'organizzazione che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="d52f4-145">Switch to the organization that you want to delete.</span></span>
4. <span data-ttu-id="d52f4-146">Selezionare **Elimina tenant**.</span><span class="sxs-lookup"><span data-stu-id="d52f4-146">Select **Delete tenant**.</span></span>
5. <span data-ttu-id="d52f4-147">Se l'organizzazione non supera uno o più controlli, viene visualizzato un collegamento a ulteriori informazioni su come superare i controlli.</span><span class="sxs-lookup"><span data-stu-id="d52f4-147">If your organization fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="d52f4-148">Dopo aver superato tutti i controlli, selezionare **Elimina** per completare il processo.</span><span class="sxs-lookup"><span data-stu-id="d52f4-148">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="d52f4-149">Dopo aver completato questo passaggio finale, l'account con Microsoft viene chiuso ed eliminato.</span><span class="sxs-lookup"><span data-stu-id="d52f4-149">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>

## <a name="related-content"></a><span data-ttu-id="d52f4-150">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="d52f4-150">Related content</span></span> 

<span data-ttu-id="d52f4-151">[Comprendere la fattura o la fattura per Microsoft 365 per le aziende](./billing-and-payments/understand-your-invoice2.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="d52f4-151">[Understand your bill or invoice for Microsoft 365 for business](./billing-and-payments/understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="d52f4-152">[Annullare l'abbonamento](./subscriptions/cancel-your-subscription.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="d52f4-152">[Cancel your subscription](./subscriptions/cancel-your-subscription.md) (article)</span></span>

