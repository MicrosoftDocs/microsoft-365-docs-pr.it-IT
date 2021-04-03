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
ms.openlocfilehash: 7f4c0aed1bccd0e5df5b09e15e6201933e937993
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51576950"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="3c987-103">Informazioni sui profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="3c987-103">Understand billing profiles</span></span>

<span data-ttu-id="3c987-104">Per i clienti commerciali che acquistano prodotti e servizi da Microsoft, i profili di fatturazione consentono di personalizzare quali elementi sono inclusi nella fattura e come pagare le fatture.</span><span class="sxs-lookup"><span data-stu-id="3c987-104">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="3c987-105">I profili di fatturazione includono le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3c987-105">Billing profiles include the following information:</span></span>

- <span data-ttu-id="3c987-106">**Account di fatturazione** &ndash; Nome dell'account di fatturazione a cui è correlato il profilo</span><span class="sxs-lookup"><span data-stu-id="3c987-106">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="3c987-107">**Metodi di pagamento** &ndash; Carte di credito o di debito, conti correnti bancari, assegno o bonifico bancario</span><span class="sxs-lookup"><span data-stu-id="3c987-107">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="3c987-108">**Informazioni di contatto** &ndash; Indirizzo di fatturazione e nome di contatto</span><span class="sxs-lookup"><span data-stu-id="3c987-108">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="3c987-109">**Impostazioni fattura** &ndash; Valuta in base al paese dell'account di fatturazione, un numero di ordine di acquisto facoltativo e l'opzione per ricevere le fatture come allegati di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="3c987-109">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="3c987-110">**Autorizzazioni** &ndash; Autorizzazioni che consentono di modificare il profilo di fatturazione, pagare le fatture o utilizzare la modalità di pagamento nel profilo di fatturazione per effettuare acquisti</span><span class="sxs-lookup"><span data-stu-id="3c987-110">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="3c987-111">Usa i profili di fatturazione per controllare gli acquisti e personalizzare la fattura.</span><span class="sxs-lookup"><span data-stu-id="3c987-111">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="3c987-112">Viene generata una fattura mensile per i prodotti acquistati con il profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="3c987-112">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="3c987-113">È possibile personalizzare la fattura, ad esempio aggiornare il numero dell'ordine di acquisto e la preferenza della fattura tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="3c987-113">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="3c987-114">Durante il primo acquisto viene creato automaticamente un profilo di fatturazione per l'account di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="3c987-114">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="3c987-115">È possibile creare profili di fatturazione nella <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">pagina Profili di</a> fatturazione per configurare altre fatture.</span><span class="sxs-lookup"><span data-stu-id="3c987-115">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="3c987-116">Ad esempio, è possibile utilizzare profili di fatturazione diversi quando si effettuano acquisti per ogni reparto dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c987-116">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="3c987-117">Alla data di fatturazione successiva riceverai una fattura per ogni profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="3c987-117">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="3c987-118">Ruoli del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="3c987-118">Billing profile roles</span></span>

<span data-ttu-id="3c987-119">I ruoli nei profili di fatturazione dispongono delle autorizzazioni per controllare gli acquisti e visualizzare e gestire le fatture.</span><span class="sxs-lookup"><span data-stu-id="3c987-119">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="3c987-120">Assegnare questi ruoli agli utenti che tracciano, organizzano e pagano le fatture, come i membri del team di approvvigionamento nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3c987-120">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="3c987-121">Ruolo</span><span class="sxs-lookup"><span data-stu-id="3c987-121">Role</span></span>                          | <span data-ttu-id="3c987-122">Descrizione</span><span class="sxs-lookup"><span data-stu-id="3c987-122">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="3c987-123">Proprietario del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="3c987-123">Billing profile owner</span></span>         | <span data-ttu-id="3c987-124">Gestire tutto per un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="3c987-124">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="3c987-125">Collaboratore del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="3c987-125">Billing profile contributor</span></span>   | <span data-ttu-id="3c987-126">Gestire tutto tranne le autorizzazioni in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="3c987-126">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="3c987-127">Lettore profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="3c987-127">Billing profile reader</span></span>        | <span data-ttu-id="3c987-128">Visualizzazione di sola lettura di tutti gli elementi in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="3c987-128">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="3c987-129">Responsabile delle fatture</span><span class="sxs-lookup"><span data-stu-id="3c987-129">Invoice manager</span></span>               | <span data-ttu-id="3c987-130">Visualizzare e pagare le fatture e ha una visualizzazione di sola lettura di tutti gli elementi in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="3c987-130">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="3c987-131">Visualizzare i profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="3c987-131">View billing profiles</span></span>

1. <span data-ttu-id="3c987-132">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fatture e pagamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="3c987-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="3c987-133">Scegliere **Profili di** fatturazione e quindi un profilo di fatturazione dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="3c987-133">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="3c987-134">Nella scheda **Panoramica** è possibile modificare i dettagli del profilo di fatturazione e attivare o disattivare l'invio di una fattura tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="3c987-134">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="3c987-135">Nella scheda **Autorizzazioni** è possibile assegnare ruoli agli utenti per il pagamento delle fatture.</span><span class="sxs-lookup"><span data-stu-id="3c987-135">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="3c987-136">Nella scheda **Saldo del credito di Azure,** i clienti di Azure possono visualizzare la cronologia dei saldi delle transazioni per i crediti di Azure usati dal profilo di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="3c987-136">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="3c987-137">Nella scheda **Crediti di Azure,** i clienti di Azure possono visualizzare un elenco dei crediti di Azure associati al profilo di fatturazione e le relative date di scadenza.</span><span class="sxs-lookup"><span data-stu-id="3c987-137">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3c987-138">Se non si dispone di crediti di Azure, non sarà possibile visualizzare il saldo del credito di **Azure** o le schede **crediti di Azure.**</span><span class="sxs-lookup"><span data-stu-id="3c987-138">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="3c987-139">Hai bisogno di assistenza?</span><span class="sxs-lookup"><span data-stu-id="3c987-139">Need help?</span></span> <span data-ttu-id="3c987-140">Contattare il supporto.</span><span class="sxs-lookup"><span data-stu-id="3c987-140">Contact support.</span></span>

<span data-ttu-id="3c987-141">Se hai domande o hai bisogno di assistenza per i costi di Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">crea una richiesta di supporto con il supporto di Azure.</a></span><span class="sxs-lookup"><span data-stu-id="3c987-141">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="3c987-142">Se hai domande o hai bisogno di assistenza con il profilo di fatturazione nell'interfaccia di amministrazione di Microsoft 365, [contatta il supporto per i prodotti aziendali.](/office365/admin/contact-support-for-business-products)</span><span class="sxs-lookup"><span data-stu-id="3c987-142">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](/office365/admin/contact-support-for-business-products).</span></span>