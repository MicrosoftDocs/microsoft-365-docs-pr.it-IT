---
title: Assegnare licenze agli utenti
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Informazioni su come assegnare licenze agli utenti.
ms.date: 07/01/2020
ms.openlocfilehash: 648a3433bf5c2bd9bb96abb90335f56ee4fb6bee
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "45015948"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="a7071-103">Assegnare licenze agli utenti</span><span class="sxs-lookup"><span data-stu-id="a7071-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a7071-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="a7071-104">The admin center is changing.</span></span> <span data-ttu-id="a7071-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a7071-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="a7071-106">È possibile assegnare licenze agli utenti nella pagina **Utenti attivi** o nella pagina **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="a7071-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="a7071-107">Il metodo da usare varia a seconda che si vogliano assegnare licenze di prodotto a utenti specifici o assegnare licenze utente a prodotti specifici.</span><span class="sxs-lookup"><span data-stu-id="a7071-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="a7071-108">[Vedere come aggiungere un utente e contemporaneamente assegnargli una licenza](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="a7071-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a7071-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="a7071-109">Before you begin</span></span>

- <span data-ttu-id="a7071-110">Per assegnare le licenze è necessario essere un amministratore globale, delle licenze o degli utenti.</span><span class="sxs-lookup"><span data-stu-id="a7071-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="a7071-111">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="a7071-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="a7071-112">È possibile [assegnare licenze ad account utente con PowerShell di Office 365](https://go.microsoft.com/fwlink/p/?linkid=850410).</span><span class="sxs-lookup"><span data-stu-id="a7071-112">You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span></span>
- <span data-ttu-id="a7071-113">Per usare licenze basate su gruppi, vedere [Assegnare licenze agli utenti in base all'appartenenza ai gruppi in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="a7071-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="a7071-114">Alcuni servizi, come Sway, vengono assegnati agli utenti automaticamente e non è necessario assegnarli singolarmente.</span><span class="sxs-lookup"><span data-stu-id="a7071-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="a7071-115">Usare la pagina Licenze per assegnare licenze agli utenti</span><span class="sxs-lookup"><span data-stu-id="a7071-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="a7071-116">Nella pagina **Licenze** si assegnano licenze di un prodotto specifico a un massimo di 20 utenti.</span><span class="sxs-lookup"><span data-stu-id="a7071-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="a7071-117">Nella pagina **Licenze** viene visualizzato un elenco di tutti i prodotti per cui si hanno abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="a7071-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="a7071-118">Si può anche vedere il numero totale di licenze per ogni prodotto, il numero di licenze assegnate e il numero di licenze disponibili.</span><span class="sxs-lookup"><span data-stu-id="a7071-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="a7071-119">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="a7071-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="a7071-120">Selezionare un prodotto.</span><span class="sxs-lookup"><span data-stu-id="a7071-120">Select a product.</span></span>
3. <span data-ttu-id="a7071-121">Nella pagina dei dettagli sul prodotto selezionare **Assegna licenze**.</span><span class="sxs-lookup"><span data-stu-id="a7071-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="a7071-122">Nel riquadro **Assegna licenze agli utenti** iniziare a digitare un nome, quindi selezionarlo nei risultati per aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="a7071-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="a7071-123">È possibile aggiungere fino a 20 utenti per volta.</span><span class="sxs-lookup"><span data-stu-id="a7071-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="a7071-124">Selezionare **Abilita o disabilita le app e i servizi** per assegnare o rimuovere l'accesso a elementi specifici.</span><span class="sxs-lookup"><span data-stu-id="a7071-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="a7071-125">Al termine, selezionare **Assegna**, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a7071-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="a7071-126">In caso di conflitto viene visualizzato un messaggio che indica qual è il problema e come risolverlo.</span><span class="sxs-lookup"><span data-stu-id="a7071-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="a7071-127">Se, ad esempio, sono state selezionate licenze che contengono servizi in conflitto, viene visualizzato un messaggio di errore che suggerisce di rivedere i servizi inclusi in ogni licenza e riprovare.</span><span class="sxs-lookup"><span data-stu-id="a7071-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="a7071-128">Modificare le app e i servizi a cui un utente ha accesso</span><span class="sxs-lookup"><span data-stu-id="a7071-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="a7071-129">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="a7071-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="a7071-130">Nella pagina **Licenze** selezionare la riga relativa a uno specifico utente.</span><span class="sxs-lookup"><span data-stu-id="a7071-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="a7071-131">Nel riquadro destro selezionare o deselezionare le app e i servizi per i quali si desidera consentire o rimuovere l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a7071-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="a7071-132">Al termine, selezionare **Salva**, quindi selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a7071-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="a7071-133">Usare la pagina Utenti attivi per assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="a7071-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="a7071-134">Nella pagina **Utenti attivi** si assegnano licenze utente ai prodotti.</span><span class="sxs-lookup"><span data-stu-id="a7071-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="a7071-135">Assegnare licenze a più utenti</span><span class="sxs-lookup"><span data-stu-id="a7071-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="a7071-136">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="a7071-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="a7071-137">Selezionare i cerchi accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="a7071-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="a7071-138">Nella parte superiore selezionare **Altre opzioni (...)**, quindi selezionare **Gestisci licenze prodotto**.</span><span class="sxs-lookup"><span data-stu-id="a7071-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="a7071-139">Nel riquadro **Gestisci licenze prodotto** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a7071-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="a7071-140">Nel riquadro **Aggiungi a prodotti esistenti** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza che si vuole assegnare agli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="a7071-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="a7071-141">Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="a7071-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="a7071-142">È possibile porre limiti ai servizi disponibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="a7071-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="a7071-143">Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="a7071-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="a7071-144">Nella parte inferiore del riquadro selezionare **Aggiungi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a7071-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="a7071-145">Assegnare licenze a più utenti</span><span class="sxs-lookup"><span data-stu-id="a7071-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="a7071-146">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="a7071-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="a7071-147">Selezionare le caselle accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="a7071-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="a7071-148">Nel riquadro **Azioni in blocco** selezionare **Modifica licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="a7071-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="a7071-149">Nel riquadro**Assegna prodotti** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a7071-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="a7071-150">Impostare sulla posizione **Attivata** l'interruttore relativo alle licenze che si vogliono assegnare agli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="a7071-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="a7071-151">Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="a7071-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="a7071-152">È possibile porre limiti ai servizi disponibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="a7071-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="a7071-153">Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="a7071-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="a7071-154">Nella parte inferiore del riquadro **Aggiungi a prodotti esistenti** selezionare **Aggiungi** \> **Chiudi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a7071-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="a7071-155">Assegnare licenze a più utenti</span><span class="sxs-lookup"><span data-stu-id="a7071-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="a7071-156">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="a7071-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="a7071-157">Selezionare le caselle accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="a7071-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="a7071-158">Nel riquadro **Azioni in blocco** selezionare **Modifica licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="a7071-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="a7071-159">Nel riquadro**Assegna prodotti** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="a7071-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="a7071-160">Impostare sulla posizione **Attivata** l'interruttore relativo alle licenze che si vogliono assegnare agli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="a7071-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="a7071-161">Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="a7071-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="a7071-162">È possibile porre limiti ai servizi disponibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="a7071-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="a7071-163">Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="a7071-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="a7071-164">Nella parte inferiore del riquadro **Aggiungi a prodotti esistenti** selezionare **Aggiungi** \> **Chiudi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a7071-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="a7071-165">Assegnare licenze a un utente</span><span class="sxs-lookup"><span data-stu-id="a7071-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="a7071-166">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="a7071-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="a7071-167">Selezionare la riga dell'utente al quale si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="a7071-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="a7071-168">Nel riquadro destro selezionare **Licenze e app**.</span><span class="sxs-lookup"><span data-stu-id="a7071-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="a7071-169">Espandere la sezione **Licenze**, selezionare le caselle delle licenze da assegnare, quindi selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a7071-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="a7071-170">Assegnare licenze a un utente</span><span class="sxs-lookup"><span data-stu-id="a7071-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="a7071-171">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="a7071-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="a7071-172">Selezionare la casella accanto al nome dell'utente a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="a7071-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="a7071-173">Nel riquadro destro, nella riga **Licenze di prodotto** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a7071-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="a7071-174">Nel riquadro **Licenze di prodotto** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza da assegnare all'utente.</span><span class="sxs-lookup"><span data-stu-id="a7071-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="a7071-175">Per impostazione predefinita, tutti i servizi associati alla licenza vengono automaticamente assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="a7071-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="a7071-176">È possibile porre limiti ai servizi disponibili all'utente.</span><span class="sxs-lookup"><span data-stu-id="a7071-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="a7071-177">Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare all'utente.</span><span class="sxs-lookup"><span data-stu-id="a7071-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="a7071-178">Nella parte inferiore del riquadro **Licenze di prodotto** selezionare **Salva** \> **Chiudi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a7071-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="a7071-179">Assegnare licenze a un utente</span><span class="sxs-lookup"><span data-stu-id="a7071-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="a7071-180">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="a7071-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="a7071-181">Selezionare la casella accanto al nome dell'utente a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="a7071-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="a7071-182">Nel riquadro destro, nella riga **Licenze di prodotto** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="a7071-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="a7071-183">Nel riquadro **Licenze di prodotto** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza da assegnare all'utente.</span><span class="sxs-lookup"><span data-stu-id="a7071-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="a7071-184">Per impostazione predefinita, tutti i servizi associati alla licenza vengono automaticamente assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="a7071-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="a7071-185">È possibile porre limiti ai servizi disponibili all'utente.</span><span class="sxs-lookup"><span data-stu-id="a7071-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="a7071-186">Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare all'utente.</span><span class="sxs-lookup"><span data-stu-id="a7071-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="a7071-187">Nella parte inferiore del riquadro **Licenze di prodotto** selezionare **Salva** \> **Chiudi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="a7071-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="next-steps"></a><span data-ttu-id="a7071-188">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="a7071-188">Next steps</span></span>

<span data-ttu-id="a7071-189">Se gli utenti non hanno ancora installato le app di Office, si può condividere con loro la [guida introduttiva per i dipendenti](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f), ricca di informazioni su come, ad esempio, [scaricare e installare Microsoft 365 o Office 2019 in un PC o un Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) e [configurare le app di Office e la posta elettronica in un dispositivo mobile](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="a7071-189">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="a7071-190">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="a7071-190">Related content</span></span>

<span data-ttu-id="a7071-191">[Informazioni su abbonamenti e licenze](../../commerce/licenses/subscriptions-and-licenses.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="a7071-191">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="a7071-192">[Annullare l'assegnazione delle licenze agli utenti](remove-licenses-from-users.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="a7071-192">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="a7071-193">[Acquistare o rimuovere licenze per l'abbonamento](../../commerce/licenses/buy-licenses.md) (articolo)\</span><span class="sxs-lookup"><span data-stu-id="a7071-193">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>