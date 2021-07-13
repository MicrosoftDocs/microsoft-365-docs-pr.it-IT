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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 77f90d4a-dc7f-4f09-8972-c1b03ea85a67
description: Raccogliere i valori/informazioni necessari per creare record DNS per connettere il dominio all'Microsoft 365 sottoscrizione.
ms.openlocfilehash: c9869444da2ccb7f96ee01576d966767681c5b49
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393884"
---
# <a name="gather-the-information-you-need-to-create-dns-records"></a><span data-ttu-id="fb750-103">Raccogliere le informazioni necessarie per creare record DNS</span><span class="sxs-lookup"><span data-stu-id="fb750-103">Gather the information you need to create DNS records</span></span>

 <span data-ttu-id="fb750-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="fb750-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
### <a name="step-1-find-the-txt-record-value-and-verify"></a><span data-ttu-id="fb750-105">Passaggio 1: trovare il valore del record TXT e verificare</span><span class="sxs-lookup"><span data-stu-id="fb750-105">Step 1: Find the TXT record value and verify</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fb750-106">Nel interfaccia di amministrazione di Microsoft 365, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini.</a></span><span class="sxs-lookup"><span data-stu-id="fb750-106">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="fb750-107">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fb750-107">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fb750-108">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fb750-108">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="fb750-109">Nella pagina **Domini** seleziona il dominio, quindi seleziona **Avvia configurazione.**</span><span class="sxs-lookup"><span data-stu-id="fb750-109">On the **Domains** page, select your domain, then select **Start setup**.</span></span> <span data-ttu-id="fb750-110">Verrà nuovamente visualizzata la configurazione guidata domini per verificare il valore specifico da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="fb750-110">You'll go back to the domains setup wizard to see the specific value you need to add.</span></span>
    
3. <span data-ttu-id="fb750-111">Nella pagina **Domain Verification** selezionare Add a TXT record to **the domain's DNS records**, quindi selezionare **Continue**.</span><span class="sxs-lookup"><span data-stu-id="fb750-111">On the **Domain Verification** page, select **Add a TXT record to the domain's DNS records**, then select **Continue**.</span></span>
    
4. <span data-ttu-id="fb750-112">Copiare **il valore TXT** visualizzato.</span><span class="sxs-lookup"><span data-stu-id="fb750-112">Copy the **TXT value** shown.</span></span> <span data-ttu-id="fb750-113">È simile al seguente: **MS=msXXXXXXXXXX**.</span><span class="sxs-lookup"><span data-stu-id="fb750-113">It looks like this: **MS=msXXXXXXXX**.</span></span> 
    
5. <span data-ttu-id="fb750-114">Passare a [Aggiungere record DNS per connettere il dominio](create-dns-records-at-any-dns-hosting-provider.md)e seguire la procedura per aggiungere record nel sito Web dell'host DNS.</span><span class="sxs-lookup"><span data-stu-id="fb750-114">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>
    
6. <span data-ttu-id="fb750-115">Seguire i passaggi per la creazione del record TXT (o record MX) nell'host DNS, quindi verificare di nuovo il dominio in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb750-115">Follow the steps for creating the TXT record (or MX record) at your DNS host, then verify the domain back in Microsoft 365.</span></span>

7. <span data-ttu-id="fb750-116">Rimuovere il record TXT (o record MX) dall'host DNS dopo aver verificato il dominio Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="fb750-116">Remove the TXT record (or MX record) from your DNS host once the domain is verified in Microsoft 365.</span></span>
    
### <a name="step-2-find-the-mx-record-value-for-email-and-more"></a><span data-ttu-id="fb750-117">Passaggio 2: Trovare il valore del record MX per la posta elettronica e altro ancora</span><span class="sxs-lookup"><span data-stu-id="fb750-117">Step 2: Find the MX record value for email and more</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="fb750-118">Nel interfaccia di amministrazione di Microsoft 365, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">domini.</a></span><span class="sxs-lookup"><span data-stu-id="fb750-118">In the Microsoft 365 admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
::: moniker range="o365-germany"

1. <span data-ttu-id="fb750-119">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fb750-119">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="fb750-120">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="fb750-120">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="fb750-121">Nella pagina **Domini** selezionare il proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="fb750-121">On the **Domains** page, select your domain.</span></span>
    
3. <span data-ttu-id="fb750-122">Scegliere **Manage DNS,** selezionare **More Options** Add your own  >  **DNS** e selezionare **Continue** per visualizzare i record DNS da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="fb750-122">Choose  **Manage DNS**, select **More Options** > **Add your own DNS** and select **Continue** to see the DNS records to add.</span></span>
    
    <span data-ttu-id="fb750-123">È consigliabile tenere a portata di mano queste informazioni quando si apportano modifiche all'host DNS, per poter copiare e incollare i valori.</span><span class="sxs-lookup"><span data-stu-id="fb750-123">You'll want to keep this information available while you make changes at your DNS host, so you can copy and paste the values.</span></span>
    
    <span data-ttu-id="fb750-124">I gruppi di record DNS presenti in questa sezione dipendono dalle impostazioni elencate in **Scopo del dominio**.</span><span class="sxs-lookup"><span data-stu-id="fb750-124">The groups of DNS records that are listed on the page depend on your choices listed under **Domain purpose**.</span></span>
    
4. <span data-ttu-id="fb750-125">Passare a [Aggiungere record DNS per connettere il dominio](create-dns-records-at-any-dns-hosting-provider.md)e seguire la procedura per aggiungere record nel sito Web dell'host DNS.</span><span class="sxs-lookup"><span data-stu-id="fb750-125">Go to [Add DNS records to connect your domain](create-dns-records-at-any-dns-hosting-provider.md), and follow the steps to add records at your DNS host's website.</span></span>

5. <span data-ttu-id="fb750-126">Eseguire la procedura per creare i record presso l'host DNS.</span><span class="sxs-lookup"><span data-stu-id="fb750-126">Follow the steps for creating the records at your DNS host.</span></span>

## <a name="related-content"></a><span data-ttu-id="fb750-127">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="fb750-127">Related content</span></span>

<span data-ttu-id="fb750-128">[Domande frequenti sui domini](../setup/domains-faq.yml) (articolo)</span><span class="sxs-lookup"><span data-stu-id="fb750-128">[Domains FAQ](../setup/domains-faq.yml) (article)</span></span>\
<span data-ttu-id="fb750-129">[Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](find-and-fix-issues.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="fb750-129">[Find and fix issues after adding your domain or DNS records](find-and-fix-issues.md) (article)</span></span>\
<span data-ttu-id="fb750-130">[Gestire i domini](index.yml) (pagina di collegamento)</span><span class="sxs-lookup"><span data-stu-id="fb750-130">[Manage domains](index.yml) (link page)</span></span>