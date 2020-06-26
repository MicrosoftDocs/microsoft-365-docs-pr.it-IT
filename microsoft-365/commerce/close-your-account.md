---
title: Chiudere il proprio account
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: Informazioni su come chiudere l'account con Microsoft.
ms.openlocfilehash: a92b9f2053d9acf4e8233bee7a42047f51288943
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2020
ms.locfileid: "44898922"
---
# <a name="close-your-account"></a><span data-ttu-id="70fd9-103">Chiudere il proprio account</span><span class="sxs-lookup"><span data-stu-id="70fd9-103">Close your account</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="70fd9-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="70fd9-104">The admin center is changing.</span></span> <span data-ttu-id="70fd9-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="70fd9-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="70fd9-106">Quando si chiude l'account con Microsoft, verranno eliminate tutte le informazioni correlate all'account.</span><span class="sxs-lookup"><span data-stu-id="70fd9-106">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="70fd9-107">Queste informazioni includono abbonamenti, licenze, modalità di pagamento, utenti e dati utente.</span><span class="sxs-lookup"><span data-stu-id="70fd9-107">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="70fd9-108">Prima di iniziare questa procedura, verificare di eseguire il backup di tutti i dati che si desidera conservare.</span><span class="sxs-lookup"><span data-stu-id="70fd9-108">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="70fd9-109">Passaggio 1: eliminare gli utenti</span><span class="sxs-lookup"><span data-stu-id="70fd9-109">Step 1: Delete users</span></span>

<span data-ttu-id="70fd9-110">Eliminare tutti gli utenti ad eccezione di un amministratore globale che completa la procedura per chiudere l'account.</span><span class="sxs-lookup"><span data-stu-id="70fd9-110">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="70fd9-111">Prima di poter eliminare la directory alla fine di questo processo, è necessario eliminare tutti gli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="70fd9-111">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="70fd9-112">Se gli utenti vengono sincronizzati dall'ambiente locale, disattivare la sincronizzazione e quindi eliminare gli utenti nella directory cloud utilizzando il portale di Azure o i cmdlet di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="70fd9-112">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="70fd9-113">Per eliminare gli utenti, vedere <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User Management admin: Delete uno o più utenti</a>.</span><span class="sxs-lookup"><span data-stu-id="70fd9-113">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="70fd9-114">È inoltre possibile utilizzare il cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> di PowerShell per eliminare gli utenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="70fd9-114">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="70fd9-115">Se nell'organizzazione viene utilizzato Active Directory che esegue la sincronizzazione con Azure AD, eliminare l'account utente da Active Directory.</span><span class="sxs-lookup"><span data-stu-id="70fd9-115">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="70fd9-116">Per istruzioni, vedere <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">eliminare in blocco gli utenti in Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="70fd9-116">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="70fd9-117">Passaggio 2: annullare tutte le sottoscrizioni attive</span><span class="sxs-lookup"><span data-stu-id="70fd9-117">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="70fd9-118">Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> .</span><span class="sxs-lookup"><span data-stu-id="70fd9-118">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="70fd9-119">Se l'elenco abbonamenti è in visualizzazione **tabella** , fare clic su **schede**sulla destra.</span><span class="sxs-lookup"><span data-stu-id="70fd9-119">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="70fd9-120">Per trovare un abbonamento attivo e nella sezione **impostazioni & azioni** , selezionare **Annulla sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="70fd9-120">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="70fd9-121">Seguire le istruzioni visualizzate per completare il processo.</span><span class="sxs-lookup"><span data-stu-id="70fd9-121">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="70fd9-122">Ripetere i passaggi da 1 a 4 per annullare tutti gli abbonamenti attivi.</span><span class="sxs-lookup"><span data-stu-id="70fd9-122">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="70fd9-123">Passaggio 3: eliminare tutte le sottoscrizioni disabilitate</span><span class="sxs-lookup"><span data-stu-id="70fd9-123">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="70fd9-124">Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">prodotti</a> .</span><span class="sxs-lookup"><span data-stu-id="70fd9-124">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="70fd9-125">Se l'elenco abbonamenti è in visualizzazione **tabella** , fare clic su **schede**sulla destra.</span><span class="sxs-lookup"><span data-stu-id="70fd9-125">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="70fd9-126">Accanto a **stato sottoscrizione**, selezionare **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="70fd9-126">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="70fd9-127">Trovare una sottoscrizione disabilitata e nella sezione **impostazioni & azioni** selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="70fd9-127">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="70fd9-128">Nella finestra di dialogo **Elimina sottoscrizione** selezionare la casella di controllo **l'impatto** , quindi selezionare **Elimina sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="70fd9-128">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="70fd9-129">Per ogni sottoscrizione disabilitata, ripetere i passaggi 4 e 5 finché tutte le sottoscrizioni non sono state eliminate.</span><span class="sxs-lookup"><span data-stu-id="70fd9-129">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="70fd9-130">Passaggio 4: disabilitare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="70fd9-130">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="70fd9-131">Nell'interfaccia di amministrazione, andare alla pagina **utenti**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">attivi</a> .</span><span class="sxs-lookup"><span data-stu-id="70fd9-131">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="70fd9-132">Scegliere **l'autenticazione a più fattori**.</span><span class="sxs-lookup"><span data-stu-id="70fd9-132">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="70fd9-133">Nella pagina autenticazione a più fattori disabilitare tutti gli account tranne l'account di amministratore globale attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="70fd9-133">On the multi-factor authentication page, disable all accounts except for the global admin account that you're currently using.</span></span>

<span data-ttu-id="70fd9-134">È inoltre possibile <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">utilizzare PowerShell per disabilitare l'autenticazione a più fattori per più utenti</a>.</span><span class="sxs-lookup"><span data-stu-id="70fd9-134">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#change-state-using-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="70fd9-135">Passaggio 5: eliminare la directory in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="70fd9-135">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="70fd9-136">Accedere all'interfaccia di <a href="https://aad.portal.azure.com/" target="_blank">amministrazione di Azure ad</a> con un account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="70fd9-136">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="70fd9-137">Selezionare **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="70fd9-137">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="70fd9-138">Passare alla directory che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="70fd9-138">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="70fd9-139">Selezionare **Elimina directory**.</span><span class="sxs-lookup"><span data-stu-id="70fd9-139">Select **Delete directory**.</span></span>

5. <span data-ttu-id="70fd9-140">Se la directory ha esito negativo su uno o più controlli, viene visualizzato un collegamento a ulteriori informazioni su come superare i controlli.</span><span class="sxs-lookup"><span data-stu-id="70fd9-140">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="70fd9-141">Dopo aver superato tutti i controlli, selezionare **Elimina** per completare il processo.</span><span class="sxs-lookup"><span data-stu-id="70fd9-141">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="70fd9-142">Dopo aver completato questo passaggio finale, l'account con Microsoft viene chiuso ed eliminato.</span><span class="sxs-lookup"><span data-stu-id="70fd9-142">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>
