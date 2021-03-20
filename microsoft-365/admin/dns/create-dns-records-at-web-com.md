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
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e altri servizi web.com per Microsoft.
ms.openlocfilehash: b667b2e69822fcd69babda7790a6468b640b073b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909983"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="a8b94-103">Creare record DNS in web.com per Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8b94-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="a8b94-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="a8b94-105">Se web.com è il provider di hosting DNS, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="a8b94-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="a8b94-106">Dopo aver aggiunto questi record in web.com, il dominio sarà configurato per l'utilizzo con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8b94-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
>  <span data-ttu-id="a8b94-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a8b94-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="a8b94-110">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="a8b94-110">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="a8b94-111"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="a8b94-111"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8b94-112">È necessario eseguire questa procedura presso il registrar da cui è stato acquistato e registrato il dominio.</span><span class="sxs-lookup"><span data-stu-id="a8b94-112">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="a8b94-113">Dopo aver effettuato l'web.com, è stato aggiunto un dominio utilizzando il processo di web.com **di** installazione.</span><span class="sxs-lookup"><span data-stu-id="a8b94-113">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="a8b94-114">Per verificare e creare record DNS per il dominio in Microsoft, è innanzitutto necessario modificare i server dei nomi presso il registrar in modo che utilizzino i server dei nomi di web.com.</span><span class="sxs-lookup"><span data-stu-id="a8b94-114">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="a8b94-115">Per modificare i server dei nomi del dominio presso il registrar, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="a8b94-115">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="a8b94-116">Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="a8b94-116">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="a8b94-117">Creare due record dei server dei nomi usando i valori della tabella seguente oppure modificare quelli esistenti in modo che corrispondano a questi valori.</span><span class="sxs-lookup"><span data-stu-id="a8b94-117">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="a8b94-118">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="a8b94-118">First nameserver</span></span>  <br/> |<span data-ttu-id="a8b94-119">Utilizzare il valore del server dei nomi fornito da web.com.</span><span class="sxs-lookup"><span data-stu-id="a8b94-119">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="a8b94-120">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="a8b94-120">Second nameserver</span></span>  <br/> |<span data-ttu-id="a8b94-121">Utilizzare il valore del server dei nomi fornito da web.com.</span><span class="sxs-lookup"><span data-stu-id="a8b94-121">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="a8b94-122">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="a8b94-122">You should use at least two name server records.</span></span> <span data-ttu-id="a8b94-123">Se sono elencati altri server dei nomi, è consigliabile eliminarli.</span><span class="sxs-lookup"><span data-stu-id="a8b94-123">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="a8b94-124">Salvare le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="a8b94-124">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a8b94-125">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="a8b94-125">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="a8b94-126">Quindi la posta elettronica Microsoft e altri servizi saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="a8b94-126">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="a8b94-127">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="a8b94-127">Add a TXT record for verification</span></span>
<span data-ttu-id="a8b94-128"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="a8b94-128"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="a8b94-p104">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="a8b94-p104">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a8b94-p105">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="a8b94-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="a8b94-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="a8b94-133">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a8b94-134">Eseguire prima l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a8b94-134">Log in first.</span></span>
  
2. <span data-ttu-id="a8b94-135">Nella pagina **Account Manager** selezionare My **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-135">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a8b94-136">In \*\*Manage \*my domain\*\*\*, selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-136">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="a8b94-137">Nella pagina **Domain Names,** in **Text (TXT Records)** fare clic **su Edit TXT Records** e quindi selezionare i valori dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a8b94-137">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="a8b94-138">**Host**</span><span class="sxs-lookup"><span data-stu-id="a8b94-138">**Host**</span></span>|<span data-ttu-id="a8b94-139">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8b94-139">**TTL**</span></span>|<span data-ttu-id="a8b94-140">**Text**</span><span class="sxs-lookup"><span data-stu-id="a8b94-140">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="a8b94-141">3600</span><span class="sxs-lookup"><span data-stu-id="a8b94-141">3600</span></span>  <br/> |<span data-ttu-id="a8b94-142">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="a8b94-142">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="a8b94-143">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="a8b94-143">**Note:** This is an example.</span></span> <span data-ttu-id="a8b94-144">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="a8b94-144">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="a8b94-145">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="a8b94-145">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="a8b94-146">Selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="a8b94-146">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="a8b94-147">Attendere alcuni minuti prima di verificare il nuovo record TXT, in modo che il record appena creato possa essere aggiornato su Internet.</span><span class="sxs-lookup"><span data-stu-id="a8b94-147">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="a8b94-148">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="a8b94-148">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="a8b94-149">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="a8b94-149">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="a8b94-150">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="a8b94-150">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="a8b94-151">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="a8b94-151">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="a8b94-152">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-152">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="a8b94-153">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-153">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="a8b94-p108">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a8b94-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="a8b94-157">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8b94-157">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="a8b94-158"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="a8b94-158"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="a8b94-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="a8b94-159">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a8b94-160">Eseguire prima l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a8b94-160">Log in first.</span></span>
  
2. <span data-ttu-id="a8b94-161">Nella pagina **Account Manager** selezionare My **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-161">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a8b94-162">In \*\*Manage \*my domain\*\*\*, selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-162">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="a8b94-163">In **Mail Servers (MX Records)** fare clic **su Edit MX Records** e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a8b94-163">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="a8b94-164">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="a8b94-164">**Priority**</span></span>|<span data-ttu-id="a8b94-165">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8b94-165">**TTL**</span></span>|<span data-ttu-id="a8b94-166">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="a8b94-166">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="a8b94-167">1</span><span class="sxs-lookup"><span data-stu-id="a8b94-167">1</span></span>  <br/> <span data-ttu-id="a8b94-168">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="a8b94-168">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="a8b94-169">3600</span><span class="sxs-lookup"><span data-stu-id="a8b94-169">3600</span></span>  <br/> |<span data-ttu-id="a8b94-170">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a8b94-170">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="a8b94-171">**Nota:** Ottenere  *\<domain-key\>*  l'utente dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8b94-171">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="a8b94-172">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="a8b94-172">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="a8b94-173">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-173">Select **Save**.</span></span>
  
6. <span data-ttu-id="a8b94-174">Se nella sezione MX Records sono elencati altri record **MX,** selezionare la casella di controllo accanto al record in **Delete** e selezionare **Save**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-174">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="a8b94-175">Nella schermata di conferma, selezionare **Salva modifiche.**</span><span class="sxs-lookup"><span data-stu-id="a8b94-175">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="a8b94-176">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8b94-176">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="a8b94-177"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="a8b94-177"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="a8b94-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="a8b94-178">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a8b94-179">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a8b94-179">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="a8b94-180">Nella pagina **Account Manager** selezionare My **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-180">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a8b94-181">In \*\*Manage \*my domain\*\*\*, selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-181">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="a8b94-182">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="a8b94-182">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="a8b94-183">In **Host Aliases (CNAME Records)** fare clic su **Edit CNAME Records** e quindi selezionare i valori dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a8b94-183">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="a8b94-184">**Alias**</span><span class="sxs-lookup"><span data-stu-id="a8b94-184">**Alias**</span></span>|<span data-ttu-id="a8b94-185">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8b94-185">**TTL**</span></span>|<span data-ttu-id="a8b94-186">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="a8b94-186">**Refers to Host Name**</span></span>|<span data-ttu-id="a8b94-187">**Altro host**</span><span class="sxs-lookup"><span data-stu-id="a8b94-187">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a8b94-188">autodiscover</span><span class="sxs-lookup"><span data-stu-id="a8b94-188">autodiscover</span></span>  <br/> |<span data-ttu-id="a8b94-189">3600</span><span class="sxs-lookup"><span data-stu-id="a8b94-189">3600</span></span>  <br/> |<span data-ttu-id="a8b94-190">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="a8b94-190">@ (none)</span></span>  <br/> |<span data-ttu-id="a8b94-191">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="a8b94-191">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="a8b94-192">sip</span><span class="sxs-lookup"><span data-stu-id="a8b94-192">sip</span></span>  <br/> |<span data-ttu-id="a8b94-193">3600</span><span class="sxs-lookup"><span data-stu-id="a8b94-193">3600</span></span>  <br/> |<span data-ttu-id="a8b94-194">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="a8b94-194">@ (none)</span></span>  <br/> |<span data-ttu-id="a8b94-195">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a8b94-195">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a8b94-196">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="a8b94-196">lyncdiscover</span></span>  <br/> |<span data-ttu-id="a8b94-197">3600</span><span class="sxs-lookup"><span data-stu-id="a8b94-197">3600</span></span>  <br/> |<span data-ttu-id="a8b94-198">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="a8b94-198">@ (none)</span></span>  <br/> | <span data-ttu-id="a8b94-199">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a8b94-199">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="a8b94-200">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="a8b94-200">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="a8b94-201">3600</span><span class="sxs-lookup"><span data-stu-id="a8b94-201">3600</span></span>  <br/> |<span data-ttu-id="a8b94-202">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="a8b94-202">@ (none)</span></span>  <br/> |<span data-ttu-id="a8b94-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="a8b94-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="a8b94-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="a8b94-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="a8b94-205">3600</span><span class="sxs-lookup"><span data-stu-id="a8b94-205">3600</span></span>  <br/> |<span data-ttu-id="a8b94-206">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="a8b94-206">@ (none)</span></span>  <br/> |<span data-ttu-id="a8b94-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="a8b94-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="a8b94-208">msoid</span><span class="sxs-lookup"><span data-stu-id="a8b94-208">msoid</span></span>  <br/> |<span data-ttu-id="a8b94-209">3600</span><span class="sxs-lookup"><span data-stu-id="a8b94-209">3600</span></span>  <br/> |<span data-ttu-id="a8b94-210">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="a8b94-210">@ (none)</span></span>  <br/> |<span data-ttu-id="a8b94-211">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="a8b94-211">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="a8b94-212">Selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="a8b94-212">Select **Continue**.</span></span>
  
6. <span data-ttu-id="a8b94-213">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="a8b94-213">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="a8b94-214">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="a8b94-214">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="a8b94-215"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="a8b94-215"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8b94-216">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="a8b94-216">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="a8b94-217">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="a8b94-217">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="a8b94-218">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a8b94-218">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="a8b94-219">Aggiungere invece i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="a8b94-219">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="a8b94-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="a8b94-220">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a8b94-221">Eseguire prima l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a8b94-221">Log in first.</span></span>
    
  
2. <span data-ttu-id="a8b94-222">Nella pagina **Account Manager** selezionare My **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-222">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a8b94-223">In \*\*Manage \*my domain\*\*\*, selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-223">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="a8b94-224">Nella pagina **Domain Names,** in **Text (TXT Records)** fare clic **su Edit TXT Records** e quindi selezionare i valori dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a8b94-224">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="a8b94-225">**Host**</span><span class="sxs-lookup"><span data-stu-id="a8b94-225">**Host**</span></span>|<span data-ttu-id="a8b94-226">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8b94-226">**TTL**</span></span>|<span data-ttu-id="a8b94-227">**Text**</span><span class="sxs-lookup"><span data-stu-id="a8b94-227">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="a8b94-228">3600</span><span class="sxs-lookup"><span data-stu-id="a8b94-228">3600</span></span>  <br/> |<span data-ttu-id="a8b94-229">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="a8b94-229">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="a8b94-230">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="a8b94-230">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="a8b94-231">Selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="a8b94-231">Select **Continue**.</span></span>

6. <span data-ttu-id="a8b94-232">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-232">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="a8b94-233">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="a8b94-233">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="a8b94-234"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="a8b94-234"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8b94-235">Tieni presente che questa web.com è responsabile della disponibilità di questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="a8b94-235">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="a8b94-236">Nel caso in cui si vedano discrepanze tra i passaggi seguenti e l'interfaccia gui di web.com corrente (interfaccia utente grafica), sfruttare la web.com [Community](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="a8b94-236">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="a8b94-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="a8b94-237">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="a8b94-238">Eseguire prima l'accesso.</span><span class="sxs-lookup"><span data-stu-id="a8b94-238">Log in first.</span></span>
      
2. <span data-ttu-id="a8b94-239">Nella pagina **Account Manager** selezionare My **Domain Names**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-239">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="a8b94-240">In \*\*Manage \*my domain\*\*\*, selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-240">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="a8b94-241">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="a8b94-241">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="a8b94-242">In **Servizio (record SRV)** fare clic su **Modifica record SRV** e quindi selezionare i valori dalla tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a8b94-242">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="a8b94-243">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="a8b94-243">**Service**</span></span>|<span data-ttu-id="a8b94-244">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="a8b94-244">**Protocol**</span></span>|<span data-ttu-id="a8b94-245">**TTL**</span><span class="sxs-lookup"><span data-stu-id="a8b94-245">**TTL**</span></span>|<span data-ttu-id="a8b94-246">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="a8b94-246">**Priority**</span></span>|<span data-ttu-id="a8b94-247">**Peso**</span><span class="sxs-lookup"><span data-stu-id="a8b94-247">**Weight**</span></span>|<span data-ttu-id="a8b94-248">**Porta**</span><span class="sxs-lookup"><span data-stu-id="a8b94-248">**Port**</span></span>|<span data-ttu-id="a8b94-249">**Target**</span><span class="sxs-lookup"><span data-stu-id="a8b94-249">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="a8b94-250">_sip</span><span class="sxs-lookup"><span data-stu-id="a8b94-250">_sip</span></span> |<span data-ttu-id="a8b94-251">_tls</span><span class="sxs-lookup"><span data-stu-id="a8b94-251">_tls</span></span> |<span data-ttu-id="a8b94-252">3600</span><span class="sxs-lookup"><span data-stu-id="a8b94-252">3600</span></span> | <span data-ttu-id="a8b94-253">100</span><span class="sxs-lookup"><span data-stu-id="a8b94-253">100</span></span>|<span data-ttu-id="a8b94-254">1</span><span class="sxs-lookup"><span data-stu-id="a8b94-254">1</span></span> |<span data-ttu-id="a8b94-255">443</span><span class="sxs-lookup"><span data-stu-id="a8b94-255">443</span></span> |<span data-ttu-id="a8b94-256">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a8b94-256">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="a8b94-257">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="a8b94-257">_sipfederationtls</span></span> |<span data-ttu-id="a8b94-258">_tcp</span><span class="sxs-lookup"><span data-stu-id="a8b94-258">_tcp</span></span> |<span data-ttu-id="a8b94-259">3600</span><span class="sxs-lookup"><span data-stu-id="a8b94-259">3600</span></span> |<span data-ttu-id="a8b94-260">100</span><span class="sxs-lookup"><span data-stu-id="a8b94-260">100</span></span> |<span data-ttu-id="a8b94-261">1</span><span class="sxs-lookup"><span data-stu-id="a8b94-261">1</span></span> |<span data-ttu-id="a8b94-262">5061</span><span class="sxs-lookup"><span data-stu-id="a8b94-262">5061</span></span> | <span data-ttu-id="a8b94-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="a8b94-263">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="a8b94-264">Aggiungere l'altro record SRV scegliendo i valori dalla seconda riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="a8b94-264">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="a8b94-265">Selezionare **Continua.**</span><span class="sxs-lookup"><span data-stu-id="a8b94-265">Select **Continue**.</span></span>

7. <span data-ttu-id="a8b94-266">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="a8b94-266">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="a8b94-p116">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="a8b94-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
