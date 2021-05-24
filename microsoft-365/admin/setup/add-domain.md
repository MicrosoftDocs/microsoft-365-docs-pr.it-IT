---
title: Aggiunta di un dominio a Microsoft 365
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
description: Utilizzare la configurazione guidata per aggiungere il dominio Microsoft 365 nell'interfaccia Microsoft 365 di amministrazione aggiungendo un record DNS nell'host DNS.
ms.openlocfilehash: 152144737b0ff8cb8b0c27db2a4fc1051fb2a8a7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635679"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="a51ee-103">Aggiunta di un dominio a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a51ee-103">Add a domain to Microsoft 365</span></span>

 <span data-ttu-id="a51ee-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="a51ee-104">**[Check the Domains FAQ](domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="a51ee-105">*Per aggiungere, modificare o rimuovere domini, **è necessario** essere un **amministratore globale** di un piano aziendale [o aziendale.](https://products.office.com/business/office) Queste modifiche influiscono *sull'intero* tenant, gli amministratori personalizzati o gli utenti *normali* non saranno in grado di apportare queste modifiche.*</span><span class="sxs-lookup"><span data-stu-id="a51ee-105">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 ## <a name="add-a-domain"></a><span data-ttu-id="a51ee-106">Aggiungere un dominio</span><span class="sxs-lookup"><span data-stu-id="a51ee-106">Add a domain</span></span>

<span data-ttu-id="a51ee-107">Seguire questa procedura per aggiungere, configurare o continuare a configurare un dominio.</span><span class="sxs-lookup"><span data-stu-id="a51ee-107">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"

1. <span data-ttu-id="a51ee-108">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="a51ee-108">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="a51ee-109">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="a51ee-109">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="a51ee-110">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="a51ee-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="a51ee-111">Passare alla pagina **Impostazioni**  >  **domini.**</span><span class="sxs-lookup"><span data-stu-id="a51ee-111">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="a51ee-112">Selezionare **Aggiungi dominio**.</span><span class="sxs-lookup"><span data-stu-id="a51ee-112">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="a51ee-113">Immettere il nome del dominio che si desidera aggiungere, quindi selezionare **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="a51ee-113">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="a51ee-114">Scegliere come si desidera verificare di essere proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="a51ee-114">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="a51ee-115">Se il registrar usa [Domain Connessione](#domain-connect-registrars-integrating-with-microsoft-365), [Microsoft](../get-help-with-domains/domain-connect.md) configura automaticamente i record facendoti accedere al registrar e confermando la connessione a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a51ee-115">If your domain registrar uses [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span> <span data-ttu-id="a51ee-116">Verrà restituito all'interfaccia di amministrazione e Microsoft verificherà automaticamente il dominio.</span><span class="sxs-lookup"><span data-stu-id="a51ee-116">You'll be returned to the admin center and Microsoft will then automatically verify your domain.</span></span>
    2. <span data-ttu-id="a51ee-117">È possibile usare un record TXT per verificare il dominio.</span><span class="sxs-lookup"><span data-stu-id="a51ee-117">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="a51ee-118">Selezionare questa opzione e **selezionare Avanti** per visualizzare le istruzioni su come aggiungere questo record DNS al sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="a51ee-118">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="a51ee-119">La verifica può richiedere fino a 30 minuti dopo l'aggiunta del record.</span><span class="sxs-lookup"><span data-stu-id="a51ee-119">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    3. <span data-ttu-id="a51ee-120">È possibile aggiungere un file di testo al sito Web del dominio.</span><span class="sxs-lookup"><span data-stu-id="a51ee-120">You can add a text file to your domain's website.</span></span> <span data-ttu-id="a51ee-121">Seleziona e scarica il .txt file dall'installazione guidata, quindi carica il file nella cartella di primo livello del sito Web.</span><span class="sxs-lookup"><span data-stu-id="a51ee-121">Select and download the .txt file from the setup wizard, then upload the file to your website's top level folder.</span></span> <span data-ttu-id="a51ee-122">Il percorso del file dovrebbe essere simile al seguente: `http://mydomain.com/ms39978200.txt` .</span><span class="sxs-lookup"><span data-stu-id="a51ee-122">The path to the file should look similar to: `http://mydomain.com/ms39978200.txt`.</span></span> <span data-ttu-id="a51ee-123">Verrà confermata la proprietà del dominio individuando il file nel sito Web.</span><span class="sxs-lookup"><span data-stu-id="a51ee-123">We'll confirm you own the domain by finding the file on your website.</span></span>
    
6. <span data-ttu-id="a51ee-124">Scegliere come apportare le modifiche DNS necessarie per l'utilizzo del dominio da parte di Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a51ee-124">Choose how you want to make the DNS changes required for Microsoft to use your domain.</span></span>
    
    1. <span data-ttu-id="a51ee-125">Scegliere **Add the DNS records for me** se il registrar supporta Domain [Connessione](#domain-connect-registrars-integrating-with-microsoft-365)e [Microsoft](../get-help-with-domains/domain-connect.md) configura automaticamente i record facendo in modo che si accede al registrar e si confermi la connessione a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a51ee-125">Choose **Add the DNS records for me** if your registrar supports [Domain Connect](#domain-connect-registrars-integrating-with-microsoft-365), and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md) by having you sign in to your registrar and confirm the connection to Microsoft 365.</span></span>
    2. <span data-ttu-id="a51ee-126">Scegliere **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span><span class="sxs-lookup"><span data-stu-id="a51ee-126">Choose **I'll add the DNS records myself** if you want to attach only specific Microsoft 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="a51ee-127">**Scegliere questa opzione solo se si è effettivamente in grado di eseguire l'operazione.**</span><span class="sxs-lookup"><span data-stu-id="a51ee-127">**Choose this option if you know exactly what you're doing.**</span></span>

7. <span data-ttu-id="a51ee-128">Se si è scelto di  aggiungere manualmente record *DNS,* selezionare Avanti e verrà visualizzata una pagina con tutti i record che è necessario aggiungere al sito Web dei registrar per configurare il dominio.</span><span class="sxs-lookup"><span data-stu-id="a51ee-128">If you chose to *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 

    <span data-ttu-id="a51ee-129">Se il portale non riconosce il registrar, è possibile [seguire queste istruzioni generali.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="a51ee-129">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="a51ee-130">Controllare l'elenco delle [istruzioni specifiche per l'host](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) per trovare l'host e seguire la procedura per aggiungere tutti i record necessari.</span><span class="sxs-lookup"><span data-stu-id="a51ee-130">Check our list of [host-specific instructions](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="a51ee-131">Per identificare il provider di hosting DNS o il registrar per il dominio, vedere [Trovare il registrar o il provider di hosting DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="a51ee-131">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="a51ee-132">Se si desidera attendere in un secondo momento, deselezionare tutti i servizi e fare clic su **Continua** oppure nel passaggio precedente della connessione al dominio scegliere **Altre** opzioni e selezionare Ignora **per ora**.</span><span class="sxs-lookup"><span data-stu-id="a51ee-132">If you want to wait for later, either unselect all the services and click **Continue**, or in the previous domain connection step choose **More Options** and select **Skip this for now**.</span></span>
    
8. <span data-ttu-id="a51ee-133">Seleziona **Fine:** hai finito.</span><span class="sxs-lookup"><span data-stu-id="a51ee-133">Select **Finish** - you're done!</span></span>

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="a51ee-134">Aggiungere o modificare record DNS personalizzati</span><span class="sxs-lookup"><span data-stu-id="a51ee-134">Add or edit custom DNS records</span></span>

<span data-ttu-id="a51ee-135">Seguire la procedura seguente per aggiungere un record personalizzato per un sito Web o un servizio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="a51ee-135">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="a51ee-136">Accedere all'interfaccia di amministrazione di Microsoft all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="a51ee-136">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="a51ee-137">Passare alla pagina **Impostazioni**   >  **domini.**</span><span class="sxs-lookup"><span data-stu-id="a51ee-137">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="a51ee-138">Nella pagina **Domini** selezionare un dominio.</span><span class="sxs-lookup"><span data-stu-id="a51ee-138">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="a51ee-139">In **Impostazioni DNS** selezionare Record **personalizzati**; quindi selezionare **Nuovo record personalizzato.**</span><span class="sxs-lookup"><span data-stu-id="a51ee-139">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="a51ee-140">Selezionare il tipo di record DNS che si desidera aggiungere e digitare le informazioni per il nuovo record.</span><span class="sxs-lookup"><span data-stu-id="a51ee-140">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="a51ee-141">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a51ee-141">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="a51ee-142">Registrars with Domain Connessione</span><span class="sxs-lookup"><span data-stu-id="a51ee-142">Registrars with Domain Connect</span></span>

<span data-ttu-id="a51ee-143">[I Connessione](https://www.domainconnect.org/) abilitati al dominio consentono di aggiungere il dominio a Microsoft 365 in un processo in tre passaggi che richiede minuti.</span><span class="sxs-lookup"><span data-stu-id="a51ee-143">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="a51ee-144">Nella procedura guidata verrà semplicemente confermata la proprietà del dominio e quindi verranno impostati automaticamente i record del dominio, in modo che la posta elettronica venga inviata a Microsoft 365 e ad altri servizi Microsoft 365, ad esempio Teams, che funzionino con il dominio.</span><span class="sxs-lookup"><span data-stu-id="a51ee-144">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a51ee-145">Disabilitare il blocco dei popup nel browser prima di iniziare la configurazione guidata.</span><span class="sxs-lookup"><span data-stu-id="a51ee-145">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="a51ee-146">Registrar Connessione di dominio che si integrano con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a51ee-146">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="a51ee-147">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="a51ee-147">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="a51ee-148">EuroDNS</span><span class="sxs-lookup"><span data-stu-id="a51ee-148">EuroDNS</span></span>](https://www.eurodns.com/)
- [<span data-ttu-id="a51ee-149">Cloudflare</span><span class="sxs-lookup"><span data-stu-id="a51ee-149">Cloudflare</span></span>](https://www.cloudflare.com/)
- [<span data-ttu-id="a51ee-150">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="a51ee-150">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="a51ee-151">WordPress.com</span><span class="sxs-lookup"><span data-stu-id="a51ee-151">WordPress.com</span></span>](https://wordpress.com/)
- [<span data-ttu-id="a51ee-152">Plesk</span><span class="sxs-lookup"><span data-stu-id="a51ee-152">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="a51ee-153">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="a51ee-153">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="a51ee-154">SecureServer o WildWestDomains (rivenditori GoDaddy che usano l'hosting DNS SecureServer)</span><span class="sxs-lookup"><span data-stu-id="a51ee-154">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - <span data-ttu-id="a51ee-155">Esempi:</span><span class="sxs-lookup"><span data-stu-id="a51ee-155">Examples:</span></span>
        - [<span data-ttu-id="a51ee-156">DomainsPricedRight</span><span class="sxs-lookup"><span data-stu-id="a51ee-156">DomainsPricedRight</span></span>](https://www.domainspricedright.com/products/domain-registration)
        - [<span data-ttu-id="a51ee-157">DomainRightNow</span><span class="sxs-lookup"><span data-stu-id="a51ee-157">DomainRightNow</span></span>](https://www.domainrightnow.com/)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="a51ee-158">Cosa succede alla posta elettronica e al sito Web?</span><span class="sxs-lookup"><span data-stu-id="a51ee-158">What happens to my email and website?</span></span>

<span data-ttu-id="a51ee-159">Al termine dell'installazione, il record MX per il dominio viene aggiornato in modo che punti a Microsoft 365 e tutti i messaggi di posta elettronica per il dominio inizieranno a essere Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="a51ee-159">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="a51ee-160">Assicurarsi di aver aggiunto utenti e di configurare le cassette postali in Microsoft 365 per tutti coloro che riceve la posta elettronica nel dominio.</span><span class="sxs-lookup"><span data-stu-id="a51ee-160">Make sure you've added users and set up mailboxes in Microsoft 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="a51ee-161">Se si ha un sito Web che si usa con l'organizzazione, continuerà a funzionare dove si trova.</span><span class="sxs-lookup"><span data-stu-id="a51ee-161">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="a51ee-162">La procedura di Connessione dominio non influisce sul sito Web.</span><span class="sxs-lookup"><span data-stu-id="a51ee-162">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-content"></a><span data-ttu-id="a51ee-163">Contenuto correlato</span><span class="sxs-lookup"><span data-stu-id="a51ee-163">Related content</span></span>

<span data-ttu-id="a51ee-164">[Domande frequenti](domains-faq.yml) sui domini (articolo)</span><span class="sxs-lookup"><span data-stu-id="a51ee-164">[Domains FAQ](domains-faq.yml) (article)</span></span>\
[<span data-ttu-id="a51ee-165">Che cosa è un dominio?</span><span class="sxs-lookup"><span data-stu-id="a51ee-165">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md) <span data-ttu-id="a51ee-166">(articolo)</span><span class="sxs-lookup"><span data-stu-id="a51ee-166">(article)</span></span>\
<span data-ttu-id="a51ee-167">[Acquistare un nome di dominio in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="a51ee-167">[Buy a domain name in Microsoft 365](../get-help-with-domains/buy-a-domain-name.md) (article)</span></span>\
<span data-ttu-id="a51ee-168">[Configurare il dominio](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (articolo)</span><span class="sxs-lookup"><span data-stu-id="a51ee-168">[Set up your domain](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md) (article)</span></span>