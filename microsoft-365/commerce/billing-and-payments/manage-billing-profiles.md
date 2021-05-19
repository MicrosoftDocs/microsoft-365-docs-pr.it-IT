---
title: Informazioni sui profili di fatturazione
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
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
- commerce_billing
search.appverid: MET150
description: Informazioni su come i profili di fatturazione supportano le fatture.
ms.date: 04/02/2021
ms.openlocfilehash: e66efe12e05d2aaf286b689c955f17c8401144f1
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537332"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="bbf50-103">Informazioni sui profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="bbf50-103">Understand billing profiles</span></span>

<span data-ttu-id="bbf50-104">Un profilo di fatturazione contiene una modalità di pagamento, informazioni di fatturazione e altre impostazioni della fattura, ad esempio il numero dell'ordine di acquisto e la preferenza della fattura di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="bbf50-104">A billing profile contains a payment method, Bill-to information, and other invoice settings, such as purchase order number and email invoice preference.</span></span> <span data-ttu-id="bbf50-105">Si utilizza un profilo di fatturazione per pagare i prodotti acquistati da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbf50-105">You use a billing profile to pay for the products that you buy from Microsoft.</span></span> <span data-ttu-id="bbf50-106">Un profilo di fatturazione viene creato automaticamente quando un utente effettua un acquisto self-service.</span><span class="sxs-lookup"><span data-stu-id="bbf50-106">A billing profile is automatically created when a user makes a self-service purchase.</span></span> <span data-ttu-id="bbf50-107">Ogni profilo di fatturazione viene fatturato separatamente.</span><span class="sxs-lookup"><span data-stu-id="bbf50-107">Each billing profile is invoiced separately.</span></span>

> [!NOTE]
>
> <span data-ttu-id="bbf50-108">I profili di fatturazione non sono disponibili per i clienti  che acquistano prodotti e servizi da Microsoft.com o nella pagina Acquista servizi dell'interfaccia Microsoft 365 di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="bbf50-108">Billing profiles are not available to customers who buy products and services from Microsoft.com or on the **Purchase services** page of the Microsoft 365 admin center.</span></span>

## <a name="what-are-billing-profile-roles"></a><span data-ttu-id="bbf50-109">Che cosa sono i ruoli del profilo di fatturazione?</span><span class="sxs-lookup"><span data-stu-id="bbf50-109">What are billing profile roles?</span></span>

<span data-ttu-id="bbf50-110">I ruoli nei profili di fatturazione dispongono delle autorizzazioni per controllare gli acquisti e visualizzare e gestire le fatture.</span><span class="sxs-lookup"><span data-stu-id="bbf50-110">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="bbf50-111">Assegnare questi ruoli agli utenti che registrano, organizzano e pagano le fatture.</span><span class="sxs-lookup"><span data-stu-id="bbf50-111">Assign these roles to users who track, organize, and pay invoices.</span></span> <span data-ttu-id="bbf50-112">Ad esempio, i membri del team di approvvigionamento nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bbf50-112">For example, members of the procurement team in your organization.</span></span>

| <span data-ttu-id="bbf50-113">Ruolo</span><span class="sxs-lookup"><span data-stu-id="bbf50-113">Role</span></span>                         | <span data-ttu-id="bbf50-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="bbf50-114">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="bbf50-115">Proprietario del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="bbf50-115">Billing profile owner</span></span>        | <span data-ttu-id="bbf50-116">Gestire tutto per un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="bbf50-116">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="bbf50-117">Collaboratore del profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="bbf50-117">Billing profile contributor</span></span>  | <span data-ttu-id="bbf50-118">Gestire tutto tranne le autorizzazioni in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="bbf50-118">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="bbf50-119">Lettore profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="bbf50-119">Billing profile reader</span></span>       | <span data-ttu-id="bbf50-120">Visualizzazione di sola lettura di tutti gli elementi in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="bbf50-120">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="bbf50-121">Responsabile delle fatture</span><span class="sxs-lookup"><span data-stu-id="bbf50-121">Invoice manager</span></span>              | <span data-ttu-id="bbf50-122">Visualizzare e pagare le fatture e ha una visualizzazione di sola lettura di tutti gli elementi in un profilo di fatturazione</span><span class="sxs-lookup"><span data-stu-id="bbf50-122">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-my-billing-profiles"></a><span data-ttu-id="bbf50-123">Visualizzare i profili di fatturazione</span><span class="sxs-lookup"><span data-stu-id="bbf50-123">View my billing profiles</span></span>

> [!NOTE]
>
> <span data-ttu-id="bbf50-124">Se si segue questa procedura e l'elenco dei profili di fatturazione è vuoto, significa che non si dispone di un profilo di fatturazione e non è possibile utilizzare questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="bbf50-124">If you follow these steps and the billing profiles list is empty, it means that you don’t have a billing profile, and can’t use this feature.</span></span>

1. <span data-ttu-id="bbf50-125">Nell'interfaccia di amministrazione passare alla pagina **Fatturazione** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Fatture e pagamenti</a>.</span><span class="sxs-lookup"><span data-stu-id="bbf50-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="bbf50-126">Seleziona la **scheda Profilo di** fatturazione, quindi seleziona un profilo di fatturazione dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="bbf50-126">Select the **Billing profile** tab, then select a billing profile from the list.</span></span>

<span data-ttu-id="bbf50-127">Ogni profilo di fatturazione include le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbf50-127">Each billing profile includes the following information:</span></span>

- <span data-ttu-id="bbf50-128">**Nome e stato del profilo di fatturazione** &ndash; Nome univoco del profilo di fatturazione e indica se il profilo di fatturazione è attivo o disabilitato per l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="bbf50-128">**Billing profile name and status** &ndash; The unique name of the billing profile, and whether the billing profile is active or disabled for purchasing.</span></span>
- <span data-ttu-id="bbf50-129">**Impostazioni fattura** &ndash; Valuta in base al paese dell'account di fatturazione, informazioni sulla frequenza e la data della fattura, l'opzione per ricevere le fatture come allegati di posta elettronica e un campo facoltativo numero di ordine di acquisto</span><span class="sxs-lookup"><span data-stu-id="bbf50-129">**Invoice settings** &ndash; Currency based on the country of the billing account, information about invoice frequency and date, the option to receive invoices as email attachments, and an optional PO number field</span></span>
- <span data-ttu-id="bbf50-130">**Metodi di pagamento** &ndash; Mostra la modalità di pagamento principale e di backup, se presente, per il profilo</span><span class="sxs-lookup"><span data-stu-id="bbf50-130">**Payment methods** &ndash; Shows the primary and backup payment method, if any, for the profile</span></span>
- <span data-ttu-id="bbf50-131">**Account di fatturazione** &ndash; Nome dell'account di fatturazione a cui è correlato il profilo.</span><span class="sxs-lookup"><span data-stu-id="bbf50-131">**Billing account** &ndash; Name of the billing account the profile is related to.</span></span> <span data-ttu-id="bbf50-132">Per ulteriori informazioni sugli account di fatturazione, vedere [Informazioni sugli account di fatturazione.](../manage-billing-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="bbf50-132">For more information about billing accounts, see [Understand billing accounts](../manage-billing-accounts.md).</span></span>
- <span data-ttu-id="bbf50-133">**Informazioni di contatto** &ndash; Indirizzo di fatturazione, nome contatto e indirizzo di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="bbf50-133">**Contact information** &ndash; Billing address and contact name and email address</span></span>
- <span data-ttu-id="bbf50-134">**Ruoli del profilo di fatturazione** &ndash; Elenco di persone a cui è assegnato uno dei ruoli del profilo di fatturazione per eseguire operazioni per tale profilo.</span><span class="sxs-lookup"><span data-stu-id="bbf50-134">**Billing profile roles** &ndash; A list of people who are assigned one of the billing profile roles to do things for that profile.</span></span> <span data-ttu-id="bbf50-135">Ad esempio, pagare le fatture, aggiungere un numero di ordine di acquisto o sostituire il metodo di pagamento utilizzato per effettuare acquisti.</span><span class="sxs-lookup"><span data-stu-id="bbf50-135">For example, pay bills, add a PO number, or replace the payment method that is used to make purchases.</span></span>

> [!NOTE]
>
> <span data-ttu-id="bbf50-136">È possibile assegnare ruoli del profilo di fatturazione solo agli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bbf50-136">You can only assign billing profile roles to users in your organization.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="bbf50-137">Hai bisogno di assistenza?</span><span class="sxs-lookup"><span data-stu-id="bbf50-137">Need help?</span></span> <span data-ttu-id="bbf50-138">Contattare il supporto</span><span class="sxs-lookup"><span data-stu-id="bbf50-138">Contact support</span></span>

<span data-ttu-id="bbf50-139">Se hai domande o hai bisogno di assistenza per i costi di Azure, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">crea una richiesta di supporto con il supporto di Azure.</a></span><span class="sxs-lookup"><span data-stu-id="bbf50-139">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="bbf50-140">Se hai domande o hai bisogno di assistenza con il profilo di fatturazione nell Microsoft 365 di amministrazione, [contatta il supporto](../../business-video/get-help-support.md).</span><span class="sxs-lookup"><span data-stu-id="bbf50-140">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support](../../business-video/get-help-support.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="bbf50-141">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="bbf50-141">Related content</span></span>

<span data-ttu-id="bbf50-142">[Come pagare l'abbonamento con un profilo di fatturazione](pay-for-subscription-billing-profile.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="bbf50-142">[How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md) (article)</span></span>\
<span data-ttu-id="bbf50-143">[Informazioni sull'account di](../manage-billing-accounts.md) fatturazione (articolo)</span><span class="sxs-lookup"><span data-stu-id="bbf50-143">[Understand billing accounts](../manage-billing-accounts.md) (article)</span></span>\
<span data-ttu-id="bbf50-144">[Gestire i metodi di pagamento](manage-payment-methods.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="bbf50-144">[Manage payment methods](manage-payment-methods.md) (article)</span></span>
