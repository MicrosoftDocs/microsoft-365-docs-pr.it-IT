---
title: Gestire gli acquisti in modalità self-service (amministratori)
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
search.appverid:
- MET150
description: Gli amministratori possono imparare a gestire gli acquisti in modalità self-service effettuati dagli utenti dell'organizzazione.
ms.openlocfilehash: 4cd59bc10d6a6a856932c8bd94e67469217c1313
ms.sourcegitcommit: 3c296126ba69a32af07e339f2f1eacdd8e5b878e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/14/2020
ms.locfileid: "41120222"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="5c4c9-103">Gestire gli acquisti in modalità self-service (amministratore)</span><span class="sxs-lookup"><span data-stu-id="5c4c9-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="5c4c9-104">Come amministratore, è possibile visualizzare gli acquisti in modalità self-service effettuati dagli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="5c4c9-105">È possibile visualizzare il prodotto, il nome dell'acquirente, gli abbonamenti acquistati, la data di scadenza, il prezzo di acquisto e gli utenti assegnati per ogni acquisto in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-105">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="5c4c9-106">Se necessario per l'organizzazione, è possibile disattivare l'acquisto in modalità self-service per ogni singolo prodotto tramite PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-106">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="5c4c9-107">Si dispone degli stessi criteri di gestione dei dati e di accesso rispetto ai prodotti acquistati tramite l'acquisto in modalità self-service o in modo centralizzato.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="5c4c9-108">È inoltre possibile controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="5c4c9-109">Per ulteriori informazioni, vedere [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5c4c9-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="5c4c9-110">Visualizzare le sottoscrizioni in modalità self-service</span><span class="sxs-lookup"><span data-stu-id="5c4c9-110">View self-service subscriptions</span></span>

1. <span data-ttu-id="5c4c9-111">Nell'interfaccia di amministrazione, accedere alla pagina dei<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">servizi di &</a> di **fatturazione** > .</span><span class="sxs-lookup"><span data-stu-id="5c4c9-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Products & services</a> page.</span></span>

2. <span data-ttu-id="5c4c9-112">Accanto a **risultati di affinamento**, dall'elenco a discesa **tipo di account** scegliere **self-service**.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-112">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="5c4c9-113">Per visualizzare ulteriori dettagli su un abbonamento, selezionarne uno dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-113">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="5c4c9-114">Visualizzazione delle licenze per un abbonamento all'acquisto in modalità self-service</span><span class="sxs-lookup"><span data-stu-id="5c4c9-114">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="5c4c9-115">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenze</a> di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-115">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="5c4c9-116">Scegliere l'icona filtro e quindi fare clic su **self-service**.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-116">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="5c4c9-117">Selezionare un prodotto per visualizzare le licenze assegnate agli utenti.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-117">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="5c4c9-118">Se per un prodotto sono presenti più acquisti, tale prodotto è elencato solo una volta e la colonna **quantità disponibile** indica il totale di tutte le sottoscrizioni acquistate per il prodotto.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-118">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="5c4c9-119">L'elenco **utenti** è raggruppato in base ai nomi delle persone che hanno effettuato acquisti in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-119">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="5c4c9-120">Per esportare un elenco di utenti con licenze per le sottoscrizioni, scegliere gli abbonamenti che si desidera esportare, quindi scegliere **Esporta utenti**.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-120">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="5c4c9-121">Disabilitare o abilitare gli acquisti in modalità self-service</span><span class="sxs-lookup"><span data-stu-id="5c4c9-121">Disable or enable self-service purchases</span></span>

<span data-ttu-id="5c4c9-122">È possibile disabilitare o abilitare l'acquisto in modalità self-service per gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-122">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="5c4c9-123">Il modulo di **MSCommerce** PowerShell include un valore del parametro **PolicyId** per **AllowSelfServicePurchase** che consente di controllare se gli utenti dell'organizzazione possono effettuare acquisti in modalità self-service e per quali prodotti.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-123">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="5c4c9-124">È possibile utilizzare il modulo di **MSCommerce** PowerShell per:</span><span class="sxs-lookup"><span data-stu-id="5c4c9-124">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="5c4c9-125">Visualizzare lo stato predefinito del valore \*\*\*\* &mdash; del parametro AllowSelfServicePurchase se è abilitato o disabilitato per prodotto</span><span class="sxs-lookup"><span data-stu-id="5c4c9-125">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="5c4c9-126">Visualizzare un elenco di prodotti applicabili e se l'acquisto in modalità self-service è abilitato o disabilitato</span><span class="sxs-lookup"><span data-stu-id="5c4c9-126">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="5c4c9-127">Visualizzare o modificare l'impostazione corrente per un prodotto specifico per abilitarlo o disabilitarlo</span><span class="sxs-lookup"><span data-stu-id="5c4c9-127">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="5c4c9-128">Per ulteriori informazioni, vedere [use AllowSelfServicePurchase for the MSCommerce PowerShell Module](allowselfservicepurchase-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="5c4c9-128">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="5c4c9-129">Centralizzare le licenze in un singolo abbonamento</span><span class="sxs-lookup"><span data-stu-id="5c4c9-129">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="5c4c9-130">È possibile assegnare licenze esistenti o acquistare abbonamenti aggiuntivi mediante contratti esistenti per gli utenti assegnati agli acquisti in modalità self-service.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-130">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="5c4c9-131">Dopo aver assegnato le licenze acquistate in modo centralizzato, è possibile richiedere che gli acquirenti cancellino le sottoscrizioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-131">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="5c4c9-132">Accedere all'interfaccia di <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Amministrazione</a> con l'account di amministratore globale o amministratore di fatturazione.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-132">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="5c4c9-133">Passare alla pagina \*\*\*\* > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">servizi di acquisto</a> per la fatturazione.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-133">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="5c4c9-134">Trovare e scegliere il prodotto che si desidera acquistare, quindi scegliere **buy**.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-134">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="5c4c9-135">Completare i passaggi rimanenti per completare l'acquisto.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-135">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="5c4c9-136">Seguire la procedura illustrata [per l'](#view-who-has-licenses-for-a-self-service-purchase-subscription) esportazione di un elenco di utenti a cui fare riferimento nel passaggio 6.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-136">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="5c4c9-137">Assegnare le licenze a tutti gli utenti che dispongono di una licenza nell'altra sottoscrizione.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-137">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="5c4c9-138">Per i passaggi completi, vedere [assegnare licenze agli utenti](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="5c4c9-138">For full steps, see [Assign licenses to users](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).</span></span>

7. <span data-ttu-id="5c4c9-139">Contattare la persona che ha acquistato l'abbonamento all'acquisto in modalità self-service e chiedergli di annullarla.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-139">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="5c4c9-140">Serve assistenza?</span><span class="sxs-lookup"><span data-stu-id="5c4c9-140">Need help?</span></span> <span data-ttu-id="5c4c9-141">Contattaci.</span><span class="sxs-lookup"><span data-stu-id="5c4c9-141">Contact us.</span></span>

<span data-ttu-id="5c4c9-142">Per domande comuni sugli acquisti in modalità self-service, vedere domande [frequenti sugli acquisti in modalità self-service](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="5c4c9-142">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="5c4c9-143">Se hai domande o hai bisogno di assistenza per gli acquisti in modalità self-service, [Contatta il supporto](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span><span class="sxs-lookup"><span data-stu-id="5c4c9-143">If you have questions or need help with self-service purchases, [contact support](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>