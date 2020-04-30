---
title: Creare record DNS in CloudFlare per Microsoft
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
- Adm_NonTOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 84acd4fc-6eec-4d00-8bed-568f036ae2af
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in CloudFlare per Microsoft.
ms.openlocfilehash: 116132d096db61e7004315dcf159fc78dd790d43
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939320"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="96ef1-103">Creare record DNS in CloudFlare per Microsoft</span><span class="sxs-lookup"><span data-stu-id="96ef1-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="96ef1-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="96ef1-105">Se il proprio provider di hosting DNS è CloudFlare, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e così via.</span><span class="sxs-lookup"><span data-stu-id="96ef1-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="96ef1-106">Dopo aver aggiunto questi record in CloudFlare, il dominio sarà configurato per l'uso con i servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96ef1-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
  
> [!NOTE]
>  <span data-ttu-id="96ef1-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="96ef1-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="96ef1-110">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="96ef1-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="96ef1-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="96ef1-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="96ef1-112">È necessario eseguire questa procedura presso il registrar da cui è stato acquistato e registrato il dominio.</span><span class="sxs-lookup"><span data-stu-id="96ef1-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="96ef1-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span><span class="sxs-lookup"><span data-stu-id="96ef1-113">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="96ef1-114">Il dominio aggiunto è stato acquistato da CloudFlare o da un registrar separato.</span><span class="sxs-lookup"><span data-stu-id="96ef1-114">The domain that you added was purchased from Cloudflare or a separate domain registrar.</span></span> <span data-ttu-id="96ef1-115">Per verificare e creare record DNS per il proprio dominio in Microsoft 365, è necessario prima di tutto cambiare i server dei nomi presso il registrar in modo che utilizzino i nameserver di CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="96ef1-115">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="96ef1-116">Per modificare i server dei nomi del dominio presso il registrar, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="96ef1-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="96ef1-117">Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="96ef1-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="96ef1-118">Creare due record dei server dei nomi usando i valori della tabella seguente oppure modificare quelli esistenti in modo che corrispondano a questi valori.</span><span class="sxs-lookup"><span data-stu-id="96ef1-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="96ef1-119">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="96ef1-119">First nameserver</span></span>  <br/> |<span data-ttu-id="96ef1-120">Usare il valore fornito da CloudFlare per il server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="96ef1-120">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="96ef1-121">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="96ef1-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="96ef1-122">Usare il valore fornito da CloudFlare per il server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="96ef1-122">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="96ef1-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="96ef1-123">You should use at least two name server records.</span></span> <span data-ttu-id="96ef1-124">Se sono elencati altri server dei nomi, è necessario eliminarli.</span><span class="sxs-lookup"><span data-stu-id="96ef1-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="96ef1-125">Salvare le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="96ef1-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="96ef1-126">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="96ef1-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="96ef1-127">L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="96ef1-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="96ef1-128">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="96ef1-128">Add a TXT record for verification</span></span>
<span data-ttu-id="96ef1-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="96ef1-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="96ef1-p105">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="96ef1-p105">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="96ef1-p106">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="96ef1-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="96ef1-p107">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="96ef1-p107">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="96ef1-136">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="96ef1-136">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="96ef1-137">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-137">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="96ef1-138">Nella pagina **gestione DNS** fare clic su **Aggiungi record**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="96ef1-138">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="96ef1-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="96ef1-139">**Type**</span></span>|<span data-ttu-id="96ef1-140">**Name**</span><span class="sxs-lookup"><span data-stu-id="96ef1-140">**Name**</span></span>|<span data-ttu-id="96ef1-141">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="96ef1-141">**Automatic TTL**</span></span>|<span data-ttu-id="96ef1-142">**Content**</span><span class="sxs-lookup"><span data-stu-id="96ef1-142">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="96ef1-143">TXT</span><span class="sxs-lookup"><span data-stu-id="96ef1-143">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="96ef1-144">30 minuti</span><span class="sxs-lookup"><span data-stu-id="96ef1-144">30 minutes</span></span>  <br/> |<span data-ttu-id="96ef1-145">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="96ef1-145">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="96ef1-146">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="96ef1-146">**Note:** This is an example.</span></span> <span data-ttu-id="96ef1-147">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="96ef1-147">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="96ef1-148">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="96ef1-148">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="96ef1-149">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-149">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="96ef1-150">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="96ef1-150">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="96ef1-151">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e cercare il record.</span><span class="sxs-lookup"><span data-stu-id="96ef1-151">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="96ef1-152">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="96ef1-152">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="96ef1-153">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="96ef1-153">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="96ef1-154">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="96ef1-154">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="96ef1-155">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-155">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="96ef1-156">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-156">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="96ef1-p109">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="96ef1-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="96ef1-160">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="96ef1-160">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="96ef1-161"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="96ef1-161"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="96ef1-162">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="96ef1-162">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="96ef1-163">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="96ef1-163">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="96ef1-164">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="96ef1-164">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="96ef1-165">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-165">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="96ef1-166">Nella pagina **gestione DNS** fare clic su **Aggiungi record**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="96ef1-166">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="96ef1-167">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="96ef1-167">**Type**</span></span>|<span data-ttu-id="96ef1-168">**Nome**</span><span class="sxs-lookup"><span data-stu-id="96ef1-168">**Name**</span></span>|<span data-ttu-id="96ef1-169">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="96ef1-169">**Mail server**</span></span>|<span data-ttu-id="96ef1-170">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="96ef1-170">**Priority**</span></span>|<span data-ttu-id="96ef1-171">**TTL**</span><span class="sxs-lookup"><span data-stu-id="96ef1-171">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="96ef1-172">MX</span><span class="sxs-lookup"><span data-stu-id="96ef1-172">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="96ef1-173">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="96ef1-173">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="96ef1-174">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96ef1-174">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="96ef1-175">Come trovarla</span><span class="sxs-lookup"><span data-stu-id="96ef1-175">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="96ef1-176">1</span><span class="sxs-lookup"><span data-stu-id="96ef1-176">1</span></span>  <br/> <span data-ttu-id="96ef1-177">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="96ef1-177">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="96ef1-178">30 minuti</span><span class="sxs-lookup"><span data-stu-id="96ef1-178">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="96ef1-179">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-179">Select **Save**.</span></span>
  
9. <span data-ttu-id="96ef1-180">Se sono presenti altri record MX nella sezione **MX Records**, eliminarli selezionando l'icona **Elimina (X)**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-180">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="96ef1-181">Nella finestra di dialogo di conferma, selezionare **Elimina** per confermare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="96ef1-181">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="96ef1-182">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="96ef1-182">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="96ef1-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="96ef1-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="96ef1-184">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="96ef1-184">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="96ef1-185">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="96ef1-185">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="96ef1-186">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="96ef1-186">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="96ef1-187">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-187">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="96ef1-188">Aggiungere il primo dei cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="96ef1-188">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="96ef1-189">Nella pagina **gestione DNS** fare clic su **Aggiungi record**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="96ef1-189">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="96ef1-190">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="96ef1-190">**Type**</span></span>|<span data-ttu-id="96ef1-191">**Nome**</span><span class="sxs-lookup"><span data-stu-id="96ef1-191">**Name**</span></span>|<span data-ttu-id="96ef1-192">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="96ef1-192">**Target**</span></span>|<span data-ttu-id="96ef1-193">**TTL**</span><span class="sxs-lookup"><span data-stu-id="96ef1-193">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="96ef1-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="96ef1-194">CNAME</span></span>  <br/> |<span data-ttu-id="96ef1-195">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="96ef1-195">autodiscover</span></span>  <br/> |<span data-ttu-id="96ef1-196">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="96ef1-196">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="96ef1-197">30 minutes</span><span class="sxs-lookup"><span data-stu-id="96ef1-197">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="96ef1-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="96ef1-198">CNAME</span></span>  <br/> |<span data-ttu-id="96ef1-199">sip</span><span class="sxs-lookup"><span data-stu-id="96ef1-199">sip</span></span>  <br/> |<span data-ttu-id="96ef1-200">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="96ef1-200">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="96ef1-201">30 minutes</span><span class="sxs-lookup"><span data-stu-id="96ef1-201">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="96ef1-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="96ef1-202">CNAME</span></span>  <br/> |<span data-ttu-id="96ef1-203">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="96ef1-203">lyncdiscover</span></span>  <br/> |<span data-ttu-id="96ef1-204">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="96ef1-204">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="96ef1-205">30 minutes</span><span class="sxs-lookup"><span data-stu-id="96ef1-205">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="96ef1-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="96ef1-206">CNAME</span></span>  <br/> |<span data-ttu-id="96ef1-207">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="96ef1-207">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="96ef1-208">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="96ef1-208">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="96ef1-209">30 minutes</span><span class="sxs-lookup"><span data-stu-id="96ef1-209">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="96ef1-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="96ef1-210">CNAME</span></span>  <br/> |<span data-ttu-id="96ef1-211">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="96ef1-211">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="96ef1-212">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="96ef1-212">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="96ef1-213">30 minutes</span><span class="sxs-lookup"><span data-stu-id="96ef1-213">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="96ef1-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="96ef1-214">CNAME</span></span>  <br/> |<span data-ttu-id="96ef1-215">msoid</span><span class="sxs-lookup"><span data-stu-id="96ef1-215">msoid</span></span>  <br/> |<span data-ttu-id="96ef1-216">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="96ef1-216">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="96ef1-217">30 minutes</span><span class="sxs-lookup"><span data-stu-id="96ef1-217">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="96ef1-218">Selezionare l'icona del **traffico DNS** (cloud arancione) per ignorare i server CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="96ef1-218">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="96ef1-219">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-219">Select **Save**.</span></span>
  
7. <span data-ttu-id="96ef1-220">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="96ef1-220">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="96ef1-221">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="96ef1-221">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="96ef1-222"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="96ef1-222"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="96ef1-223">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="96ef1-223">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="96ef1-224">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="96ef1-224">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="96ef1-225">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="96ef1-225">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="96ef1-226">Al contrario, aggiungere i valori di Microsoft 365 necessari al record corrente in modo da ottenere un *unico* record SPF che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="96ef1-226">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="96ef1-227">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="96ef1-227">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="96ef1-228">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="96ef1-228">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="96ef1-229">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="96ef1-229">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="96ef1-230">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-230">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="96ef1-231">Nella pagina **gestione DNS** fare clic su **Aggiungi record**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="96ef1-231">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="96ef1-232">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="96ef1-232">**Type**</span></span>|<span data-ttu-id="96ef1-233">**Nome**</span><span class="sxs-lookup"><span data-stu-id="96ef1-233">**Name**</span></span>|<span data-ttu-id="96ef1-234">**TTL**</span><span class="sxs-lookup"><span data-stu-id="96ef1-234">**TTL**</span></span>|<span data-ttu-id="96ef1-235">**Content**</span><span class="sxs-lookup"><span data-stu-id="96ef1-235">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="96ef1-236">TXT</span><span class="sxs-lookup"><span data-stu-id="96ef1-236">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="96ef1-237">30 minuti</span><span class="sxs-lookup"><span data-stu-id="96ef1-237">30 minutes</span></span>  <br/> |<span data-ttu-id="96ef1-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="96ef1-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="96ef1-239">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="96ef1-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="96ef1-240">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-240">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="96ef1-241">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="96ef1-241">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="96ef1-242"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="96ef1-242"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="96ef1-243">Tenere presente che CloudFlare è responsabile di rendere disponibile questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="96ef1-243">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="96ef1-244">Nel caso in cui si vedano discrepanze tra i passaggi seguenti e l'interfaccia utente di CloudFlare (GUI) corrente, utilizzare la [community di CloudFlare](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="96ef1-244">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="96ef1-245">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="96ef1-245">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="96ef1-246">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="96ef1-246">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="96ef1-247">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="96ef1-247">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="96ef1-248">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-248">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="96ef1-249">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="96ef1-249">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="96ef1-250">Nella pagina **gestione DNS** fare clic su **Aggiungi record**e quindi selezionare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="96ef1-250">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="96ef1-251">**Type**</span><span class="sxs-lookup"><span data-stu-id="96ef1-251">**Type**</span></span>|<span data-ttu-id="96ef1-252">**Service**</span><span class="sxs-lookup"><span data-stu-id="96ef1-252">**Service**</span></span>|<span data-ttu-id="96ef1-253">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="96ef1-253">**Protocol**</span></span>|<span data-ttu-id="96ef1-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="96ef1-254">**Name**</span></span>|<span data-ttu-id="96ef1-255">**TTL**</span><span class="sxs-lookup"><span data-stu-id="96ef1-255">**TTL**</span></span>|<span data-ttu-id="96ef1-256">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="96ef1-256">**Priority**</span></span>|<span data-ttu-id="96ef1-257">**Peso**</span><span class="sxs-lookup"><span data-stu-id="96ef1-257">**Weight**</span></span>|<span data-ttu-id="96ef1-258">**Porta**</span><span class="sxs-lookup"><span data-stu-id="96ef1-258">**Port**</span></span>|<span data-ttu-id="96ef1-259">**Target**</span><span class="sxs-lookup"><span data-stu-id="96ef1-259">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="96ef1-260">SRV</span><span class="sxs-lookup"><span data-stu-id="96ef1-260">SRV</span></span>|<span data-ttu-id="96ef1-261">_sip</span><span class="sxs-lookup"><span data-stu-id="96ef1-261">_sip</span></span> |<span data-ttu-id="96ef1-262">TLS</span><span class="sxs-lookup"><span data-stu-id="96ef1-262">TLS</span></span> |<span data-ttu-id="96ef1-263">Utilizzare il *Domain_name*; ad esempio, contoso.com</span><span class="sxs-lookup"><span data-stu-id="96ef1-263">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="96ef1-264">30 minuti</span><span class="sxs-lookup"><span data-stu-id="96ef1-264">30 minutes</span></span> | <span data-ttu-id="96ef1-265">100</span><span class="sxs-lookup"><span data-stu-id="96ef1-265">100</span></span>|<span data-ttu-id="96ef1-266">1</span><span class="sxs-lookup"><span data-stu-id="96ef1-266">1</span></span> |<span data-ttu-id="96ef1-267">443</span><span class="sxs-lookup"><span data-stu-id="96ef1-267">443</span></span> |<span data-ttu-id="96ef1-268">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="96ef1-268">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="96ef1-269">SRV</span><span class="sxs-lookup"><span data-stu-id="96ef1-269">SRV</span></span>|<span data-ttu-id="96ef1-270">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="96ef1-270">_sipfederationtls</span></span> | <span data-ttu-id="96ef1-271">TCP</span><span class="sxs-lookup"><span data-stu-id="96ef1-271">TCP</span></span>|<span data-ttu-id="96ef1-272">Utilizzare il *Domain_name*; ad esempio, contoso.com</span><span class="sxs-lookup"><span data-stu-id="96ef1-272">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="96ef1-273">30 minuti</span><span class="sxs-lookup"><span data-stu-id="96ef1-273">30 minutes</span></span> |<span data-ttu-id="96ef1-274">100</span><span class="sxs-lookup"><span data-stu-id="96ef1-274">100</span></span> |<span data-ttu-id="96ef1-275">1</span><span class="sxs-lookup"><span data-stu-id="96ef1-275">1</span></span> |<span data-ttu-id="96ef1-276">5061</span><span class="sxs-lookup"><span data-stu-id="96ef1-276">5061</span></span> | <span data-ttu-id="96ef1-277">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="96ef1-277">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="96ef1-278">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="96ef1-278">Select **Save**.</span></span>

  
6. <span data-ttu-id="96ef1-279">Aggiungere l'altro record SRV scegliendo i valori della seconda riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="96ef1-279">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="96ef1-p117">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="96ef1-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
