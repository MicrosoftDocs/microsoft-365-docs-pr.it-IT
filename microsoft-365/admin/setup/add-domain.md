---
title: Aggiungere un dominio a Microsoft 365
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
- Adm_O365_Setup
- Adm_O365
- Adm_TOC
ms.custom:
- TopSMBIssues
- SaRA
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 6383f56d-3d09-4dcb-9b41-b5f5a5efd611
description: Aggiungere il dominio a Microsoft 365 nell'interfaccia di amministrazione di Microsoft 365 aggiungendo un record DNS nell'host DNS. L'installazione guidata illustra il processo.
ms.openlocfilehash: 30bce7dd207532c441fdfaf572add44baec16d8d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914271"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="6ba44-104">Aggiungere un dominio a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6ba44-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6ba44-105">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="6ba44-105">The admin center is changing.</span></span> <span data-ttu-id="6ba44-106">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="6ba44-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="6ba44-107">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="6ba44-107">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="6ba44-108">*Per aggiungere, modificare o rimuovere domini, **è necessario** essere un **amministratore globale** di un piano aziendale [o aziendale.](https://products.office.com/business/office) Queste modifiche influiscono *sull'intero* tenant, gli amministratori personalizzati o gli utenti *normali* non saranno in grado di apportare queste modifiche.*</span><span class="sxs-lookup"><span data-stu-id="6ba44-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="6ba44-109">Seguire questa procedura per aggiungere, configurare o continuare a configurare un dominio.</span><span class="sxs-lookup"><span data-stu-id="6ba44-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6ba44-110">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="6ba44-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="6ba44-111">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="6ba44-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6ba44-112">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="6ba44-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="6ba44-113">Passare alla **pagina Impostazioni**  >  **Domini.**</span><span class="sxs-lookup"><span data-stu-id="6ba44-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="6ba44-114">Selezionare **Aggiungi dominio**.</span><span class="sxs-lookup"><span data-stu-id="6ba44-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="6ba44-115">Immettere il nome del dominio che si desidera aggiungere, quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="6ba44-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="6ba44-116">Scegliere come si desidera verificare di essere proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="6ba44-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="6ba44-117">Se il registrar usa [Domain Connect,](#domain-connect-registrars-integrating-with-microsoft-365) [Microsoft](../get-help-with-domains/domain-connect.md) configura automaticamente i record facendoti accedere al registrar e confermando la connessione a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ba44-117">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="6ba44-118">Verrà restituito all'interfaccia di amministrazione e Microsoft verificherà automaticamente il dominio.</span><span class="sxs-lookup"><span data-stu-id="6ba44-118">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="6ba44-119">È possibile usare un record TXT per verificare il dominio.</span><span class="sxs-lookup"><span data-stu-id="6ba44-119">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="6ba44-120">Selezionare questa opzione e **selezionare Avanti** per visualizzare le istruzioni su come aggiungere questo record DNS al sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="6ba44-120">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="6ba44-121">La verifica può richiedere fino a 30 minuti dopo l'aggiunta del record.</span><span class="sxs-lookup"><span data-stu-id="6ba44-121">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="6ba44-122">È possibile aggiungere un file di testo al sito Web del dominio.</span><span class="sxs-lookup"><span data-stu-id="6ba44-122">You can add a text file to your domain's website.</span></span> <span data-ttu-id="6ba44-123">Seleziona e scarica il file txt dall'installazione guidata, quindi carica il file nella cartella di primo livello del sito Web.</span><span class="sxs-lookup"><span data-stu-id="6ba44-123">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="6ba44-124">Il percorso del file dovrebbe essere simile al seguente: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="6ba44-124">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="6ba44-125">Verrà confermata la proprietà del dominio individuando il file nel sito Web.</span><span class="sxs-lookup"><span data-stu-id="6ba44-125">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="6ba44-126">Scegliere come apportare le modifiche DNS necessarie per l'utilizzo del dominio da parte di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="6ba44-126">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="6ba44-127">Scegliere **Add the DNS records for me** se il registrar supporta Domain [Connect](#domain-connect-registrars-integrating-with-microsoft-365)e [Microsoft](../get-help-with-domains/domain-connect.md) configura automaticamente i record facendo in modo di accedere al registrar e confermare la connessione a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ba44-127">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="6ba44-128">Scegliere **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span><span class="sxs-lookup"><span data-stu-id="6ba44-128">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="6ba44-129">**Scegliere questa opzione solo se si è effettivamente in grado di eseguire l'operazione.**</span><span class="sxs-lookup"><span data-stu-id="6ba44-129">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="6ba44-130">Se si è scelto di  aggiungere manualmente record *DNS,* selezionare Avanti e verrà visualizzata una pagina con tutti i record che è necessario aggiungere al sito Web dei registrar per configurare il dominio.</span><span class="sxs-lookup"><span data-stu-id="6ba44-130">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="6ba44-131">Se il portale non riconosce il registrar, è possibile [seguire queste istruzioni generali.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="6ba44-131">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="6ba44-132">Controllare l'elenco delle [istruzioni specifiche per l'host](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) per trovare l'host e seguire la procedura per aggiungere tutti i record necessari.</span><span class="sxs-lookup"><span data-stu-id="6ba44-132">Check our list of [host-specific instructions](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="6ba44-133">Per identificare il provider di hosting DNS o il registrar per il dominio, vedere [Trovare il registrar o il provider di hosting DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="6ba44-133">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="6ba44-134">Se si desidera attendere in un secondo momento, deselezionare tutti i servizi e fare clic su **Continua** oppure nel passaggio precedente della connessione al dominio scegliere **Altre** opzioni e selezionare Ignora **per ora**.</span><span class="sxs-lookup"><span data-stu-id="6ba44-134">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="6ba44-135">Seleziona **Fine:** hai finito.</span><span class="sxs-lookup"><span data-stu-id="6ba44-135">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="6ba44-136">Aggiungere o modificare record DNS personalizzati</span><span class="sxs-lookup"><span data-stu-id="6ba44-136">Add or edit custom DNS records</span></span>

<span data-ttu-id="6ba44-137">Seguire la procedura seguente per aggiungere un record personalizzato per un sito Web o un servizio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6ba44-137">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="6ba44-138">Accedere all'interfaccia di amministrazione di Microsoft all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="6ba44-138">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="6ba44-139">Passare alla **pagina Impostazioni**   >  **Domini.**</span><span class="sxs-lookup"><span data-stu-id="6ba44-139">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="6ba44-140">Nella pagina **Domini** selezionare un dominio.</span><span class="sxs-lookup"><span data-stu-id="6ba44-140">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="6ba44-141">In **Impostazioni DNS** selezionare Record **personalizzati**; quindi selezionare **Nuovo record personalizzato.**</span><span class="sxs-lookup"><span data-stu-id="6ba44-141">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="6ba44-142">Selezionare il tipo di record DNS che si desidera aggiungere e digitare le informazioni per il nuovo record.</span><span class="sxs-lookup"><span data-stu-id="6ba44-142">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="6ba44-143">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6ba44-143">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="6ba44-144">Registrar con Domain Connect</span><span class="sxs-lookup"><span data-stu-id="6ba44-144">Registrars with Domain Connect</span></span>

<span data-ttu-id="6ba44-145">[I registrar](https://www.domainconnect.org/) abilitati per Domain Connect consentono di aggiungere il dominio a Microsoft 365 in un processo in tre passaggi che richiede minuti.</span><span class="sxs-lookup"><span data-stu-id="6ba44-145">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="6ba44-146">Nella procedura guidata, verrà semplicemente confermato che si è proprietari del dominio e quindi si configurano automaticamente i record del dominio, in modo che la posta elettronica venga inviata a Microsoft 365 e ad altri servizi di Microsoft 365, ad esempio Teams, con il dominio.</span><span class="sxs-lookup"><span data-stu-id="6ba44-146">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6ba44-147">Disabilitare il blocco dei popup nel browser prima di iniziare la configurazione guidata.</span><span class="sxs-lookup"><span data-stu-id="6ba44-147">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="6ba44-148">Registrar di Domain Connect che si integrano con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6ba44-148">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="6ba44-149">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="6ba44-149">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="6ba44-150">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="6ba44-150">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="6ba44-151">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="6ba44-151">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="6ba44-152">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="6ba44-152">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="6ba44-153">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="6ba44-153">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="6ba44-154">Plesk</span><span class="sxs-lookup"><span data-stu-id="6ba44-154">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="6ba44-155">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="6ba44-155">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="6ba44-156">SecureServer o WildWestDomains (rivenditori GoDaddy che usano l'hosting DNS SecureServer)</span><span class="sxs-lookup"><span data-stu-id="6ba44-156">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="6ba44-157">Esempi:</span><span class="sxs-lookup"><span data-stu-id="6ba44-157">Examples:</span></span>
        - [<span data-ttu-id="6ba44-158">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="6ba44-158">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="6ba44-159">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="6ba44-159">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="6ba44-160">Cosa succede alla posta elettronica e al sito Web?</span><span class="sxs-lookup"><span data-stu-id="6ba44-160">What happens to my email and website?</span></span>

<span data-ttu-id="6ba44-161">Al termine dell'installazione, il record MX per il dominio viene aggiornato in modo che punti a Microsoft 365 e tutta la posta elettronica per il dominio inizierà a essere inviata a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="6ba44-161">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="6ba44-162">Assicurarsi di aver aggiunto utenti e configurare le cassette postali in Microsoft 365 per tutti coloro che riceve la posta elettronica nel dominio.</span><span class="sxs-lookup"><span data-stu-id="6ba44-162">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="6ba44-163">Se si ha un sito Web che si usa con l'organizzazione, continuerà a funzionare dove si trova.</span><span class="sxs-lookup"><span data-stu-id="6ba44-163">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="6ba44-164">La procedura di configurazione di Domain Connect non influisce sul sito Web.</span><span class="sxs-lookup"><span data-stu-id="6ba44-164">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="6ba44-165">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="6ba44-165">Related articles</span></span>

[<span data-ttu-id="6ba44-166">Domande frequenti sui domini</span><span class="sxs-lookup"><span data-stu-id="6ba44-166">Domains FAQ</span></span>](domains-faq.yml)

[<span data-ttu-id="6ba44-167">Che cosa è un dominio?</span><span class="sxs-lookup"><span data-stu-id="6ba44-167">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="6ba44-168">Acquistare un nome di dominio in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6ba44-168">Buy a domain name in Microsoft 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="6ba44-169">Configurare il dominio (istruzioni specifiche per l’host)</span><span class="sxs-lookup"><span data-stu-id="6ba44-169">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)