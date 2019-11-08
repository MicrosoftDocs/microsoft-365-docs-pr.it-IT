---
title: Gestire i profili di fatturazione
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
ms.openlocfilehash: 9db8b949cb07c8386505234d9d88aa2627a752b5
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/07/2019
ms.locfileid: "38029050"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="134d8-104">Gestire i profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="134d8-104">Manage billing profiles</span></span>
<span data-ttu-id="134d8-105">Per i clienti commerciali che acquistano prodotti e servizi da Microsoft, i profili di fatturazione consentono di personalizzare gli elementi inclusi nella fattura e come vengono pagate le fatture.</span><span class="sxs-lookup"><span data-stu-id="134d8-105">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="134d8-106">I profili di fatturazione includono le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="134d8-106">Billing profiles include the following information:</span></span>

- <span data-ttu-id="134d8-107">Nome **account** &mdash; di fatturazione dell'account di fatturazione a cui è associato il profilo</span><span class="sxs-lookup"><span data-stu-id="134d8-107">**Billing account** &mdash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="134d8-108">**Metodi** &mdash; di pagamento carte di credito o di debito, conti correnti bancari, assegno o bonifico bancario</span><span class="sxs-lookup"><span data-stu-id="134d8-108">**Payment methods** &mdash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="134d8-109">Indirizzo di fatturazione **delle informazioni** &mdash; di contatto e nome del contatto</span><span class="sxs-lookup"><span data-stu-id="134d8-109">**Contact information** &mdash; Billing address and a contact name</span></span>
- <span data-ttu-id="134d8-110">Le **Impostazioni** &mdash; delle fatture valutano in base al paese dell'account di fatturazione, un numero di ordine facoltativo e l'opzione per la ricezione delle fatture come allegati di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="134d8-110">**Invoice settings** &mdash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="134d8-111">Autorizzazioni per le **autorizzazioni** &mdash; che consentono di modificare il profilo di fatturazione, pagare le bollette o utilizzare il metodo di pagamento sul profilo di fatturazione per effettuare gli acquisti</span><span class="sxs-lookup"><span data-stu-id="134d8-111">**Permissions** &mdash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="134d8-112">Utilizzare i profili di fatturazione per controllare gli acquisti e personalizzare la fattura.</span><span class="sxs-lookup"><span data-stu-id="134d8-112">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="134d8-113">Viene generata una fattura mensile per i prodotti acquistati con il profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="134d8-113">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="134d8-114">È possibile personalizzare la fattura, ad esempio aggiornare il numero dell'ordine di acquisto e la preferenza della fattura di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="134d8-114">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="134d8-115">Un profilo di fatturazione viene creato automaticamente per l'account di fatturazione durante il primo acquisto.</span><span class="sxs-lookup"><span data-stu-id="134d8-115">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="134d8-116">È possibile creare profili di fatturazione nella pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">profili di fatturazione</a> per configurare altre fatture.</span><span class="sxs-lookup"><span data-stu-id="134d8-116">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="134d8-117">Ad esempio, è possibile utilizzare diversi profili di fatturazione quando si effettuano acquisti per ogni reparto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="134d8-117">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="134d8-118">Alla data di fatturazione successiva, si riceverà una fattura per ogni profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="134d8-118">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="134d8-119">Ruoli del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="134d8-119">Billing profile roles</span></span>

<span data-ttu-id="134d8-120">I ruoli nei profili di fatturazione dispongono delle autorizzazioni per controllare gli acquisti e visualizzare e gestire le fatture.</span><span class="sxs-lookup"><span data-stu-id="134d8-120">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="134d8-121">Assegnare questi ruoli agli utenti che registrano, organizzano e pagano fatture, come i membri del team di approvvigionamento nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="134d8-121">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="134d8-122">Ruolo</span><span class="sxs-lookup"><span data-stu-id="134d8-122">Role</span></span>                          | <span data-ttu-id="134d8-123">Descrizione</span><span class="sxs-lookup"><span data-stu-id="134d8-123">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="134d8-124">Proprietario del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="134d8-124">Billing profile owner</span></span>         | <span data-ttu-id="134d8-125">Gestire tutti gli elementi per un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="134d8-125">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="134d8-126">Collaboratore del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="134d8-126">Billing profile contributor</span></span>   | <span data-ttu-id="134d8-127">Gestire tutto tranne le autorizzazioni in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="134d8-127">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="134d8-128">Lettore profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="134d8-128">Billing profile reader</span></span>        | <span data-ttu-id="134d8-129">Visualizzazione di sola lettura di tutto in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="134d8-129">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="134d8-130">Responsabile fatturazione</span><span class="sxs-lookup"><span data-stu-id="134d8-130">Invoice manager</span></span>               | <span data-ttu-id="134d8-131">Visualizzare e pagare le bollette e dispone di una visualizzazione di sola lettura di tutto in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="134d8-131">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="134d8-132">Visualizzare i profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="134d8-132">View billing profiles</span></span>

1. <span data-ttu-id="134d8-133">Nell'interfaccia di amministrazione, **andare alla** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">fatture & pagamenti</a> .</span><span class="sxs-lookup"><span data-stu-id="134d8-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="134d8-134">Scegliere **profili di fatturazione**e quindi scegliere un profilo di fatturazione dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="134d8-134">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="134d8-135">Nella scheda **Panoramica** , è possibile modificare i dettagli del profilo di fatturazione e abilitare o disabilitare l'invio di una fattura tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="134d8-135">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="134d8-136">Nella scheda **autorizzazioni** , è possibile assegnare i ruoli agli utenti per pagare le fatture.</span><span class="sxs-lookup"><span data-stu-id="134d8-136">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="134d8-137">Nella scheda **bilanciamento del credito di Azure** , i clienti di Azure possono visualizzare la cronologia degli equilibri delle transazioni per i crediti di Azure utilizzati dal profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="134d8-137">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="134d8-138">Nella scheda **crediti** di Azure, i clienti di Azure possono visualizzare un elenco di crediti di Azure associati al profilo di fatturazione e le relative date di scadenza.</span><span class="sxs-lookup"><span data-stu-id="134d8-138">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="134d8-139">Se non si dispone di alcun credito di Azure, non verranno visualizzate le schede Azure credit **Balance** o **Azure Credits** .</span><span class="sxs-lookup"><span data-stu-id="134d8-139">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="134d8-140">Serve assistenza?</span><span class="sxs-lookup"><span data-stu-id="134d8-140">Need help?</span></span> <span data-ttu-id="134d8-141">Contattare il supporto.</span><span class="sxs-lookup"><span data-stu-id="134d8-141">Contact support.</span></span>

<span data-ttu-id="134d8-142">Se hai domande o hai bisogno di assistenza con i costi di Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">Crea una richiesta di supporto con supporto di Azure</a>.</span><span class="sxs-lookup"><span data-stu-id="134d8-142">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="134d8-143">Se hai domande o hai bisogno di assistenza con il tuo profilo di fatturazione nell'interfaccia di amministrazione di Microsoft 365, [Contatta il supporto per i prodotti per le aziende](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="134d8-143">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>