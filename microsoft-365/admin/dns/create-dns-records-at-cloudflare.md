---
title: Creare record DNS in CloudFlare per Microsoft
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
- Adm_NonTOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in CloudFlare per Microsoft.
ms.openlocfilehash: 110bd96c0eecf40ae96efe7055d82a8d12dde607
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657961"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="1787e-103">Creare record DNS in CloudFlare per Microsoft</span><span class="sxs-lookup"><span data-stu-id="1787e-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="1787e-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="1787e-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1787e-105">Se il proprio provider di hosting DNS è CloudFlare, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e così via.</span><span class="sxs-lookup"><span data-stu-id="1787e-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="1787e-106">Dopo aver aggiunto questi record in CloudFlare, il dominio sarà configurato per l'uso con i servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1787e-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="1787e-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1787e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="1787e-110">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="1787e-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="1787e-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="1787e-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1787e-112">È necessario eseguire questa procedura presso il registrar da cui è stato acquistato e registrato il dominio.</span><span class="sxs-lookup"><span data-stu-id="1787e-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="1787e-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span><span class="sxs-lookup"><span data-stu-id="1787e-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="1787e-114">Il dominio aggiunto è stato acquistato da CloudFlare o da un registrar separato.</span><span class="sxs-lookup"><span data-stu-id="1787e-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="1787e-115">Per verificare e creare record DNS per il proprio dominio in Microsoft 365, è necessario prima di tutto cambiare i server dei nomi presso il registrar in modo che utilizzino i nameserver di CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="1787e-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="1787e-116">Per modificare i server dei nomi del dominio presso il registrar, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="1787e-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="1787e-117">Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="1787e-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="1787e-118">Creare due record dei server dei nomi usando i valori della tabella seguente oppure modificare quelli esistenti in modo che corrispondano a questi valori.</span><span class="sxs-lookup"><span data-stu-id="1787e-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="1787e-119">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="1787e-119">First nameserver</span></span>  <br/> |<span data-ttu-id="1787e-120">Usare il valore fornito da CloudFlare per il server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1787e-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="1787e-121">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="1787e-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="1787e-122">Usare il valore fornito da CloudFlare per il server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="1787e-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="1787e-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="1787e-123">You should use at least two name server records.</span></span> <span data-ttu-id="1787e-124">Se sono elencati altri server dei nomi, è necessario eliminarli.</span><span class="sxs-lookup"><span data-stu-id="1787e-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="1787e-125">Salvare le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="1787e-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1787e-126">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="1787e-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="1787e-127">L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="1787e-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="1787e-128">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="1787e-128">Add a TXT record for verification</span></span>
<span data-ttu-id="1787e-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="1787e-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="1787e-p105">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="1787e-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1787e-p106">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="1787e-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="1787e-p107">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1787e-p107">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="1787e-136">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="1787e-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="1787e-137">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="1787e-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="1787e-138">Nella pagina **gestione DNS** fare clic su **Aggiungi record** e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1787e-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="1787e-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1787e-139">**Type**</span></span>|<span data-ttu-id="1787e-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="1787e-140">**Name**</span></span>|<span data-ttu-id="1787e-141">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="1787e-141">**Automatic TTL**</span></span>|<span data-ttu-id="1787e-142">**Content**</span><span class="sxs-lookup"><span data-stu-id="1787e-142">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="1787e-143">TXT</span><span class="sxs-lookup"><span data-stu-id="1787e-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="1787e-144">30 minutes</span><span class="sxs-lookup"><span data-stu-id="1787e-144">30 minutes</span></span>  <br/> |<span data-ttu-id="1787e-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="1787e-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="1787e-146">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="1787e-146">**Note:** This is an example.</span></span> <span data-ttu-id="1787e-147">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="1787e-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="1787e-148">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="1787e-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="1787e-149">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1787e-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="1787e-150">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="1787e-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="1787e-151">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e cercare il record.</span><span class="sxs-lookup"><span data-stu-id="1787e-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="1787e-152">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="1787e-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="1787e-153">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="1787e-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="1787e-154">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="1787e-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="1787e-155">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="1787e-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="1787e-156">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="1787e-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="1787e-p109">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1787e-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="1787e-160">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="1787e-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="1787e-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="1787e-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="1787e-p110">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1787e-p110">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="1787e-164">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="1787e-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="1787e-165">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="1787e-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="1787e-166">Nella pagina **gestione DNS** fare clic su **Aggiungi record** e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1787e-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="1787e-167">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1787e-167">**Type**</span></span>|<span data-ttu-id="1787e-168">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1787e-168">**Name**</span></span>|<span data-ttu-id="1787e-169">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="1787e-169">**Mail server**</span></span>|<span data-ttu-id="1787e-170">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="1787e-170">**Priority**</span></span>|<span data-ttu-id="1787e-171">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1787e-171">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1787e-172">MX</span><span class="sxs-lookup"><span data-stu-id="1787e-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="1787e-173">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1787e-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="1787e-174">**Nota:** Ottenere il proprio  *\<domain-key\>*  account Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1787e-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="1787e-175">Come trovarla</span><span class="sxs-lookup"><span data-stu-id="1787e-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="1787e-176">1 </span><span class="sxs-lookup"><span data-stu-id="1787e-176">1</span></span>  <br/> <span data-ttu-id="1787e-177">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="1787e-177">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/>|<span data-ttu-id="1787e-178">30 minuti</span><span class="sxs-lookup"><span data-stu-id="1787e-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="1787e-179">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1787e-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="1787e-180">Se sono presenti altri record MX nella sezione **MX Records**, eliminarli selezionando l'icona **Elimina (X)**.</span><span class="sxs-lookup"><span data-stu-id="1787e-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="1787e-181">Nella finestra di dialogo di conferma, selezionare **Elimina** per confermare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1787e-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="1787e-182">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="1787e-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="1787e-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="1787e-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="1787e-p112">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1787e-p112">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="1787e-186">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="1787e-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="1787e-187">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="1787e-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="1787e-188">Aggiungere il primo dei cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="1787e-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="1787e-189">Nella pagina **gestione DNS** fare clic su **Aggiungi record** e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1787e-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="1787e-190">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1787e-190">**Type**</span></span>|<span data-ttu-id="1787e-191">**Nome**</span><span class="sxs-lookup"><span data-stu-id="1787e-191">**Name**</span></span>|<span data-ttu-id="1787e-192">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="1787e-192">**Target**</span></span>|<span data-ttu-id="1787e-193">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1787e-193">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1787e-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="1787e-194">CNAME</span></span>  <br/> |<span data-ttu-id="1787e-195">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="1787e-195">autodiscover</span></span>  <br/> |<span data-ttu-id="1787e-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="1787e-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="1787e-197">30 minutes</span><span class="sxs-lookup"><span data-stu-id="1787e-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="1787e-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="1787e-198">CNAME</span></span>  <br/> |<span data-ttu-id="1787e-199">sip</span><span class="sxs-lookup"><span data-stu-id="1787e-199">sip</span></span>  <br/> |<span data-ttu-id="1787e-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1787e-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1787e-201">30 minutes</span><span class="sxs-lookup"><span data-stu-id="1787e-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="1787e-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="1787e-202">CNAME</span></span>  <br/> |<span data-ttu-id="1787e-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="1787e-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="1787e-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1787e-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="1787e-205">30 minutes</span><span class="sxs-lookup"><span data-stu-id="1787e-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="1787e-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="1787e-206">CNAME</span></span>  <br/> |<span data-ttu-id="1787e-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="1787e-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="1787e-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="1787e-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="1787e-209">30 minutes</span><span class="sxs-lookup"><span data-stu-id="1787e-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="1787e-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="1787e-210">CNAME</span></span>  <br/> |<span data-ttu-id="1787e-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="1787e-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="1787e-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="1787e-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="1787e-213">30 minutes</span><span class="sxs-lookup"><span data-stu-id="1787e-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="1787e-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="1787e-214">CNAME</span></span>  <br/> |<span data-ttu-id="1787e-215">msoid</span><span class="sxs-lookup"><span data-stu-id="1787e-215">msoid</span></span>  <br/> |<span data-ttu-id="1787e-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="1787e-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="1787e-217">30 minutes</span><span class="sxs-lookup"><span data-stu-id="1787e-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="1787e-218">Selezionare l'icona del **traffico DNS** (cloud arancione) per ignorare i server CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="1787e-218">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="1787e-219">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1787e-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="1787e-220">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="1787e-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="1787e-221">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="1787e-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="1787e-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="1787e-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1787e-223">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="1787e-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="1787e-224">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="1787e-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="1787e-225">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1787e-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="1787e-226">Al contrario, aggiungere i valori di Microsoft 365 necessari al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="1787e-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="1787e-227">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="1787e-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="1787e-228">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1787e-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="1787e-229">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="1787e-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="1787e-230">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="1787e-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="1787e-231">Nella pagina **gestione DNS** fare clic su **Aggiungi record** e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1787e-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="1787e-232">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1787e-232">**Type**</span></span>|<span data-ttu-id="1787e-233">**Name**</span><span class="sxs-lookup"><span data-stu-id="1787e-233">**Name**</span></span>|<span data-ttu-id="1787e-234">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1787e-234">**TTL**</span></span>|<span data-ttu-id="1787e-235">**Content**</span><span class="sxs-lookup"><span data-stu-id="1787e-235">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1787e-236">TXT</span><span class="sxs-lookup"><span data-stu-id="1787e-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="1787e-237">30 minutes</span><span class="sxs-lookup"><span data-stu-id="1787e-237">30 minutes</span></span>  <br/> |<span data-ttu-id="1787e-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="1787e-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="1787e-239">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="1787e-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="1787e-240">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1787e-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="1787e-241">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="1787e-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="1787e-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="1787e-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="1787e-243">Tenere presente che CloudFlare è responsabile di rendere disponibile questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="1787e-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="1787e-244">Nel caso in cui si vedano discrepanze tra i passaggi seguenti e l'interfaccia utente di CloudFlare (GUI) corrente, utilizzare la [community di CloudFlare](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="1787e-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="1787e-245">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="1787e-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="1787e-246">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="1787e-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="1787e-247">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="1787e-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="1787e-248">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="1787e-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="1787e-249">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="1787e-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="1787e-250">Nella pagina **gestione DNS** fare clic su **Aggiungi record** e quindi selezionare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1787e-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="1787e-251">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1787e-251">**Type**</span></span>|<span data-ttu-id="1787e-252">**Service**</span><span class="sxs-lookup"><span data-stu-id="1787e-252">**Service**</span></span>|<span data-ttu-id="1787e-253">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="1787e-253">**Protocol**</span></span>|<span data-ttu-id="1787e-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="1787e-254">**Name**</span></span>|<span data-ttu-id="1787e-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="1787e-255">**TTL**</span></span>|<span data-ttu-id="1787e-256">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="1787e-256">**Priority**</span></span>|<span data-ttu-id="1787e-257">**Peso**</span><span class="sxs-lookup"><span data-stu-id="1787e-257">**Weight**</span></span>|<span data-ttu-id="1787e-258">**Porta**</span><span class="sxs-lookup"><span data-stu-id="1787e-258">**Port**</span></span>|<span data-ttu-id="1787e-259">**Target**</span><span class="sxs-lookup"><span data-stu-id="1787e-259">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="1787e-260">SRV</span><span class="sxs-lookup"><span data-stu-id="1787e-260">SRV</span></span>|<span data-ttu-id="1787e-261">_sip</span><span class="sxs-lookup"><span data-stu-id="1787e-261">_sip</span></span> |<span data-ttu-id="1787e-262">TLS</span><span class="sxs-lookup"><span data-stu-id="1787e-262">TLS</span></span> |<span data-ttu-id="1787e-263">Utilizzare il *Domain_name*; ad esempio, contoso.com</span><span class="sxs-lookup"><span data-stu-id="1787e-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="1787e-264">30 minuti</span><span class="sxs-lookup"><span data-stu-id="1787e-264">30 minutes</span></span> | <span data-ttu-id="1787e-265">100</span><span class="sxs-lookup"><span data-stu-id="1787e-265">100</span></span>|<span data-ttu-id="1787e-266">1 </span><span class="sxs-lookup"><span data-stu-id="1787e-266">1</span></span> |<span data-ttu-id="1787e-267">443</span><span class="sxs-lookup"><span data-stu-id="1787e-267">443</span></span> |<span data-ttu-id="1787e-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1787e-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="1787e-269">SRV</span><span class="sxs-lookup"><span data-stu-id="1787e-269">SRV</span></span>|<span data-ttu-id="1787e-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="1787e-270">_sipfederationtls</span></span> | <span data-ttu-id="1787e-271">TCP</span><span class="sxs-lookup"><span data-stu-id="1787e-271">TCP</span></span>|<span data-ttu-id="1787e-272">Utilizzare il *Domain_name*; ad esempio, contoso.com</span><span class="sxs-lookup"><span data-stu-id="1787e-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="1787e-273">30 minuti</span><span class="sxs-lookup"><span data-stu-id="1787e-273">30 minutes</span></span> |<span data-ttu-id="1787e-274">100</span><span class="sxs-lookup"><span data-stu-id="1787e-274">100</span></span> |<span data-ttu-id="1787e-275">1 </span><span class="sxs-lookup"><span data-stu-id="1787e-275">1</span></span> |<span data-ttu-id="1787e-276">5061</span><span class="sxs-lookup"><span data-stu-id="1787e-276">5061</span></span> | <span data-ttu-id="1787e-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="1787e-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="1787e-278">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="1787e-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="1787e-279">Aggiungere l'altro record SRV scegliendo i valori della seconda riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="1787e-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="1787e-p117">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="1787e-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
