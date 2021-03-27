---
title: Assegnare licenze agli utenti
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce
search.appverid:
- MET150
description: Informazioni su come assegnare licenze agli utenti.
ms.openlocfilehash: 3622be180ae622d5d08066cc03773a8175fe9342
ms.sourcegitcommit: c5d1528559953c6db7dca1d5cb453e0aa3215f02
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/27/2021
ms.locfileid: "51398164"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="af133-103">Assegnare licenze agli utenti</span><span class="sxs-lookup"><span data-stu-id="af133-103">Assign licenses to users</span></span>

<span data-ttu-id="af133-104">È possibile assegnare licenze agli utenti nella pagina **Utenti attivi** o nella pagina **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="af133-104">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="af133-105">Il metodo da usare varia a seconda che si vogliano assegnare licenze di prodotto a utenti specifici o assegnare licenze utente a prodotti specifici.</span><span class="sxs-lookup"><span data-stu-id="af133-105">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

> [!NOTE]
> <span data-ttu-id="af133-106">Gli amministratori non possono assegnare o annullare l'assegnazione di licenze per un abbonamento acquistato in modalità self-service da un utente dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="af133-106">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="af133-107">È possibile [assumere il controllo di un abbonamento acquistato in modalità self-service](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription) e quindi assegnare licenze o annullarne l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="af133-107">You can [take over a self-service purchase subscription](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

<span data-ttu-id="af133-108">[Vedere come aggiungere un utente e contemporaneamente assegnargli una licenza](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="af133-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="af133-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="af133-109">Before you begin</span></span>

- <span data-ttu-id="af133-110">Per assegnare le licenze è necessario essere un amministratore globale, delle licenze o degli utenti.</span><span class="sxs-lookup"><span data-stu-id="af133-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="af133-111">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="af133-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="af133-112">È possibile [assegnare licenze ad account utente con PowerShell di Office 365](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="af133-112">You can [assign licenses to user accounts with Office 365 PowerShell](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).</span></span>
- <span data-ttu-id="af133-113">Per usare licenze basate su gruppi, vedere [Assegnare licenze agli utenti in base all'appartenenza ai gruppi in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="af133-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="af133-114">Alcuni servizi, come Sway, vengono assegnati agli utenti automaticamente e non è necessario assegnarli singolarmente.</span><span class="sxs-lookup"><span data-stu-id="af133-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="af133-115">Usare la pagina Licenze per assegnare licenze agli utenti</span><span class="sxs-lookup"><span data-stu-id="af133-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="af133-116">Nella pagina **Licenze** si assegnano licenze di un prodotto specifico a un massimo di 20 utenti.</span><span class="sxs-lookup"><span data-stu-id="af133-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="af133-117">Nella pagina **Licenze** viene visualizzato un elenco di tutti i prodotti per cui si hanno abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="af133-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="af133-118">Si può anche vedere il numero totale di licenze per ogni prodotto, il numero di licenze assegnate e il numero di licenze disponibili.</span><span class="sxs-lookup"><span data-stu-id="af133-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="af133-119">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="af133-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="af133-120">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="af133-120">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="af133-121">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="af133-121">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="af133-122">Selezionare un prodotto.</span><span class="sxs-lookup"><span data-stu-id="af133-122">Select a product.</span></span>
3. <span data-ttu-id="af133-123">Nella pagina dei dettagli sul prodotto selezionare **Assegna licenze**.</span><span class="sxs-lookup"><span data-stu-id="af133-123">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="af133-124">Nel riquadro **Assegna licenze agli utenti** iniziare a digitare un nome, quindi selezionarlo nei risultati per aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="af133-124">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="af133-125">È possibile aggiungere fino a 20 utenti per volta.</span><span class="sxs-lookup"><span data-stu-id="af133-125">You can add up to 20 users at a time.</span></span>
4. <span data-ttu-id="af133-126">Selezionare **Abilita o disabilita le app e i servizi** per assegnare o rimuovere l'accesso a elementi specifici.</span><span class="sxs-lookup"><span data-stu-id="af133-126">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="af133-127">Al termine, selezionare **Assegna**, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="af133-127">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="af133-128">In caso di conflitto viene visualizzato un messaggio che indica qual è il problema e come risolverlo.</span><span class="sxs-lookup"><span data-stu-id="af133-128">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="af133-129">Se, ad esempio, sono state selezionate licenze che contengono servizi in conflitto, viene visualizzato un messaggio di errore che suggerisce di rivedere i servizi inclusi in ogni licenza e riprovare.</span><span class="sxs-lookup"><span data-stu-id="af133-129">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="af133-130">Modificare le app e i servizi a cui un utente ha accesso</span><span class="sxs-lookup"><span data-stu-id="af133-130">Change the apps and services a user has access to</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="af133-131">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="af133-131">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="af133-132">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="af133-132">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="af133-133">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="af133-133">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Licenses** page.</span></span>

::: moniker-end

2. <span data-ttu-id="af133-134">Nella pagina **Licenze** selezionare la riga relativa a uno specifico utente.</span><span class="sxs-lookup"><span data-stu-id="af133-134">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="af133-135">Nel riquadro destro selezionare o deselezionare le app e i servizi per i quali si desidera consentire o rimuovere l'accesso.</span><span class="sxs-lookup"><span data-stu-id="af133-135">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="af133-136">Al termine, selezionare **Salva**, quindi selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="af133-136">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="af133-137">Usare la pagina Utenti attivi per assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="af133-137">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="af133-138">Nella pagina **Utenti attivi** si assegnano licenze utente ai prodotti.</span><span class="sxs-lookup"><span data-stu-id="af133-138">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="af133-139">Assegnare licenze a più utenti</span><span class="sxs-lookup"><span data-stu-id="af133-139">Assign licenses to multiple users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="af133-140">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="af133-140">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="af133-141">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="af133-141">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="af133-142">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="af133-142">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="af133-143">Selezionare i cerchi accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="af133-143">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="af133-144">Nella parte superiore selezionare **Altre opzioni (...)**, quindi selezionare **Gestisci licenze prodotto**.</span><span class="sxs-lookup"><span data-stu-id="af133-144">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="af133-145">Nel riquadro **Gestisci licenze prodotto** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="af133-145">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="af133-146">Nel riquadro **Aggiungi a prodotti esistenti** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza che si vuole assegnare agli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="af133-146">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="af133-147">Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="af133-147">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="af133-148">È possibile porre limiti ai servizi disponibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="af133-148">You can limit which services are available to the users.</span></span> <span data-ttu-id="af133-149">Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="af133-149">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="af133-150">Nella parte inferiore del riquadro selezionare **Aggiungi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="af133-150">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="af133-151">Assegnare licenze a un utente</span><span class="sxs-lookup"><span data-stu-id="af133-151">Assign licenses to one user</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="af133-152">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="af133-152">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="af133-153">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="af133-153">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="af133-154">Nell'<a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">interfaccia di amministrazione</a> passare alla pagina **Fatturazione** > **Utenti attivi**.</span><span class="sxs-lookup"><span data-stu-id="af133-154">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Active users** page.</span></span>

::: moniker-end

2. <span data-ttu-id="af133-155">Selezionare la riga dell'utente al quale si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="af133-155">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="af133-156">Nel riquadro destro selezionare **Licenze e app**.</span><span class="sxs-lookup"><span data-stu-id="af133-156">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="af133-157">Espandere la sezione **Licenze**, selezionare le caselle delle licenze da assegnare, quindi selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="af133-157">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="af133-158">Assegnare una licenza a un utente guest</span><span class="sxs-lookup"><span data-stu-id="af133-158">Assign a license to a guest user</span></span>

<span data-ttu-id="af133-159">È possibile invitare gli utenti guest a collaborare con l'organizzazione nell'interfaccia di amministrazione di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="af133-159">You can invite guest users to collaborate with your organization in the Azure Active Directory admin center.</span></span> <span data-ttu-id="af133-160">Per informazioni sugli utenti guest, vedere [Cos'è l'accesso degli utenti guest in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b)</span><span class="sxs-lookup"><span data-stu-id="af133-160">To learn about guest users, see [What is guest user access in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b).</span></span> <span data-ttu-id="af133-161">Se vi sono utenti guest, vedere [Guida introduttiva: aggiungere utenti guest alla directory nel portale di Azure](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="af133-161">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="af133-162">Per eseguire questi passaggi, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="af133-162">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="af133-163">Andare sull’<a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">interfaccia di amministrazione di Azure Active Directory</a></span><span class="sxs-lookup"><span data-stu-id="af133-163">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="af133-164">Nel riquadro di spostamento selezionare **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="af133-164">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="af133-165">Nella pagina **Utenti | Tutti gli utenti (anteprima)**, selezionare **Aggiungi filtri**.</span><span class="sxs-lookup"><span data-stu-id="af133-165">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="af133-166">Nel menu **Selezionare un campo**, scegliere **Tipo di utente**, quindi selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="af133-166">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="af133-167">Nel menu successivo, selezionare **Guest**.</span><span class="sxs-lookup"><span data-stu-id="af133-167">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="af133-168">Nell'elenco dei risultati, selezionare l'utente che necessita di una licenza.</span><span class="sxs-lookup"><span data-stu-id="af133-168">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="af133-169">In **Gestisci**, selezionare **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="af133-169">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="af133-170">Selezionare **Attività**.</span><span class="sxs-lookup"><span data-stu-id="af133-170">Select **Assignments**.</span></span>
9. <span data-ttu-id="af133-171">Nella pagina **Aggiornare le assegnazioni di licenze**, selezionare il prodotto per cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="af133-171">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="af133-172">Nella parte destra, deselezionare le caselle di controllo per tutti i servizi a cui non si vuole consentire l'accesso all'utente guest.</span><span class="sxs-lookup"><span data-stu-id="af133-172">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="af133-173">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="af133-173">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="af133-174">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="af133-174">Next steps</span></span>

<span data-ttu-id="af133-175">Se gli utenti non hanno ancora installato le app di Office, si può condividere con loro la [guida introduttiva per i dipendenti](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f), ricca di informazioni su come, ad esempio, [scaricare e installare Microsoft 365 o Office 2019 in un PC o un Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) e [configurare le app di Office e la posta elettronica in un dispositivo mobile](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="af133-175">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="af133-176">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="af133-176">Related content</span></span>

<span data-ttu-id="af133-177">[Informazioni su abbonamenti e licenze](../../commerce/licenses/subscriptions-and-licenses.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="af133-177">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="af133-178">[Annullare l'assegnazione delle licenze agli utenti](remove-licenses-from-users.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="af133-178">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="af133-179">[Acquistare o rimuovere licenze per l'abbonamento](../../commerce/licenses/buy-licenses.md) (articolo)\</span><span class="sxs-lookup"><span data-stu-id="af133-179">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>