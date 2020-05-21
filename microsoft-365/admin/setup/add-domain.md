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
ms.openlocfilehash: b40f537ec10b7d2406a9bb2fe281c39342f2d119
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327219"
---
# <a name="add-a-domain-to-microsoft-365"></a><span data-ttu-id="38b5f-104">Aggiungere un dominio a Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="38b5f-104">Add a domain to Microsoft 365</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="38b5f-105">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="38b5f-105">The admin center is changing.</span></span> <span data-ttu-id="38b5f-106">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="38b5f-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

 <span data-ttu-id="38b5f-107">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="38b5f-107">**[Check the Domains FAQ](domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
 <span data-ttu-id="38b5f-108">*Per aggiungere, modificare o rimuovere i domini, è **necessario** essere un **amministratore globale** di un [piano aziendale o aziendale](https://products.office.com/business/office). Queste modifiche hanno effetto sull'intero tenant, gli *amministratori personalizzati* o *gli utenti normali* non saranno in grado di apportare queste modifiche.*</span><span class="sxs-lookup"><span data-stu-id="38b5f-108">*To Add, modify or remove domains you **must** be a **Global Administrator** of a [business or enterprise plan](https://products.office.com/business/office). These changes affect the whole tenant, *Customized administrators* or *regular users* won't be able to make these changes.*</span></span>  

 <span data-ttu-id="38b5f-109">Eseguire la procedura seguente per aggiungere, configurare o continuare a configurare un dominio.</span><span class="sxs-lookup"><span data-stu-id="38b5f-109">Follow these steps to add, set up, or continue setting up a domain.</span></span> 

::: moniker range="o365-worldwide"
  
::: moniker-end

::: moniker range="o365-germany"

> [!VIDEO https://www.microsoft.com/videoplayer/embed/dda6df6d-37b0-41ff-905b-089448355a31?autoplay=false]
  
::: moniker-end

::: moniker range="o365-worldwide"

1. <span data-ttu-id="38b5f-110">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="38b5f-110">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

::: moniker-end
::: moniker range="o365-germany"

1. <span data-ttu-id="38b5f-111">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span><span class="sxs-lookup"><span data-stu-id="38b5f-111">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de/adminportal</a>.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="38b5f-112">Passare all'interfaccia di amministrazione all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span><span class="sxs-lookup"><span data-stu-id="38b5f-112">Go to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.</span></span>

::: moniker-end
    
2. <span data-ttu-id="38b5f-113">Passare alla pagina **Impostazioni**  >  **domini** .</span><span class="sxs-lookup"><span data-stu-id="38b5f-113">Go to the **Settings** > **Domains** page.</span></span> 

3. <span data-ttu-id="38b5f-114">Selezionare **Aggiungi dominio**.</span><span class="sxs-lookup"><span data-stu-id="38b5f-114">Select **Add domain**.</span></span>
    
4. <span data-ttu-id="38b5f-115">Immettere il nome del dominio che si desidera aggiungere, quindi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="38b5f-115">Enter the name of the domain you want to add, then select **Next**.</span></span>
    
5. <span data-ttu-id="38b5f-116">Scegliere in che modo si desidera verificare che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="38b5f-116">Choose how you want to verify that you own the domain.</span></span>
    
    1. <span data-ttu-id="38b5f-117">Se il dominio è registrato su GoDaddy o 1 &amp; 1, selezionare **Accedi**  >  **successivamente** e Microsoft [consentirà la configurazione automatica dei record](../get-help-with-domains/domain-connect.md).</span><span class="sxs-lookup"><span data-stu-id="38b5f-117">If your domain is registered at GoDaddy or 1&amp;1, select **Sign in** > **Next** and Microsoft [will set up your records automatically](../get-help-with-domains/domain-connect.md).</span></span>
    
    2. <span data-ttu-id="38b5f-118">È possibile specificare l'invio di un messaggio di posta elettronica contenente un codice di verifica al contatto registrato per il dominio.</span><span class="sxs-lookup"><span data-stu-id="38b5f-118">You can have an email sent to the registered contact for the domain with a verification code.</span></span> <span data-ttu-id="38b5f-119">Se non si riconosce o si ha accesso al messaggio di posta elettronica su record, è possibile utilizzare la terza opzione.</span><span class="sxs-lookup"><span data-stu-id="38b5f-119">If you don't recognize or have access to the email on record, you can use the third option.</span></span>
    
    3. <span data-ttu-id="38b5f-120">È possibile usare un record TXT per verificare il dominio.</span><span class="sxs-lookup"><span data-stu-id="38b5f-120">You can use a TXT record to verify your domain.</span></span> <span data-ttu-id="38b5f-121">Selezionarlo e quindi fare clic su **Avanti** per visualizzare le istruzioni su come aggiungere il record DNS al sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="38b5f-121">Select this and select **Next** to see instructions for how to add this DNS record to your registrar's website.</span></span> <span data-ttu-id="38b5f-122">Dopo aver aggiunto il record, possono essere necessari fino a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="38b5f-122">This can take up to 30 minutes to verify after you've added the record.</span></span> 
    
6. <span data-ttu-id="38b5f-123">Scegliere in che modo si desidera rendere necessarie le modifiche del DNS per l'utilizzo del dominio da parte di Office.</span><span class="sxs-lookup"><span data-stu-id="38b5f-123">Choose how you want to make the DNS changes required for Office to use your domain.</span></span>
    
    1. <span data-ttu-id="38b5f-124">Scegliere **Add the DNS Records for me** se si desidera che Office configuri automaticamente il DNS.</span><span class="sxs-lookup"><span data-stu-id="38b5f-124">Choose **Add the DNS records for me** if you want Office to configure your DNS automatically.</span></span> 
    
  
    2. <span data-ttu-id="38b5f-125">Scegliere **i ' ll add the DNS Records me stesso** se si desidera collegare solo i servizi specifici di Office 365 al dominio o se si desidera ignorare questo per ora e farlo in un secondo momento.</span><span class="sxs-lookup"><span data-stu-id="38b5f-125">Choose **I'll add the DNS records myself** if you want to attach only specific Office 365 services to your domain or if you want to skip this for now and do this later.</span></span> <span data-ttu-id="38b5f-126">**Scegliere questa opzione solo se si è effettivamente in grado di eseguire l'operazione.**</span><span class="sxs-lookup"><span data-stu-id="38b5f-126">**Choose this option if you know exactly what you're doing.**</span></span>
    
7. <span data-ttu-id="38b5f-127">Se si è scelto di *aggiungere manualmente i record DNS* , selezionare **Avanti** e visualizzare una pagina contenente tutti i record che è necessario aggiungere al sito Web di registrazione per configurare il dominio.</span><span class="sxs-lookup"><span data-stu-id="38b5f-127">If you chose to  *add DNS records yourself*  , select **Next** and you'll see a page with all the records that you need to add to your registrars website to set up your domain.</span></span> 
    
  
  
    <span data-ttu-id="38b5f-128">Se il portale non riconosce il registrar, è possibile [seguire queste istruzioni generali.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span><span class="sxs-lookup"><span data-stu-id="38b5f-128">If the portal doesn't recognize your registrar, you can [follow these general instructions.](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)</span></span>
    
    <span data-ttu-id="38b5f-129">Controllare l'elenco delle [istruzioni specifiche per l'host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) per trovare l'host e seguire la procedura per aggiungere tutti i record necessari.</span><span class="sxs-lookup"><span data-stu-id="38b5f-129">Check our list of [host-specific instructions](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/set-up-your-domain-host-specific-instructions) to find your host and follow the steps to add all the records you need.</span></span> 
    
    <span data-ttu-id="38b5f-130">Per identificare il provider di hosting DNS o il registrar per il dominio, vedere [Trovare il registrar o il provider di hosting DNS](../get-help-with-domains/find-your-domain-registrar.md).</span><span class="sxs-lookup"><span data-stu-id="38b5f-130">If you don't know the DNS hosting provider or domain registrar for your domain, see [Find your domain registrar or DNS hosting provider](../get-help-with-domains/find-your-domain-registrar.md).</span></span>
    
    <span data-ttu-id="38b5f-131">Se si desidera attendere in un secondo momento, scorrere fino alla fine e selezionare **Ignora questo passaggio**.</span><span class="sxs-lookup"><span data-stu-id="38b5f-131">If you want to wait for later, scroll to the bottom and select **Skip this step**.</span></span>
    
8. <span data-ttu-id="38b5f-132">Seleziona **fine** -hai finito!</span><span class="sxs-lookup"><span data-stu-id="38b5f-132">Select **Finish** - you're done!</span></span> 

## <a name="add-or-edit-custom-dns-records"></a><span data-ttu-id="38b5f-133">Aggiungere o modificare record DNS personalizzati</span><span class="sxs-lookup"><span data-stu-id="38b5f-133">Add or edit custom DNS records</span></span>

<span data-ttu-id="38b5f-134">Attenersi alla procedura riportata di seguito per aggiungere un record personalizzato per un sito Web o un servizio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="38b5f-134">Follow the steps below to add a custom record for a website or 3rd party service.</span></span>

1. <span data-ttu-id="38b5f-135">Accedere all'interfaccia di amministrazione di Microsoft all'indirizzo <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="38b5f-135">Sign in to the Microsoft admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="38b5f-136">Passare alla pagina **Impostazioni**   >  **domini** .</span><span class="sxs-lookup"><span data-stu-id="38b5f-136">Go to the **Settings**  > **Domains** page.</span></span>

3. <span data-ttu-id="38b5f-137">Nella pagina **Domini** selezionare un dominio.</span><span class="sxs-lookup"><span data-stu-id="38b5f-137">On the **Domains** page, select a domain.</span></span> 
    
4. <span data-ttu-id="38b5f-138">In **impostazioni DNS**selezionare **record personalizzati**; quindi selezionare **nuovo record personalizzato**.</span><span class="sxs-lookup"><span data-stu-id="38b5f-138">Under **DNS settings**, select **Custom Records**; then select **New custom record**.</span></span>

5. <span data-ttu-id="38b5f-139">Selezionare il tipo di record DNS che si desidera aggiungere e digitare le informazioni per il nuovo record.</span><span class="sxs-lookup"><span data-stu-id="38b5f-139">Select the type of DNS record you want to add and type the information for the new record.</span></span>
    
6. <span data-ttu-id="38b5f-140">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="38b5f-140">Select **Save**.</span></span>

## <a name="registrars-with-domain-connect"></a><span data-ttu-id="38b5f-141">Registrar con Domain Connect</span><span class="sxs-lookup"><span data-stu-id="38b5f-141">Registrars with Domain Connect</span></span>

<span data-ttu-id="38b5f-142">I registrar abilitati alla [connessione di dominio](https://www.domainconnect.org/) consentono di aggiungere il dominio a Microsoft 365 in un processo in tre passaggi che richiede minuti.</span><span class="sxs-lookup"><span data-stu-id="38b5f-142">[Domain Connect](https://www.domainconnect.org/) enabled registrars let you add your domain to Microsoft 365 in a three-step process that takes minutes.</span></span> 
  
<span data-ttu-id="38b5f-143">Nella procedura guidata, è sufficiente confermare che si è proprietari del dominio e quindi configurare automaticamente i record del dominio, in modo che la posta elettronica venga a Microsoft 365 e ad altri servizi Microsoft 365, come i team, che collaborino con il proprio dominio.</span><span class="sxs-lookup"><span data-stu-id="38b5f-143">In the wizard, we'll just confirm that you own the domain, and then automatically set up your domain's records, so email comes to Microsoft 365 and other Microsoft 365 services, like Teams, work with your domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="38b5f-144">Disabilitare il blocco dei popup nel browser prima di iniziare la configurazione guidata.</span><span class="sxs-lookup"><span data-stu-id="38b5f-144">Make sure you disable any popup blockers in your browser before you start the setup wizard.</span></span>
  
### <a name="domain-connect-registrars-integrating-with-microsoft-365"></a><span data-ttu-id="38b5f-145">Domain Connect registrar che si integrano con Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="38b5f-145">Domain Connect registrars integrating with Microsoft 365</span></span>

- [<span data-ttu-id="38b5f-146">1 &amp; 1 IONOS</span><span class="sxs-lookup"><span data-stu-id="38b5f-146">1&amp;1 IONOS</span></span>](https://www.1and1.com/)
- [<span data-ttu-id="38b5f-147">123Reg</span><span class="sxs-lookup"><span data-stu-id="38b5f-147">123Reg</span></span>](https://www.123-reg.co.uk/)
- [<span data-ttu-id="38b5f-148">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="38b5f-148">GoDaddy</span></span>](https://www.godaddy.com/)
- [<span data-ttu-id="38b5f-149">WordPress</span><span class="sxs-lookup"><span data-stu-id="38b5f-149">WordPress</span></span>](https://wordpress.com/)
- [<span data-ttu-id="38b5f-150">Plesk</span><span class="sxs-lookup"><span data-stu-id="38b5f-150">Plesk</span></span>](https://www.plesk.com/)
- [<span data-ttu-id="38b5f-151">MediaTemple</span><span class="sxs-lookup"><span data-stu-id="38b5f-151">MediaTemple</span></span>](https://mediatemple.net/)
- <span data-ttu-id="38b5f-152">SecureServer o WildWestDomains (rivenditori GoDaddy con hosting DNS di SecureServer)</span><span class="sxs-lookup"><span data-stu-id="38b5f-152">SecureServer or WildWestDomains (GoDaddy resellers using SecureServer DNS hosting)</span></span>
    - [<span data-ttu-id="38b5f-153">Domini di MadDog</span><span class="sxs-lookup"><span data-stu-id="38b5f-153">MadDog Domains</span></span>](https://www.maddogdomains.com/)
    - [<span data-ttu-id="38b5f-154">CheapNames</span><span class="sxs-lookup"><span data-stu-id="38b5f-154">CheapNames</span></span>](https://www.cheapnames.com)

### <a name="what-happens-to-my-email-and-website"></a><span data-ttu-id="38b5f-155">Cosa succede alla posta elettronica e al sito Web?</span><span class="sxs-lookup"><span data-stu-id="38b5f-155">What happens to my email and website?</span></span>

<span data-ttu-id="38b5f-156">Dopo aver completato l'installazione, il record MX per il dominio viene aggiornato in modo che punti a Microsoft 365 e tutti i messaggi di posta elettronica per il dominio inizieranno a essere inviati a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="38b5f-156">After you finish setup, the MX record for your domain is updated to point to Microsoft 365 and all email for your domain will start coming to Microsoft 365.</span></span> <span data-ttu-id="38b5f-157">Assicurarsi di aver aggiunto utenti e configurato le cassette postali in Office 365 per tutte le persone che ricevono posta nel dominio.</span><span class="sxs-lookup"><span data-stu-id="38b5f-157">Make sure you've added users and set up mailboxes in Office 365 for everyone who gets email on your domain!</span></span>
  
<span data-ttu-id="38b5f-158">Se si ha un sito Web che si usa con l'organizzazione, continuerà a funzionare dove si trova.</span><span class="sxs-lookup"><span data-stu-id="38b5f-158">If you have a website that you use with your business, it will keep working where it is.</span></span> <span data-ttu-id="38b5f-159">I passaggi di installazione di Domain Connect non influiscono sul sito Web.</span><span class="sxs-lookup"><span data-stu-id="38b5f-159">The Domain Connect setup steps don't affect your website.</span></span>

## <a name="related-articles"></a><span data-ttu-id="38b5f-160">Articoli correlati</span><span class="sxs-lookup"><span data-stu-id="38b5f-160">Related articles</span></span>

[<span data-ttu-id="38b5f-161">Domande frequenti sui domini</span><span class="sxs-lookup"><span data-stu-id="38b5f-161">Domains FAQ</span></span>](domains-faq.md)

[<span data-ttu-id="38b5f-162">Che cosa è un dominio?</span><span class="sxs-lookup"><span data-stu-id="38b5f-162">What is a domain?</span></span>](../get-help-with-domains/what-is-a-domain.md)

[<span data-ttu-id="38b5f-163">Acquistare un nome di dominio in Office 365</span><span class="sxs-lookup"><span data-stu-id="38b5f-163">Buy a domain name in Office 365</span></span>](../get-help-with-domains/buy-a-domain-name.md)

[<span data-ttu-id="38b5f-164">Configurare il dominio (istruzioni specifiche per l’host)</span><span class="sxs-lookup"><span data-stu-id="38b5f-164">Set up your domain (host-specific instructions)</span></span>](../get-help-with-domains/set-up-your-domain-host-specific-instructions.md)

[<span data-ttu-id="38b5f-165">Ottenere assistenza per i domini</span><span class="sxs-lookup"><span data-stu-id="38b5f-165">Get help with domains</span></span>](../get-help-with-domains/get-help-with-domains.md)
