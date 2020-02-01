---
title: Chiudere l'account
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
ms.custom: ''
search.appverid:
- MET150
description: Informazioni su come chiudere l'account con Microsoft.
ms.openlocfilehash: bbb3b56d72c0f67e7771c9a188df751aa3dd95ed
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594140"
---
# <a name="close-your-account"></a><span data-ttu-id="b7940-103">Chiudere l'account</span><span class="sxs-lookup"><span data-stu-id="b7940-103">Close your account</span></span>

<span data-ttu-id="b7940-104">Quando chiudi l'account con Microsoft, tutte le informazioni relative al tuo account vengono eliminate.</span><span class="sxs-lookup"><span data-stu-id="b7940-104">When you close your account with Microsoft, all information related to your account is deleted.</span></span> <span data-ttu-id="b7940-105">Queste informazioni includono abbonamenti, licenze, metodi di pagamento, utenti e dati utente.</span><span class="sxs-lookup"><span data-stu-id="b7940-105">This information includes subscriptions, licenses, payment methods, users, and user data.</span></span> <span data-ttu-id="b7940-106">Prima di iniziare questa procedura, verificare di eseguire il backup di tutti i dati che si desidera conservare.</span><span class="sxs-lookup"><span data-stu-id="b7940-106">Before you start this process, make sure to backup any data that you want to preserve.</span></span>

## <a name="step-1-delete-users"></a><span data-ttu-id="b7940-107">Passaggio 1: eliminare gli utenti</span><span class="sxs-lookup"><span data-stu-id="b7940-107">Step 1: Delete users</span></span>

<span data-ttu-id="b7940-108">Eliminare tutti gli utenti ad eccezione di un amministratore globale che completa la procedura per chiudere l'account.</span><span class="sxs-lookup"><span data-stu-id="b7940-108">Delete all users except for one global administrator who completes the steps to close the account.</span></span> <span data-ttu-id="b7940-109">Prima di poter eliminare la directory alla fine di questo processo, è necessario eliminare tutti gli altri utenti.</span><span class="sxs-lookup"><span data-stu-id="b7940-109">Before you can delete the directory at the end of this process, you must delete all other users.</span></span>

<span data-ttu-id="b7940-110">Se gli utenti vengono sincronizzati dall'ambiente locale, disattivare la sincronizzazione e quindi eliminare gli utenti nella directory cloud utilizzando il portale di Azure o i cmdlet di Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b7940-110">If users are synchronized from on-premises, first turn off sync, then delete the users in the cloud directory by using the Azure portal or Azure PowerShell cmdlets.</span></span>

<span data-ttu-id="b7940-111">Per eliminare gli utenti, vedere <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User Management admin: Delete uno o più utenti</a>.</span><span class="sxs-lookup"><span data-stu-id="b7940-111">To delete users, see <a href="https://docs.microsoft.com/office365/admin/add-users/delete-a-user?view=o365-worldwide#user-management-admin-delete-one-or-more-users-from-office-365">User management admin: Delete one or more users</a>.</span></span>

<span data-ttu-id="b7940-112">È inoltre possibile utilizzare il cmdlet <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> di PowerShell per eliminare gli utenti in blocco.</span><span class="sxs-lookup"><span data-stu-id="b7940-112">You can also use the <a href="https://go.microsoft.com/fwlink/?linkid=842230">Remove-MsolUser</a> PowerShell cmdlet to delete users in bulk.</span></span>

<span data-ttu-id="b7940-113">Se nell'organizzazione viene utilizzato Active Directory che esegue la sincronizzazione con Azure AD, eliminare l'account utente da Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b7940-113">If your organization uses Active Directory that synchronizes with Azure AD, delete the user account from Active Directory, instead.</span></span> <span data-ttu-id="b7940-114">Per istruzioni, vedere <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">eliminare in blocco gli utenti in Azure Active Directory</a>.</span><span class="sxs-lookup"><span data-stu-id="b7940-114">For instructions, see <a href="https://docs.microsoft.com/azure/active-directory/users-groups-roles/users-bulk-delete">Bulk delete users in Azure Active Directory</a>.</span></span>

## <a name="step-2-cancel-all-active-subscriptions"></a><span data-ttu-id="b7940-115">Passaggio 2: annullare tutte le sottoscrizioni attive</span><span class="sxs-lookup"><span data-stu-id="b7940-115">Step 2: Cancel all active subscriptions</span></span>

1. <span data-ttu-id="b7940-116">Nell'interfaccia di amministrazione, accedere alla pagina dei<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">servizi di &</a> di **fatturazione** > .</span><span class="sxs-lookup"><span data-stu-id="b7940-116">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="b7940-117">Se l'elenco abbonamenti è in visualizzazione **tabella** , fare clic su **schede**sulla destra.</span><span class="sxs-lookup"><span data-stu-id="b7940-117">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="b7940-118">Per trovare un abbonamento attivo e nella sezione **impostazioni & azioni** , selezionare **Annulla sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="b7940-118">Find an active subscription, and in the **Settings & Actions** section, select **Cancel subscription**.</span></span>

4. <span data-ttu-id="b7940-119">Seguire le istruzioni visualizzate per completare il processo.</span><span class="sxs-lookup"><span data-stu-id="b7940-119">Follow the prompts to finish the process.</span></span>

5. <span data-ttu-id="b7940-120">Ripetere i passaggi da 1 a 4 per annullare tutti gli abbonamenti attivi.</span><span class="sxs-lookup"><span data-stu-id="b7940-120">Repeat steps 1 through 4 to cancel all active subscriptions.</span></span>

## <a name="step-3-delete-all-disabled-subscriptions"></a><span data-ttu-id="b7940-121">Passaggio 3: eliminare tutte le sottoscrizioni disabilitate</span><span class="sxs-lookup"><span data-stu-id="b7940-121">Step 3: Delete all disabled subscriptions</span></span>

1. <span data-ttu-id="b7940-122">Nell'interfaccia di amministrazione, accedere alla pagina dei<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">servizi di &</a> di **fatturazione** > .</span><span class="sxs-lookup"><span data-stu-id="b7940-122">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="b7940-123">Se l'elenco abbonamenti è in visualizzazione **tabella** , fare clic su **schede**sulla destra.</span><span class="sxs-lookup"><span data-stu-id="b7940-123">If the subscriptions list is in **Table** view, on the right, select **Cards**.</span></span>

3. <span data-ttu-id="b7940-124">Accanto a **stato sottoscrizione**, selezionare **disattivata**.</span><span class="sxs-lookup"><span data-stu-id="b7940-124">Next to **Subscription status**, select **Disabled**.</span></span>

4. <span data-ttu-id="b7940-125">Trovare una sottoscrizione disabilitata e nella sezione **impostazioni & azioni** selezionare **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b7940-125">Find a disabled subscription, and in the **Settings & Actions** section, select **Delete**.</span></span>

5. <span data-ttu-id="b7940-126">Nella finestra di dialogo **Elimina sottoscrizione** selezionare la casella di controllo **l'impatto** , quindi selezionare **Elimina sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="b7940-126">In the **Delete subscription** dialog box, select the **I understand the impact** check box, then select **Delete subscription**.</span></span>

6. <span data-ttu-id="b7940-127">Per ogni sottoscrizione disabilitata, ripetere i passaggi 4 e 5 finché tutte le sottoscrizioni non sono state eliminate.</span><span class="sxs-lookup"><span data-stu-id="b7940-127">For each disabled subscription, repeat steps 4 and 5 until all subscriptions have been deleted.</span></span>

## <a name="step-4-disable-multi-factor-authentication"></a><span data-ttu-id="b7940-128">Passaggio 4: disabilitare l'autenticazione a più fattori</span><span class="sxs-lookup"><span data-stu-id="b7940-128">Step 4: Disable multi-factor authentication</span></span>

1. <span data-ttu-id="b7940-129">Nell'interfaccia di amministrazione, andare alla > pagina **utenti**<a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">attivi</a> .</span><span class="sxs-lookup"><span data-stu-id="b7940-129">In the admin center, go to the **Users** > <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

2. <span data-ttu-id="b7940-130">Scegliere **l'autenticazione a più fattori**.</span><span class="sxs-lookup"><span data-stu-id="b7940-130">Choose **Multi-factor authentication**.</span></span>

3. <span data-ttu-id="b7940-131">Nella pagina autenticazione a più fattori disabilitare tutti gli account tranne l'account di amministratore globale attualmente in uso.</span><span class="sxs-lookup"><span data-stu-id="b7940-131">On the multi-factor authentication page, disable all accounts except for the global admin account that you’re currently using.</span></span>

<span data-ttu-id="b7940-132">È inoltre possibile <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#use-powershell">utilizzare PowerShell per disabilitare l'autenticazione a più fattori per più utenti</a>.</span><span class="sxs-lookup"><span data-stu-id="b7940-132">You can also <a href="https://docs.microsoft.com/azure/active-directory/authentication/howto-mfa-userstates#use-powershell">use PowerShell to disable multi-factor authentication for multiple users</a>.</span></span>

## <a name="step-5-delete-the-directory-in-azure-active-directory"></a><span data-ttu-id="b7940-133">Passaggio 5: eliminare la directory in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b7940-133">Step 5: Delete the directory in Azure Active Directory</span></span>

1. <span data-ttu-id="b7940-134">Accedere all'interfaccia di <a href="https://aad.portal.azure.com/" target="_blank">amministrazione di Azure ad</a> con un account di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="b7940-134">Sign in to the <a href="https://aad.portal.azure.com/" target="_blank">Azure AD admin center</a> with a Global Administrator account.</span></span>

2. <span data-ttu-id="b7940-135">Selezionare **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="b7940-135">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="b7940-136">Passare alla directory che si desidera eliminare.</span><span class="sxs-lookup"><span data-stu-id="b7940-136">Switch to the directory you want to delete.</span></span>

4. <span data-ttu-id="b7940-137">Selezionare **Elimina directory**.</span><span class="sxs-lookup"><span data-stu-id="b7940-137">Select **Delete directory**.</span></span>

5. <span data-ttu-id="b7940-138">Se la directory ha esito negativo su uno o più controlli, viene visualizzato un collegamento a ulteriori informazioni su come superare i controlli.</span><span class="sxs-lookup"><span data-stu-id="b7940-138">If your directory fails one or more checks, you see a link to more information on how to pass the checks.</span></span> <span data-ttu-id="b7940-139">Dopo aver superato tutti i controlli, selezionare **Elimina** per completare il processo.</span><span class="sxs-lookup"><span data-stu-id="b7940-139">After you pass all checks, select **Delete** to complete the process.</span></span>

<span data-ttu-id="b7940-140">Dopo aver completato questo passaggio finale, l'account con Microsoft viene chiuso ed eliminato.</span><span class="sxs-lookup"><span data-stu-id="b7940-140">After you complete this final step, your account with Microsoft is closed and deleted.</span></span>