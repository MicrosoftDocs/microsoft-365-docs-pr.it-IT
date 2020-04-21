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
ms.openlocfilehash: f04e4b4a29085a3ddd9b388c7178c1cd638445ea
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629708"
---
# <a name="create-dns-records-at-cloudflare-for-microsoft"></a><span data-ttu-id="02b36-103">Creare record DNS in CloudFlare per Microsoft</span><span class="sxs-lookup"><span data-stu-id="02b36-103">Create DNS records at Cloudflare for Microsoft</span></span>

 <span data-ttu-id="02b36-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="02b36-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="02b36-105">Se il proprio provider di hosting DNS è CloudFlare, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e così via.</span><span class="sxs-lookup"><span data-stu-id="02b36-105">If Cloudflare is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="02b36-106">Dopo aver aggiunto questi record in CloudFlare, il dominio sarà configurato per l'uso con i servizi Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02b36-106">After you add these records at Cloudflare, your domain will be set up to work with Microsoft 365 services.</span></span>
  
<span data-ttu-id="02b36-107">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="02b36-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="02b36-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="02b36-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="02b36-111">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="02b36-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="02b36-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="02b36-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="02b36-113">È necessario eseguire questa procedura presso il registrar da cui è stato acquistato e registrato il dominio.</span><span class="sxs-lookup"><span data-stu-id="02b36-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="02b36-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span><span class="sxs-lookup"><span data-stu-id="02b36-114">When you signed up for Cloudflare, you added a domain by using the Cloudflare **Setup** process.</span></span> 
  
<span data-ttu-id="02b36-115">Il dominio aggiunto è stato acquistato da un registrar distinto, perché CloudFlare non offre servizi di registrazione di domini.</span><span class="sxs-lookup"><span data-stu-id="02b36-115">The domain that you added was purchased from a separate domain registrar; Cloudflare does not offer domain registration services.</span></span> <span data-ttu-id="02b36-116">Per verificare e creare record DNS per il proprio dominio in Microsoft 365, è necessario prima di tutto cambiare i server dei nomi presso il registrar in modo che utilizzino i nameserver di CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="02b36-116">To verify and create DNS records for your domain in Microsoft 365, you first need to change the nameservers at your domain registrar so that they use Cloudflare's nameservers.</span></span>
  
<span data-ttu-id="02b36-117">Per modificare i server dei nomi del dominio presso il registrar, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="02b36-117">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="02b36-118">Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="02b36-118">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="02b36-119">Creare due record dei server dei nomi usando i valori della tabella seguente oppure modificare quelli esistenti in modo che corrispondano a questi valori.</span><span class="sxs-lookup"><span data-stu-id="02b36-119">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="02b36-120">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="02b36-120">First nameserver</span></span>  <br/> |<span data-ttu-id="02b36-121">Usare il valore fornito da CloudFlare per il server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="02b36-121">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
    |<span data-ttu-id="02b36-122">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="02b36-122">Second nameserver</span></span>  <br/> |<span data-ttu-id="02b36-123">Usare il valore fornito da CloudFlare per il server dei nomi.</span><span class="sxs-lookup"><span data-stu-id="02b36-123">Use the nameserver value provided by Cloudflare.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="02b36-124">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="02b36-124">You should use at least two name server records.</span></span> <span data-ttu-id="02b36-125">Se sono elencati altri server dei nomi, è necessario eliminarli.</span><span class="sxs-lookup"><span data-stu-id="02b36-125">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="02b36-126">Salvare le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="02b36-126">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="02b36-127">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="02b36-127">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="02b36-128">L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="02b36-128">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="02b36-129">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="02b36-129">Add a TXT record for verification</span></span>
<span data-ttu-id="02b36-130"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="02b36-130"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="02b36-131">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="02b36-131">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="02b36-132">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="02b36-132">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="02b36-p106">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="02b36-p106">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="02b36-p107">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="02b36-p107">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login). You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="02b36-137">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="02b36-137">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="02b36-138">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="02b36-138">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="02b36-139">Nella pagina **gestione DNS** fare clic su **Aggiungi record**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="02b36-139">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="02b36-140">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="02b36-140">**Type**</span></span>|<span data-ttu-id="02b36-141">**Name**</span><span class="sxs-lookup"><span data-stu-id="02b36-141">**Name**</span></span>|<span data-ttu-id="02b36-142">**Automatic TTL**</span><span class="sxs-lookup"><span data-stu-id="02b36-142">**Automatic TTL**</span></span>|<span data-ttu-id="02b36-143">**Content**</span><span class="sxs-lookup"><span data-stu-id="02b36-143">**Content**</span></span>|
    |:-----|:-----|:-----|:----|
    |<span data-ttu-id="02b36-144">TXT</span><span class="sxs-lookup"><span data-stu-id="02b36-144">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="02b36-145">30 minuti</span><span class="sxs-lookup"><span data-stu-id="02b36-145">30 minutes</span></span>  <br/> |<span data-ttu-id="02b36-146">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="02b36-146">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="02b36-147">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="02b36-147">**Note:** This is an example.</span></span> <span data-ttu-id="02b36-148">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="02b36-148">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="02b36-149">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="02b36-149">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="02b36-150">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="02b36-150">Select **Save**.</span></span>
  
  
9. <span data-ttu-id="02b36-151">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="02b36-151">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="02b36-152">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e cercare il record.</span><span class="sxs-lookup"><span data-stu-id="02b36-152">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and search for the record.</span></span>
  
<span data-ttu-id="02b36-153">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="02b36-153">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="02b36-154">Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .</span><span class="sxs-lookup"><span data-stu-id="02b36-154">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="02b36-155">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="02b36-155">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="02b36-156">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="02b36-156">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="02b36-157">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="02b36-157">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="02b36-p109">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="02b36-p109">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="02b36-161">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="02b36-161">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="02b36-162"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="02b36-162"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="02b36-163">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="02b36-163">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="02b36-164">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="02b36-164">You'll be prompted to log in first.</span></span>
  
2. <span data-ttu-id="02b36-165">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="02b36-165">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="02b36-166">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="02b36-166">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="02b36-167">Nella pagina **gestione DNS** fare clic su **Aggiungi record**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="02b36-167">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="02b36-168">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="02b36-168">**Type**</span></span>|<span data-ttu-id="02b36-169">**Nome**</span><span class="sxs-lookup"><span data-stu-id="02b36-169">**Name**</span></span>|<span data-ttu-id="02b36-170">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="02b36-170">**Mail server**</span></span>|<span data-ttu-id="02b36-171">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="02b36-171">**Priority**</span></span>|<span data-ttu-id="02b36-172">**TTL**</span><span class="sxs-lookup"><span data-stu-id="02b36-172">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="02b36-173">MX</span><span class="sxs-lookup"><span data-stu-id="02b36-173">MX</span></span>  <br/> |@  <br/> |<span data-ttu-id="02b36-174">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="02b36-174">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="02b36-175">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02b36-175">**Note:** Get your  *\<domain-key\>*  from your Microsoft 365 account.</span></span>   [<span data-ttu-id="02b36-176">Come trovarla</span><span class="sxs-lookup"><span data-stu-id="02b36-176">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="02b36-177">1 </span><span class="sxs-lookup"><span data-stu-id="02b36-177">1</span></span>  <br/> <span data-ttu-id="02b36-178">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="02b36-178">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/>|<span data-ttu-id="02b36-179">30 minuti</span><span class="sxs-lookup"><span data-stu-id="02b36-179">30 minutes</span></span>  <br/> |
   

  
5. <span data-ttu-id="02b36-180">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="02b36-180">Select **Save**.</span></span>
  
9. <span data-ttu-id="02b36-181">Se sono presenti altri record MX nella sezione **MX Records**, eliminarli selezionando l'icona **Elimina (X)**.</span><span class="sxs-lookup"><span data-stu-id="02b36-181">If there are any other MX records listed in the **MX Records** section, delete them by selecting the **Delete (X)** icon.</span></span> 
  
10. <span data-ttu-id="02b36-182">Nella finestra di dialogo di conferma, selezionare **Elimina** per confermare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="02b36-182">In the confirmation dialog box, select **Delete** to confirm your changes.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="02b36-183">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="02b36-183">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="02b36-184"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="02b36-184"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="02b36-185">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="02b36-185">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="02b36-186">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="02b36-186">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="02b36-187">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="02b36-187">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="02b36-188">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="02b36-188">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="02b36-189">Aggiungere il primo dei cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="02b36-189">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="02b36-190">Nella pagina **gestione DNS** fare clic su **Aggiungi record**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="02b36-190">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="02b36-191">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="02b36-191">**Type**</span></span>|<span data-ttu-id="02b36-192">**Nome**</span><span class="sxs-lookup"><span data-stu-id="02b36-192">**Name**</span></span>|<span data-ttu-id="02b36-193">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="02b36-193">**Target**</span></span>|<span data-ttu-id="02b36-194">**TTL**</span><span class="sxs-lookup"><span data-stu-id="02b36-194">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="02b36-195">CNAME</span><span class="sxs-lookup"><span data-stu-id="02b36-195">CNAME</span></span>  <br/> |<span data-ttu-id="02b36-196">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="02b36-196">autodiscover</span></span>  <br/> |<span data-ttu-id="02b36-197">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="02b36-197">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="02b36-198">30 minutes</span><span class="sxs-lookup"><span data-stu-id="02b36-198">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="02b36-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="02b36-199">CNAME</span></span>  <br/> |<span data-ttu-id="02b36-200">sip</span><span class="sxs-lookup"><span data-stu-id="02b36-200">sip</span></span>  <br/> |<span data-ttu-id="02b36-201">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="02b36-201">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="02b36-202">30 minutes</span><span class="sxs-lookup"><span data-stu-id="02b36-202">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="02b36-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="02b36-203">CNAME</span></span>  <br/> |<span data-ttu-id="02b36-204">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="02b36-204">lyncdiscover</span></span>  <br/> |<span data-ttu-id="02b36-205">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="02b36-205">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="02b36-206">30 minutes</span><span class="sxs-lookup"><span data-stu-id="02b36-206">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="02b36-207">CNAME</span><span class="sxs-lookup"><span data-stu-id="02b36-207">CNAME</span></span>  <br/> |<span data-ttu-id="02b36-208">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="02b36-208">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="02b36-209">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="02b36-209">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="02b36-210">30 minutes</span><span class="sxs-lookup"><span data-stu-id="02b36-210">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="02b36-211">CNAME</span><span class="sxs-lookup"><span data-stu-id="02b36-211">CNAME</span></span>  <br/> |<span data-ttu-id="02b36-212">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="02b36-212">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="02b36-213">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="02b36-213">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="02b36-214">30 minutes</span><span class="sxs-lookup"><span data-stu-id="02b36-214">30 minutes</span></span>  <br/> |
    |<span data-ttu-id="02b36-215">CNAME</span><span class="sxs-lookup"><span data-stu-id="02b36-215">CNAME</span></span>  <br/> |<span data-ttu-id="02b36-216">msoid</span><span class="sxs-lookup"><span data-stu-id="02b36-216">msoid</span></span>  <br/> |<span data-ttu-id="02b36-217">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="02b36-217">clientconfig.microsoftonline-p.net</span></span>  <br/> |<span data-ttu-id="02b36-218">30 minutes</span><span class="sxs-lookup"><span data-stu-id="02b36-218">30 minutes</span></span>  <br/> |
    
  
5. <span data-ttu-id="02b36-219">Selezionare l'icona del **traffico DNS** (cloud arancione) per ignorare i server CloudFlare.</span><span class="sxs-lookup"><span data-stu-id="02b36-219">Select the **DNS Traffic** icon (orange cloud) to bypass the Cloudflare servers.</span></span>
  
6. <span data-ttu-id="02b36-220">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="02b36-220">Select **Save**.</span></span>
  
7. <span data-ttu-id="02b36-221">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="02b36-221">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="02b36-222">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="02b36-222">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="02b36-223"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="02b36-223"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="02b36-224">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="02b36-224">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="02b36-225">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="02b36-225">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="02b36-226">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="02b36-226">If you already have an SPF record for your domain, don't create a new one for Microsoft 365.</span></span> <span data-ttu-id="02b36-227">Al contrario, aggiungere i valori di Microsoft 365 necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="02b36-227">Instead, add the required Microsoft 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="02b36-228">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="02b36-228">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="02b36-229">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="02b36-229">You'll be prompted to log in first.</span></span>
    
  
2. <span data-ttu-id="02b36-230">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="02b36-230">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="02b36-231">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="02b36-231">On the **Overview** page for your domain, select **DNS**.</span></span>

  
4. <span data-ttu-id="02b36-232">Nella pagina **gestione DNS** fare clic su **Aggiungi record**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="02b36-232">On the **DNS management** page, click **Add record**, and then select the values from the following table.</span></span>  
    
    |<span data-ttu-id="02b36-233">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="02b36-233">**Type**</span></span>|<span data-ttu-id="02b36-234">**Nome**</span><span class="sxs-lookup"><span data-stu-id="02b36-234">**Name**</span></span>|<span data-ttu-id="02b36-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="02b36-235">**TTL**</span></span>|<span data-ttu-id="02b36-236">**Content**</span><span class="sxs-lookup"><span data-stu-id="02b36-236">**Content**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="02b36-237">TXT</span><span class="sxs-lookup"><span data-stu-id="02b36-237">TXT</span></span>  <br/> |@  <br/> |<span data-ttu-id="02b36-238">30 minuti</span><span class="sxs-lookup"><span data-stu-id="02b36-238">30 minutes</span></span>  <br/> |<span data-ttu-id="02b36-239">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="02b36-239">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="02b36-240">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="02b36-240">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="02b36-241">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="02b36-241">Select **Save**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="02b36-242">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="02b36-242">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="02b36-243"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="02b36-243"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="02b36-244">Tenere presente che CloudFlare è responsabile di rendere disponibile questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="02b36-244">Please keep in mind that Cloudflare is responsible for making this functionality available.</span></span> <span data-ttu-id="02b36-245">Nel caso in cui si vedano discrepanze tra i passaggi seguenti e l'interfaccia utente di CloudFlare (GUI) corrente, utilizzare la [community di CloudFlare](https://community.cloudflare.com/).</span><span class="sxs-lookup"><span data-stu-id="02b36-245">In case you see discrepancies between the steps below and the current Cloudflare GUI (Graphical User Interface), please leverage the [Cloudflare Community](https://community.cloudflare.com/).</span></span> 

1. <span data-ttu-id="02b36-246">Per iniziare, passare alla propria pagina dei domini su CloudFlare usando [questo collegamento](https://www.cloudflare.com/a/login).</span><span class="sxs-lookup"><span data-stu-id="02b36-246">To get started, go to your domains page at Cloudflare by using [this link](https://www.cloudflare.com/a/login).</span></span> <span data-ttu-id="02b36-247">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="02b36-247">You'll be prompted to log in first.</span></span>
      
2. <span data-ttu-id="02b36-248">Nella **Home** page, selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="02b36-248">On the **Home** page, select the domain that you want to update.</span></span> 
  
3. <span data-ttu-id="02b36-249">Nella pagina **Panoramica** del dominio selezionare **DNS**.</span><span class="sxs-lookup"><span data-stu-id="02b36-249">On the **Overview** page for your domain, select **DNS**.</span></span>
  
4. <span data-ttu-id="02b36-250">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="02b36-250">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="02b36-251">Nella pagina **gestione DNS** fare clic su **Aggiungi record**e quindi selezionare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="02b36-251">On the **DNS management** page, click **Add record**, and then select the values from the first row of the following table.</span></span>
        
    |<span data-ttu-id="02b36-252">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="02b36-252">**Type**</span></span>|<span data-ttu-id="02b36-253">**Service**</span><span class="sxs-lookup"><span data-stu-id="02b36-253">**Service**</span></span>|<span data-ttu-id="02b36-254">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="02b36-254">**Protocol**</span></span>|<span data-ttu-id="02b36-255">**Name**</span><span class="sxs-lookup"><span data-stu-id="02b36-255">**Name**</span></span>|<span data-ttu-id="02b36-256">**TTL**</span><span class="sxs-lookup"><span data-stu-id="02b36-256">**TTL**</span></span>|<span data-ttu-id="02b36-257">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="02b36-257">**Priority**</span></span>|<span data-ttu-id="02b36-258">**Peso**</span><span class="sxs-lookup"><span data-stu-id="02b36-258">**Weight**</span></span>|<span data-ttu-id="02b36-259">**Porta**</span><span class="sxs-lookup"><span data-stu-id="02b36-259">**Port**</span></span>|<span data-ttu-id="02b36-260">**Target**</span><span class="sxs-lookup"><span data-stu-id="02b36-260">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="02b36-261">SRV</span><span class="sxs-lookup"><span data-stu-id="02b36-261">SRV</span></span>|<span data-ttu-id="02b36-262">_sip</span><span class="sxs-lookup"><span data-stu-id="02b36-262">_sip</span></span> |<span data-ttu-id="02b36-263">TLS</span><span class="sxs-lookup"><span data-stu-id="02b36-263">TLS</span></span> |<span data-ttu-id="02b36-264">Utilizzare il *Domain_name*; ad esempio, contoso.com</span><span class="sxs-lookup"><span data-stu-id="02b36-264">Use your *domain_name*; for example, contoso.com</span></span>  |<span data-ttu-id="02b36-265">30 minuti</span><span class="sxs-lookup"><span data-stu-id="02b36-265">30 minutes</span></span> | <span data-ttu-id="02b36-266">100</span><span class="sxs-lookup"><span data-stu-id="02b36-266">100</span></span>|<span data-ttu-id="02b36-267">1 </span><span class="sxs-lookup"><span data-stu-id="02b36-267">1</span></span> |<span data-ttu-id="02b36-268">443</span><span class="sxs-lookup"><span data-stu-id="02b36-268">443</span></span> |<span data-ttu-id="02b36-269">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="02b36-269">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="02b36-270">SRV</span><span class="sxs-lookup"><span data-stu-id="02b36-270">SRV</span></span>|<span data-ttu-id="02b36-271">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="02b36-271">_sipfederationtls</span></span> | <span data-ttu-id="02b36-272">TCP</span><span class="sxs-lookup"><span data-stu-id="02b36-272">TCP</span></span>|<span data-ttu-id="02b36-273">Utilizzare il *Domain_name*; ad esempio, contoso.com</span><span class="sxs-lookup"><span data-stu-id="02b36-273">Use your *domain_name*; for example, contoso.com</span></span>   |<span data-ttu-id="02b36-274">30 minuti</span><span class="sxs-lookup"><span data-stu-id="02b36-274">30 minutes</span></span> |<span data-ttu-id="02b36-275">100</span><span class="sxs-lookup"><span data-stu-id="02b36-275">100</span></span> |<span data-ttu-id="02b36-276">1 </span><span class="sxs-lookup"><span data-stu-id="02b36-276">1</span></span> |<span data-ttu-id="02b36-277">5061</span><span class="sxs-lookup"><span data-stu-id="02b36-277">5061</span></span> | <span data-ttu-id="02b36-278">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="02b36-278">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="02b36-279">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="02b36-279">Select **Save**.</span></span>

  
6. <span data-ttu-id="02b36-280">Aggiungere l'altro record SRV scegliendo i valori della seconda riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="02b36-280">Add the other SRV record by choosing the values from the second row of the table.</span></span> 

    
> [!NOTE]
>  <span data-ttu-id="02b36-p117">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="02b36-p117">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
