---
title: Raccogliere le informazioni necessarie per creare record DNS di Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: 'Per ulteriori informazioni, vedere i valori o i dati necessari per la creazione di record DNS per Office 365. '
ms.custom: okr_smb
ms.openlocfilehash: d6093dd8a7e8d901be7b172a31dcd0e56c549ab3
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "43189003"
---
# <a name="gather-the-information-you-need-to-create-office-365-dns-records"></a><span data-ttu-id="98ce9-103">Raccogliere le informazioni necessarie per creare record DNS di Office 365</span><span class="sxs-lookup"><span data-stu-id="98ce9-103">Gather the information you need to create Office 365 DNS records</span></span>

 <span data-ttu-id="98ce9-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="98ce9-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="98ce9-105">Passaggio 1: trovare il valore del record TXT e verificare</span><span class="sxs-lookup"><span data-stu-id="98ce9-105">Step 1: Find the TXT record value and verify</span></span>

1. <span data-ttu-id="98ce9-106">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **installazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini</a> .</span><span class="sxs-lookup"><span data-stu-id="98ce9-106">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker range="o365-germany"

1. <span data-ttu-id="98ce9-107">Nell'interfaccia di amministrazione, accedere a questa pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domini</a> .</span><span class="sxs-lookup"><span data-stu-id="98ce9-107">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="98ce9-108">Nell'interfaccia di amministrazione, accedere a questa pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domini</a> .</span><span class="sxs-lookup"><span data-stu-id="98ce9-108">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="98ce9-109">Nella pagina **Domains** selezionare il dominio, quindi fare clic su **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="98ce9-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="98ce9-110">Verrà nuovamente visualizzata la configurazione guidata domini per verificare il valore specifico da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="98ce9-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="98ce9-111">Nella pagina **Verifica dominio** selezionare **Aggiungi un record TXT**e quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="98ce9-111">On the **Verify domain** page, select **Add a TXT record instead**, then select **Next**.</span></span>
    
4. <span data-ttu-id="98ce9-112">Copiare il **valore txt** visualizzato.</span><span class="sxs-lookup"><span data-stu-id="98ce9-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="98ce9-113">Ha un aspetto simile al seguente: **MS = msXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="98ce9-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="98ce9-114">Passare a [creare record DNS presso un provider di hosting DNS](create-dns-records-at-any-dns-hosting-provider.md)e selezionare l'host DNS dall'elenco dei registrar per visualizzare le istruzioni dettagliate.</span><span class="sxs-lookup"><span data-stu-id="98ce9-114">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and select your DNS host from the list of registrars to see the step-by-step instructions.</span></span>
    
6. <span data-ttu-id="98ce9-115">Seguire la procedura per creare il record TXT (o il record MX) presso l'host DNS, quindi verificare nuovamente il dominio in Office 365.</span><span class="sxs-lookup"><span data-stu-id="98ce9-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Office 365.</span></span>

7. <span data-ttu-id="98ce9-116">Rimuovere il record TXT (o il record MX) dall'host DNS dopo la verifica del dominio in Office 365.</span><span class="sxs-lookup"><span data-stu-id="98ce9-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Office 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="98ce9-117">Passaggio 2: trovare il valore del record MX per la posta elettronica e altro ancora</span><span class="sxs-lookup"><span data-stu-id="98ce9-117">Step 2: Find the MX record value for email and more</span></span>

1. <span data-ttu-id="98ce9-118">Nell'interfaccia di amministrazione di Microsoft 365 passare alla pagina **installazione** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini</a> .</span><span class="sxs-lookup"><span data-stu-id="98ce9-118">In the Microsoft 365 admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
::: moniker range="o365-germany"

1. <span data-ttu-id="98ce9-119">Nell'interfaccia di amministrazione, accedere a questa pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">domini</a> .</span><span class="sxs-lookup"><span data-stu-id="98ce9-119">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="98ce9-120">Nell'interfaccia di amministrazione, accedere a questa pagina dei <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">domini</a> .</span><span class="sxs-lookup"><span data-stu-id="98ce9-120">In the admin center, go to this <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="98ce9-121">Nella pagina **Domini** selezionare il proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="98ce9-121">On the **Domains** page, select your domain.</span></span> 
    
3. <span data-ttu-id="98ce9-122">In **Record DNS necessari** verranno visualizzati i record DNS da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="98ce9-122">Under **Required DNS settings**, you'll see the DNS records to add.</span></span>
    
    <span data-ttu-id="98ce9-123">È consigliabile tenere a portata di mano queste informazioni quando si apportano modifiche all'host DNS, per poter copiare e incollare i valori.</span><span class="sxs-lookup"><span data-stu-id="98ce9-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="98ce9-124">I gruppi di record DNS presenti in questa sezione dipendono dalle impostazioni elencate in **Scopo del dominio**.</span><span class="sxs-lookup"><span data-stu-id="98ce9-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="98ce9-125">Passare a [creare record DNS presso un provider di hosting DNS](create-dns-records-at-any-dns-hosting-provider.md), quindi selezionare l'host DNS nell'elenco dei registrar per visualizzare le istruzioni dettagliate per l'aggiunta di record nel sito Web dell'host DNS.</span><span class="sxs-lookup"><span data-stu-id="98ce9-125">Go to [Create DNS records at any DNS hosting provider](create-dns-records-at-any-dns-hosting-provider.md), and then select your DNS host from the list of registrars to see step-by-step instructions for adding records at that DNS host's website.</span></span>
    
5. <span data-ttu-id="98ce9-126">Eseguire la procedura per creare i record presso l'host DNS.</span><span class="sxs-lookup"><span data-stu-id="98ce9-126">Follow the steps for creating the records at your DNS host.</span></span>
