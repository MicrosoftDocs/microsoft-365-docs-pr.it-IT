---
title: Raccogliere le informazioni necessarie per creare record DNS
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Per ulteriori informazioni, vedere i valori o i dati necessari per la creazione di record DNS per Microsoft 365. '
ms.openlocfilehash: eca9dbe4e40193f76538b639624b827177ff7772
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645312"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="c9dcf-103">Raccogliere le informazioni necessarie per creare record DNS</span><span class="sxs-lookup"><span data-stu-id="c9dcf-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="c9dcf-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="c9dcf-105">Passaggio 1: trovare il valore del record TXT e verificare</span><span class="sxs-lookup"><span data-stu-id="c9dcf-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c9dcf-106">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **installazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini</a> .</span><span class="sxs-lookup"><span data-stu-id="c9dcf-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c9dcf-107">Nell'interfaccia di amministrazione, andare alla pagina dei domini di **installazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> .</span><span class="sxs-lookup"><span data-stu-id="c9dcf-107">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c9dcf-108">Nell'interfaccia di amministrazione, andare alla pagina dei domini di **installazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> .</span><span class="sxs-lookup"><span data-stu-id="c9dcf-108">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="c9dcf-109">Nella pagina **Domains** selezionare il dominio, quindi fare clic su **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="c9dcf-110">Verrà nuovamente visualizzata la configurazione guidata domini per verificare il valore specifico da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="c9dcf-111">Nella pagina **Verifica dominio** selezionare **Aggiungi un record TXT**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="c9dcf-112">Copiare il **valore txt** visualizzato.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="c9dcf-113">Ha un aspetto simile al seguente: **MS = msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="c9dcf-114">Passare a [creare record DNS presso un provider di hosting DNS](create-dns-records-at-any-dns-hosting-provider.md)e selezionare l'host DNS dall'elenco dei registrar per visualizzare le istruzioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="c9dcf-115">Seguire la procedura per creare il record TXT (o il record MX) nell'host DNS, quindi verificare il dominio di nuovo in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="c9dcf-116">Rimuovere il record TXT (o il record MX) dall'host DNS dopo che il dominio è stato verificato in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="c9dcf-117">Passaggio 2: trovare il valore del record MX per la posta elettronica e altro ancora</span><span class="sxs-lookup"><span data-stu-id="c9dcf-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c9dcf-118">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **installazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini</a> .</span><span class="sxs-lookup"><span data-stu-id="c9dcf-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="c9dcf-119">Nell'interfaccia di amministrazione, andare alla pagina dei domini di **installazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> .</span><span class="sxs-lookup"><span data-stu-id="c9dcf-119">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c9dcf-120">Nell'interfaccia di amministrazione, andare alla pagina dei domini di **installazione** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> .</span><span class="sxs-lookup"><span data-stu-id="c9dcf-120">In the admin center, go to the **Setup** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="c9dcf-121">Nella pagina **Domini** selezionare il proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="c9dcf-122">In **Record DNS necessari** verranno visualizzati i record DNS da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="c9dcf-123">È consigliabile tenere a portata di mano queste informazioni quando si apportano modifiche all'host DNS, per poter copiare e incollare i valori.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="c9dcf-124">I gruppi di record DNS presenti in questa sezione dipendono dalle impostazioni elencate in **Scopo del dominio**.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="c9dcf-125">Passare a [creare record DNS presso un provider di hosting DNS](create-dns-records-at-any-dns-hosting-provider.md), quindi selezionare l'host DNS nell'elenco dei registrar per visualizzare le istruzioni dettagliate per l'aggiunta di record nel sito Web dell'host DNS.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="c9dcf-126">Eseguire la procedura per creare i record presso l'host DNS.</span><span class="sxs-lookup"><span data-stu-id="c9dcf-126">Follow the steps for creating the records at your DNS host.</span></span>
