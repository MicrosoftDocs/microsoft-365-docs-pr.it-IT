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
ms.openlocfilehash: 3e6d77eec71ca1137e0aaf44b62d198d9c87b0c5
ms.sourcegitcommit: cf7c410268175e2633e9f0d65dc859c5034658e5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2020
ms.locfileid: "44232746"
---
# <a name="manage-third-party-app-subscriptions-for-your-organization"></a><span data-ttu-id="06b9a-103">Gestire le sottoscrizioni delle app di terze parti per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="06b9a-103">Manage third-party app subscriptions for your organization</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="06b9a-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="06b9a-104">The admin center is changing.</span></span> <span data-ttu-id="06b9a-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="06b9a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="06b9a-106">È possibile gestire le licenze e la fatturazione per le app di terze parti nell'interfaccia di amministrazione di Microsoft 365 con la modalità Anteprima attivata.</span><span class="sxs-lookup"><span data-stu-id="06b9a-106">You can manage licenses and billing for third-party apps in Microsoft 365 admin center with preview mode turned on.</span></span> <span data-ttu-id="06b9a-107">Le funzionalità aggiornate includono la gestione avanzata degli abbonamenti, l'accesso migliorato alle informazioni sulla fatturazione e una maggiore flessibilità per la gestione delle fatture.</span><span class="sxs-lookup"><span data-stu-id="06b9a-107">Updated features include enhanced subscription management, improved access to billing information, and improved flexibility for managing bills.</span></span> <span data-ttu-id="06b9a-108">La gestione della sottoscrizione si basa sulla piattaforma di commercio aggiornata di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="06b9a-108">Subscription management is based on Microsoft's updated commerce platform.</span></span> <span data-ttu-id="06b9a-109">Questo si applica alle app software-as-a-Service che i clienti acquistano direttamente o da un provider di terze parti.</span><span class="sxs-lookup"><span data-stu-id="06b9a-109">This applies to software-as-a-service apps that customers purchase directly, or from third-party provider.</span></span>

## <a name="how-to-get-software-as-a-service-apps"></a><span data-ttu-id="06b9a-110">Come ottenere le app software-come-a-Service</span><span class="sxs-lookup"><span data-stu-id="06b9a-110">How to get software-as-a-service apps</span></span>

<span data-ttu-id="06b9a-111">Esistono alcuni modi per acquistare app di terze parti.</span><span class="sxs-lookup"><span data-stu-id="06b9a-111">There are a few ways to purchase third-party apps.</span></span>

- <span data-ttu-id="06b9a-112">**Acquisto diretto** – i clienti possono acquistare direttamente abbonamenti da [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/)o [AppSource](https://www.appsource.com/).</span><span class="sxs-lookup"><span data-stu-id="06b9a-112">**Direct purchase** – Customers can directly purchase subscriptions from [Azure Marketplace](https://azuremarketplace.microsoft.com/marketplace/), or [AppSource](https://www.appsource.com/).</span></span>
- <span data-ttu-id="06b9a-113">**Acquisto partner** – collaborare con un partner tramite centro partner per l'acquisto di sottoscrizioni.</span><span class="sxs-lookup"><span data-stu-id="06b9a-113">**Partner purchase** –  Work with a partner through Partner Center to purchase subscriptions.</span></span>
- <span data-ttu-id="06b9a-114">**Proposta Microsoft** – rispondere a una proposta di Microsoft Sales che include app di terze parti.</span><span class="sxs-lookup"><span data-stu-id="06b9a-114">**Microsoft proposal** – Respond to a proposal from Microsoft Sales that includes third-party apps.</span></span>

<span data-ttu-id="06b9a-115">Quando i clienti acquistano le app e accettano il contratto per i clienti Microsoft, possono gestirle nell'interfaccia di amministrazione di Microsoft 365 o in Microsoft Store for business.</span><span class="sxs-lookup"><span data-stu-id="06b9a-115">Once customers purchase the apps and accept the Microsoft Customer Agreement, they can manage them in Microsoft 365 admin center, or Microsoft Store for Business.</span></span>

<span data-ttu-id="06b9a-116">I provider di app vendono le proprie app a una tariffa forfettaria o acquistando licenze per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="06b9a-116">App providers sell their apps either at a flat rate, or by purchasing licenses for users.</span></span>

- <span data-ttu-id="06b9a-117">**Flat rate** – denominato anche prezzi basati sul sito, le app hanno un prezzo mensile o annuale.</span><span class="sxs-lookup"><span data-stu-id="06b9a-117">**Flat rate** – Also called site-based pricing, apps are priced with a monthly or annual price.</span></span> <span data-ttu-id="06b9a-118">Nella pagina app, la quantità di licenza è elencata a illimitata.</span><span class="sxs-lookup"><span data-stu-id="06b9a-118">On the app page, license quantity is listed at Unlimited.</span></span>
- <span data-ttu-id="06b9a-119">**Licenze** : le app sono prezzate dalla licenza.</span><span class="sxs-lookup"><span data-stu-id="06b9a-119">**Licenses** – Apps are priced by license.</span></span> <span data-ttu-id="06b9a-120">I clienti assegnano le licenze a ciascun utente nella propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="06b9a-120">Customers assign licenses to each user in their organization</span></span>

## <a name="supported-regions"></a><span data-ttu-id="06b9a-121">Aree supportate</span><span class="sxs-lookup"><span data-stu-id="06b9a-121">Supported regions</span></span>

<span data-ttu-id="06b9a-122">Il supporto per le app di terze parti è disponibile in queste aree:</span><span class="sxs-lookup"><span data-stu-id="06b9a-122">Support for third-party apps is available in these regions:</span></span>

- <span data-ttu-id="06b9a-123">Argentina</span><span class="sxs-lookup"><span data-stu-id="06b9a-123">Argentina</span></span>
- <span data-ttu-id="06b9a-124">Australia</span><span class="sxs-lookup"><span data-stu-id="06b9a-124">Australia</span></span>
- <span data-ttu-id="06b9a-125">Canada</span><span class="sxs-lookup"><span data-stu-id="06b9a-125">Canada</span></span>
- <span data-ttu-id="06b9a-126">Cile</span><span class="sxs-lookup"><span data-stu-id="06b9a-126">Chile</span></span>
- <span data-ttu-id="06b9a-127">Francia</span><span class="sxs-lookup"><span data-stu-id="06b9a-127">France</span></span>
- <span data-ttu-id="06b9a-128">Germania</span><span class="sxs-lookup"><span data-stu-id="06b9a-128">Germany</span></span>
- <span data-ttu-id="06b9a-129">Grecia</span><span class="sxs-lookup"><span data-stu-id="06b9a-129">Greece</span></span>
- <span data-ttu-id="06b9a-130">Portorico</span><span class="sxs-lookup"><span data-stu-id="06b9a-130">Puerto Rico</span></span>
- <span data-ttu-id="06b9a-131">Sudafrica</span><span class="sxs-lookup"><span data-stu-id="06b9a-131">South Africa</span></span>
- <span data-ttu-id="06b9a-132">Regno Unito</span><span class="sxs-lookup"><span data-stu-id="06b9a-132">United Kingdom</span></span>
- <span data-ttu-id="06b9a-133">Stati Uniti</span><span class="sxs-lookup"><span data-stu-id="06b9a-133">United States</span></span>
- <span data-ttu-id="06b9a-134">Europa occidentale</span><span class="sxs-lookup"><span data-stu-id="06b9a-134">Western Europe</span></span>

## <a name="activate-third-party-apps"></a><span data-ttu-id="06b9a-135">Attivare le app di terze parti</span><span class="sxs-lookup"><span data-stu-id="06b9a-135">Activate third-party apps</span></span>

<span data-ttu-id="06b9a-136">Gli amministratori devono attivare le app di terze parti prima di assegnarle agli utenti.</span><span class="sxs-lookup"><span data-stu-id="06b9a-136">Admins must activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="06b9a-137">Queste app vengono attivate nel portale dell'editore di terze parti.</span><span class="sxs-lookup"><span data-stu-id="06b9a-137">These apps are activated in the third-party publisher's portal.</span></span>

1. <span data-ttu-id="06b9a-138">Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  **prodotti**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="06b9a-138">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="06b9a-139">Individuare e selezionare l'app che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="06b9a-139">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="06b9a-140">In **impostazioni & azioni**fare clic **su Gestisci nel portale di Publisher**.</span><span class="sxs-lookup"><span data-stu-id="06b9a-140">Under **Settings & actions**, select **Manage in publisher's portal**.</span></span>

<span data-ttu-id="06b9a-141">Verrà indirizzato al sito dell'app Publisher in cui è possibile attivare l'app.</span><span class="sxs-lookup"><span data-stu-id="06b9a-141">You'll be directed to the app publisher's site where you can activate the app.</span></span>

## <a name="manage-third-party-apps"></a><span data-ttu-id="06b9a-142">Gestire app di terze parti</span><span class="sxs-lookup"><span data-stu-id="06b9a-142">Manage third-party apps</span></span>

<span data-ttu-id="06b9a-143">Gli amministratori gestiscono le app di terze parti in due posizioni: l'interfaccia di amministrazione di Microsoft 365 e il portale del provider di applicazioni di terze parti.</span><span class="sxs-lookup"><span data-stu-id="06b9a-143">Admins manage third-party apps in two locations: Microsoft 365 admin center, and the third-party app provider's portal.</span></span>

<span data-ttu-id="06b9a-144">Di seguito sono riportate le operazioni che è possibile eseguire in ogni portale.</span><span class="sxs-lookup"><span data-stu-id="06b9a-144">Here's what you can do in each portal.</span></span>

| <span data-ttu-id="06b9a-145">Interfaccia di amministrazione di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="06b9a-145">Microsoft 365 admin center</span></span> | <span data-ttu-id="06b9a-146">Portale App Publisher</span><span class="sxs-lookup"><span data-stu-id="06b9a-146">App publisher portal</span></span> |
| --- | --- |
| <span data-ttu-id="06b9a-147">Modificare la quantità di licenza</span><span class="sxs-lookup"><span data-stu-id="06b9a-147">Change license quantity</span></span> <br> <span data-ttu-id="06b9a-148">Gestire la modalità di pagamento della fattura</span><span class="sxs-lookup"><span data-stu-id="06b9a-148">Manage how you pay your bill</span></span> <br> <span data-ttu-id="06b9a-149">Gestire la modalità di pagamento della fattura</span><span class="sxs-lookup"><span data-stu-id="06b9a-149">Manage how you pay your bill</span></span> <br> <span data-ttu-id="06b9a-150">Cambiare il metodo di pagamento (carta di credito)</span><span class="sxs-lookup"><span data-stu-id="06b9a-150">Change payment method (credit card)</span></span> <br> <span data-ttu-id="06b9a-151">Visualizza fattura</span><span class="sxs-lookup"><span data-stu-id="06b9a-151">View invoice</span></span> <br> <span data-ttu-id="06b9a-152">Annullare l'abbonamento all'app</span><span class="sxs-lookup"><span data-stu-id="06b9a-152">Cancel app subscription</span></span> | <span data-ttu-id="06b9a-153">Configurare un'app (una volta per ogni app)</span><span class="sxs-lookup"><span data-stu-id="06b9a-153">Set up app (once for each app)</span></span> <br> <span data-ttu-id="06b9a-154">Assegnare licenze agli utenti</span><span class="sxs-lookup"><span data-stu-id="06b9a-154">Assign licenses to users</span></span> <br> <span data-ttu-id="06b9a-155">Supporto tecnico</span><span class="sxs-lookup"><span data-stu-id="06b9a-155">Technical support</span></span> |

<span data-ttu-id="06b9a-156">Dopo che l'app è stata attivata, rimarrà attiva a meno che non venga annullata, scaduta o se il pagamento non viene mantenuto corrente.</span><span class="sxs-lookup"><span data-stu-id="06b9a-156">After the app is activated, it remains active unless it's canceled, expires, or if payment isn't kept current.</span></span> <span data-ttu-id="06b9a-157">Questi eventi modificano lo stato dell'applicazione su disabilitato.</span><span class="sxs-lookup"><span data-stu-id="06b9a-157">These events change the app status to disabled.</span></span> <span data-ttu-id="06b9a-158">Una volta disabilitata, l'app non può essere riattivata.</span><span class="sxs-lookup"><span data-stu-id="06b9a-158">Once an app is disabled, it can't be reactivated.</span></span> <span data-ttu-id="06b9a-159">Per continuare a utilizzare l'app, acquistarne un'altra copia.</span><span class="sxs-lookup"><span data-stu-id="06b9a-159">To continue using the app, buy another copy of it.</span></span>

## <a name="assign-licenses"></a><span data-ttu-id="06b9a-160">Assegnazione delle licenze</span><span class="sxs-lookup"><span data-stu-id="06b9a-160">Assign licenses</span></span>

<span data-ttu-id="06b9a-161">Gli amministratori devono attivare le app di terze parti prima di assegnarle agli utenti.</span><span class="sxs-lookup"><span data-stu-id="06b9a-161">Admins need to activate third-party apps before assigning them to users.</span></span> <span data-ttu-id="06b9a-162">Vengono attivati nel portale dell'editore di terze parti.</span><span class="sxs-lookup"><span data-stu-id="06b9a-162">They're activated in the third-party publisher's portal.</span></span> <span data-ttu-id="06b9a-163">Nella pagina app, in **impostazioni & azioni**, selezionare il collegamento per assegnare le licenze.</span><span class="sxs-lookup"><span data-stu-id="06b9a-163">On the app page, under **Settings & actions**, select the link to assign licenses.</span></span>

1. <span data-ttu-id="06b9a-164">Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  **prodotti**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="06b9a-164">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="06b9a-165">Individuare e selezionare l'app che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="06b9a-165">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="06b9a-166">In **impostazioni & azioni**selezionare il collegamento da **gestire nel portale di Publisher**.</span><span class="sxs-lookup"><span data-stu-id="06b9a-166">Under **Settings & actions**, select the link to **Manage in publisher's portal**.</span></span>

## <a name="change-license-quantity"></a><span data-ttu-id="06b9a-167">Modificare la quantità di licenza</span><span class="sxs-lookup"><span data-stu-id="06b9a-167">Change license quantity</span></span>

<span data-ttu-id="06b9a-168">Gli amministratori possono modificare il numero di licenze possedute dalla propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="06b9a-168">Admins can change the number of licenses owned by their organization.</span></span> <span data-ttu-id="06b9a-169">Questo vale solo per le app acquistate con prezzi basati su Seat.</span><span class="sxs-lookup"><span data-stu-id="06b9a-169">This only applies to apps purchased with seat-based pricing.</span></span>

1. <span data-ttu-id="06b9a-170">Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  **prodotti**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="06b9a-170">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="06b9a-171">Individuare e selezionare l'app che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="06b9a-171">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="06b9a-172">Selezionare **Cambia quantità di licenza**.</span><span class="sxs-lookup"><span data-stu-id="06b9a-172">Select **Change license quantity**.</span></span>

## <a name="manage-payment-methods"></a><span data-ttu-id="06b9a-173">Gestire metodi di pagamento</span><span class="sxs-lookup"><span data-stu-id="06b9a-173">Manage payment methods</span></span>

<span data-ttu-id="06b9a-174">Le app software-come-a-Service dispongono ognuna di un profilo di fatturazione assegnato.</span><span class="sxs-lookup"><span data-stu-id="06b9a-174">Software-as-a-service apps each have a billing profile assigned to them.</span></span> <span data-ttu-id="06b9a-175">I profili di fatturazione consentono di personalizzare i prodotti inclusi nella fattura e la modalità di pagamento delle fatture.</span><span class="sxs-lookup"><span data-stu-id="06b9a-175">Billing profiles let you customize what products are included on your invoice, and how you pay your invoices.</span></span> <span data-ttu-id="06b9a-176">Sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="06b9a-176">They include:</span></span>

- <span data-ttu-id="06b9a-177">**Metodi di pagamento** – carte di credito o bonifico bancario</span><span class="sxs-lookup"><span data-stu-id="06b9a-177">**Payment methods** – Credit cards or check/wire transfer</span></span>
- <span data-ttu-id="06b9a-178">**Informazioni di contatto** – indirizzo di fatturazione e nome del contatto</span><span class="sxs-lookup"><span data-stu-id="06b9a-178">**Contact information** –  Billing address and a contact name</span></span>
- <span data-ttu-id="06b9a-179">**Ruoli** : ruoli che consentono di modificare il profilo di fatturazione, pagare le bollette o utilizzare il metodo di pagamento sul profilo di fatturazione per effettuare l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="06b9a-179">**Roles** – Roles that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchase.</span></span>

<span data-ttu-id="06b9a-180">Per ulteriori informazioni sui profili di fatturazione, vedere [understand Billing Profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span><span class="sxs-lookup"><span data-stu-id="06b9a-180">For more information on billing profiles, see [Understand billing profiles](https://docs.microsoft.com/microsoft-store/billing-profile).</span></span>

### <a name="change-the-billing-profile-on-a-software-as-a-service-app-subscription"></a><span data-ttu-id="06b9a-181">Modificare il profilo di fatturazione su una sottoscrizione di app software-come-a-Service</span><span class="sxs-lookup"><span data-stu-id="06b9a-181">Change the billing profile on a software-as-a-service app subscription</span></span>

1. <span data-ttu-id="06b9a-182">Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  **prodotti**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="06b9a-182">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="06b9a-183">Individuare e selezionare l'app che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="06b9a-183">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="06b9a-184">Fare clic su **modifica**accanto a **profilo di fatturazione**.</span><span class="sxs-lookup"><span data-stu-id="06b9a-184">Next to **Billing profile**, select **Edit**.</span></span>

<span data-ttu-id="06b9a-185">Per ulteriori informazioni sulle fatture, vedere [understand your Bill or fattura](billing-and-payments/understand-your-invoice.md).</span><span class="sxs-lookup"><span data-stu-id="06b9a-185">For more information on invoices, see [Understand your bill or invoice](billing-and-payments/understand-your-invoice.md).</span></span>

## <a name="cancel-a-software-as-a-service-app-subscription"></a><span data-ttu-id="06b9a-186">Annullamento di una sottoscrizione di app software-as-a-Service</span><span class="sxs-lookup"><span data-stu-id="06b9a-186">Cancel a software-as-a-service app subscription</span></span>

<span data-ttu-id="06b9a-187">È possibile annullare un'app software-as-a-Service dalla pagina app.</span><span class="sxs-lookup"><span data-stu-id="06b9a-187">You can cancel a software-as-a-service app from the app page.</span></span>

1. <span data-ttu-id="06b9a-188">Nell'interfaccia di amministrazione, andare alla pagina **fatturazione**dei  >  **prodotti**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> .</span><span class="sxs-lookup"><span data-stu-id="06b9a-188">In the admin center, go to the **Billing** > **Your products** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2125823" target="_blank">Apps</a> page.</span></span>
2. <span data-ttu-id="06b9a-189">Individuare e selezionare l'app che si desidera gestire.</span><span class="sxs-lookup"><span data-stu-id="06b9a-189">Find and select the app you want to manage.</span></span>
3. <span data-ttu-id="06b9a-190">In **impostazioni & azioni**selezionare **Annulla sottoscrizione**.</span><span class="sxs-lookup"><span data-stu-id="06b9a-190">Under **Settings & actions**, select **Cancel subscription**.</span></span>
