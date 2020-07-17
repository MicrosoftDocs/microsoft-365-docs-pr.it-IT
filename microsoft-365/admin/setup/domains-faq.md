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
ms.openlocfilehash: c588586ddd3d57fdbe78d7751131f61e6aa53eba
ms.sourcegitcommit: dc5de2064706137256307f100b8dc61e9797bd1c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/07/2020
ms.locfileid: "45068104"
---
# <a name="domains-faq"></a><span data-ttu-id="e4041-103">Domande frequenti sui domini</span><span class="sxs-lookup"><span data-stu-id="e4041-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e4041-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="e4041-104">The admin center is changing.</span></span> <span data-ttu-id="e4041-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e4041-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="e4041-106">Questo articolo contiene le risposte alle domande frequenti sui domini in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4041-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="e4041-107">Se non si riesce a trovare una risposta a una domanda, lasciare un commento per segnalare la risposta mancante, che verrà aggiunta all'elenco.</span><span class="sxs-lookup"><span data-stu-id="e4041-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="e4041-108">In questo articolo</span><span class="sxs-lookup"><span data-stu-id="e4041-108">In this article</span></span>

- [<span data-ttu-id="e4041-109">Cos'è la priorità MX?</span><span class="sxs-lookup"><span data-stu-id="e4041-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="e4041-110">Come si fa a convalidare i record SPF per un dominio?</span><span class="sxs-lookup"><span data-stu-id="e4041-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="e4041-111">Cos'è un nome di dominio?</span><span class="sxs-lookup"><span data-stu-id="e4041-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="e4041-112">Cosa succede se il provider DNS non supporta alcuni tipi di record?</span><span class="sxs-lookup"><span data-stu-id="e4041-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="e4041-113">Come impostare o modificare il dominio predefinito in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e4041-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="e4041-114">È possibile aggiungere sottodomini personalizzati o più domini a Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e4041-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="e4041-115">Perché è presente un dominio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="e4041-115">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="e4041-116">Perché è presente un dominio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="e4041-116">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="e4041-117">Come verificare lo stato dell'istruzione o dell'organizzazione no profit</span><span class="sxs-lookup"><span data-stu-id="e4041-117">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="e4041-118">Cos'è la priorità MX?</span><span class="sxs-lookup"><span data-stu-id="e4041-118">What is MX priority?</span></span>

<span data-ttu-id="e4041-119">La posta viene recapitata al server Mail Exchange con il numero di preferenza più basso (priorità più alta), quindi il record MX usato per il routing della posta deve avere il numero di preferenza più basso, in genere 0, o priorità  *Alta*  .</span><span class="sxs-lookup"><span data-stu-id="e4041-119">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="e4041-120">Quando si crea un record MX, la maggior parte dei provider di hosting DNS richiede di impostare il numero della preferenza.</span><span class="sxs-lookup"><span data-stu-id="e4041-120">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="e4041-121">Alcuni provider presentano una casella chiamata  *preferenza*  e altri  *priorità*  .</span><span class="sxs-lookup"><span data-stu-id="e4041-121">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="e4041-122">Alcuni richiedono di specificare un numero mentre altri richiedono di selezionare il livello di priorità  *basso*  ,  *medio*  o  *alto*  .</span><span class="sxs-lookup"><span data-stu-id="e4041-122">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="e4041-123">Se è presente un solo record MX, è possibile specificare qualsiasi valore per la priorità o la preferenza.</span><span class="sxs-lookup"><span data-stu-id="e4041-123">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="e4041-124">Se sono presenti più record MX, accertarsi che quello usato per il routing della posta abbia una priorità più alta rispetto a quello usato per la conferma della proprietà del dominio.</span><span class="sxs-lookup"><span data-stu-id="e4041-124">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="e4041-125">Come si fa a convalidare i record SPF per un dominio?</span><span class="sxs-lookup"><span data-stu-id="e4041-125">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="e4041-126">È importante disporre o creare **un solo record TXT per SPF**.</span><span class="sxs-lookup"><span data-stu-id="e4041-126">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="e4041-127">Se si dispone già di un record SPF, è necessario aggiungere i nuovi valori di Microsoft 365, anziché crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="e4041-127">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="e4041-128">Dopo aver aggiunto o aggiornato il record SPF per il messaggio di posta elettronica Microsoft, è necessario verificare che la sintassi sia corretta con uno di questi strumenti:</span><span class="sxs-lookup"><span data-stu-id="e4041-128">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="e4041-129">Strumenti di test del record SPF</span><span class="sxs-lookup"><span data-stu-id="e4041-129">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="e4041-130">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="e4041-130">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="e4041-131">Interfaccia Web Dig</span><span class="sxs-lookup"><span data-stu-id="e4041-131">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="e4041-132">Cos'è un nome di dominio?</span><span class="sxs-lookup"><span data-stu-id="e4041-132">What is a domain name?</span></span>

<span data-ttu-id="e4041-p103">Un dominio è un nome univoco che segue il segno **@** negli indirizzi di posta elettronica e **www.** negli indirizzi Web. In genere è composto dal nome dell'organizzazione e da un suffisso Internet standard, come  *nomeazienda.com*  o  *nomeuniversità.edu*  .</span><span class="sxs-lookup"><span data-stu-id="e4041-p103">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="e4041-136">L'utilizzo di un dominio personalizzato come "**rob \@ contoso.com**" con Microsoft 365 può contribuire a creare credibilità e riconoscimento per il proprio marchio.</span><span class="sxs-lookup"><span data-stu-id="e4041-136">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="e4041-137">È possibile [acquistare un dominio in Microsoft 365 e noi lo configurano automaticamente](../get-help-with-domains/buy-a-domain-name.md)oppure è possibile acquistarne uno o portarlo già da un registrar.</span><span class="sxs-lookup"><span data-stu-id="e4041-137">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="e4041-138">Cosa succede se il provider DNS non supporta alcuni tipi di record?</span><span class="sxs-lookup"><span data-stu-id="e4041-138">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="e4041-139">Se si gestiscono i propri record DNS e l'host DNS non supporta tutti i record DNS necessari per Microsoft 365, alcune funzionalità di Microsoft 365 non funzioneranno.</span><span class="sxs-lookup"><span data-stu-id="e4041-139">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="e4041-140">È consigliabile trasferire il dominio presso un registrar che supporti tutti i record DNS necessari.</span><span class="sxs-lookup"><span data-stu-id="e4041-140">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="e4041-141">Provider che supportano tutti i record DNS necessari:</span><span class="sxs-lookup"><span data-stu-id="e4041-141">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="e4041-142">Dynadot</span><span class="sxs-lookup"><span data-stu-id="e4041-142">Dynadot</span></span>
    
- <span data-ttu-id="e4041-143">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="e4041-143">eNomCentral</span></span>
    
- <span data-ttu-id="e4041-144">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="e4041-144">Europe Registry</span></span>
    
- <span data-ttu-id="e4041-145">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="e4041-145">GoDaddy</span></span>
    
- <span data-ttu-id="e4041-146">Hover</span><span class="sxs-lookup"><span data-stu-id="e4041-146">Hover</span></span>
    
- <span data-ttu-id="e4041-147">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="e4041-147">MyHosting.com</span></span>
    
- <span data-ttu-id="e4041-148">Name.com</span><span class="sxs-lookup"><span data-stu-id="e4041-148">Name.com</span></span>
    
- <span data-ttu-id="e4041-149">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="e4041-149">Nearly Free Speech</span></span>
    
- <span data-ttu-id="e4041-150">Nettica</span><span class="sxs-lookup"><span data-stu-id="e4041-150">Nettica</span></span>
    
- <span data-ttu-id="e4041-151">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="e4041-151">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="e4041-152">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="e4041-152">Network Solutions</span></span>
    
- <span data-ttu-id="e4041-153">Register.com</span><span class="sxs-lookup"><span data-stu-id="e4041-153">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="e4041-154">Come impostare o modificare il dominio predefinito in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e4041-154">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="e4041-155">È necessario disporre di almeno un dominio personalizzato che è stato aggiunto a Microsoft 365 prima di poter scegliere un dominio predefinito.</span><span class="sxs-lookup"><span data-stu-id="e4041-155">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e4041-156">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="e4041-156">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e4041-157">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="e4041-157">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e4041-158">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="e4041-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="e4041-159">Nella pagina **Domains** selezionare il dominio che si desidera impostare come predefinito per i nuovi indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e4041-159">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="e4041-160">Selezionare **Imposta come predefinito**.</span><span class="sxs-lookup"><span data-stu-id="e4041-160">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="e4041-161">Non è possibile modificare il nome del dominio  *.onmicrosoft.com*  iniziale.</span><span class="sxs-lookup"><span data-stu-id="e4041-161">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="e4041-162">Non è possibile modificare il nome del dominio iniziale *. onmicrosoft.de* .</span><span class="sxs-lookup"><span data-stu-id="e4041-162">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="e4041-163">Non è possibile modificare il nome del dominio iniziale *. partner.onmschina.cn* .</span><span class="sxs-lookup"><span data-stu-id="e4041-163">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="e4041-164">È possibile aggiungere sottodomini personalizzati o più domini a Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e4041-164">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="e4041-165">Sì.</span><span class="sxs-lookup"><span data-stu-id="e4041-165">Yes.</span></span> <span data-ttu-id="e4041-166">Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="e4041-166">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="e4041-167">Se si desidera consentire a Microsoft di gestire le impostazioni DNS con i record NS o se il dominio è stato acquistato da Microsoft, non è possibile aggiungere sottodomini.</span><span class="sxs-lookup"><span data-stu-id="e4041-167">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="e4041-168">Sì!</span><span class="sxs-lookup"><span data-stu-id="e4041-168">Yes!</span></span> <span data-ttu-id="e4041-169">Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="e4041-169">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="e4041-170">Se si desidera consentire a Microsoft di gestire le impostazioni DNS con i record NS o se il dominio è stato acquistato da Microsoft, non è possibile aggiungere sottodomini.</span><span class="sxs-lookup"><span data-stu-id="e4041-170">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="e4041-171">Sì!</span><span class="sxs-lookup"><span data-stu-id="e4041-171">Yes!</span></span> <span data-ttu-id="e4041-172">Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="e4041-172">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="e4041-173">Se si consente a 21Vianet di gestire le impostazioni DNS con i record NS, non è possibile aggiungere sottodomini.</span><span class="sxs-lookup"><span data-stu-id="e4041-173">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="e4041-174">In genere, è possibile aggiungere fino a 900 domini alla sottoscrizione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4041-174">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="e4041-175">Ad esempio, è possibile aggiungere i domini contoso.com e contosomarketing.com e quindi i sottodomini www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com e così via.</span><span class="sxs-lookup"><span data-stu-id="e4041-175">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="e4041-176">Quando si aggiunge un sottodominio, la verifica viene eseguita automaticamente in base al dominio padre che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="e4041-176">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="e4041-177">Quando si aggiungono più domini a Microsoft 365, è possibile ospitare uno qualsiasi dei servizi (come la posta elettronica) in uno dei domini che sono stati aggiunti.</span><span class="sxs-lookup"><span data-stu-id="e4041-177">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="e4041-178">*Quando si modifica il messaggio di posta elettronica a Microsoft 365, aggiornando il record MX di un dominio, tutti i messaggi di posta elettronica inviati a tale dominio inizieranno a essere Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="e4041-178">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e4041-179">Se è stato aggiunto un dominio di contoso.com a un abbonamento a Microsoft 365, è possibile aggiungere anche il sottodominio xyz.contoso.com a un'altra organizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4041-179">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="e4041-180">Quando si aggiunge il sottodominio, viene richiesto di aggiungere un record TXT nel provider di hosting DNS.</span><span class="sxs-lookup"><span data-stu-id="e4041-180">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="e4041-181">Perché è presente un dominio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="e4041-181">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="e4041-182">Microsoft 365 crea un dominio per l'utente, come *contoso.onmicrosoft.com*, quando si esegue l'iscrizione al servizio.</span><span class="sxs-lookup"><span data-stu-id="e4041-182">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="e4041-183">L'ID utente creato al momento dell'iscrizione include il dominio, ad esempio *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="e4041-183">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="e4041-184">**Se si desidera che la posta elettronica sia simile a *Alan \@ contoso.com*:** [acquistare il dominio](../get-help-with-domains/buy-a-domain-name.md) oppure seguire la procedura descritta in [aggiungere gli utenti e il dominio a Microsoft 365](add-domain.md) , se lo si possiede già.</span><span class="sxs-lookup"><span data-stu-id="e4041-184">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="e4041-185">**Dopo l'iscrizione, non è possibile rinominare il dominio onmicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="e4041-185">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="e4041-186">Se ad esempio il dominio iniziale scelto è fourthcoffee.onmicrosoft.com, non lo si può cambiare in fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e4041-186">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="e4041-187">Per utilizzare un dominio onmicrosoft.com diverso, è necessario avviare un nuovo abbonamento con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4041-187">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="e4041-188">**Non è possibile rinominare l'URL del sito del team.**</span><span class="sxs-lookup"><span data-stu-id="e4041-188">**You can't rename your team site URL.**</span></span> <span data-ttu-id="e4041-189">L'URL del sito del team si basa sul nome di dominio onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="e4041-189">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="e4041-190">Purtroppo, a causa del modo in cui funziona l'architettura di SharePoint Online, non è possibile rinominare il sito del team.</span><span class="sxs-lookup"><span data-stu-id="e4041-190">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="e4041-191">**Non è possibile rimuovere il dominio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="e4041-191">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="e4041-192">Microsoft 365 deve conservarlo perché viene utilizzato dietro le quinte per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="e4041-192">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="e4041-193">Non è tuttavia necessario usare personalmente il dominio dopo averne aggiunto uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e4041-193">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="e4041-p114">Si può continuare a usare il dominio iniziale onmicrosoft.com anche dopo l'aggiunta di quello personalizzato. È infatti sempre valido per la posta elettronica e altri servizi. La scelta spetta all'utente.</span><span class="sxs-lookup"><span data-stu-id="e4041-p114">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="e4041-196">Perché è presente un dominio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="e4041-196">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="e4041-197">Microsoft 365 crea un dominio per l'utente, come *contoso.onmicrosoft.de*, quando si esegue l'iscrizione al servizio.</span><span class="sxs-lookup"><span data-stu-id="e4041-197">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="e4041-198">L'ID utente creato al momento dell'iscrizione include il dominio, ad esempio *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="e4041-198">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="e4041-199">**Se si desidera che la posta elettronica sia simile a *Alan@contoso.de*:** [acquistare il dominio](../get-help-with-domains/buy-a-domain-name.md) oppure seguire la procedura descritta in [aggiungere gli utenti e il dominio a Microsoft 365](add-domain.md) , se lo si possiede già.</span><span class="sxs-lookup"><span data-stu-id="e4041-199">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="e4041-200">**Dopo l'iscrizione, non è possibile rinominare il dominio onmicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="e4041-200">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="e4041-201">Ad esempio, se il dominio iniziale scelto era fourthcoffee.onmicrosoft.de, non è possibile modificarlo in modo che sia fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="e4041-201">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="e4041-202">Per utilizzare un dominio onmicrosoft.de diverso, è necessario avviare un nuovo abbonamento con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4041-202">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="e4041-203">**Non è possibile rinominare l'URL del sito del team.**</span><span class="sxs-lookup"><span data-stu-id="e4041-203">**You can't rename your team site URL.**</span></span> <span data-ttu-id="e4041-204">L'URL del sito del team si basa sul nome di dominio onmicrosoft.de. Purtroppo, a causa del modo in cui funziona l'architettura di SharePoint Online, non è possibile rinominare il sito del team.</span><span class="sxs-lookup"><span data-stu-id="e4041-204">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="e4041-205">**Non è possibile rimuovere il dominio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="e4041-205">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="e4041-206">Microsoft 365 deve conservarlo perché viene utilizzato dietro le quinte per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="e4041-206">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="e4041-207">Non è tuttavia necessario usare personalmente il dominio dopo averne aggiunto uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e4041-207">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="e4041-208">È possibile continuare a utilizzare il dominio onmicrosoft.de iniziale anche dopo aver aggiunto il dominio.</span><span class="sxs-lookup"><span data-stu-id="e4041-208">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="e4041-209">Funziona ancora per la posta elettronica e altri servizi, quindi è una tua scelta.</span><span class="sxs-lookup"><span data-stu-id="e4041-209">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="e4041-210">Come verificare lo stato dell'istruzione o dell'organizzazione no profit</span><span class="sxs-lookup"><span data-stu-id="e4041-210">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="e4041-211">Selezionare **installazione** nell'interfaccia di [Amministrazione](https://docs.microsoft.com/microsoft-365/admin/admin-home) per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="e4041-211">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="e4041-212">(Assicurarsi di accedere a Microsoft 365 per primo).</span><span class="sxs-lookup"><span data-stu-id="e4041-212">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="e4041-213">Per diventare l'amministratore dell'Istituto di istruzione, selezionare l'opzione **diventa amministratore** in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e4041-213">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="e4041-214">Verrà richiesto di aggiungere un record DNS TXT nel sito Web host DNS per il dominio.</span><span class="sxs-lookup"><span data-stu-id="e4041-214">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="e4041-215">Perché?</span><span class="sxs-lookup"><span data-stu-id="e4041-215">Why?</span></span> <span data-ttu-id="e4041-216">Poiché accedendo all'host DNS e aggiungendo un record per il dominio, si dimostra a Microsoft 365 che si è proprietari del nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="e4041-216">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="e4041-217">Dopo aver aggiunto il record, è possibile tornare al portale Microsoft 365 e verificare di averla aggiunta, in modo che Microsoft 365 possa controllare.</span><span class="sxs-lookup"><span data-stu-id="e4041-217">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="e4041-218">Avere un no profit e desidera ottenere Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="e4041-218">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="e4041-219">Verificare [che l'organizzazione sia qualificata](https://www.microsoft.com/en-us/nonprofits/eligibility) e quindi iscriversi al servizio.</span><span class="sxs-lookup"><span data-stu-id="e4041-219">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="e4041-220">Vuoi saperne di più su come diventare l'amministratore per la tua scuola?</span><span class="sxs-lookup"><span data-stu-id="e4041-220">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="e4041-221">Informazioni [su tutto](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="e4041-221">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>