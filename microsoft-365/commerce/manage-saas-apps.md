---
title: Gestire le app software-come-a-Service per l'organizzazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: Normal
ms.collection:
- commerce
search.appverid: MET150
description: Informazioni su come attivare e gestire app di terze parti nell'interfaccia di amministrazione di Microsoft 365.
ms.openlocfilehash: eb2826a4b0c69d61eb35a9dfff37e9dc2dd6ad71
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141189"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="f8bd9-103">Gestire le sottoscrizioni delle app di terze parti per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="f8bd9-103">Manage third-party app subscriptions for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="f8bd9-104">L'interfaccia di amministrazione cambia.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-104">The admin center is changing.</span></span> <span data-ttu-id="f8bd9-105">Se l'esperienza non corrisponde ai dettagli presentati, vedere [About The New Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="f8bd9-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="f8bd9-106">È possibile gestire le licenze e la fatturazione per le app di terze parti nell'interfaccia di amministrazione di Microsoft 365 con la modalità Anteprima attivata.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-106">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="f8bd9-107">Le funzionalità aggiornate includono la gestione avanzata degli abbonamenti, l'accesso migliorato alle informazioni sulla fatturazione e una maggiore flessibilità per la gestione delle fatture.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-107">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="f8bd9-108">La gestione della sottoscrizione si basa sulla piattaforma di commercio aggiornata di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-108">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="f8bd9-109">Questo si applica alle app software-as-a-Service che i clienti acquistano direttamente o da un provider di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-109">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="f8bd9-110">Come ottenere le app software-come-a-Service</span><span class="sxs-lookup"><span data-stu-id="f8bd9-110">How to get software-as-a-service apps</span></span>

<span data-ttu-id="f8bd9-111">Esistono alcuni modi per acquistare app di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-111">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="f8bd9-112">**Acquisto diretto** – i clienti possono acquistare direttamente abbonamenti da [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)o [AppSource](https://www.appsource.com/).</span><span class="sxs-lookup"><span data-stu-id="f8bd9-112">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="f8bd9-113">**Acquisto partner** – collaborare con un partner tramite centro partner per l'acquisto di sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-113">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="f8bd9-114">**Proposta Microsoft** – rispondere a una proposta di Microsoft Sales che include app di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-114">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="f8bd9-115">Quando i clienti acquistano le app e accettano il contratto per i clienti Microsoft, possono gestirle nell'interfaccia di amministrazione di Microsoft 365 o in Microsoft Store for business.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-115">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="f8bd9-116">I provider di app vendono le proprie app a una tariffa forfettaria o acquistando licenze per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-116">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="f8bd9-117">**Flat rate** – denominato anche prezzi basati sul sito, le app hanno un prezzo mensile o annuale.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-117">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="f8bd9-118">Nella pagina app, la quantità di licenza è elencata a illimitata.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-118">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="f8bd9-119">**Licenze** : le app sono prezzate dalla licenza.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-119">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="f8bd9-120">I clienti assegnano le licenze a ciascun utente nella propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="f8bd9-120">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="f8bd9-121">Aree supportate</span><span class="sxs-lookup"><span data-stu-id="f8bd9-121">Supported regions</span></span>

<span data-ttu-id="f8bd9-122">Il supporto per le app di terze parti è disponibile in queste aree:</span><span class="sxs-lookup"><span data-stu-id="f8bd9-122">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="f8bd9-123">Argentina</span><span class="sxs-lookup"><span data-stu-id="f8bd9-123">Argentina</span></span>
- <span data-ttu-id="f8bd9-124">Australia</span><span class="sxs-lookup"><span data-stu-id="f8bd9-124">Australia</span></span>
- <span data-ttu-id="f8bd9-125">Canada</span><span class="sxs-lookup"><span data-stu-id="f8bd9-125">Canada</span></span>
- <span data-ttu-id="f8bd9-126">Cile</span><span class="sxs-lookup"><span data-stu-id="f8bd9-126">Chile</span></span>
- <span data-ttu-id="f8bd9-127">Francia</span><span class="sxs-lookup"><span data-stu-id="f8bd9-127">France</span></span>
- <span data-ttu-id="f8bd9-128">Germania</span><span class="sxs-lookup"><span data-stu-id="f8bd9-128">Germany</span></span>
- <span data-ttu-id="f8bd9-129">Grecia</span><span class="sxs-lookup"><span data-stu-id="f8bd9-129">Greece</span></span>
- <span data-ttu-id="f8bd9-130">Portorico</span><span class="sxs-lookup"><span data-stu-id="f8bd9-130">Puerto Rico</span></span>
- <span data-ttu-id="f8bd9-131">Sudafrica</span><span class="sxs-lookup"><span data-stu-id="f8bd9-131">South Africa</span></span>
- <span data-ttu-id="f8bd9-132">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="f8bd9-132">United Kingdom</span></span>
- <span data-ttu-id="f8bd9-133">Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="f8bd9-133">United States</span></span>
- <span data-ttu-id="f8bd9-134">Europa occidentale</span><span class="sxs-lookup"><span data-stu-id="f8bd9-134">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="f8bd9-135">Attivare le app di terze parti</span><span class="sxs-lookup"><span data-stu-id="f8bd9-135">Activate third-party apps</span></span>

<span data-ttu-id="f8bd9-136">Gli amministratori devono attivare le app di terze parti prima di assegnarle agli utenti.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-136">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="f8bd9-137">Queste app vengono attivate nel portale dell'editore di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-137">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="f8bd9-138">Nell'interfaccia di amministrazione, andare alla pagina **fatturazione** > dei**prodotti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="f8bd9-138">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="f8bd9-139">Individuare e selezionare l'app che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-139">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="f8bd9-140">In **impostazioni & azioni**fare clic **su Gestisci nel portale di Publisher**.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="f8bd9-141">Verrà indirizzato al sito dell'app Publisher in cui è possibile attivare l'app.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-141">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="f8bd9-142">Gestire app di terze parti</span><span class="sxs-lookup"><span data-stu-id="f8bd9-142">Manage third-party apps</span></span>

<span data-ttu-id="f8bd9-143">Gli amministratori gestiscono le app di terze parti in due posizioni: l'interfaccia di amministrazione di Microsoft 365 e il portale del provider di applicazioni di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="f8bd9-144">Di seguito sono riportate le operazioni che è possibile eseguire in ogni portale.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-144">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="f8bd9-145">Interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f8bd9-145">Microsoft 365 admin center</span></span> | <span data-ttu-id="f8bd9-146">Portale App Publisher</span><span class="sxs-lookup"><span data-stu-id="f8bd9-146">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="f8bd9-147">Modificare la quantità di licenza</span><span class="sxs-lookup"><span data-stu-id="f8bd9-147">Change license quantity</span></span> <br> <span data-ttu-id="f8bd9-148">Gestire la modalità di pagamento della fattura</span><span class="sxs-lookup"><span data-stu-id="f8bd9-148">Manage how you pay your bill</span></span> <br> <span data-ttu-id="f8bd9-149">Gestire la modalità di pagamento della fattura</span><span class="sxs-lookup"><span data-stu-id="f8bd9-149">Manage how you pay your bill</span></span> <br> <span data-ttu-id="f8bd9-150">Cambiare il metodo di pagamento (carta di credito)</span><span class="sxs-lookup"><span data-stu-id="f8bd9-150">Change payment method (credit card)</span></span> <br> <span data-ttu-id="f8bd9-151">Visualizza fattura</span><span class="sxs-lookup"><span data-stu-id="f8bd9-151">View invoice</span></span> <br> <span data-ttu-id="f8bd9-152">Annullare l'abbonamento all'app</span><span class="sxs-lookup"><span data-stu-id="f8bd9-152">Cancel app subscription</span></span> | <span data-ttu-id="f8bd9-153">Configurare un'app (una volta per ogni app)</span><span class="sxs-lookup"><span data-stu-id="f8bd9-153">Set up app (once for each app)</span></span> <br> <span data-ttu-id="f8bd9-154">Assegnare licenze agli utenti</span><span class="sxs-lookup"><span data-stu-id="f8bd9-154">Assign licenses to users</span></span> <br> <span data-ttu-id="f8bd9-155">Supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="f8bd9-155">Technical support</span></span> |

<span data-ttu-id="f8bd9-156">Dopo che l'app è stata attivata, rimarrà attiva a meno che non venga annullata, scaduta o se il pagamento non viene mantenuto corrente.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-156">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="f8bd9-157">Questi eventi modificano lo stato dell'applicazione su disabilitato.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-157">These events change the app status to disabled.</span></span> <span data-ttu-id="f8bd9-158">Una volta disabilitata, l'app non può essere riattivata.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-158">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="f8bd9-159">Per continuare a utilizzare l'app, acquistarne un'altra copia.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-159">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="f8bd9-160">Assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="f8bd9-160">Assign licenses</span></span>

<span data-ttu-id="f8bd9-161">Gli amministratori devono attivare le app di terze parti prima di assegnarle agli utenti.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-161">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="f8bd9-162">Vengono attivati nel portale dell'editore di terze parti.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-162">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="f8bd9-163">Nella pagina app, in **impostazioni & azioni**, selezionare il collegamento per assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-163">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="f8bd9-164">Nell'interfaccia di amministrazione, andare alla pagina **fatturazione** > dei**prodotti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="f8bd9-164">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="f8bd9-165">Individuare e selezionare l'app che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-165">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="f8bd9-166">In **impostazioni & azioni**selezionare il collegamento da **gestire nel portale di Publisher**.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-166">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="f8bd9-167">Modificare la quantità di licenza</span><span class="sxs-lookup"><span data-stu-id="f8bd9-167">Change license quantity</span></span>

<span data-ttu-id="f8bd9-168">Gli amministratori possono modificare il numero di licenze possedute dalla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-168">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="f8bd9-169">Questo vale solo per le app acquistate con prezzi basati su Seat.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-169">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="f8bd9-170">Nell'interfaccia di amministrazione, andare alla pagina **fatturazione** > dei**prodotti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="f8bd9-170">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="f8bd9-171">Individuare e selezionare l'app che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-171">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="f8bd9-172">Selezionare **Cambia quantità di licenza**.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-172">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="f8bd9-173">Gestire i metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="f8bd9-173">Manage payment methods</span></span>

<span data-ttu-id="f8bd9-174">Le app software-come-a-Service dispongono ognuna di un profilo di fatturazione assegnato.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-174">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="f8bd9-175">I profili di fatturazione consentono di personalizzare i prodotti inclusi nella fattura e la modalità di pagamento delle fatture.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-175">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="f8bd9-176">Sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="f8bd9-176">They include:</span></span>

- <span data-ttu-id="f8bd9-177">**Metodi di pagamento** – carte di credito o bonifico bancario</span><span class="sxs-lookup"><span data-stu-id="f8bd9-177">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="f8bd9-178">**Informazioni di contatto** – indirizzo di fatturazione e nome del contatto</span><span class="sxs-lookup"><span data-stu-id="f8bd9-178">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="f8bd9-179">**Ruoli** : ruoli che consentono di modificare il profilo di fatturazione, pagare le bollette o utilizzare il metodo di pagamento sul profilo di fatturazione per effettuare l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-179">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="f8bd9-180">Per ulteriori informazioni sui profili di fatturazione, vedere [understand Billing Profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span><span class="sxs-lookup"><span data-stu-id="f8bd9-180">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="f8bd9-181">Modificare il profilo di fatturazione su una sottoscrizione di app software-come-a-Service</span><span class="sxs-lookup"><span data-stu-id="f8bd9-181">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="f8bd9-182">Nell'interfaccia di amministrazione, andare alla pagina **fatturazione** > dei**prodotti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="f8bd9-182">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="f8bd9-183">Individuare e selezionare l'app che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-183">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="f8bd9-184">Fare clic su **modifica**accanto a **profilo di fatturazione**.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-184">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="f8bd9-185">Per ulteriori informazioni sulle fatture, vedere [understand your fattura](billing-and-payments/understand-your-invoice.md).</span><span class="sxs-lookup"><span data-stu-id="f8bd9-185">For more information on invoices, see [Understand your invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="f8bd9-186">Annullamento di una sottoscrizione di app software-as-a-Service</span><span class="sxs-lookup"><span data-stu-id="f8bd9-186">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="f8bd9-187">È possibile annullare un'app software-as-a-Service dalla pagina app.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-187">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="f8bd9-188">Nell'interfaccia di amministrazione, andare alla pagina **fatturazione** > dei**prodotti** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="f8bd9-188">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="f8bd9-189">Individuare e selezionare l'app che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-189">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="f8bd9-190">In **impostazioni & azioni**selezionare **Annulla sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="f8bd9-190">Under **Settings & actions**, select **Cancel subscription**.</span></span>
