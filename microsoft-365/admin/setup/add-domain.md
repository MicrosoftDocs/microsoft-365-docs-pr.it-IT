---
title: Aggiungere un dominio a Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Aggiungere il dominio a Office 365 nell'interfaccia di amministrazione di Microsoft 365 aggiungendo un record DNS all'host DNS. La procedura guidata di installazione illustra i passaggi del processo.
ms.openlocfilehash: 8e08233ffe33ac2b5d41ad164af80468de52983d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631816"
---
# <a name="add-a-domain-to-office-365"></a><span data-ttu-id="7cb17-104">Aggiungere un dominio a Office 365</span><span class="sxs-lookup"><span data-stu-id="7cb17-104">Add a domain to Office 365</span></span>

 <span data-ttu-id="7cb17-105">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="7cb17-105">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="7cb17-106">*Per aggiungere, modificare o rimuovere i domini, è **necessario** essere un **amministratore globale** di un [piano aziendale o aziendale](https://products.office.com/business/office). Queste modifiche hanno effetto sull'intero tenant, gli *amministratori personalizzati* o *gli utenti normali* non saranno in grado di apportare queste modifiche.*</span><span class="sxs-lookup"><span data-stu-id="7cb17-106">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="7cb17-107">Eseguire la procedura seguente per aggiungere, configurare o continuare a configurare un dominio.</span><span class="sxs-lookup"><span data-stu-id="7cb17-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="7cb17-108">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb17-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="7cb17-109">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb17-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="7cb17-110">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="7cb17-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="7cb17-111">Passare alla pagina **configurazione** > **domini** .</span><span class="sxs-lookup"><span data-stu-id="7cb17-111">Go to the **Setup** > **Domains** page.</span></span> 

3. <span data-ttu-id="7cb17-112">Selezionare **Aggiungi dominio**.</span><span class="sxs-lookup"><span data-stu-id="7cb17-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="7cb17-113">Immettere il nome del dominio che si desidera aggiungere, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="7cb17-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="7cb17-114">Scegliere in che modo si desidera verificare che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="7cb17-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="7cb17-115">Se il dominio è registrato su GoDaddy o 1&amp;1, selezionare **Accedi** > **successivamente** e Microsoft[consentirà la configurazione automatica dei record](../get-help-with-domains/domain-connect.md).</span><span class="sxs-lookup"><span data-stu-id="7cb17-115">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft[will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="7cb17-116">È possibile specificare l'invio di un messaggio di posta elettronica contenente un codice di verifica al contatto registrato per il dominio.</span><span class="sxs-lookup"><span data-stu-id="7cb17-116">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="7cb17-117">Se non si riconosce o si ha accesso al messaggio di posta elettronica su record, è possibile utilizzare la terza opzione.</span><span class="sxs-lookup"><span data-stu-id="7cb17-117">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="7cb17-118">È possibile usare un record TXT per verificare il dominio.</span><span class="sxs-lookup"><span data-stu-id="7cb17-118">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="7cb17-119">Selezionarlo e quindi fare clic su **Avanti** per visualizzare le istruzioni su come aggiungere il record DNS al sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="7cb17-119">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="7cb17-120">Dopo aver aggiunto il record, possono essere necessari fino a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="7cb17-120">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="7cb17-121">Scegliere in che modo si desidera rendere necessarie le modifiche del DNS per l'utilizzo del dominio da parte di Office.</span><span class="sxs-lookup"><span data-stu-id="7cb17-121">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="7cb17-122">Scegliere **Add the DNS Records for me** se si desidera che Office configuri automaticamente il DNS.</span><span class="sxs-lookup"><span data-stu-id="7cb17-122">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="7cb17-123">Scegliere **i ' ll add the DNS Records me stesso** se si desidera collegare solo i servizi specifici di Office 365 al dominio o se si desidera ignorare questo per ora e farlo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="7cb17-123">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="7cb17-124">**Scegliere questa opzione solo se si è effettivamente in grado di eseguire l'operazione.**</span><span class="sxs-lookup"><span data-stu-id="7cb17-124">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="7cb17-125">Se si è scelto di *aggiungere manualmente i record DNS* , selezionare **Avanti** e visualizzare una pagina contenente tutti i record che è necessario aggiungere al sito Web di registrazione per configurare il dominio.</span><span class="sxs-lookup"><span data-stu-id="7cb17-125">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="7cb17-126">Se il portale non riconosce il registrar, è possibile [seguire queste istruzioni generali.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="7cb17-126">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="7cb17-127">Controllare l'elenco delle [istruzioni specifiche per l'host](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) per trovare l'host e seguire la procedura per aggiungere tutti i record necessari.</span><span class="sxs-lookup"><span data-stu-id="7cb17-127">Check our list of [host-specific instructions](https://support.office.com/article/ae950c9e-e8d9-4108-b0cb-449156998580) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="7cb17-128">Per identificare il provider di hosting DNS o il registrar per il dominio, vedere [Trovare il registrar o il provider di hosting DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="7cb17-128">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="7cb17-129">Se si desidera attendere in un secondo momento, scorrere fino alla fine e selezionare **Ignora questo passaggio**.</span><span class="sxs-lookup"><span data-stu-id="7cb17-129">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="7cb17-130">Seleziona **fine** -hai finito!</span><span class="sxs-lookup"><span data-stu-id="7cb17-130">Select **Finish** - you're done!</span></span> 

## <a name="related-articles"></a><span data-ttu-id="7cb17-131">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="7cb17-131">Related articles</span></span>

[<span data-ttu-id="7cb17-132">Domande frequenti sui domini</span><span class="sxs-lookup"><span data-stu-id="7cb17-132">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="7cb17-133">Che cosa è un dominio?</span><span class="sxs-lookup"><span data-stu-id="7cb17-133">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="7cb17-134">Acquistare un nome di dominio in Office 365</span><span class="sxs-lookup"><span data-stu-id="7cb17-134">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="7cb17-135">Configurare il dominio (istruzioni specifiche per l’host)</span><span class="sxs-lookup"><span data-stu-id="7cb17-135">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="7cb17-136">Ottenere assistenza per i domini</span><span class="sxs-lookup"><span data-stu-id="7cb17-136">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
