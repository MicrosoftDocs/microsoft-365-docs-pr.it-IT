---
title: Creare record DNS in web.com per Microsoft
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
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in web.com per Microsoft.
ms.openlocfilehash: ec1d0168fb8a9dfb30d47412146777bc88f90a46
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629252"
---
# <a name="create-dns-records-at-webcom-for-microsoft"></a><span data-ttu-id="8a026-103">Creare record DNS in web.com per Microsoft</span><span class="sxs-lookup"><span data-stu-id="8a026-103">Create DNS records at web.com for Microsoft</span></span>

 <span data-ttu-id="8a026-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="8a026-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="8a026-105">Se web.com è il provider di hosting DNS, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e così via.</span><span class="sxs-lookup"><span data-stu-id="8a026-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="8a026-106">Dopo aver aggiunto questi record in web.com, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8a026-106">After you add these records at web.com, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="8a026-107">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="8a026-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="8a026-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8a026-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="8a026-111">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="8a026-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="8a026-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="8a026-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a026-113">È necessario eseguire questa procedura presso il registrar da cui è stato acquistato e registrato il dominio.</span><span class="sxs-lookup"><span data-stu-id="8a026-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="8a026-114">Quando è stato eseguito l'accesso a web.com, è stato aggiunto un dominio utilizzando il processo di **installazione** di Web.com.</span><span class="sxs-lookup"><span data-stu-id="8a026-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="8a026-115">Per verificare e creare record DNS per il proprio dominio in Microsoft, è innanzitutto necessario cambiare i server dei nomi presso il registrar in modo che utilizzino i server di gestione Web. com.</span><span class="sxs-lookup"><span data-stu-id="8a026-115">To verify and create DNS records for your domain in Microsoft, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="8a026-116">Per modificare i server dei nomi del dominio presso il registrar, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="8a026-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="8a026-117">Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="8a026-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="8a026-118">Creare due record dei server dei nomi usando i valori della tabella seguente oppure modificare quelli esistenti in modo che corrispondano a questi valori.</span><span class="sxs-lookup"><span data-stu-id="8a026-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="8a026-119">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="8a026-119">First nameserver</span></span>  <br/> |<span data-ttu-id="8a026-120">Utilizzare il valore del server dei nomi fornito da web.com.</span><span class="sxs-lookup"><span data-stu-id="8a026-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="8a026-121">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="8a026-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="8a026-122">Utilizzare il valore del server dei nomi fornito da web.com.</span><span class="sxs-lookup"><span data-stu-id="8a026-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="8a026-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="8a026-123">You should use at least two name server records.</span></span> <span data-ttu-id="8a026-124">Se sono elencati altri server dei nomi, è necessario eliminarli.</span><span class="sxs-lookup"><span data-stu-id="8a026-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="8a026-125">Salvare le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="8a026-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="8a026-126">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore.</span><span class="sxs-lookup"><span data-stu-id="8a026-126">Your nameserver record updates may take up to several hours to update across the Internet's DNS system.</span></span> <span data-ttu-id="8a026-127">L'indirizzo di posta elettronica e gli altri servizi di Microsoft saranno tutti impostati per l'utilizzo con il dominio.</span><span class="sxs-lookup"><span data-stu-id="8a026-127">Then your Microsoft email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="8a026-128">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="8a026-128">Add a TXT record for verification</span></span>
<span data-ttu-id="8a026-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="8a026-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="8a026-130">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="8a026-130">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="8a026-131">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="8a026-131">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8a026-p105">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="8a026-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="8a026-134">Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="8a026-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="8a026-135">Accedere per primo.</span><span class="sxs-lookup"><span data-stu-id="8a026-135">Log in first.</span></span>
  
2. <span data-ttu-id="8a026-136">Nella pagina **account manager** selezionare i **nomi di dominio personali**.</span><span class="sxs-lookup"><span data-stu-id="8a026-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="8a026-137">In \* \* Manage \* My Domain \* \* \* selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="8a026-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="8a026-138">Nella pagina **Domain Names** , sotto **Text (TXT Records)**, fare clic su **Edit TXT Records**, quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8a026-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="8a026-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="8a026-139">**Host**</span></span>|<span data-ttu-id="8a026-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8a026-140">**TTL**</span></span>|<span data-ttu-id="8a026-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="8a026-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="8a026-142">3600</span><span class="sxs-lookup"><span data-stu-id="8a026-142">3600</span></span>  <br/> |<span data-ttu-id="8a026-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="8a026-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="8a026-144">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="8a026-144">**Note:** This is an example.</span></span> <span data-ttu-id="8a026-145">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="8a026-145">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="8a026-146">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="8a026-146">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
  
    
5. <span data-ttu-id="8a026-147">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="8a026-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="8a026-148">Attendere alcuni minuti prima di verificare il nuovo record TXT, in modo che il record appena creato possa essere aggiornato su Internet.</span><span class="sxs-lookup"><span data-stu-id="8a026-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="8a026-149">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="8a026-149">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="8a026-150">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="8a026-150">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="8a026-151">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="8a026-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="8a026-152">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="8a026-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="8a026-153">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="8a026-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="8a026-154">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="8a026-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="8a026-p108">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8a026-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="8a026-158">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="8a026-158">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="8a026-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="8a026-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="8a026-160">Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="8a026-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="8a026-161">Accedere per primo.</span><span class="sxs-lookup"><span data-stu-id="8a026-161">Log in first.</span></span>
  
2. <span data-ttu-id="8a026-162">Nella pagina **account manager** selezionare i **nomi di dominio personali**.</span><span class="sxs-lookup"><span data-stu-id="8a026-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="8a026-163">In \* \* Manage \* My Domain \* \* \* selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="8a026-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="8a026-164">In **server di posta elettronica (record MX)** fare clic su **Modifica record MX**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8a026-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="8a026-165">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="8a026-165">**Priority**</span></span>|<span data-ttu-id="8a026-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8a026-166">**TTL**</span></span>|<span data-ttu-id="8a026-167">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="8a026-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="8a026-168">1 </span><span class="sxs-lookup"><span data-stu-id="8a026-168">1</span></span>  <br/> <span data-ttu-id="8a026-169">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="8a026-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="8a026-170">3600</span><span class="sxs-lookup"><span data-stu-id="8a026-170">3600</span></span>  <br/> |<span data-ttu-id="8a026-171">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8a026-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="8a026-172">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8a026-172">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="8a026-173">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="8a026-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="8a026-174">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8a026-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="8a026-175">Se nella sezione **MX Records** sono presenti altri record MX, selezionare la casella di controllo accanto al record in **Delete**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8a026-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="8a026-176">Nella schermata di conferma fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="8a026-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="8a026-177">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="8a026-177">Add the Six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="8a026-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="8a026-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="8a026-179">Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="8a026-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="8a026-180">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="8a026-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="8a026-181">Nella pagina **account manager** selezionare i **nomi di dominio personali**.</span><span class="sxs-lookup"><span data-stu-id="8a026-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="8a026-182">In \* \* Manage \* My Domain \* \* \* selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="8a026-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="8a026-183">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="8a026-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="8a026-184">In **alias host (record CNAME)** fare clic su **Modifica record CNAME**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8a026-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="8a026-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="8a026-185">**Alias**</span></span>|<span data-ttu-id="8a026-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8a026-186">**TTL**</span></span>|<span data-ttu-id="8a026-187">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="8a026-187">**Refers to Host Name**</span></span>|<span data-ttu-id="8a026-188">**Altro host**</span><span class="sxs-lookup"><span data-stu-id="8a026-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8a026-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="8a026-189">autodiscover</span></span>  <br/> |<span data-ttu-id="8a026-190">3600</span><span class="sxs-lookup"><span data-stu-id="8a026-190">3600</span></span>  <br/> |<span data-ttu-id="8a026-191">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="8a026-191">@ (none)</span></span>  <br/> |<span data-ttu-id="8a026-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="8a026-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="8a026-193">sip</span><span class="sxs-lookup"><span data-stu-id="8a026-193">sip</span></span>  <br/> |<span data-ttu-id="8a026-194">3600</span><span class="sxs-lookup"><span data-stu-id="8a026-194">3600</span></span>  <br/> |<span data-ttu-id="8a026-195">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="8a026-195">@ (none)</span></span>  <br/> |<span data-ttu-id="8a026-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a026-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8a026-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8a026-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="8a026-198">3600</span><span class="sxs-lookup"><span data-stu-id="8a026-198">3600</span></span>  <br/> |<span data-ttu-id="8a026-199">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="8a026-199">@ (none)</span></span>  <br/> | <span data-ttu-id="8a026-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a026-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="8a026-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="8a026-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="8a026-202">3600</span><span class="sxs-lookup"><span data-stu-id="8a026-202">3600</span></span>  <br/> |<span data-ttu-id="8a026-203">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="8a026-203">@ (none)</span></span>  <br/> |<span data-ttu-id="8a026-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="8a026-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="8a026-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="8a026-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="8a026-206">3600</span><span class="sxs-lookup"><span data-stu-id="8a026-206">3600</span></span>  <br/> |<span data-ttu-id="8a026-207">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="8a026-207">@ (none)</span></span>  <br/> |<span data-ttu-id="8a026-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8a026-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="8a026-209">msoid</span><span class="sxs-lookup"><span data-stu-id="8a026-209">msoid</span></span>  <br/> |<span data-ttu-id="8a026-210">3600</span><span class="sxs-lookup"><span data-stu-id="8a026-210">3600</span></span>  <br/> |<span data-ttu-id="8a026-211">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="8a026-211">@ (none)</span></span>  <br/> |<span data-ttu-id="8a026-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="8a026-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="8a026-213">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="8a026-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="8a026-214">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="8a026-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="8a026-215">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="8a026-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="8a026-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="8a026-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a026-217">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="8a026-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="8a026-218">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="8a026-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="8a026-219">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8a026-219">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="8a026-220">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="8a026-220">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="8a026-221">Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="8a026-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="8a026-222">Accedere per primo.</span><span class="sxs-lookup"><span data-stu-id="8a026-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="8a026-223">Nella pagina **account manager** selezionare i **nomi di dominio personali**.</span><span class="sxs-lookup"><span data-stu-id="8a026-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="8a026-224">In \* \* Manage \* My Domain \* \* \* selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="8a026-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="8a026-225">Nella pagina **Domain Names** , sotto **Text (TXT Records)**, fare clic su **Edit TXT Records**, quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8a026-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="8a026-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="8a026-226">**Host**</span></span>|<span data-ttu-id="8a026-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8a026-227">**TTL**</span></span>|<span data-ttu-id="8a026-228">**Text**</span><span class="sxs-lookup"><span data-stu-id="8a026-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="8a026-229">3600</span><span class="sxs-lookup"><span data-stu-id="8a026-229">3600</span></span>  <br/> |<span data-ttu-id="8a026-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="8a026-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="8a026-231">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="8a026-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="8a026-232">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="8a026-232">Select **Continue**.</span></span>

6. <span data-ttu-id="8a026-233">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="8a026-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="8a026-234">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="8a026-234">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="8a026-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="8a026-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8a026-236">Tenere presente che web.com è responsabile di rendere disponibile questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="8a026-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="8a026-237">Nel caso in cui si vedano discrepanze tra i passaggi seguenti e l'interfaccia utente di web.com (GUI) corrente, utilizzare la [community di Web.com](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="8a026-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="8a026-238">Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="8a026-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="8a026-239">Accedere per primo.</span><span class="sxs-lookup"><span data-stu-id="8a026-239">Log in first.</span></span>
      
2. <span data-ttu-id="8a026-240">Nella pagina **account manager** selezionare i **nomi di dominio personali**.</span><span class="sxs-lookup"><span data-stu-id="8a026-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="8a026-241">In \* \* Manage \* My Domain \* \* \* selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="8a026-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="8a026-242">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="8a026-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="8a026-243">In **servizio (record SRV)** fare clic su **Modifica record SRV**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8a026-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="8a026-244">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="8a026-244">**Service**</span></span>|<span data-ttu-id="8a026-245">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="8a026-245">**Protocol**</span></span>|<span data-ttu-id="8a026-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="8a026-246">**TTL**</span></span>|<span data-ttu-id="8a026-247">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="8a026-247">**Priority**</span></span>|<span data-ttu-id="8a026-248">**Peso**</span><span class="sxs-lookup"><span data-stu-id="8a026-248">**Weight**</span></span>|<span data-ttu-id="8a026-249">**Porta**</span><span class="sxs-lookup"><span data-stu-id="8a026-249">**Port**</span></span>|<span data-ttu-id="8a026-250">**Target**</span><span class="sxs-lookup"><span data-stu-id="8a026-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="8a026-251">_sip</span><span class="sxs-lookup"><span data-stu-id="8a026-251">_sip</span></span> |<span data-ttu-id="8a026-252">_tls</span><span class="sxs-lookup"><span data-stu-id="8a026-252">_tls</span></span> |<span data-ttu-id="8a026-253">3600</span><span class="sxs-lookup"><span data-stu-id="8a026-253">3600</span></span> | <span data-ttu-id="8a026-254">100</span><span class="sxs-lookup"><span data-stu-id="8a026-254">100</span></span>|<span data-ttu-id="8a026-255">1 </span><span class="sxs-lookup"><span data-stu-id="8a026-255">1</span></span> |<span data-ttu-id="8a026-256">443</span><span class="sxs-lookup"><span data-stu-id="8a026-256">443</span></span> |<span data-ttu-id="8a026-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a026-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="8a026-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="8a026-258">_sipfederationtls</span></span> |<span data-ttu-id="8a026-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="8a026-259">_tcp</span></span> |<span data-ttu-id="8a026-260">3600</span><span class="sxs-lookup"><span data-stu-id="8a026-260">3600</span></span> |<span data-ttu-id="8a026-261">100</span><span class="sxs-lookup"><span data-stu-id="8a026-261">100</span></span> |<span data-ttu-id="8a026-262">1 </span><span class="sxs-lookup"><span data-stu-id="8a026-262">1</span></span> |<span data-ttu-id="8a026-263">5061</span><span class="sxs-lookup"><span data-stu-id="8a026-263">5061</span></span> | <span data-ttu-id="8a026-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="8a026-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="8a026-265">Aggiungere l'altro record SRV scegliendo i valori della seconda riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="8a026-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="8a026-266">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="8a026-266">Select **Continue**.</span></span>

7. <span data-ttu-id="8a026-267">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="8a026-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="8a026-p116">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="8a026-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
