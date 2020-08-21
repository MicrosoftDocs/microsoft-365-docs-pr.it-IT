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
ms.openlocfilehash: fe602c45059be1b273b7ebe3a11cd91adf89a479
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845845"
---
# <a name="domains-faq"></a><span data-ttu-id="0f212-103">Domande frequenti sui domini</span><span class="sxs-lookup"><span data-stu-id="0f212-103">Domains FAQ</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="0f212-104">L'interfaccia di amministrazione sta cambiando.</span><span class="sxs-lookup"><span data-stu-id="0f212-104">The admin center is changing.</span></span> <span data-ttu-id="0f212-105">Se alcuni dettagli non corrispondono a quelli presentati qui, vedere [Informazioni sulla nuova interfaccia di amministrazione di Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="0f212-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="0f212-106">Questo articolo contiene le risposte alle domande frequenti sui domini in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f212-106">This article contains answers to frequently asked questions about domains in Microsoft 365.</span></span>

<span data-ttu-id="0f212-107">Se non si riesce a trovare una risposta a una domanda, lasciare un commento per segnalare la risposta mancante, che verrà aggiunta all'elenco.</span><span class="sxs-lookup"><span data-stu-id="0f212-107">If you can't find an answer to your question, let us know by leaving a comment and we'll add it to the list.</span></span>

<span data-ttu-id="0f212-108">In questo articolo</span><span class="sxs-lookup"><span data-stu-id="0f212-108">In this article</span></span>

- [<span data-ttu-id="0f212-109">Cos'è la priorità MX?</span><span class="sxs-lookup"><span data-stu-id="0f212-109">What is MX priority?</span></span>](#what-is-mx-priority)
- [<span data-ttu-id="0f212-110">Come si fa a convalidare i record SPF per un dominio?</span><span class="sxs-lookup"><span data-stu-id="0f212-110">How can I validate SPF records for my domain?</span></span>](#how-can-i-validate-spf-records-for-my-domain)
- [<span data-ttu-id="0f212-111">Cos'è un nome di dominio?</span><span class="sxs-lookup"><span data-stu-id="0f212-111">What is a domain name?</span></span>](#what-is-a-domain-name)
- [<span data-ttu-id="0f212-112">Cosa succede se il provider DNS non supporta alcuni tipi di record?</span><span class="sxs-lookup"><span data-stu-id="0f212-112">What happens if my DNS provider doesn't support certain record types?</span></span>](#what-happens-if-my-dns-provider-doesnt-support-certain-record-types)
- [<span data-ttu-id="0f212-113">Come impostare o modificare il dominio predefinito in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0f212-113">How do I set or change the default domain in Microsoft 365?</span></span>](#how-do-i-set-or-change-the-default-domain-in-microsoft-365)
- [<span data-ttu-id="0f212-114">È possibile aggiungere sottodomini personalizzati o più domini a Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0f212-114">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>](#can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365)
- [<span data-ttu-id="0f212-115">Come si trasferisce un dominio da Microsoft 365 a un altro host?</span><span class="sxs-lookup"><span data-stu-id="0f212-115">How do I transfer a domain from Microsoft 365 to another host?</span></span>](#how-do-i-transfer-a-domain-from-microsoft-365-to-another-host)
- [<span data-ttu-id="0f212-116">Perché è presente un dominio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="0f212-116">Why do I have an "onmicrosoft.com" domain?</span></span>](#why-do-i-have-an-onmicrosoftcom-domain)
- [<span data-ttu-id="0f212-117">Perché è presente un dominio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="0f212-117">Why do I have an "onmicrosoft.de" domain?</span></span>](#why-do-i-have-an-onmicrosoftde-domain)
- [<span data-ttu-id="0f212-118">Come verificare lo stato dell'istruzione o dell'organizzazione no profit</span><span class="sxs-lookup"><span data-stu-id="0f212-118">How do I verify my nonprofit or education status?</span></span>](#how-do-i-verify-my-nonprofit-or-education-status)
    
## <a name="what-is-mx-priority"></a><span data-ttu-id="0f212-119">Cos'è la priorità MX?</span><span class="sxs-lookup"><span data-stu-id="0f212-119">What is MX priority?</span></span>

<span data-ttu-id="0f212-120">La posta viene recapitata al server Mail Exchange con il numero di preferenza più basso (priorità più alta), quindi il record MX usato per il routing della posta deve avere il numero di preferenza più basso, in genere 0, o priorità  *Alta*  .</span><span class="sxs-lookup"><span data-stu-id="0f212-120">Mail is delivered to the mail exchange server with the lowest preference number (highest priority), so the MX record you use for mail routing should have the lowest preference number, typically 0 or  *High*  priority.</span></span> 
  
- <span data-ttu-id="0f212-121">Quando si crea un record MX, la maggior parte dei provider di hosting DNS richiede di impostare il numero della preferenza.</span><span class="sxs-lookup"><span data-stu-id="0f212-121">When you create an MX record, most DNS hosting providers require you to set the preference number.</span></span>
    
- <span data-ttu-id="0f212-122">Alcuni provider presentano una casella chiamata  *preferenza*  e altri  *priorità*  .</span><span class="sxs-lookup"><span data-stu-id="0f212-122">Some label the box  *preference*  , and some label it  *priority*  .</span></span> 
    
- <span data-ttu-id="0f212-123">Alcuni richiedono di specificare un numero mentre altri richiedono di selezionare il livello di priorità  *basso*  ,  *medio*  o  *alto*  .</span><span class="sxs-lookup"><span data-stu-id="0f212-123">Some require a number, and some ask you to select  *Low*  ,  *Medium*  , or  *High*  .</span></span> 
    
- <span data-ttu-id="0f212-124">Se è presente un solo record MX, è possibile specificare qualsiasi valore per la priorità o la preferenza.</span><span class="sxs-lookup"><span data-stu-id="0f212-124">If you only have one MX record, any value is fine for priority or preference.</span></span>
    
- <span data-ttu-id="0f212-125">Se sono presenti più record MX, accertarsi che quello usato per il routing della posta abbia una priorità più alta rispetto a quello usato per la conferma della proprietà del dominio.</span><span class="sxs-lookup"><span data-stu-id="0f212-125">If you have more than one, make sure the MX record for mail routing is higher priority than the one used for validating that you own the domain.</span></span>
    
## <a name="how-can-i-validate-spf-records-for-my-domain"></a><span data-ttu-id="0f212-126">Come si fa a convalidare i record SPF per un dominio?</span><span class="sxs-lookup"><span data-stu-id="0f212-126">How can I validate SPF records for my domain?</span></span>

<span data-ttu-id="0f212-127">È importante disporre o creare  **un solo record TXT per SPF**.</span><span class="sxs-lookup"><span data-stu-id="0f212-127">It's important that you have or create  **only one TXT record for SPF**.</span></span> <span data-ttu-id="0f212-128">Se si dispone già di un record SPF, è necessario aggiungere i nuovi valori di Microsoft 365, anziché crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="0f212-128">If you already have an SPF record, you should append the new Microsoft 365 values to it, rather than create a new one.</span></span> <span data-ttu-id="0f212-129">Dopo aver aggiunto o aggiornato il record SPF per il messaggio di posta elettronica Microsoft, è necessario verificare che la sintassi sia corretta con uno di questi strumenti:</span><span class="sxs-lookup"><span data-stu-id="0f212-129">After you've added or updated your SPF record for Microsoft email, you should check to make sure that the syntax is correct with one of these tools:</span></span> 
  
- [<span data-ttu-id="0f212-130">Strumenti di test del record SPF</span><span class="sxs-lookup"><span data-stu-id="0f212-130">SPF Record Testing Tools</span></span>](http://www.kitterman.com/spf/validate.html)
    
- [<span data-ttu-id="0f212-131">SPF Surveyor</span><span class="sxs-lookup"><span data-stu-id="0f212-131">SPF Surveyor</span></span>](https://dmarcian.com/spf-survey/)
    
- [<span data-ttu-id="0f212-132">Interfaccia Web Dig</span><span class="sxs-lookup"><span data-stu-id="0f212-132">Dig web interface</span></span>](http://digwebinterface.com/)

## <a name="what-is-a-domain-name"></a><span data-ttu-id="0f212-133">Cos'è un nome di dominio?</span><span class="sxs-lookup"><span data-stu-id="0f212-133">What is a domain name?</span></span>

<span data-ttu-id="0f212-p103">Un dominio è un nome univoco che segue il segno **@** negli indirizzi di posta elettronica e **www.** negli indirizzi Web. In genere è composto dal nome dell'organizzazione e da un suffisso Internet standard, come  *nomeazienda.com*  o  *nomeuniversità.edu*  .</span><span class="sxs-lookup"><span data-stu-id="0f212-p103">A domain is a unique name that appears after the **@** sign in email addresses, and after **www.** in web addresses. It typically takes the form of your organization's name and a standard Internet suffix, such as  *yourbusiness.com*  or  *stateuniversity.edu.*</span></span> 
  
<span data-ttu-id="0f212-137">L'utilizzo di un dominio personalizzato come "**rob \@ contoso.com**" con Microsoft 365 può contribuire a creare credibilità e riconoscimento per il proprio marchio.</span><span class="sxs-lookup"><span data-stu-id="0f212-137">Using a custom domain like "**rob\@contoso.com**" with Microsoft 365 can help build credibility and recognition for your brand.</span></span> 
  
<span data-ttu-id="0f212-138">È possibile [acquistare un dominio in Microsoft 365 e noi lo configurano automaticamente](../get-help-with-domains/buy-a-domain-name.md)oppure è possibile acquistarne uno o portarlo già da un registrar.</span><span class="sxs-lookup"><span data-stu-id="0f212-138">You can [buy a domain in Microsoft 365 and we'll set it up automatically](../get-help-with-domains/buy-a-domain-name.md), or you can buy or bring one you already own from a domain registrar.</span></span>
    
## <a name="what-happens-if-my-dns-provider-doesnt-support-certain-record-types"></a><span data-ttu-id="0f212-139">Cosa succede se il provider DNS non supporta alcuni tipi di record?</span><span class="sxs-lookup"><span data-stu-id="0f212-139">What happens if my DNS provider doesn't support certain record types?</span></span>

<span data-ttu-id="0f212-140">Se si gestiscono i propri record DNS e l'host DNS non supporta tutti i record DNS necessari per Microsoft 365, alcune funzionalità di Microsoft 365 non funzioneranno.</span><span class="sxs-lookup"><span data-stu-id="0f212-140">If you manage your own DNS records and your DNS host does not support all the DNS records that Microsoft 365 needs, some Microsoft 365 features won't work.</span></span> <span data-ttu-id="0f212-141">È consigliabile trasferire il dominio presso un registrar che supporti tutti i record DNS necessari.</span><span class="sxs-lookup"><span data-stu-id="0f212-141">We recommend that you transfer your domain to a registrar that supports all required DNS records.</span></span>
  
<span data-ttu-id="0f212-142">Provider che supportano tutti i record DNS necessari:</span><span class="sxs-lookup"><span data-stu-id="0f212-142">Providers that support all required DNS records:</span></span>
  
- <span data-ttu-id="0f212-143">Dynadot</span><span class="sxs-lookup"><span data-stu-id="0f212-143">Dynadot</span></span>
    
- <span data-ttu-id="0f212-144">eNomCentral</span><span class="sxs-lookup"><span data-stu-id="0f212-144">eNomCentral</span></span>
    
- <span data-ttu-id="0f212-145">Europe Registry</span><span class="sxs-lookup"><span data-stu-id="0f212-145">Europe Registry</span></span>
    
- <span data-ttu-id="0f212-146">GoDaddy</span><span class="sxs-lookup"><span data-stu-id="0f212-146">GoDaddy</span></span>
    
- <span data-ttu-id="0f212-147">Hover</span><span class="sxs-lookup"><span data-stu-id="0f212-147">Hover</span></span>
    
- <span data-ttu-id="0f212-148">MyHosting.com</span><span class="sxs-lookup"><span data-stu-id="0f212-148">MyHosting.com</span></span>
    
- <span data-ttu-id="0f212-149">Name.com</span><span class="sxs-lookup"><span data-stu-id="0f212-149">Name.com</span></span>
    
- <span data-ttu-id="0f212-150">Nearly Free Speech</span><span class="sxs-lookup"><span data-stu-id="0f212-150">Nearly Free Speech</span></span>
    
- <span data-ttu-id="0f212-151">Nettica</span><span class="sxs-lookup"><span data-stu-id="0f212-151">Nettica</span></span>
    
- <span data-ttu-id="0f212-152">Network Information Center (NIC)</span><span class="sxs-lookup"><span data-stu-id="0f212-152">Network Information Center (NIC)</span></span>
    
- <span data-ttu-id="0f212-153">Network Solutions</span><span class="sxs-lookup"><span data-stu-id="0f212-153">Network Solutions</span></span>
    
- <span data-ttu-id="0f212-154">Register.com</span><span class="sxs-lookup"><span data-stu-id="0f212-154">Register.com</span></span>
  
## <a name="how-do-i-set-or-change-the-default-domain-in-microsoft-365"></a><span data-ttu-id="0f212-155">Come impostare o modificare il dominio predefinito in Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0f212-155">How do I set or change the default domain in Microsoft 365?</span></span>

<span data-ttu-id="0f212-156">È necessario disporre di almeno un dominio personalizzato che è stato aggiunto a Microsoft 365 prima di poter scegliere un dominio predefinito.</span><span class="sxs-lookup"><span data-stu-id="0f212-156">You must have at least one custom domain that you've added to Microsoft 365 before you can choose a default domain.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0f212-157">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="0f212-157">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0f212-158">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="0f212-158">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0f212-159">Nell'interfaccia di amministrazione passare a **Impostazioni** > pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="0f212-159">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
    
2. <span data-ttu-id="0f212-160">Nella pagina **Domains** selezionare il dominio che si desidera impostare come predefinito per i nuovi indirizzi di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="0f212-160">On the **Domains** page, select the domain you want to set as the default for new email addresses.</span></span> 
    
3. <span data-ttu-id="0f212-161">Selezionare **Imposta come predefinito**.</span><span class="sxs-lookup"><span data-stu-id="0f212-161">Select **Set as default**.</span></span>
    
::: moniker range="o365-worldwide"

<span data-ttu-id="0f212-162">Non è possibile modificare il nome del dominio  *.onmicrosoft.com*  iniziale.</span><span class="sxs-lookup"><span data-stu-id="0f212-162">You cannot change the name of your initial  *.onmicrosoft.com*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="0f212-163">Non è possibile modificare il nome del dominio iniziale  *. onmicrosoft.de*  .</span><span class="sxs-lookup"><span data-stu-id="0f212-163">You cannot change the name of your initial  *.onmicrosoft.de*  domain.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="0f212-164">Non è possibile modificare il nome del dominio iniziale  *. partner.onmschina.cn*  .</span><span class="sxs-lookup"><span data-stu-id="0f212-164">You cannot change the name of your initial  *.partner.onmschina.cn*  domain.</span></span> 

::: moniker-end

## <a name="can-i-add-custom-subdomains-or-multiple-domains-to-microsoft-365"></a><span data-ttu-id="0f212-165">È possibile aggiungere sottodomini personalizzati o più domini a Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0f212-165">Can I add custom subdomains or multiple domains to Microsoft 365?</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="0f212-166">Sì.</span><span class="sxs-lookup"><span data-stu-id="0f212-166">Yes.</span></span> <span data-ttu-id="0f212-167">Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="0f212-167">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="0f212-168">Se si desidera consentire a Microsoft di gestire le impostazioni DNS con i record NS o se il dominio è stato acquistato da Microsoft, non è possibile aggiungere sottodomini.</span><span class="sxs-lookup"><span data-stu-id="0f212-168">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="0f212-169">Sì!</span><span class="sxs-lookup"><span data-stu-id="0f212-169">Yes!</span></span> <span data-ttu-id="0f212-170">Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="0f212-170">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="0f212-171">Se si desidera consentire a Microsoft di gestire le impostazioni DNS con i record NS o se il dominio è stato acquistato da Microsoft, non è possibile aggiungere sottodomini.</span><span class="sxs-lookup"><span data-stu-id="0f212-171">If you are letting Microsoft manage your DNS settings with NS records, or if you bought the domain from Microsoft, you can't add subdomains.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="0f212-172">Sì!</span><span class="sxs-lookup"><span data-stu-id="0f212-172">Yes!</span></span> <span data-ttu-id="0f212-173">Per aggiungere sottodomini, è necessario gestire le proprie impostazioni DNS nel sito Web del registrar.</span><span class="sxs-lookup"><span data-stu-id="0f212-173">To add subdomains, you must manage your own DNS settings at your registrar's website.</span></span> <span data-ttu-id="0f212-174">Se si consente a 21Vianet di gestire le impostazioni DNS con i record NS, non è possibile aggiungere sottodomini.</span><span class="sxs-lookup"><span data-stu-id="0f212-174">If you are letting 21Vianet manage your DNS settings with NS records, you can't add subdomains.</span></span>

::: moniker-end

<span data-ttu-id="0f212-175">In genere, è possibile aggiungere fino a 900 domini alla sottoscrizione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f212-175">Typically, you can add up to 900 domains to your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="0f212-176">Ad esempio, è possibile aggiungere i domini contoso.com e contosomarketing.com e quindi i sottodomini www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com e così via.</span><span class="sxs-lookup"><span data-stu-id="0f212-176">For example, you could add the domains contoso.com and contosomarketing.com, and then add the subdomains www.contoso.com, www.partners.contoso.com, www.partners.marketing.contoso.com, and so on.</span></span>
  
<span data-ttu-id="0f212-177">Quando si aggiunge un sottodominio, la verifica viene eseguita automaticamente in base al dominio padre che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="0f212-177">When you add a subdomain, it is automatically verified based on the parent domain that is being verified.</span></span>
  
<span data-ttu-id="0f212-178">Quando si aggiungono più domini a Microsoft 365, è possibile ospitare uno qualsiasi dei servizi (come la posta elettronica) in uno dei domini che sono stati aggiunti.</span><span class="sxs-lookup"><span data-stu-id="0f212-178">When you add multiple domains to Microsoft 365, you can host any of the services (like email) on any of the domains you've added.</span></span>  <span data-ttu-id="0f212-179">*Quando si modifica il messaggio di posta elettronica a Microsoft 365, aggiornando il record MX di un dominio, tutti i messaggi di posta elettronica inviati a tale dominio inizieranno a essere Microsoft 365.*</span><span class="sxs-lookup"><span data-stu-id="0f212-179">*When you change your email to Microsoft 365, by updating a domain's MX record, ALL email sent to that domain will start coming to Microsoft 365.*</span></span> 
 
::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="0f212-180">Se è stato aggiunto un dominio di contoso.com a un abbonamento a Microsoft 365, è possibile aggiungere anche il sottodominio xyz.contoso.com a un'altra organizzazione Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f212-180">If you added a contoso.com domain to a Microsoft 365 subscription, you can also add the subdomain xyz.contoso.com to another Microsoft 365 organization.</span></span> <span data-ttu-id="0f212-181">Quando si aggiunge il sottodominio, viene richiesto di aggiungere un record TXT nel provider di hosting DNS.</span><span class="sxs-lookup"><span data-stu-id="0f212-181">When adding the subdomain, you are prompted to add a TXT record in the DNS hosting provider.</span></span>

## <a name="how-do-i-transfer-a-domain-from-microsoft-365-to-another-host"></a><span data-ttu-id="0f212-182">Come si trasferisce un dominio da Microsoft 365 a un altro host?</span><span class="sxs-lookup"><span data-stu-id="0f212-182">How do I transfer a domain from Microsoft 365 to another host?</span></span>

<span data-ttu-id="0f212-183">Per la procedura per il trasferimento di un dominio, vedere [trasferire un dominio da Microsoft a un altro host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span><span class="sxs-lookup"><span data-stu-id="0f212-183">For the procedure to transfer a domain, see [Transfer a domain from Microsoft to another host](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/transfer-a-domain-from-microsoft-to-another-host).</span></span>

## <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="0f212-184">Pilotare Microsoft 365 dal dominio personalizzato</span><span class="sxs-lookup"><span data-stu-id="0f212-184">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="0f212-185">Per la procedura per pilotare la funzionalità di posta elettronica Microsoft 365 da un dominio personalizzato a una cassetta postale di Microsoft 365, vedere [Pilot microsoft 365 from My Custom Domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span><span class="sxs-lookup"><span data-stu-id="0f212-185">For the procedure to pilot Microsoft 365 email functionality from a custom domain to a Microsoft 365 mailbox, see [Pilot Microsoft 365 from my custom domain](https://docs.microsoft.com/microsoft-365/admin/misc/pilot-microsoft-365-from-my-custom-domain).</span></span>

## <a name="why-do-i-have-an-onmicrosoftcom-domain"></a><span data-ttu-id="0f212-186">Perché è presente un dominio "onmicrosoft.com"?</span><span class="sxs-lookup"><span data-stu-id="0f212-186">Why do I have an "onmicrosoft.com" domain?</span></span>

<span data-ttu-id="0f212-187">Microsoft 365 crea un dominio per l'utente, come *contoso.onmicrosoft.com*, quando si esegue l'iscrizione al servizio.</span><span class="sxs-lookup"><span data-stu-id="0f212-187">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.com*, when you sign up with the service.</span></span> <span data-ttu-id="0f212-188">L'ID utente creato al momento dell'iscrizione include il dominio, ad esempio *Alan@contoso.onmicrosoft.com*.</span><span class="sxs-lookup"><span data-stu-id="0f212-188">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.com*.</span></span> 
  
 <span data-ttu-id="0f212-189">**Se si desidera che la posta elettronica sia simile a *Alan \@ contoso.com*:** [acquistare il dominio](../get-help-with-domains/buy-a-domain-name.md) oppure seguire la procedura descritta in [aggiungere gli utenti e il dominio a Microsoft 365](add-domain.md) , se lo si possiede già.</span><span class="sxs-lookup"><span data-stu-id="0f212-189">**If you want to have your email look like *alan\@contoso.com*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="0f212-190">**Dopo l'iscrizione, non è possibile rinominare il dominio onmicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="0f212-190">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="0f212-191">Se ad esempio il dominio iniziale scelto è fourthcoffee.onmicrosoft.com, non lo si può cambiare in fabrikam.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="0f212-191">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.com, you can't change it to be fabrikam.onmicrosoft.com.</span></span> <span data-ttu-id="0f212-192">Per utilizzare un dominio onmicrosoft.com diverso, è necessario avviare un nuovo abbonamento con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f212-192">To use a different onmicrosoft.com domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="0f212-193">**Non è possibile rinominare l'URL del sito del team.**</span><span class="sxs-lookup"><span data-stu-id="0f212-193">**You can't rename your team site URL.**</span></span> <span data-ttu-id="0f212-194">L'URL del sito del team si basa sul nome di dominio onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="0f212-194">Your team site URL is based on your onmicrosoft.com domain name.</span></span> <span data-ttu-id="0f212-195">Purtroppo, a causa del modo in cui funziona l'architettura di SharePoint Online, non è possibile rinominare il sito del team.</span><span class="sxs-lookup"><span data-stu-id="0f212-195">Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="0f212-196">**Non è possibile rimuovere il dominio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="0f212-196">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="0f212-197">Microsoft 365 deve conservarlo perché viene utilizzato dietro le quinte per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="0f212-197">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="0f212-198">Non è tuttavia necessario usare personalmente il dominio dopo averne aggiunto uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0f212-198">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="0f212-p114">Si può continuare a usare il dominio iniziale onmicrosoft.com anche dopo l'aggiunta di quello personalizzato. È infatti sempre valido per la posta elettronica e altri servizi. La scelta spetta all'utente.</span><span class="sxs-lookup"><span data-stu-id="0f212-p114">You can keep using the initial onmicrosoft.com domain even after you add your domain. It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"
## <a name="why-do-i-have-an-onmicrosoftde-domain"></a><span data-ttu-id="0f212-201">Perché è presente un dominio "onmicrosoft.de"?</span><span class="sxs-lookup"><span data-stu-id="0f212-201">Why do I have an "onmicrosoft.de" domain?</span></span>

<span data-ttu-id="0f212-202">Microsoft 365 crea un dominio per l'utente, come *contoso.onmicrosoft.de*, quando si esegue l'iscrizione al servizio.</span><span class="sxs-lookup"><span data-stu-id="0f212-202">Microsoft 365 creates a domain for you, like *contoso.onmicrosoft.de*, when you sign up with the service.</span></span> <span data-ttu-id="0f212-203">L'ID utente creato al momento dell'iscrizione include il dominio, ad esempio *Alan@contoso.onmicrosoft.de*.</span><span class="sxs-lookup"><span data-stu-id="0f212-203">The user ID that you create when you sign up includes the domain, like *alan@contoso.onmicrosoft.de*.</span></span> 
  
 <span data-ttu-id="0f212-204">**Se si desidera che la posta elettronica sia simile a *Alan@contoso.de*:** [acquistare il dominio](../get-help-with-domains/buy-a-domain-name.md) oppure seguire la procedura descritta in [aggiungere gli utenti e il dominio a Microsoft 365](add-domain.md) , se lo si possiede già.</span><span class="sxs-lookup"><span data-stu-id="0f212-204">**If you want to have your email look like *alan@contoso.de*:** [buy the domain](../get-help-with-domains/buy-a-domain-name.md) or just follow the steps in [Add your users and domain to Microsoft 365](add-domain.md) if you own it already.</span></span> 
  
- <span data-ttu-id="0f212-205">**Dopo l'iscrizione, non è possibile rinominare il dominio onmicrosoft**.</span><span class="sxs-lookup"><span data-stu-id="0f212-205">**You can't rename the onmicrosoft domain after sign-up.**</span></span> <span data-ttu-id="0f212-206">Ad esempio, se il dominio iniziale scelto era fourthcoffee.onmicrosoft.de, non è possibile modificarlo in modo che sia fabrikam.onmicrosoft.de.</span><span class="sxs-lookup"><span data-stu-id="0f212-206">For example, if the initial domain you chose was fourthcoffee.onmicrosoft.de, you can't change it to be fabrikam.onmicrosoft.de.</span></span> <span data-ttu-id="0f212-207">Per utilizzare un dominio onmicrosoft.de diverso, è necessario avviare un nuovo abbonamento con Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f212-207">To use a different onmicrosoft.de domain, you'd have to start a new subscription with Microsoft 365.</span></span> 
    
- <span data-ttu-id="0f212-208">**Non è possibile rinominare l'URL del sito del team.**</span><span class="sxs-lookup"><span data-stu-id="0f212-208">**You can't rename your team site URL.**</span></span> <span data-ttu-id="0f212-209">L'URL del sito del team si basa sul nome di dominio onmicrosoft.de. Purtroppo, a causa del modo in cui funziona l'architettura di SharePoint Online, non è possibile rinominare il sito del team.</span><span class="sxs-lookup"><span data-stu-id="0f212-209">Your team site URL is based on your onmicrosoft.de domain name.Unfortunately, because of the way SharePoint Online architecture works, you can't rename the team site.</span></span> 
    
- <span data-ttu-id="0f212-210">**Non è possibile rimuovere il dominio onmicrosoft.**</span><span class="sxs-lookup"><span data-stu-id="0f212-210">**You can't remove your onmicrosoft domain.**</span></span> <span data-ttu-id="0f212-211">Microsoft 365 deve conservarlo perché viene utilizzato dietro le quinte per l'abbonamento.</span><span class="sxs-lookup"><span data-stu-id="0f212-211">Microsoft 365 needs to keep it around because it's used behind the scenes for your subscription.</span></span> <span data-ttu-id="0f212-212">Non è tuttavia necessario usare personalmente il dominio dopo averne aggiunto uno personalizzato.</span><span class="sxs-lookup"><span data-stu-id="0f212-212">But you don't have to use the domain yourself after you've added a custom domain.</span></span> 
    
<span data-ttu-id="0f212-213">È possibile continuare a utilizzare il dominio onmicrosoft.de iniziale anche dopo aver aggiunto il dominio.</span><span class="sxs-lookup"><span data-stu-id="0f212-213">You can keep using the initial onmicrosoft.de domain even after you add your domain.</span></span> <span data-ttu-id="0f212-214">Funziona ancora per la posta elettronica e altri servizi, quindi è una tua scelta.</span><span class="sxs-lookup"><span data-stu-id="0f212-214">It still works for email and other services, so it's your choice.</span></span>
  
::: moniker-end

## <a name="how-do-i-verify-my-nonprofit-or-education-status"></a><span data-ttu-id="0f212-215">Come verificare lo stato dell'istruzione o dell'organizzazione no profit</span><span class="sxs-lookup"><span data-stu-id="0f212-215">How do I verify my nonprofit or education status?</span></span>

1. <span data-ttu-id="0f212-216">Selezionare **installazione** nell'interfaccia di [Amministrazione](https://docs.microsoft.com/microsoft-365/admin/admin-home) per avviare la procedura guidata.</span><span class="sxs-lookup"><span data-stu-id="0f212-216">Select **Setup** in the [admin center](https://docs.microsoft.com/microsoft-365/admin/admin-home) to start the wizard.</span></span> <span data-ttu-id="0f212-217">(Assicurarsi di accedere a Microsoft 365 per primo).</span><span class="sxs-lookup"><span data-stu-id="0f212-217">(Be sure to sign in to Microsoft 365 first.)</span></span> 
    
2. <span data-ttu-id="0f212-218">Per diventare l'amministratore dell'Istituto di istruzione, selezionare l'opzione  **diventa amministratore** in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="0f212-218">To become the admin for your school, select the  **Become an admin** option in Microsoft 365.</span></span> 
    
3. <span data-ttu-id="0f212-219">Verrà richiesto di aggiungere un record DNS TXT nel sito Web host DNS per il dominio.</span><span class="sxs-lookup"><span data-stu-id="0f212-219">You'll be prompted to add a TXT DNS record at the DNS host website for your domain.</span></span> <span data-ttu-id="0f212-220">Perché?</span><span class="sxs-lookup"><span data-stu-id="0f212-220">Why?</span></span> <span data-ttu-id="0f212-221">Poiché accedendo all'host DNS e aggiungendo un record per il dominio, si dimostra a Microsoft 365 che si è proprietari del nome di dominio.</span><span class="sxs-lookup"><span data-stu-id="0f212-221">Because by signing in at the DNS host and adding a record for your domain, you prove to Microsoft 365 that you own the domain name.</span></span>
    
4. <span data-ttu-id="0f212-222">Dopo aver aggiunto il record, è possibile tornare al portale Microsoft 365 e verificare di averla aggiunta, in modo che Microsoft 365 possa controllare.</span><span class="sxs-lookup"><span data-stu-id="0f212-222">After you add the record, you'll go back to the Microsoft 365 portal and confirm that you've added it, so Microsoft 365 can check.</span></span>
    
<span data-ttu-id="0f212-223">Avere un no profit e desidera ottenere Microsoft 365?</span><span class="sxs-lookup"><span data-stu-id="0f212-223">Have a nonprofit and want to get Microsoft 365?</span></span> <span data-ttu-id="0f212-224">Verificare [che l'organizzazione sia qualificata](https://www.microsoft.com/en-us/nonprofits/eligibility) e quindi iscriversi al servizio.</span><span class="sxs-lookup"><span data-stu-id="0f212-224">[Make sure your organization qualifies](https://www.microsoft.com/en-us/nonprofits/eligibility) and then sign up for the service.</span></span> 
  
<span data-ttu-id="0f212-225">Vuoi saperne di più su come diventare l'amministratore per la tua scuola?</span><span class="sxs-lookup"><span data-stu-id="0f212-225">Want to know more about becoming the admin for your school?</span></span> <span data-ttu-id="0f212-226">Informazioni [su tutto](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span><span class="sxs-lookup"><span data-stu-id="0f212-226">[Learn all about it](https://docs.microsoft.com/microsoft-365/education/deploy/becoming-an-admin-in-office-365-education
).</span></span>