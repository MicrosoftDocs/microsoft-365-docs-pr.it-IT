---
title: Creare record DNS in web.com per Microsoft
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
description: Informazioni su come verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e altri servizi web.com per Microsoft.
ms.openlocfilehash: 943070f3790f532a0cc686270e0ecdea08f802fd
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656892"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="835a6-103">Creare record DNS in web.com per Microsoft</span><span class="sxs-lookup"><span data-stu-id="835a6-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="835a6-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="835a6-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="835a6-105">Se web.com è il provider di hosting DNS, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="835a6-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="835a6-106">Dopo aver aggiunto questi record in web.com, il dominio sarà configurato per l'utilizzo con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="835a6-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="835a6-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="835a6-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="835a6-110">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="835a6-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="835a6-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="835a6-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="835a6-112">È necessario eseguire questa procedura presso il registrar da cui è stato acquistato e registrato il dominio.</span><span class="sxs-lookup"><span data-stu-id="835a6-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="835a6-113">Quando si è effettuato l'web.com, è stato aggiunto un dominio utilizzando il web.com **di** installazione.</span><span class="sxs-lookup"><span data-stu-id="835a6-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="835a6-114">Per verificare e creare record DNS per il dominio in Microsoft, è innanzitutto necessario modificare i server dei nomi presso il registrar in modo che utilizzino i server dei nomi di web.com.</span><span class="sxs-lookup"><span data-stu-id="835a6-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="835a6-115">Per modificare i server dei nomi del dominio presso il registrar, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="835a6-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="835a6-116">Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="835a6-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="835a6-117">Creare due record dei server dei nomi usando i valori della tabella seguente oppure modificare quelli esistenti in modo che corrispondano a questi valori.</span><span class="sxs-lookup"><span data-stu-id="835a6-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="835a6-118">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="835a6-118">First nameserver</span></span>  <br/> |<span data-ttu-id="835a6-119">Utilizzare il valore del server dei nomi fornito da web.com.</span><span class="sxs-lookup"><span data-stu-id="835a6-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="835a6-120">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="835a6-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="835a6-121">Utilizzare il valore del server dei nomi fornito da web.com.</span><span class="sxs-lookup"><span data-stu-id="835a6-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="835a6-122">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="835a6-122">You should use at least two name server records.</span></span> <span data-ttu-id="835a6-123">Se sono elencati altri server dei nomi, è necessario eliminarli.</span><span class="sxs-lookup"><span data-stu-id="835a6-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="835a6-124">Salvare le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="835a6-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="835a6-125">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="835a6-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="835a6-126">Quindi la posta elettronica Microsoft e altri servizi saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="835a6-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="835a6-127">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="835a6-127">Add a TXT record for verification</span></span>
<span data-ttu-id="835a6-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="835a6-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="835a6-p104">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="835a6-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="835a6-p105">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="835a6-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="835a6-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="835a6-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="835a6-134">Eseguire prima l'accesso.</span><span class="sxs-lookup"><span data-stu-id="835a6-134">Log in first.</span></span>
  
2. <span data-ttu-id="835a6-135">Nella pagina **Account Manager** selezionare My **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="835a6-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="835a6-136">In \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="835a6-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="835a6-137">Nella pagina **Domain Names,** in **Text (TXT Records),** fare clic **su Edit TXT Records** e quindi selezionare i valori dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="835a6-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="835a6-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="835a6-138">**Host**</span></span>|<span data-ttu-id="835a6-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="835a6-139">**TTL**</span></span>|<span data-ttu-id="835a6-140">**Text**</span><span class="sxs-lookup"><span data-stu-id="835a6-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="835a6-141">3600</span><span class="sxs-lookup"><span data-stu-id="835a6-141">3600</span></span>  <br/> |<span data-ttu-id="835a6-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="835a6-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="835a6-143">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="835a6-143">**Note:** This is an example.</span></span> <span data-ttu-id="835a6-144">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="835a6-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="835a6-145">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="835a6-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="835a6-146">Selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="835a6-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="835a6-147">Attendere alcuni minuti prima di verificare il nuovo record TXT, in modo che il record appena creato possa essere aggiornato su Internet.</span><span class="sxs-lookup"><span data-stu-id="835a6-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="835a6-148">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="835a6-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="835a6-149">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="835a6-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="835a6-150">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="835a6-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="835a6-151">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="835a6-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="835a6-152">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="835a6-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="835a6-153">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="835a6-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="835a6-p108">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="835a6-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="835a6-157">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="835a6-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="835a6-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="835a6-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="835a6-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="835a6-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="835a6-160">Eseguire prima l'accesso.</span><span class="sxs-lookup"><span data-stu-id="835a6-160">Log in first.</span></span>
  
2. <span data-ttu-id="835a6-161">Nella pagina **Account Manager** selezionare My **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="835a6-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="835a6-162">In \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="835a6-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="835a6-163">In **Mail Servers (MX Records)** fare clic **su Edit MX Records** e quindi selezionare i valori dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="835a6-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="835a6-164">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="835a6-164">**Priority**</span></span>|<span data-ttu-id="835a6-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="835a6-165">**TTL**</span></span>|<span data-ttu-id="835a6-166">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="835a6-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="835a6-167">1 </span><span class="sxs-lookup"><span data-stu-id="835a6-167">1</span></span>  <br/> <span data-ttu-id="835a6-168">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="835a6-168">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |<span data-ttu-id="835a6-169">3600</span><span class="sxs-lookup"><span data-stu-id="835a6-169">3600</span></span>  <br/> |<span data-ttu-id="835a6-170">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="835a6-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="835a6-171">**Nota:** Ottenere il  *\<domain-key\>*  proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="835a6-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="835a6-172">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="835a6-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="835a6-173">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="835a6-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="835a6-174">Se nella sezione MX Records sono elencati altri record **MX,** selezionare la casella di controllo accanto al record in **Delete** e selezionare **Save**.</span><span class="sxs-lookup"><span data-stu-id="835a6-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="835a6-175">Nella schermata di conferma, selezionare **Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="835a6-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="835a6-176">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="835a6-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="835a6-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="835a6-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="835a6-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="835a6-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="835a6-179">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="835a6-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="835a6-180">Nella pagina **Account Manager** selezionare My **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="835a6-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="835a6-181">In \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="835a6-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="835a6-182">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="835a6-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="835a6-183">In **Host Aliases (CNAME Records)** fare clic su **Edit CNAME Records** e quindi selezionare i valori dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="835a6-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="835a6-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="835a6-184">**Alias**</span></span>|<span data-ttu-id="835a6-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="835a6-185">**TTL**</span></span>|<span data-ttu-id="835a6-186">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="835a6-186">**Refers to Host Name**</span></span>|<span data-ttu-id="835a6-187">**Altro host**</span><span class="sxs-lookup"><span data-stu-id="835a6-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="835a6-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="835a6-188">autodiscover</span></span>  <br/> |<span data-ttu-id="835a6-189">3600</span><span class="sxs-lookup"><span data-stu-id="835a6-189">3600</span></span>  <br/> |<span data-ttu-id="835a6-190">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="835a6-190">@ (none)</span></span>  <br/> |<span data-ttu-id="835a6-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="835a6-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="835a6-192">sip</span><span class="sxs-lookup"><span data-stu-id="835a6-192">sip</span></span>  <br/> |<span data-ttu-id="835a6-193">3600</span><span class="sxs-lookup"><span data-stu-id="835a6-193">3600</span></span>  <br/> |<span data-ttu-id="835a6-194">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="835a6-194">@ (none)</span></span>  <br/> |<span data-ttu-id="835a6-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="835a6-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="835a6-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="835a6-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="835a6-197">3600</span><span class="sxs-lookup"><span data-stu-id="835a6-197">3600</span></span>  <br/> |<span data-ttu-id="835a6-198">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="835a6-198">@ (none)</span></span>  <br/> | <span data-ttu-id="835a6-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="835a6-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="835a6-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="835a6-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="835a6-201">3600</span><span class="sxs-lookup"><span data-stu-id="835a6-201">3600</span></span>  <br/> |<span data-ttu-id="835a6-202">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="835a6-202">@ (none)</span></span>  <br/> |<span data-ttu-id="835a6-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="835a6-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="835a6-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="835a6-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="835a6-205">3600</span><span class="sxs-lookup"><span data-stu-id="835a6-205">3600</span></span>  <br/> |<span data-ttu-id="835a6-206">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="835a6-206">@ (none)</span></span>  <br/> |<span data-ttu-id="835a6-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="835a6-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="835a6-208">msoid</span><span class="sxs-lookup"><span data-stu-id="835a6-208">msoid</span></span>  <br/> |<span data-ttu-id="835a6-209">3600</span><span class="sxs-lookup"><span data-stu-id="835a6-209">3600</span></span>  <br/> |<span data-ttu-id="835a6-210">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="835a6-210">@ (none)</span></span>  <br/> |<span data-ttu-id="835a6-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="835a6-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="835a6-212">Selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="835a6-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="835a6-213">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="835a6-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="835a6-214">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="835a6-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="835a6-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="835a6-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="835a6-216">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="835a6-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="835a6-217">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="835a6-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="835a6-218">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="835a6-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="835a6-219">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="835a6-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="835a6-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="835a6-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="835a6-221">Eseguire prima l'accesso.</span><span class="sxs-lookup"><span data-stu-id="835a6-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="835a6-222">Nella pagina **Account Manager** selezionare My **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="835a6-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="835a6-223">In \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="835a6-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="835a6-224">Nella pagina **Domain Names,** in **Text (TXT Records),** fare clic **su Edit TXT Records** e quindi selezionare i valori dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="835a6-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="835a6-225">**Host**</span><span class="sxs-lookup"><span data-stu-id="835a6-225">**Host**</span></span>|<span data-ttu-id="835a6-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="835a6-226">**TTL**</span></span>|<span data-ttu-id="835a6-227">**Text**</span><span class="sxs-lookup"><span data-stu-id="835a6-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="835a6-228">3600</span><span class="sxs-lookup"><span data-stu-id="835a6-228">3600</span></span>  <br/> |<span data-ttu-id="835a6-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="835a6-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="835a6-230">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="835a6-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="835a6-231">Selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="835a6-231">Select **Continue**.</span></span>

6. <span data-ttu-id="835a6-232">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="835a6-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="835a6-233">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="835a6-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="835a6-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="835a6-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="835a6-235">Tieni presente che la web.com è responsabile di rendere disponibile questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="835a6-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="835a6-236">In caso di discrepanze tra i passaggi riportati di seguito e l'interfaccia web.com corrente (interfaccia utente grafica), utilizzare la web.com [Community.](https://community.web.com.com/)</span><span class="sxs-lookup"><span data-stu-id="835a6-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="835a6-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="835a6-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="835a6-238">Eseguire prima l'accesso.</span><span class="sxs-lookup"><span data-stu-id="835a6-238">Log in first.</span></span>
      
2. <span data-ttu-id="835a6-239">Nella pagina **Account Manager** selezionare My **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="835a6-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="835a6-240">In \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="835a6-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="835a6-241">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="835a6-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="835a6-242">In **Service (SRV Records)** fare clic **su Edit SRV Records** e quindi selezionare i valori dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="835a6-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="835a6-243">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="835a6-243">**Service**</span></span>|<span data-ttu-id="835a6-244">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="835a6-244">**Protocol**</span></span>|<span data-ttu-id="835a6-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="835a6-245">**TTL**</span></span>|<span data-ttu-id="835a6-246">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="835a6-246">**Priority**</span></span>|<span data-ttu-id="835a6-247">**Peso**</span><span class="sxs-lookup"><span data-stu-id="835a6-247">**Weight**</span></span>|<span data-ttu-id="835a6-248">**Porta**</span><span class="sxs-lookup"><span data-stu-id="835a6-248">**Port**</span></span>|<span data-ttu-id="835a6-249">**Target**</span><span class="sxs-lookup"><span data-stu-id="835a6-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="835a6-250">_sip</span><span class="sxs-lookup"><span data-stu-id="835a6-250">_sip</span></span> |<span data-ttu-id="835a6-251">_tls</span><span class="sxs-lookup"><span data-stu-id="835a6-251">_tls</span></span> |<span data-ttu-id="835a6-252">3600</span><span class="sxs-lookup"><span data-stu-id="835a6-252">3600</span></span> | <span data-ttu-id="835a6-253">100</span><span class="sxs-lookup"><span data-stu-id="835a6-253">100</span></span>|<span data-ttu-id="835a6-254">1 </span><span class="sxs-lookup"><span data-stu-id="835a6-254">1</span></span> |<span data-ttu-id="835a6-255">443</span><span class="sxs-lookup"><span data-stu-id="835a6-255">443</span></span> |<span data-ttu-id="835a6-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="835a6-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="835a6-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="835a6-257">_sipfederationtls</span></span> |<span data-ttu-id="835a6-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="835a6-258">_tcp</span></span> |<span data-ttu-id="835a6-259">3600</span><span class="sxs-lookup"><span data-stu-id="835a6-259">3600</span></span> |<span data-ttu-id="835a6-260">100</span><span class="sxs-lookup"><span data-stu-id="835a6-260">100</span></span> |<span data-ttu-id="835a6-261">1 </span><span class="sxs-lookup"><span data-stu-id="835a6-261">1</span></span> |<span data-ttu-id="835a6-262">5061</span><span class="sxs-lookup"><span data-stu-id="835a6-262">5061</span></span> | <span data-ttu-id="835a6-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="835a6-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="835a6-264">Aggiungere l'altro record SRV scegliendo i valori dalla seconda riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="835a6-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="835a6-265">Selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="835a6-265">Select **Continue**.</span></span>

7. <span data-ttu-id="835a6-266">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="835a6-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="835a6-p116">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="835a6-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
