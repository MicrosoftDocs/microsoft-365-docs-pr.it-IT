---
title: Domande frequenti sui domini
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
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 1272bad0-4bd4-4796-8005-67d6fb3afc5a
description: Per ulteriori informazioni sui domini, è possibile trovare le risposte alle domande più frequenti.
ms.openlocfilehash: 093125d1652355fbd9b624e1f15b5858fd586301
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049737"
---
# <a name="domains-faq"></a><span data-ttu-id="75fbb-103">Domande frequenti sui domini</span><span class="sxs-lookup"><span data-stu-id="75fbb-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="75fbb-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="75fbb-104">The admin center is changing.</span></span> <span data-ttu-id="75fbb-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="75fbb-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="75fbb-106">Questo articolo contiene le risposte alle domande frequenti sui domini in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75fbb-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="75fbb-107">Se non si riesce a trovare una risposta a una domanda, lasciare un commento per segnalare la risposta mancante, che verrà aggiunta all'elenco.</span><span class="sxs-lookup"><span data-stu-id="75fbb-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="75fbb-108">In questo articolo</span><span class="sxs-lookup"><span data-stu-id="75fbb-108">In this article</span></span>

<span data-ttu-id="75fbb-109">[Che cos'è la priorità MX?](#what-is-mx-priority) 
 [Come è possibile convalidare i record SPF per il dominio?](#how-can-i-validate-spf-records-for-my-domain) 
 [Che cos'è un nome di dominio?](#what-is-a-domain-name) 
 [Cosa succede se il provider DNS non supporta alcuni tipi di record?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types) 
 [Come impostare o modificare il dominio predefinito in Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365) 
 È [possibile aggiungere sottodomini personalizzati o più domini a Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365) 
 [Perché è presente un dominio "onmicrosoft.com"?](#why-do-i-have-an-onmicrosoftcom-domain) 
 [Perché è presente un dominio "onmicrosoft.de"?](#why-do-i-have-an-onmicrosoftde-domain) 
 [Come verificare lo stato dell'istruzione o dell'organizzazione no profit](#how-do-i-verify-my-nonprofit-or-education-status)</span><span class="sxs-lookup"><span data-stu-id="75fbb-109">[What is MX priority?](#what-is-mx-priority)
[How can I validate SPF records for my domain?](#how-can-i-validate-spf-records-for-my-domain)
[What is a domain name?](#what-is-a-domain-name)
[What happens if my DNS provider doesn't support certain record types?](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
[How do I set or change the default domain in Microsoft 365?](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
[Can I add custom subdomains or multiple domains to Microsoft 365?](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
[Why do I have an "onmicrosoft.com" domain?](#why-do-i-have-an-onmicrosoftcom-domain)
[Why do I have an "onmicrosoft.de" domain?](#why-do-i-have-an-onmicrosoftde-domain)
[How do I verify my nonprofit or education status?](#how-do-i-verify-my-nonprofit-or-education-status)</span></span>
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="75fbb-110">Cos'è la priorità MX?</span><span class="sxs-lookup"><span data-stu-id="75fbb-110">What is MX priority?</span></span>

<span data-ttu-id="75fbb-111">La posta viene recapitata al server Mail Exchange con il numero di preferenza più basso (priorità più alta), quindi il record MX usato per il routing della posta deve avere il numero di preferenza più basso, in genere 0, o priorità  *Alta*  .</span><span class="sxs-lookup"><span data-stu-id="75fbb-111">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="75fbb-112">Quando si crea un record MX, la maggior parte dei provider di hosting DNS richiede di impostare il numero della preferenza.</span><span class="sxs-lookup"><span data-stu-id="75fbb-112">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="75fbb-113">Alcuni provider presentano una casella chiamata  *preferenza*  e altri  *priorità*  .</span><span class="sxs-lookup"><span data-stu-id="75fbb-113">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="75fbb-114">Alcuni richiedono di specificare un numero mentre altri richiedono di selezionare il livello di priorità  *basso*  ,  *medio*  o  *alto*  .</span><span class="sxs-lookup"><span data-stu-id="75fbb-114">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="75fbb-115">Se è presente un solo record MX, è possibile specificare qualsiasi valore per la priorità o la preferenza.</span><span class="sxs-lookup"><span data-stu-id="75fbb-115">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="75fbb-116">Se sono presenti più record MX, accertarsi che quello usato per il routing della posta abbia una priorità più alta rispetto a quello usato per la conferma della proprietà del dominio.</span><span class="sxs-lookup"><span data-stu-id="75fbb-116">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="75fbb-117">Come si fa a convalidare i record SPF per un dominio?</span><span class="sxs-lookup"><span data-stu-id="75fbb-117">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="75fbb-118">È importante disporre o creare **un solo record TXT per SPF**.</span><span class="sxs-lookup"><span data-stu-id="75fbb-118">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="75fbb-119">Se si dispone già di un record SPF, è necessario aggiungere i nuovi valori di Microsoft 365, anziché crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="75fbb-119">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="75fbb-120">Dopo aver aggiunto o aggiornato il record SPF per il messaggio di posta elettronica Microsoft, è necessario verificare che la sintassi sia corretta con uno di questi strumenti:</span><span class="sxs-lookup"><span data-stu-id="75fbb-120">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="75fbb-121">Strumenti di test del record SPF</span><span class="sxs-lookup"><span data-stu-id="75fbb-121">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="75fbb-122">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="75fbb-122">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="75fbb-123">Interfaccia Web Dig</span><span class="sxs-lookup"><span data-stu-id="75fbb-123">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="75fbb-124">Cos'è un nome di dominio?</span><span class="sxs-lookup"><span data-stu-id="75fbb-124">What is a domain name?</span></span>

<span data-ttu-id="75fbb-125">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span><span class="sxs-lookup"><span data-stu-id="75fbb-125">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.**</span></span> <span data-ttu-id="75fbb-126">in web addresses.</span><span class="sxs-lookup"><span data-stu-id="75fbb-126">in web addresses.</span></span> <span data-ttu-id="75fbb-127">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span><span class="sxs-lookup"><span data-stu-id="75fbb-127">It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="75fbb-128">L'utilizzo di un dominio personalizzato come "**rob \@ contoso.com**" con Microsoft 365 può contribuire a creare credibilità e riconoscimento per il proprio marchio.</span><span class="sxs-lookup"><span data-stu-id="75fbb-128">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="75fbb-129">È possibile [acquistare un dominio in Microsoft 365 e noi lo configurano automaticamente](../get-help-with-domains/buy-a-domain-name.md)oppure è possibile acquistarne uno o portarlo già da un registrar.</span><span class="sxs-lookup"><span data-stu-id="75fbb-129">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="75fbb-130">Cosa succede se il provider DNS non supporta alcuni tipi di record?</span><span class="sxs-lookup"><span data-stu-id="75fbb-130">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="75fbb-131">Se si gestiscono i propri record DNS e l'host DNS non supporta tutti i record DNS necessari per Microsoft 365, alcune funzionalità di Microsoft 365 non funzioneranno.</span><span class="sxs-lookup"><span data-stu-id="75fbb-131">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="75fbb-132">È consigliabile trasferire il dominio presso un registrar che supporti tutti i record DNS necessari.</span><span class="sxs-lookup"><span data-stu-id="75fbb-132">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="75fbb-133">Provider che supportano tutti i record DNS necessari:</span><span class="sxs-lookup"><span data-stu-id="75fbb-133">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="75fbb-134">Dynadot</span><span class="sxs-lookup"><span data-stu-id="75fbb-134">Dynadot</span></span>
    
- <span data-ttu-id="75fbb-135">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="75fbb-135">eNomCentral</span></span>
    
- <span data-ttu-id="75fbb-136">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="75fbb-136">Europe Registry</span></span>
    
- <span data-ttu-id="75fbb-137">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="75fbb-137">GoDaddy</span></span>
    
- <span data-ttu-id="75fbb-138">Hover</span><span class="sxs-lookup"><span data-stu-id="75fbb-138">Hover</span></span>
    
- <span data-ttu-id="75fbb-139">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="75fbb-139">MyHosting.com</span></span>
    
- <span data-ttu-id="75fbb-140">Name.com</span><span class="sxs-lookup"><span data-stu-id="75fbb-140">Name.com</span></span>
    
- <span data-ttu-id="75fbb-141">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="75fbb-141">Nearly Free Speech</span></span>
    
- <span data-ttu-id="75fbb-142">Nettica</span><span class="sxs-lookup"><span data-stu-id="75fbb-142">Nettica</span></span>
    
- <span data-ttu-id="75fbb-143">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="75fbb-143">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="75fbb-144">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="75fbb-144">Network Solutions</span></span>
    
- <span data-ttu-id="75fbb-145">Register.com</span><span class="sxs-lookup"><span data-stu-id="75fbb-145">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="75fbb-146">Come impostare o modificare il dominio predefinito in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="75fbb-146">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="75fbb-147">È necessario disporre di almeno un dominio personalizzato che è stato aggiunto a Microsoft 365 prima di poter scegliere un dominio predefinito.</span><span class="sxs-lookup"><span data-stu-id="75fbb-147">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="75fbb-148">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="75fbb-148">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="75fbb-149">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="75fbb-149">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="75fbb-150">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="75fbb-150">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="75fbb-151">Nella pagina **Domains** selezionare il dominio che si desidera impostare come predefinito per i nuovi indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="75fbb-151">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="75fbb-152">Selezionare **Imposta come predefinito**.</span><span class="sxs-lookup"><span data-stu-id="75fbb-152">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="75fbb-153">Non è possibile modificare il nome del dominio  *.onmicrosoft.com*  iniziale.</span><span class="sxs-lookup"><span data-stu-id="75fbb-153">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="75fbb-154">Non è possibile modificare il nome del dominio iniziale *. onmicrosoft.de* .</span><span class="sxs-lookup"><span data-stu-id="75fbb-154">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="75fbb-155">Non è possibile modificare il nome del dominio iniziale *. partner.onmschina.cn* .</span><span class="sxs-lookup"><span data-stu-id="75fbb-155">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="75fbb-156">È possibile aggiungere sottodomini personalizzati o più domini a Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="75fbb-156">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="75fbb-157">Sì.</span><span class="sxs-lookup"><span data-stu-id="75fbb-157">Yes.</span></span> <span data-ttu-id="75fbb-158">Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="75fbb-158">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="75fbb-159">Se si desidera consentire a Microsoft di gestire le impostazioni DNS con i record NS o se il dominio è stato acquistato da Microsoft, non è possibile aggiungere sottodomini.</span><span class="sxs-lookup"><span data-stu-id="75fbb-159">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="75fbb-160">Sì!</span><span class="sxs-lookup"><span data-stu-id="75fbb-160">Yes!</span></span> <span data-ttu-id="75fbb-161">Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="75fbb-161">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="75fbb-162">Se si desidera consentire a Microsoft di gestire le impostazioni DNS con i record NS o se il dominio è stato acquistato da Microsoft, non è possibile aggiungere sottodomini.</span><span class="sxs-lookup"><span data-stu-id="75fbb-162">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="75fbb-163">Sì!</span><span class="sxs-lookup"><span data-stu-id="75fbb-163">Yes!</span></span> <span data-ttu-id="75fbb-164">Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="75fbb-164">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="75fbb-165">Se si consente a 21Vianet di gestire le impostazioni DNS con i record NS, non è possibile aggiungere sottodomini.</span><span class="sxs-lookup"><span data-stu-id="75fbb-165">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="75fbb-166">In genere, è possibile aggiungere fino a 900 domini alla sottoscrizione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75fbb-166">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="75fbb-167">Ad esempio, è possibile aggiungere i domini contoso.com e contosomarketing.com e quindi i sottodomini www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com e così via.</span><span class="sxs-lookup"><span data-stu-id="75fbb-167">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="75fbb-168">Quando si aggiunge un sottodominio, la verifica viene eseguita automaticamente in base al dominio padre che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="75fbb-168">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="75fbb-169">Quando si aggiungono più domini a Microsoft 365, è possibile ospitare uno qualsiasi dei servizi (come la posta elettronica) in uno dei domini che sono stati aggiunti.</span><span class="sxs-lookup"><span data-stu-id="75fbb-169">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="75fbb-170">*Quando si modifica il messaggio di posta elettronica a Microsoft 365, aggiornando il record MX di un dominio, tutti i messaggi di posta elettronica inviati a tale dominio inizieranno a essere Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="75fbb-170">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="75fbb-171">Se è stato aggiunto un dominio di contoso.com a un abbonamento a Microsoft 365, è possibile aggiungere anche il sottodominio xyz.contoso.com a un'altra organizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75fbb-171">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="75fbb-172">Quando si aggiunge il sottodominio, viene richiesto di aggiungere un record TXT nel provider di hosting DNS.</span><span class="sxs-lookup"><span data-stu-id="75fbb-172">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="75fbb-173">Perché è presente un dominio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="75fbb-173">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="75fbb-174">Microsoft 365 crea un dominio per l'utente, come *contoso.onmicrosoft.com*, quando si esegue l'iscrizione al servizio.</span><span class="sxs-lookup"><span data-stu-id="75fbb-174">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="75fbb-175">L'ID utente creato al momento dell'iscrizione include il dominio, ad esempio *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="75fbb-175">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="75fbb-176">**Se si desidera che la posta elettronica sia simile a *Alan \@ contoso.com*:** [acquistare il dominio](../get-help-with-domains/buy-a-domain-name.md) oppure seguire la procedura descritta in [aggiungere gli utenti e il dominio a Microsoft 365](add-domain.md) , se lo si possiede già.</span><span class="sxs-lookup"><span data-stu-id="75fbb-176">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="75fbb-177">**Dopo l'iscrizione, non è possibile rinominare il dominio onmicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="75fbb-177">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="75fbb-178">Se ad esempio il dominio iniziale scelto è fourthcoffee.onmicrosoft.com, non lo si può cambiare in fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="75fbb-178">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="75fbb-179">Per utilizzare un dominio onmicrosoft.com diverso, è necessario avviare un nuovo abbonamento con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75fbb-179">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="75fbb-180">**Non è possibile rinominare l'URL del sito del team.**</span><span class="sxs-lookup"><span data-stu-id="75fbb-180">**You can't rename your team site URL.**</span></span> <span data-ttu-id="75fbb-181">L'URL del sito del team si basa sul nome di dominio onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="75fbb-181">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="75fbb-182">Purtroppo, a causa del modo in cui funziona l'architettura di SharePoint Online, non è possibile rinominare il sito del team.</span><span class="sxs-lookup"><span data-stu-id="75fbb-182">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="75fbb-183">**Non è possibile rimuovere il dominio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="75fbb-183">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="75fbb-184">Microsoft 365 deve conservarlo perché viene utilizzato dietro le quinte per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="75fbb-184">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="75fbb-185">Non è tuttavia necessario usare personalmente il dominio dopo averne aggiunto uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="75fbb-185">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="75fbb-186">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span><span class="sxs-lookup"><span data-stu-id="75fbb-186">You can keep using the initial onmicrosoft.com domain even after you add your domain.</span></span> <span data-ttu-id="75fbb-187">It still works for email and other services, so it's your choice.</span><span class="sxs-lookup"><span data-stu-id="75fbb-187">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="75fbb-188">Perché è presente un dominio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="75fbb-188">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="75fbb-189">Microsoft 365 crea un dominio per l'utente, come *contoso.onmicrosoft.de*, quando si esegue l'iscrizione al servizio.</span><span class="sxs-lookup"><span data-stu-id="75fbb-189">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="75fbb-190">L'ID utente creato al momento dell'iscrizione include il dominio, ad esempio *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="75fbb-190">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="75fbb-191">**Se si desidera che la posta elettronica sia simile a *Alan@contoso.de*:** [acquistare il dominio](../get-help-with-domains/buy-a-domain-name.md) oppure seguire la procedura descritta in [aggiungere gli utenti e il dominio a Microsoft 365](add-domain.md) , se lo si possiede già.</span><span class="sxs-lookup"><span data-stu-id="75fbb-191">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="75fbb-192">**Dopo l'iscrizione, non è possibile rinominare il dominio onmicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="75fbb-192">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="75fbb-193">Ad esempio, se il dominio iniziale scelto era fourthcoffee.onmicrosoft.de, non è possibile modificarlo in modo che sia fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="75fbb-193">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="75fbb-194">Per utilizzare un dominio onmicrosoft.de diverso, è necessario avviare un nuovo abbonamento con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75fbb-194">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="75fbb-195">**Non è possibile rinominare l'URL del sito del team.**</span><span class="sxs-lookup"><span data-stu-id="75fbb-195">**You can't rename your team site URL.**</span></span> <span data-ttu-id="75fbb-196">L'URL del sito del team si basa sul nome di dominio onmicrosoft.de. Purtroppo, a causa del modo in cui funziona l'architettura di SharePoint Online, non è possibile rinominare il sito del team.</span><span class="sxs-lookup"><span data-stu-id="75fbb-196">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="75fbb-197">**Non è possibile rimuovere il dominio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="75fbb-197">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="75fbb-198">Microsoft 365 deve conservarlo perché viene utilizzato dietro le quinte per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="75fbb-198">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="75fbb-199">Non è tuttavia necessario usare personalmente il dominio dopo averne aggiunto uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="75fbb-199">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="75fbb-200">È possibile continuare a utilizzare il dominio onmicrosoft.de iniziale anche dopo aver aggiunto il dominio.</span><span class="sxs-lookup"><span data-stu-id="75fbb-200">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="75fbb-201">Funziona ancora per la posta elettronica e altri servizi, quindi è una tua scelta.</span><span class="sxs-lookup"><span data-stu-id="75fbb-201">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="75fbb-202">Come verificare lo stato dell'istruzione o dell'organizzazione no profit</span><span class="sxs-lookup"><span data-stu-id="75fbb-202">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="75fbb-203">Selezionare **installazione** nell'interfaccia di [Amministrazione](https://docs.microsoft.com/microsoft-365/admin/admin-home) per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="75fbb-203">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="75fbb-204">(Assicurarsi di accedere a Microsoft 365 per primo).</span><span class="sxs-lookup"><span data-stu-id="75fbb-204">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="75fbb-205">Per diventare l'amministratore dell'Istituto di istruzione, selezionare l'opzione **diventa amministratore** in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75fbb-205">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="75fbb-206">Verrà richiesto di aggiungere un record DNS TXT nel sito Web host DNS per il dominio.</span><span class="sxs-lookup"><span data-stu-id="75fbb-206">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="75fbb-207">Perché?</span><span class="sxs-lookup"><span data-stu-id="75fbb-207">Why?</span></span> <span data-ttu-id="75fbb-208">Poiché accedendo all'host DNS e aggiungendo un record per il dominio, si dimostra a Microsoft 365 che si è proprietari del nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="75fbb-208">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="75fbb-209">Dopo aver aggiunto il record, è possibile tornare al portale Microsoft 365 e verificare di averla aggiunta, in modo che Microsoft 365 possa controllare.</span><span class="sxs-lookup"><span data-stu-id="75fbb-209">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="75fbb-210">Avere un no profit e desidera ottenere Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="75fbb-210">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="75fbb-211">Verificare [che l'organizzazione sia qualificata](https://www.microsoft.com/en-us/nonprofits/eligibility) e quindi iscriversi al servizio.</span><span class="sxs-lookup"><span data-stu-id="75fbb-211">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="75fbb-212">Vuoi saperne di più su come diventare l'amministratore per la tua scuola?</span><span class="sxs-lookup"><span data-stu-id="75fbb-212">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="75fbb-213">Informazioni [su tutto](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="75fbb-213">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>