---
title: Creare record DNS in web.com per Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
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
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in web.com per Office 365.
ms.openlocfilehash: eb231f85e568e81a5e229f0533d8176feb590f48
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42249456"
---
# <a name="create-dns-records-at-webcom-for-office-365"></a><span data-ttu-id="f03ef-103">Creare record DNS in web.com per Office 365</span><span class="sxs-lookup"><span data-stu-id="f03ef-103">Create DNS records at web.com for Office 365</span></span>

 <span data-ttu-id="f03ef-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="f03ef-105">Se web.com è il provider di hosting DNS, seguire la procedura descritta in questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e così via.</span><span class="sxs-lookup"><span data-stu-id="f03ef-105">If web.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="f03ef-106">Dopo aver aggiunto questi record in web.com, il dominio sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f03ef-106">After you add these records at web.com, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="f03ef-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span><span class="sxs-lookup"><span data-stu-id="f03ef-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/a8178510-501d-4bd8-9921-b04f2e9517a5.aspx).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f03ef-p101">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f03ef-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="change-your-domains-nameserver-ns-records"></a><span data-ttu-id="f03ef-111">Modificare i record dei server dei nomi del dominio</span><span class="sxs-lookup"><span data-stu-id="f03ef-111">Change your domain's nameserver (NS) records</span></span>
<span data-ttu-id="f03ef-112"><a name="BKMK_Nameservers"> </a></span><span class="sxs-lookup"><span data-stu-id="f03ef-112"><a name="BKMK_Nameservers"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f03ef-113">È necessario eseguire questa procedura presso il registrar da cui è stato acquistato e registrato il dominio.</span><span class="sxs-lookup"><span data-stu-id="f03ef-113">You must perform this procedure at the domain registrar where you purchased and registered your domain.</span></span> 
  
<span data-ttu-id="f03ef-114">Quando è stato eseguito l'accesso a web.com, è stato aggiunto un dominio utilizzando il processo di **installazione** di Web.com.</span><span class="sxs-lookup"><span data-stu-id="f03ef-114">When you signed up for web.com, you added a domain by using the web.com **Setup** process.</span></span> 
  
<span data-ttu-id="f03ef-115">Per verificare e creare record DNS per il proprio dominio in Office 365, è innanzitutto necessario cambiare i server dei nomi presso il registrar in modo che utilizzino i server di gestione Web. com.</span><span class="sxs-lookup"><span data-stu-id="f03ef-115">To verify and create DNS records for your domain in Office 365, you first need to change the nameservers at your domain registrar so that they use web.com's nameservers.</span></span>
  
<span data-ttu-id="f03ef-116">Per modificare i server dei nomi del dominio presso il registrar, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="f03ef-116">To change your domain's name servers at your domain registrar's website yourself, follow these steps.</span></span>
  
1. <span data-ttu-id="f03ef-117">Trovare l'area del sito Web del registrar in cui è possibile modificare i server dei nomi per il dominio.</span><span class="sxs-lookup"><span data-stu-id="f03ef-117">Find the area on the domain registrar's website where you can edit the nameservers for your domain.</span></span>
    
2. <span data-ttu-id="f03ef-118">Creare due record dei server dei nomi usando i valori della tabella seguente oppure modificare quelli esistenti in modo che corrispondano a questi valori.</span><span class="sxs-lookup"><span data-stu-id="f03ef-118">Either create two nameserver records by using the values in the following table, or edit the existing nameserver records so that they match these values.</span></span>
    
    |||
    |:-----|:-----|
    |<span data-ttu-id="f03ef-119">Primo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="f03ef-119">First nameserver</span></span>  <br/> |<span data-ttu-id="f03ef-120">Utilizzare il valore del server dei nomi fornito da web.com.</span><span class="sxs-lookup"><span data-stu-id="f03ef-120">Use the nameserver value provided by web.com.</span></span>  <br/> |
    |<span data-ttu-id="f03ef-121">Secondo server dei nomi</span><span class="sxs-lookup"><span data-stu-id="f03ef-121">Second nameserver</span></span>  <br/> |<span data-ttu-id="f03ef-122">Utilizzare il valore del server dei nomi fornito da web.com.</span><span class="sxs-lookup"><span data-stu-id="f03ef-122">Use the nameserver value provided by web.com.</span></span>  <br/> |
   
    > [!TIP]
    > <span data-ttu-id="f03ef-123">You should use at least two name server records.</span><span class="sxs-lookup"><span data-stu-id="f03ef-123">You should use at least two name server records.</span></span> <span data-ttu-id="f03ef-124">Se sono elencati altri server dei nomi, è necessario eliminarli.</span><span class="sxs-lookup"><span data-stu-id="f03ef-124">If there are any other name servers listed, you should delete them.</span></span> 
  
3. <span data-ttu-id="f03ef-125">Salvare le modifiche apportate.</span><span class="sxs-lookup"><span data-stu-id="f03ef-125">Save your changes.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f03ef-p103">L'aggiornamento dei record dei server dei nomi nel sistema DNS di Internet può richiedere fino a diverse ore. Al termine, la posta elettronica e altri servizi di Office 365 verranno tutti impostati per funzionare con il dominio.</span><span class="sxs-lookup"><span data-stu-id="f03ef-p103">Your nameserver record updates may take up to several hours to update across the Internet's DNS system. Then your Office 365 email and other services will be all set to work with your domain.</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="f03ef-128">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="f03ef-128">Add a TXT record for verification</span></span>
<span data-ttu-id="f03ef-129"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="f03ef-129"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="f03ef-p104">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="f03ef-p104">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f03ef-p105">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="f03ef-p105">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="f03ef-134">Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="f03ef-134">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f03ef-135">Accedere per primo.</span><span class="sxs-lookup"><span data-stu-id="f03ef-135">Log in first.</span></span>
  
2. <span data-ttu-id="f03ef-136">Nella pagina **account manager** selezionare i **nomi di dominio personali**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-136">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f03ef-137">In \* \* Manage \* My Domain \* \* \* selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-137">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="f03ef-138">Nella pagina **Domain Names** , sotto **Text (TXT Records)**, fare clic su **Edit TXT Records**, quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f03ef-138">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="f03ef-139">**Host**</span><span class="sxs-lookup"><span data-stu-id="f03ef-139">**Host**</span></span>|<span data-ttu-id="f03ef-140">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f03ef-140">**TTL**</span></span>|<span data-ttu-id="f03ef-141">**Text**</span><span class="sxs-lookup"><span data-stu-id="f03ef-141">**Text**</span></span>|
    |:-----|:-----|:----|
    |@  <br/> |<span data-ttu-id="f03ef-142">3600</span><span class="sxs-lookup"><span data-stu-id="f03ef-142">3600</span></span>  <br/> |<span data-ttu-id="f03ef-143">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="f03ef-143">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="f03ef-p107">**Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="f03ef-p107">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
  
    
5. <span data-ttu-id="f03ef-147">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-147">Select **Continue**.</span></span>
  
  
6. <span data-ttu-id="f03ef-148">Attendere alcuni minuti prima di verificare il nuovo record TXT, in modo che il record appena creato possa essere aggiornato su Internet.</span><span class="sxs-lookup"><span data-stu-id="f03ef-148">Wait a few minutes before you verify your new TXT record, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="f03ef-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="f03ef-149">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="f03ef-150">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="f03ef-150">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="f03ef-151">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="f03ef-151">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="f03ef-152">Nella pagina **Domains** selezionare il dominio che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="f03ef-152">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="f03ef-153">Nella pagina **configurazione** , selezionare **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-153">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="f03ef-154">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-154">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="f03ef-p108">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f03ef-p108">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="f03ef-158">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="f03ef-158">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="f03ef-159"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="f03ef-159"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="f03ef-160">Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="f03ef-160">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f03ef-161">Accedere per primo.</span><span class="sxs-lookup"><span data-stu-id="f03ef-161">Log in first.</span></span>
  
2. <span data-ttu-id="f03ef-162">Nella pagina **account manager** selezionare i **nomi di dominio personali**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-162">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f03ef-163">In \* \* Manage \* My Domain \* \* \* selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-163">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="f03ef-164">In **server di posta elettronica (record MX)** fare clic su **Modifica record MX**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f03ef-164">Under **Mail Servers (MX Records)**, click **Edit MX Records**, and then select the values from the following table.</span></span> 
    
    |<span data-ttu-id="f03ef-165">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="f03ef-165">**Priority**</span></span>|<span data-ttu-id="f03ef-166">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f03ef-166">**TTL**</span></span>|<span data-ttu-id="f03ef-167">**Mail server**</span><span class="sxs-lookup"><span data-stu-id="f03ef-167">**Mail server**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="f03ef-168">1</span><span class="sxs-lookup"><span data-stu-id="f03ef-168">1</span></span>  <br/> <span data-ttu-id="f03ef-169">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="f03ef-169">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="f03ef-170">3600</span><span class="sxs-lookup"><span data-stu-id="f03ef-170">3600</span></span>  <br/> |<span data-ttu-id="f03ef-171">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f03ef-171">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="f03ef-172">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f03ef-172">**Note:** Get your  *\<domain-key\>*  from your Office 365 account.</span></span>   [<span data-ttu-id="f03ef-173">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="f03ef-173">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |
   

5. <span data-ttu-id="f03ef-174">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-174">Select **Save**.</span></span>
  
6. <span data-ttu-id="f03ef-175">Se nella sezione **MX Records** sono presenti altri record MX, selezionare la casella di controllo accanto al record in **Delete**e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-175">If there are any other MX records listed in the **MX Records** section, select the check box next to the record under **Delete**, and select **Save**.</span></span> 
  
7. <span data-ttu-id="f03ef-176">Nella schermata di conferma fare clic su **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-176">On the confirmation screen, select **Save changes**.</span></span> 

  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="f03ef-177">Aggiungere i sei record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="f03ef-177">Add the Six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="f03ef-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="f03ef-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="f03ef-179">Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="f03ef-179">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f03ef-180">You'll be prompted to log in first.</span><span class="sxs-lookup"><span data-stu-id="f03ef-180">You'll be prompted to log in first.</span></span>
     
2. <span data-ttu-id="f03ef-181">Nella pagina **account manager** selezionare i **nomi di dominio personali**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-181">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f03ef-182">In \* \* Manage \* My Domain \* \* \* selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-182">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

4. <span data-ttu-id="f03ef-183">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="f03ef-183">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="f03ef-184">In **alias host (record CNAME)** fare clic su **Modifica record CNAME**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f03ef-184">Under **Host Aliases (CNAME Records)**, click **Edit CNAME Records**, and then select the values from the following table.</span></span>
    
    
    |<span data-ttu-id="f03ef-185">**Alias**</span><span class="sxs-lookup"><span data-stu-id="f03ef-185">**Alias**</span></span>|<span data-ttu-id="f03ef-186">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f03ef-186">**TTL**</span></span>|<span data-ttu-id="f03ef-187">**Refers to Host Name**</span><span class="sxs-lookup"><span data-stu-id="f03ef-187">**Refers to Host Name**</span></span>|<span data-ttu-id="f03ef-188">**Altro host**</span><span class="sxs-lookup"><span data-stu-id="f03ef-188">**Other Host**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f03ef-189">autodiscover</span><span class="sxs-lookup"><span data-stu-id="f03ef-189">autodiscover</span></span>  <br/> |<span data-ttu-id="f03ef-190">3600</span><span class="sxs-lookup"><span data-stu-id="f03ef-190">3600</span></span>  <br/> |<span data-ttu-id="f03ef-191">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="f03ef-191">@ (none)</span></span>  <br/> |<span data-ttu-id="f03ef-192">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="f03ef-192">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="f03ef-193">sip</span><span class="sxs-lookup"><span data-stu-id="f03ef-193">sip</span></span>  <br/> |<span data-ttu-id="f03ef-194">3600</span><span class="sxs-lookup"><span data-stu-id="f03ef-194">3600</span></span>  <br/> |<span data-ttu-id="f03ef-195">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="f03ef-195">@ (none)</span></span>  <br/> |<span data-ttu-id="f03ef-196">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f03ef-196">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f03ef-197">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="f03ef-197">lyncdiscover</span></span>  <br/> |<span data-ttu-id="f03ef-198">3600</span><span class="sxs-lookup"><span data-stu-id="f03ef-198">3600</span></span>  <br/> |<span data-ttu-id="f03ef-199">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="f03ef-199">@ (none)</span></span>  <br/> | <span data-ttu-id="f03ef-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f03ef-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="f03ef-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="f03ef-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="f03ef-202">3600</span><span class="sxs-lookup"><span data-stu-id="f03ef-202">3600</span></span>  <br/> |<span data-ttu-id="f03ef-203">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="f03ef-203">@ (none)</span></span>  <br/> |<span data-ttu-id="f03ef-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="f03ef-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="f03ef-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="f03ef-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="f03ef-206">3600</span><span class="sxs-lookup"><span data-stu-id="f03ef-206">3600</span></span>  <br/> |<span data-ttu-id="f03ef-207">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="f03ef-207">@ (none)</span></span>  <br/> |<span data-ttu-id="f03ef-208">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="f03ef-208">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
    |<span data-ttu-id="f03ef-209">msoid</span><span class="sxs-lookup"><span data-stu-id="f03ef-209">msoid</span></span>  <br/> |<span data-ttu-id="f03ef-210">3600</span><span class="sxs-lookup"><span data-stu-id="f03ef-210">3600</span></span>  <br/> |<span data-ttu-id="f03ef-211">@ (nessuno)</span><span class="sxs-lookup"><span data-stu-id="f03ef-211">@ (none)</span></span>  <br/> |<span data-ttu-id="f03ef-212">clientconfig.microsoftonline-p.net</span><span class="sxs-lookup"><span data-stu-id="f03ef-212">clientconfig.microsoftonline-p.net</span></span>  <br/> |
    
  
5. <span data-ttu-id="f03ef-213">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-213">Select **Continue**.</span></span>
  
6. <span data-ttu-id="f03ef-214">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="f03ef-214">Add each of the other five CNAME records.</span></span>

    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="f03ef-215">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="f03ef-215">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="f03ef-216"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="f03ef-216"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f03ef-217">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="f03ef-217">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="f03ef-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="f03ef-218">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="f03ef-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="f03ef-219">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="f03ef-220">Al contrario, aggiungere i valori di Office 365 necessari al record corrente in modo che sia presente un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="f03ef-220">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="f03ef-221">Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="f03ef-221">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f03ef-222">Accedere per primo.</span><span class="sxs-lookup"><span data-stu-id="f03ef-222">Log in first.</span></span>
    
  
2. <span data-ttu-id="f03ef-223">Nella pagina **account manager** selezionare i **nomi di dominio personali**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-223">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f03ef-224">In \* \* Manage \* My Domain \* \* \* selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-224">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>

  
4. <span data-ttu-id="f03ef-225">Nella pagina **Domain Names** , sotto **Text (TXT Records)**, fare clic su **Edit TXT Records**, quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f03ef-225">On the **Domain Names** page, under **Text (TXT Records)**, click **Edit TXT Records**, and then select the values from the following table.</span></span>   
    
    |<span data-ttu-id="f03ef-226">**Host**</span><span class="sxs-lookup"><span data-stu-id="f03ef-226">**Host**</span></span>|<span data-ttu-id="f03ef-227">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f03ef-227">**TTL**</span></span>|<span data-ttu-id="f03ef-228">**Text**</span><span class="sxs-lookup"><span data-stu-id="f03ef-228">**Text**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="f03ef-229">3600</span><span class="sxs-lookup"><span data-stu-id="f03ef-229">3600</span></span>  <br/> |<span data-ttu-id="f03ef-230">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="f03ef-230">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="f03ef-231">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="f03ef-231">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>   |

 
5. <span data-ttu-id="f03ef-232">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-232">Select **Continue**.</span></span>

6. <span data-ttu-id="f03ef-233">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-233">Select **Save changes**.</span></span>
    

  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="f03ef-234">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="f03ef-234">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="f03ef-235"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="f03ef-235"><a name="BKMK_add_SRV"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="f03ef-236">Tenere presente che web.com è responsabile di rendere disponibile questa funzionalità.</span><span class="sxs-lookup"><span data-stu-id="f03ef-236">Please keep in mind that web.com is responsible for making this functionality available.</span></span> <span data-ttu-id="f03ef-237">Nel caso in cui si vedano discrepanze tra i passaggi seguenti e l'interfaccia utente di web.com (GUI) corrente, utilizzare la [community di Web.com](https://community.web.com.com/).</span><span class="sxs-lookup"><span data-stu-id="f03ef-237">In case you see discrepancies between the steps below and the current web.com GUI(Graphical User Interface), please leverage the [web.com Community](https://community.web.com.com/).</span></span> 

1. <span data-ttu-id="f03ef-238">Per iniziare, passare alla propria pagina dei domini su web.com usando [questo collegamento](https://checkout.web.com/manage-it/index.jsp).</span><span class="sxs-lookup"><span data-stu-id="f03ef-238">To get started, go to your domains page at web.com by using [this link](https://checkout.web.com/manage-it/index.jsp).</span></span> <span data-ttu-id="f03ef-239">Accedere per primo.</span><span class="sxs-lookup"><span data-stu-id="f03ef-239">Log in first.</span></span>
      
2. <span data-ttu-id="f03ef-240">Nella pagina **account manager** selezionare i **nomi di dominio personali**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-240">On the **Account Manager** page, select **My Domain Names**.</span></span> 
  
3. <span data-ttu-id="f03ef-241">In \* \* Manage \* My Domain \* \* \* selezionare **Edit Advanced DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-241">Under \*\*Manage \*my domain\*\*\*, select **Edit Advanced DNS Records**.</span></span>
  
4. <span data-ttu-id="f03ef-242">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="f03ef-242">Add the first of the two SRV records.</span></span>

    <span data-ttu-id="f03ef-243">In **servizio (record SRV)** fare clic su **Modifica record SRV**e quindi selezionare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f03ef-243">Under **Service (SRV Records)**, click **Edit SRV Records**, and then select the values from the following table.</span></span> 
        
    |<span data-ttu-id="f03ef-244">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="f03ef-244">**Service**</span></span>|<span data-ttu-id="f03ef-245">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="f03ef-245">**Protocol**</span></span>|<span data-ttu-id="f03ef-246">**TTL**</span><span class="sxs-lookup"><span data-stu-id="f03ef-246">**TTL**</span></span>|<span data-ttu-id="f03ef-247">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="f03ef-247">**Priority**</span></span>|<span data-ttu-id="f03ef-248">**Peso**</span><span class="sxs-lookup"><span data-stu-id="f03ef-248">**Weight**</span></span>|<span data-ttu-id="f03ef-249">**Port**</span><span class="sxs-lookup"><span data-stu-id="f03ef-249">**Port**</span></span>|<span data-ttu-id="f03ef-250">**Target**</span><span class="sxs-lookup"><span data-stu-id="f03ef-250">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="f03ef-251">_sip</span><span class="sxs-lookup"><span data-stu-id="f03ef-251">_sip</span></span> |<span data-ttu-id="f03ef-252">_tls</span><span class="sxs-lookup"><span data-stu-id="f03ef-252">_tls</span></span> |<span data-ttu-id="f03ef-253">3600</span><span class="sxs-lookup"><span data-stu-id="f03ef-253">3600</span></span> | <span data-ttu-id="f03ef-254">100</span><span class="sxs-lookup"><span data-stu-id="f03ef-254">100</span></span>|<span data-ttu-id="f03ef-255">1</span><span class="sxs-lookup"><span data-stu-id="f03ef-255">1</span></span> |<span data-ttu-id="f03ef-256">443</span><span class="sxs-lookup"><span data-stu-id="f03ef-256">443</span></span> |<span data-ttu-id="f03ef-257">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f03ef-257">sipfed.online.lync.com</span></span>  |
    |<span data-ttu-id="f03ef-258">_sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="f03ef-258">_sipfederationtls</span></span> |<span data-ttu-id="f03ef-259">_tcp</span><span class="sxs-lookup"><span data-stu-id="f03ef-259">_tcp</span></span> |<span data-ttu-id="f03ef-260">3600</span><span class="sxs-lookup"><span data-stu-id="f03ef-260">3600</span></span> |<span data-ttu-id="f03ef-261">100</span><span class="sxs-lookup"><span data-stu-id="f03ef-261">100</span></span> |<span data-ttu-id="f03ef-262">1</span><span class="sxs-lookup"><span data-stu-id="f03ef-262">1</span></span> |<span data-ttu-id="f03ef-263">5061</span><span class="sxs-lookup"><span data-stu-id="f03ef-263">5061</span></span> | <span data-ttu-id="f03ef-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="f03ef-264">sipfed.online.lync.com</span></span> |

  
5. <span data-ttu-id="f03ef-265">Aggiungere l'altro record SRV scegliendo i valori della seconda riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="f03ef-265">Add the other SRV record by choosing the values from the second row of the table.</span></span> 
  
6. <span data-ttu-id="f03ef-266">Selezionare **continua**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-266">Select **Continue**.</span></span>

7. <span data-ttu-id="f03ef-267">Selezionare **Salva modifiche**.</span><span class="sxs-lookup"><span data-stu-id="f03ef-267">Select **Save changes**.</span></span>

    
> [!NOTE]
>  <span data-ttu-id="f03ef-p116">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="f03ef-p116">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
