---
title: Informazioni sui profili di fatturazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- Commerce
search.appverid:
- MET150
description: Informazioni su come i profili di fatturazione supportano le fatture.
ms.openlocfilehash: 2f56b9a3edbbbe14927df64bed8b699a68826c9e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911867"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="ac643-103">Informazioni sui profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="ac643-103">Understand billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ac643-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="ac643-104">The admin center is changing.</span></span> <span data-ttu-id="ac643-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="ac643-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="ac643-106">Per i clienti commerciali che acquistano prodotti e servizi da Microsoft, i profili di fatturazione consentono di personalizzare quali elementi sono inclusi nella fattura e come pagare le fatture.</span><span class="sxs-lookup"><span data-stu-id="ac643-106">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="ac643-107">I profili di fatturazione includono le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ac643-107">Billing profiles include the following information:</span></span>

- <span data-ttu-id="ac643-108">**Account di fatturazione** &ndash; Nome dell'account di fatturazione a cui è correlato il profilo</span><span class="sxs-lookup"><span data-stu-id="ac643-108">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="ac643-109">**Metodi di pagamento** &ndash; Carte di credito o di debito, conti correnti bancari, assegno o bonifico bancario</span><span class="sxs-lookup"><span data-stu-id="ac643-109">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="ac643-110">**Informazioni di contatto** &ndash; Indirizzo di fatturazione e nome di contatto</span><span class="sxs-lookup"><span data-stu-id="ac643-110">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="ac643-111">**Impostazioni fattura** &ndash; Valuta in base al paese dell'account di fatturazione, un numero di ordine di acquisto facoltativo e l'opzione per ricevere le fatture come allegati di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="ac643-111">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="ac643-112">**Autorizzazioni** &ndash; Autorizzazioni che consentono di modificare il profilo di fatturazione, pagare le fatture o utilizzare la modalità di pagamento nel profilo di fatturazione per effettuare acquisti</span><span class="sxs-lookup"><span data-stu-id="ac643-112">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="ac643-113">Usa i profili di fatturazione per controllare gli acquisti e personalizzare la fattura.</span><span class="sxs-lookup"><span data-stu-id="ac643-113">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="ac643-114">Viene generata una fattura mensile per i prodotti acquistati con il profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="ac643-114">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="ac643-115">È possibile personalizzare la fattura, ad esempio aggiornare il numero dell'ordine di acquisto e la preferenza della fattura tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ac643-115">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="ac643-116">Durante il primo acquisto viene creato automaticamente un profilo di fatturazione per l'account di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="ac643-116">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="ac643-117">È possibile creare profili di fatturazione nella <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">pagina Profili di</a> fatturazione per configurare altre fatture.</span><span class="sxs-lookup"><span data-stu-id="ac643-117">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="ac643-118">Ad esempio, è possibile utilizzare profili di fatturazione diversi quando si effettuano acquisti per ogni reparto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ac643-118">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="ac643-119">Alla data di fatturazione successiva riceverai una fattura per ogni profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="ac643-119">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="ac643-120">Ruoli del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="ac643-120">Billing profile roles</span></span>

<span data-ttu-id="ac643-121">I ruoli nei profili di fatturazione dispongono delle autorizzazioni per controllare gli acquisti e visualizzare e gestire le fatture.</span><span class="sxs-lookup"><span data-stu-id="ac643-121">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="ac643-122">Assegnare questi ruoli agli utenti che tracciano, organizzano e pagano le fatture, come i membri del team di approvvigionamento nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ac643-122">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="ac643-123">Ruolo</span><span class="sxs-lookup"><span data-stu-id="ac643-123">Role</span></span>                          | <span data-ttu-id="ac643-124">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ac643-124">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="ac643-125">Proprietario del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="ac643-125">Billing profile owner</span></span>         | <span data-ttu-id="ac643-126">Gestire tutto per un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="ac643-126">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="ac643-127">Collaboratore del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="ac643-127">Billing profile contributor</span></span>   | <span data-ttu-id="ac643-128">Gestire tutto tranne le autorizzazioni in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="ac643-128">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="ac643-129">Lettore profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="ac643-129">Billing profile reader</span></span>        | <span data-ttu-id="ac643-130">Visualizzazione di sola lettura di tutti gli elementi in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="ac643-130">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="ac643-131">Responsabile delle fatture</span><span class="sxs-lookup"><span data-stu-id="ac643-131">Invoice manager</span></span>               | <span data-ttu-id="ac643-132">Visualizzare e pagare le fatture e ha una visualizzazione di sola lettura di tutti gli elementi in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="ac643-132">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="ac643-133">Visualizzare i profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="ac643-133">View billing profiles</span></span>

1. <span data-ttu-id="ac643-134">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fatture e pagamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="ac643-134">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="ac643-135">Scegliere **Profili di** fatturazione e quindi un profilo di fatturazione dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="ac643-135">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="ac643-136">Nella scheda **Panoramica** è possibile modificare i dettagli del profilo di fatturazione e attivare o disattivare l'invio di una fattura tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ac643-136">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="ac643-137">Nella scheda **Autorizzazioni** è possibile assegnare ruoli agli utenti per il pagamento delle fatture.</span><span class="sxs-lookup"><span data-stu-id="ac643-137">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="ac643-138">Nella scheda **Saldo del credito di Azure,** i clienti di Azure possono visualizzare la cronologia dei saldi delle transazioni per i crediti di Azure usati dal profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="ac643-138">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="ac643-139">Nella scheda **Crediti di Azure,** i clienti di Azure possono visualizzare un elenco dei crediti di Azure associati al profilo di fatturazione e le relative date di scadenza.</span><span class="sxs-lookup"><span data-stu-id="ac643-139">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ac643-140">Se non si dispone di crediti di Azure, non sarà possibile visualizzare il saldo del credito di **Azure** o le schede **crediti di Azure.**</span><span class="sxs-lookup"><span data-stu-id="ac643-140">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="ac643-141">Hai bisogno di assistenza?</span><span class="sxs-lookup"><span data-stu-id="ac643-141">Need help?</span></span> <span data-ttu-id="ac643-142">Contattare il supporto.</span><span class="sxs-lookup"><span data-stu-id="ac643-142">Contact support.</span></span>

<span data-ttu-id="ac643-143">Se hai domande o hai bisogno di assistenza per i costi di Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">crea una richiesta di supporto con il supporto di Azure.</a></span><span class="sxs-lookup"><span data-stu-id="ac643-143">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="ac643-144">Se hai domande o hai bisogno di assistenza con il profilo di fatturazione nell'interfaccia di amministrazione di Microsoft 365, [contatta il supporto per i prodotti aziendali.](/office365/admin/contact-support-for-business-products)</span><span class="sxs-lookup"><span data-stu-id="ac643-144">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](/office365/admin/contact-support-for-business-products).</span></span>