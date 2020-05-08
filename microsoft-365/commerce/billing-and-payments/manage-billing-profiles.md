---
title: Gestire profili di fatturazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Informazioni su come i profili di fatturazione supportano le fatture.
keywords: Profilo di fatturazione, fatture, addebiti, spese gestite
ms.openlocfilehash: f93ca5af11ba416fecd13fcceffe75055a776553
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140891"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="9a7a6-104">Gestire profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a7a6-104">Manage billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="9a7a6-105">L'interfaccia di amministrazione cambia.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-105">The admin center is changing.</span></span> <span data-ttu-id="9a7a6-106">Se l'esperienza non corrisponde ai dettagli presentati, vedere [About The New Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="9a7a6-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="9a7a6-107">Per i clienti commerciali che acquistano prodotti e servizi da Microsoft, i profili di fatturazione consentono di personalizzare gli elementi inclusi nella fattura e come vengono pagate le fatture.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-107">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="9a7a6-108">I profili di fatturazione includono le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9a7a6-108">Billing profiles include the following information:</span></span>

- <span data-ttu-id="9a7a6-109">Nome **account** &ndash; di fatturazione dell'account di fatturazione a cui è associato il profilo</span><span class="sxs-lookup"><span data-stu-id="9a7a6-109">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="9a7a6-110">**Metodi** &ndash; di pagamento carte di credito o di debito, conti correnti bancari, assegno o bonifico bancario</span><span class="sxs-lookup"><span data-stu-id="9a7a6-110">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="9a7a6-111">Indirizzo di fatturazione **delle informazioni** &ndash; di contatto e nome del contatto</span><span class="sxs-lookup"><span data-stu-id="9a7a6-111">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="9a7a6-112">Le **Impostazioni** &ndash; delle fatture valutano in base al paese dell'account di fatturazione, un numero di ordine facoltativo e l'opzione per la ricezione delle fatture come allegati di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="9a7a6-112">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="9a7a6-113">Autorizzazioni per le **autorizzazioni** &ndash; che consentono di modificare il profilo di fatturazione, pagare le bollette o utilizzare il metodo di pagamento sul profilo di fatturazione per effettuare gli acquisti</span><span class="sxs-lookup"><span data-stu-id="9a7a6-113">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="9a7a6-114">Utilizzare i profili di fatturazione per controllare gli acquisti e personalizzare la fattura.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-114">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="9a7a6-115">Viene generata una fattura mensile per i prodotti acquistati con il profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-115">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="9a7a6-116">È possibile personalizzare la fattura, ad esempio aggiornare il numero dell'ordine di acquisto e la preferenza della fattura di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-116">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="9a7a6-117">Un profilo di fatturazione viene creato automaticamente per l'account di fatturazione durante il primo acquisto.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-117">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="9a7a6-118">È possibile creare profili di fatturazione nella pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">profili di fatturazione</a> per configurare altre fatture.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-118">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="9a7a6-119">Ad esempio, è possibile utilizzare diversi profili di fatturazione quando si effettuano acquisti per ogni reparto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-119">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="9a7a6-120">Alla data di fatturazione successiva, si riceverà una fattura per ogni profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-120">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="9a7a6-121">Ruoli del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a7a6-121">Billing profile roles</span></span>

<span data-ttu-id="9a7a6-122">I ruoli nei profili di fatturazione dispongono delle autorizzazioni per controllare gli acquisti e visualizzare e gestire le fatture.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-122">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="9a7a6-123">Assegnare questi ruoli agli utenti che registrano, organizzano e pagano fatture, come i membri del team di approvvigionamento nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-123">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="9a7a6-124">Ruolo</span><span class="sxs-lookup"><span data-stu-id="9a7a6-124">Role</span></span>                          | <span data-ttu-id="9a7a6-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9a7a6-125">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="9a7a6-126">Proprietario del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a7a6-126">Billing profile owner</span></span>         | <span data-ttu-id="9a7a6-127">Gestire tutti gli elementi per un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a7a6-127">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="9a7a6-128">Collaboratore del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a7a6-128">Billing profile contributor</span></span>   | <span data-ttu-id="9a7a6-129">Gestire tutto tranne le autorizzazioni in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a7a6-129">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="9a7a6-130">Lettore profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a7a6-130">Billing profile reader</span></span>        | <span data-ttu-id="9a7a6-131">Visualizzazione di sola lettura di tutto in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a7a6-131">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="9a7a6-132">Responsabile fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a7a6-132">Invoice manager</span></span>               | <span data-ttu-id="9a7a6-133">Visualizzare e pagare le bollette e dispone di una visualizzazione di sola lettura di tutto in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a7a6-133">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="9a7a6-134">Visualizzare i profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="9a7a6-134">View billing profiles</span></span>

1. <span data-ttu-id="9a7a6-135">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \><a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Fatture e pagamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-135">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="9a7a6-136">Scegliere **profili di fatturazione**e quindi scegliere un profilo di fatturazione dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-136">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="9a7a6-137">Nella scheda **Panoramica** , è possibile modificare i dettagli del profilo di fatturazione e abilitare o disabilitare l'invio di una fattura tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-137">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="9a7a6-138">Nella scheda **autorizzazioni** , è possibile assegnare i ruoli agli utenti per pagare le fatture.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-138">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="9a7a6-139">Nella scheda **bilanciamento del credito di Azure** , i clienti di Azure possono visualizzare la cronologia degli equilibri delle transazioni per i crediti di Azure utilizzati dal profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-139">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="9a7a6-140">Nella scheda **crediti** di Azure, i clienti di Azure possono visualizzare un elenco di crediti di Azure associati al profilo di fatturazione e le relative date di scadenza.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-140">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9a7a6-141">Se non si dispone di alcun credito di Azure, non verranno visualizzate le schede Azure credit **Balance** o **Azure Credits** .</span><span class="sxs-lookup"><span data-stu-id="9a7a6-141">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="9a7a6-142">Serve assistenza?</span><span class="sxs-lookup"><span data-stu-id="9a7a6-142">Need help?</span></span> <span data-ttu-id="9a7a6-143">Contattare il supporto.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-143">Contact support.</span></span>

<span data-ttu-id="9a7a6-144">Se hai domande o hai bisogno di assistenza con i costi di Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Crea una richiesta di supporto con supporto di Azure</a>.</span><span class="sxs-lookup"><span data-stu-id="9a7a6-144">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="9a7a6-145">Se hai domande o hai bisogno di assistenza con il tuo profilo di fatturazione nell'interfaccia di amministrazione di Microsoft 365, [Contatta il supporto per i prodotti per le aziende](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="9a7a6-145">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
