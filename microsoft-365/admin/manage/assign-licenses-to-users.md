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
ms.date: 08/14/2020
ms.openlocfilehash: e1f28107f7774fa4eccbecb3882cbd002a6eea1a
ms.sourcegitcommit: 919b5d0f33b41b4beaca5fbb06e1c75d65027b7e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/15/2020
ms.locfileid: "46757558"
---
# <a name="assign-licenses-to-users"></a><span data-ttu-id="8bee7-103">Assegnare licenze agli utenti</span><span class="sxs-lookup"><span data-stu-id="8bee7-103">Assign licenses to users</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="8bee7-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="8bee7-104">The admin center is changing.</span></span> <span data-ttu-id="8bee7-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="8bee7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="8bee7-106">È possibile assegnare licenze agli utenti nella pagina **Utenti attivi** o nella pagina **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-106">You can assign licenses to users on either the **Active users** page, or on the **Licenses** page.</span></span> <span data-ttu-id="8bee7-107">Il metodo da usare varia a seconda che si vogliano assegnare licenze di prodotto a utenti specifici o assegnare licenze utente a prodotti specifici.</span><span class="sxs-lookup"><span data-stu-id="8bee7-107">The method you use depends on whether you want to assign product licenses to specific users or assign users licenses to a specific product.</span></span>

::: moniker-end

<span data-ttu-id="8bee7-108">[Vedere come aggiungere un utente e contemporaneamente assegnargli una licenza](../add-users/add-users.md).</span><span class="sxs-lookup"><span data-stu-id="8bee7-108">[Learn how to add a user and assign a license at the same time](../add-users/add-users.md).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8bee7-109">Prima di iniziare</span><span class="sxs-lookup"><span data-stu-id="8bee7-109">Before you begin</span></span>

- <span data-ttu-id="8bee7-110">Per assegnare le licenze è necessario essere un amministratore globale, delle licenze o degli utenti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-110">You must be a Global, License, or User admin to assign licenses.</span></span> <span data-ttu-id="8bee7-111">Per altre informazioni, vedere [Informazioni sui ruoli di amministratore di Microsoft 365](../add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="8bee7-111">For more information, see [About Microsoft 365 admin roles](../add-users/about-admin-roles.md).</span></span>
- <span data-ttu-id="8bee7-112">È possibile [assegnare licenze ad account utente con PowerShell di Office 365](https://go.microsoft.com/fwlink/p/?linkid=850410).</span><span class="sxs-lookup"><span data-stu-id="8bee7-112">You can [assign licenses to user accounts with Office 365 PowerShell](https://go.microsoft.com/fwlink/p/?linkid=850410).</span></span>
- <span data-ttu-id="8bee7-113">Per usare licenze basate su gruppi, vedere [Assegnare licenze agli utenti in base all'appartenenza ai gruppi in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).</span><span class="sxs-lookup"><span data-stu-id="8bee7-113">To use group-based licensing, see [Assign licenses to users by group membership in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)</span></span>
- <span data-ttu-id="8bee7-114">Alcuni servizi, come Sway, vengono assegnati agli utenti automaticamente e non è necessario assegnarli singolarmente.</span><span class="sxs-lookup"><span data-stu-id="8bee7-114">Some services, like Sway, are automatically assigned to users, and don't need to be assigned individually.</span></span>

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a><span data-ttu-id="8bee7-115">Usare la pagina Licenze per assegnare licenze agli utenti</span><span class="sxs-lookup"><span data-stu-id="8bee7-115">Use the Licenses page to assign licenses to users</span></span>

<span data-ttu-id="8bee7-116">Nella pagina **Licenze** si assegnano licenze di un prodotto specifico a un massimo di 20 utenti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-116">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product to up to 20 users.</span></span> <span data-ttu-id="8bee7-117">Nella pagina **Licenze** viene visualizzato un elenco di tutti i prodotti per cui si hanno abbonamenti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-117">On the **Licenses** page, you see a list of all the products that you have subscriptions for.</span></span> <span data-ttu-id="8bee7-118">Si può anche vedere il numero totale di licenze per ogni prodotto, il numero di licenze assegnate e il numero di licenze disponibili.</span><span class="sxs-lookup"><span data-stu-id="8bee7-118">You also see the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="8bee7-119">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="8bee7-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="8bee7-120">Selezionare un prodotto.</span><span class="sxs-lookup"><span data-stu-id="8bee7-120">Select a product.</span></span>
3. <span data-ttu-id="8bee7-121">Nella pagina dei dettagli sul prodotto selezionare **Assegna licenze**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-121">On the product details page, select **Assign licenses**.</span></span>
4. <span data-ttu-id="8bee7-122">Nel riquadro **Assegna licenze agli utenti** iniziare a digitare un nome, quindi selezionarlo nei risultati per aggiungerlo all'elenco.</span><span class="sxs-lookup"><span data-stu-id="8bee7-122">In the **Assign licenses to users** pane, begin typing a name, and then choose it from the results to add it to the list.</span></span> <span data-ttu-id="8bee7-123">È possibile aggiungere fino a 20 utenti per volta.</span><span class="sxs-lookup"><span data-stu-id="8bee7-123">You can add up to 20 users at a time.</span></span>
5. <span data-ttu-id="8bee7-124">Selezionare **Abilita o disabilita le app e i servizi** per assegnare o rimuovere l'accesso a elementi specifici.</span><span class="sxs-lookup"><span data-stu-id="8bee7-124">Select **Turn apps and services on or off** to assign or remove access to specific items.</span></span>
6. <span data-ttu-id="8bee7-125">Al termine, selezionare **Assegna**, quindi fare clic su **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-125">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="8bee7-126">In caso di conflitto viene visualizzato un messaggio che indica qual è il problema e come risolverlo.</span><span class="sxs-lookup"><span data-stu-id="8bee7-126">If there's a conflict, a message displays, tells you what the problem is, and tells you how to fix it.</span></span> <span data-ttu-id="8bee7-127">Se, ad esempio, sono state selezionate licenze che contengono servizi in conflitto, viene visualizzato un messaggio di errore che suggerisce di rivedere i servizi inclusi in ogni licenza e riprovare.</span><span class="sxs-lookup"><span data-stu-id="8bee7-127">For example, if you selected licenses that contain conflicting services, the error message says to review the services included with each license and try again.</span></span>

## <a name="change-the-apps-and-services-a-user-has-access-to"></a><span data-ttu-id="8bee7-128">Modificare le app e i servizi a cui un utente ha accesso</span><span class="sxs-lookup"><span data-stu-id="8bee7-128">Change the apps and services a user has access to</span></span>

1. <span data-ttu-id="8bee7-129">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenze</a>.</span><span class="sxs-lookup"><span data-stu-id="8bee7-129">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="8bee7-130">Nella pagina **Licenze** selezionare la riga relativa a uno specifico utente.</span><span class="sxs-lookup"><span data-stu-id="8bee7-130">On the **Licenses** page, select the row for a specific user.</span></span>
3. <span data-ttu-id="8bee7-131">Nel riquadro destro selezionare o deselezionare le app e i servizi per i quali si desidera consentire o rimuovere l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8bee7-131">In the right pane, select or deselect the apps and services that you want to give access to or remove access from.</span></span>
4. <span data-ttu-id="8bee7-132">Al termine, selezionare **Salva**, quindi selezionare **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-132">When you're finished, select **Save**, then select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a><span data-ttu-id="8bee7-133">Usare la pagina Utenti attivi per assegnare licenze</span><span class="sxs-lookup"><span data-stu-id="8bee7-133">Use the Active users page to assign licenses</span></span>

<span data-ttu-id="8bee7-134">Nella pagina **Utenti attivi** si assegnano licenze utente ai prodotti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-134">When you use the **Active users** page to assign licenses, you assign users licenses to products.</span></span>

### <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="8bee7-135">Assegnare licenze a più utenti</span><span class="sxs-lookup"><span data-stu-id="8bee7-135">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="8bee7-136">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="8bee7-136">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="8bee7-137">Selezionare i cerchi accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="8bee7-137">Select the circles next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="8bee7-138">Nella parte superiore selezionare **Altre opzioni (...)**, quindi selezionare **Gestisci licenze prodotto**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-138">At the top, select **More options (...)**, then select **Manage product licenses**.</span></span>
4. <span data-ttu-id="8bee7-139">Nel riquadro **Gestisci licenze prodotto** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-139">In the **Manage product licenses** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="8bee7-140">Nel riquadro **Aggiungi a prodotti esistenti** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza che si vuole assegnare agli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="8bee7-140">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span>\
    <span data-ttu-id="8bee7-141">Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-141">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="8bee7-142">È possibile porre limiti ai servizi disponibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-142">You can limit which services are available to the users.</span></span> <span data-ttu-id="8bee7-143">Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-143">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="8bee7-144">Nella parte inferiore del riquadro selezionare **Aggiungi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-144">At the bottom of the pane, select **Add** \> **Close**.</span></span>  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="8bee7-145">Assegnare licenze a più utenti</span><span class="sxs-lookup"><span data-stu-id="8bee7-145">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="8bee7-146">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="8bee7-146">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="8bee7-147">Selezionare le caselle accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="8bee7-147">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="8bee7-148">Nel riquadro **Azioni in blocco** selezionare **Modifica licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-148">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="8bee7-149">Nel riquadro**Assegna prodotti** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-149">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="8bee7-150">Impostare sulla posizione **Attivata** l'interruttore relativo alle licenze che si vogliono assegnare agli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="8bee7-150">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="8bee7-151">Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-151">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="8bee7-152">È possibile porre limiti ai servizi disponibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="8bee7-153">Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="8bee7-154">Nella parte inferiore del riquadro **Aggiungi a prodotti esistenti** selezionare **Aggiungi** \> **Chiudi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-154">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a><span data-ttu-id="8bee7-155">Assegnare licenze a più utenti</span><span class="sxs-lookup"><span data-stu-id="8bee7-155">Assign licenses to multiple users</span></span>

1. <span data-ttu-id="8bee7-156">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="8bee7-156">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="8bee7-157">Selezionare le caselle accanto ai nomi degli utenti a cui si vogliono assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="8bee7-157">Select the boxes next to the names of the users that you want to assign licenses to.</span></span>
3. <span data-ttu-id="8bee7-158">Nel riquadro **Azioni in blocco** selezionare **Modifica licenze di prodotto**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-158">In the **Bulk actions** pane, select **Edit product licenses**.</span></span>
4. <span data-ttu-id="8bee7-159">Nel riquadro**Assegna prodotti** selezionare **Aggiungi ad assegnazioni licenze prodotto esistenti** \> **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-159">In the **Assign products** pane, select **Add to existing product license assignments** \> **Next**.</span></span>
5. <span data-ttu-id="8bee7-160">Impostare sulla posizione **Attivata** l'interruttore relativo alle licenze che si vogliono assegnare agli utenti selezionati.</span><span class="sxs-lookup"><span data-stu-id="8bee7-160">Switch the toggle to the **On** position for the licenses that you want the selected users to have.</span></span>\
    <span data-ttu-id="8bee7-161">Per impostazione predefinita, tutti i servizi associati a tali licenze vengono automaticamente assegnati agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-161">By default, all services associated with those licenses are automatically assigned to the users.</span></span> <span data-ttu-id="8bee7-162">È possibile porre limiti ai servizi disponibili agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-162">You can limit which services are available to the users.</span></span> <span data-ttu-id="8bee7-163">Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8bee7-163">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="8bee7-164">Nella parte inferiore del riquadro **Aggiungi a prodotti esistenti** selezionare **Aggiungi** \> **Chiudi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-164">At the bottom of the **Add to existing products** pane, select **Add** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a><span data-ttu-id="8bee7-165">Assegnare licenze a un utente</span><span class="sxs-lookup"><span data-stu-id="8bee7-165">Assign licenses to one user</span></span>

1. <span data-ttu-id="8bee7-166">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="8bee7-166">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="8bee7-167">Selezionare la riga dell'utente al quale si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="8bee7-167">Select the row of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="8bee7-168">Nel riquadro destro selezionare **Licenze e app**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-168">In the right pane, select **Licenses and Apps**.</span></span>
4. <span data-ttu-id="8bee7-169">Espandere la sezione **Licenze**, selezionare le caselle delle licenze da assegnare, quindi selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-169">Expand the **Licenses** section, select the boxes for the licenses that you want to assign, then select **Save changes**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="8bee7-170">Assegnare licenze a un utente</span><span class="sxs-lookup"><span data-stu-id="8bee7-170">Assign licenses to one user</span></span>

1. <span data-ttu-id="8bee7-171">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="8bee7-171">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="8bee7-172">Selezionare la casella accanto al nome dell'utente a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="8bee7-172">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="8bee7-173">Nel riquadro destro, nella riga **Licenze di prodotto** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-173">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="8bee7-174">Nel riquadro **Licenze di prodotto** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza da assegnare all'utente.</span><span class="sxs-lookup"><span data-stu-id="8bee7-174">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="8bee7-175">Per impostazione predefinita, tutti i servizi associati alla licenza vengono automaticamente assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="8bee7-175">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="8bee7-176">È possibile porre limiti ai servizi disponibili all'utente.</span><span class="sxs-lookup"><span data-stu-id="8bee7-176">You can limit which services are available to the user.</span></span> <span data-ttu-id="8bee7-177">Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare all'utente.</span><span class="sxs-lookup"><span data-stu-id="8bee7-177">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="8bee7-178">Nella parte inferiore del riquadro **Licenze di prodotto** selezionare **Salva** \> **Chiudi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-178">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a><span data-ttu-id="8bee7-179">Assegnare licenze a un utente</span><span class="sxs-lookup"><span data-stu-id="8bee7-179">Assign licenses to one user</span></span>

1. <span data-ttu-id="8bee7-180">Nell'interfaccia di amministrazione passare alla pagina **Utenti** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Utenti attivi</a>.</span><span class="sxs-lookup"><span data-stu-id="8bee7-180">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="8bee7-181">Selezionare la casella accanto al nome dell'utente a cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="8bee7-181">Select the box next to the name of the user that you want to assign a license to.</span></span>
3. <span data-ttu-id="8bee7-182">Nel riquadro destro, nella riga **Licenze di prodotto** selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-182">In the right pane, in the **Product licenses** row, select **Edit**.</span></span>
4. <span data-ttu-id="8bee7-183">Nel riquadro **Licenze di prodotto** impostare sulla posizione **Attivata** l'interruttore relativo alla licenza da assegnare all'utente.</span><span class="sxs-lookup"><span data-stu-id="8bee7-183">In the **Product licenses** pane, switch the toggle to the **On** position for the license that you want to assign to this user.</span></span>\
    <span data-ttu-id="8bee7-184">Per impostazione predefinita, tutti i servizi associati alla licenza vengono automaticamente assegnati all'utente.</span><span class="sxs-lookup"><span data-stu-id="8bee7-184">By default, all services associated with that license are automatically assigned to the user.</span></span> <span data-ttu-id="8bee7-185">È possibile porre limiti ai servizi disponibili all'utente.</span><span class="sxs-lookup"><span data-stu-id="8bee7-185">You can limit which services are available to the user.</span></span> <span data-ttu-id="8bee7-186">Impostare sulla posizione **Disattivata** gli interruttori relativi ai servizi che non si desidera assegnare all'utente.</span><span class="sxs-lookup"><span data-stu-id="8bee7-186">Switch the toggles to the **Off** position for the services that you don't want that user to have.</span></span>
5. <span data-ttu-id="8bee7-187">Nella parte inferiore del riquadro **Licenze di prodotto** selezionare **Salva** \> **Chiudi** \> **Chiudi**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-187">At the bottom of the **Product licenses** pane, select **Save** \> **Close** \> **Close**.</span></span>

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a><span data-ttu-id="8bee7-188">Assegnare una licenza a un utente guest</span><span class="sxs-lookup"><span data-stu-id="8bee7-188">Assign a license to a guest user</span></span>

<span data-ttu-id="8bee7-189">È possibile invitare gli utenti guest a collaborare con l'organizzazione nell'interfaccia di amministrazione di Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8bee7-189">You can invite guest users to collaborate with your organization in Azure Active directory admin center.</span></span> <span data-ttu-id="8bee7-190">Per informazioni sui guest user, vedere [Cos'è l'accesso degli utenti guest in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b)</span><span class="sxs-lookup"><span data-stu-id="8bee7-190">To learn about guess users, see [What is guest user access in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b)</span></span> <span data-ttu-id="8bee7-191">Se vi sono utenti guest, vedere [Guida introduttiva: aggiungere utenti guest alla directory nel portale di Azure](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span><span class="sxs-lookup"><span data-stu-id="8bee7-191">If you don't have any guest users, see [Quickstart: Add guest users to your directory in the Azure portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8bee7-192">Per eseguire questi passaggi, è necessario essere un amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="8bee7-192">You must be a Global admin to do these steps.</span></span>

1. <span data-ttu-id="8bee7-193">Andare sull’<a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">interfaccia di amministrazione di Azure Active Directory</a></span><span class="sxs-lookup"><span data-stu-id="8bee7-193">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory admin center</a></span></span>
2. <span data-ttu-id="8bee7-194">Nel riquadro di spostamento selezionare **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-194">In the navigation pane, select **Users**.</span></span>
3. <span data-ttu-id="8bee7-195">Nella pagina **Utenti | Tutti gli utenti (anteprima)**, selezionare **Aggiungi filtri**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-195">On the **Users | All Users (Preview)** page, select **Add filters**.</span></span>
4. <span data-ttu-id="8bee7-196">Nel menu **Selezionare un campo**, scegliere **Tipo di utente**, quindi selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-196">In the **Pick a field** menu, choose **User type**, then select **Apply**.</span></span>
5. <span data-ttu-id="8bee7-197">Nel menu successivo, selezionare **Guest**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-197">In the next menu, select **Guest**.</span></span>
6. <span data-ttu-id="8bee7-198">Nell'elenco dei risultati, selezionare l'utente che necessita di una licenza.</span><span class="sxs-lookup"><span data-stu-id="8bee7-198">In the list of results, select the user who needs a license.</span></span>
7. <span data-ttu-id="8bee7-199">In **Gestisci**, selezionare **Licenze**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-199">Under **Manage**, select **Licenses**.</span></span>
8. <span data-ttu-id="8bee7-200">Selezionare **Attività**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-200">Select **Assignments**.</span></span>
9. <span data-ttu-id="8bee7-201">Nella pagina **Aggiornare le assegnazioni di licenze**, selezionare il prodotto per cui si vuole assegnare una licenza.</span><span class="sxs-lookup"><span data-stu-id="8bee7-201">On the **Update license assignments** page, select the product you want to assign a license for.</span></span>
10. <span data-ttu-id="8bee7-202">Nella parte destra, deselezionare le caselle di controllo per tutti i servizi a cui non si vuole consentire l'accesso all'utente guest.</span><span class="sxs-lookup"><span data-stu-id="8bee7-202">On the right, clear the check boxes for any services you don't want the guest user to have access to.</span></span>
11. <span data-ttu-id="8bee7-203">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8bee7-203">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8bee7-204">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="8bee7-204">Next steps</span></span>

<span data-ttu-id="8bee7-205">Se gli utenti non hanno ancora installato le app di Office, si può condividere con loro la [guida introduttiva per i dipendenti](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f), ricca di informazioni su come, ad esempio, [scaricare e installare Microsoft 365 o Office 2019 in un PC o un Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) e [configurare le app di Office e la posta elettronica in un dispositivo mobile](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span><span class="sxs-lookup"><span data-stu-id="8bee7-205">If your users don't yet have the Office apps installed, you can share the [Employee quick start guide](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) with your users to set up things, like [how to download and install Microsoft 365 or Office 2019 on a PC or Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) and [how to set up Office apps and email on a mobile device](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).</span></span>

## <a name="related-content"></a><span data-ttu-id="8bee7-206">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="8bee7-206">Related content</span></span>

<span data-ttu-id="8bee7-207">[Informazioni su abbonamenti e licenze](../../commerce/licenses/subscriptions-and-licenses.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="8bee7-207">[Understand subscriptions and licenses](../../commerce/licenses/subscriptions-and-licenses.md) (article)</span></span>\
<span data-ttu-id="8bee7-208">[Annullare l'assegnazione delle licenze agli utenti](remove-licenses-from-users.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="8bee7-208">[Unassign licenses from users](remove-licenses-from-users.md) (article)</span></span>\
<span data-ttu-id="8bee7-209">[Acquistare o rimuovere licenze per l'abbonamento](../../commerce/licenses/buy-licenses.md) (articolo)\</span><span class="sxs-lookup"><span data-stu-id="8bee7-209">[Buy or remove licenses for your subscription](../../commerce/licenses/buy-licenses.md) (article)</span></span>