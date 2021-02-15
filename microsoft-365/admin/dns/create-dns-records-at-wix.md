---
title: Creare record DNS in Wix per Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Informazioni su come verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e altri servizi in Wix per Microsoft.
ms.openlocfilehash: 01317f7e2da87b532c93f12269fd65b7d4fe2dd6
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49656880"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="46a72-103">Creare record DNS in Wix per Microsoft</span><span class="sxs-lookup"><span data-stu-id="46a72-103">Create DNS records at Wix for Microsoft</span></span>

<span data-ttu-id="46a72-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="46a72-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="46a72-105">Se Wix è il provider di hosting DNS in uso, seguire i passaggi indicati in questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="46a72-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>

<span data-ttu-id="46a72-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="46a72-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="46a72-107">[Aggiungere un record TXT a scopo di verifica](#add-a-txt-record-for-verification).</span><span class="sxs-lookup"><span data-stu-id="46a72-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="46a72-108">[Aggiungere un record MX in modo che la posta elettronica per il dominio venga inviata a Microsoft.](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft)</span><span class="sxs-lookup"><span data-stu-id="46a72-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="46a72-109">[Aggiungere i cinque record CNAME necessari per Microsoft.](#add-the-five-cname-records-that-are-required-for-microsoft)</span><span class="sxs-lookup"><span data-stu-id="46a72-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="46a72-110">[Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span><span class="sxs-lookup"><span data-stu-id="46a72-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="46a72-111">[Aggiungere i due record SRV necessari per Microsoft.](#add-the-two-srv-records-that-are-required-for-microsoft)</span><span class="sxs-lookup"><span data-stu-id="46a72-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="46a72-112">Dopo aver aggiunto questi record in Wix, il dominio sarà configurato per l'utilizzo con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="46a72-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="46a72-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="46a72-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="46a72-116">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="46a72-116">Add a TXT record for verification</span></span>
<span data-ttu-id="46a72-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="46a72-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="46a72-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="46a72-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="46a72-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="46a72-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 

> [!NOTE]
> <span data-ttu-id="46a72-122">WIX non supporta le voci DNS per i sottodomini.</span><span class="sxs-lookup"><span data-stu-id="46a72-122">WIX does not support DNS entries for subdomains.</span></span>
  
1. <span data-ttu-id="46a72-123">Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="46a72-123">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="46a72-124">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="46a72-124">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="46a72-125">Nell'area Avanzate della  pagina **My Domains** selezionare il pulsante **Edit DNS.**</span><span class="sxs-lookup"><span data-stu-id="46a72-125">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="46a72-126">Selezionare **+ Aggiungi un altro** nella riga TXT **(Text)** dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="46a72-126">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="46a72-127">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="46a72-127">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
   ||||
   |:-----|:-----|:-----|
   | <span data-ttu-id="46a72-128">Nome host</span><span class="sxs-lookup"><span data-stu-id="46a72-128">Host Name</span></span> <br/> | <span data-ttu-id="46a72-129">TXT Value</span><span class="sxs-lookup"><span data-stu-id="46a72-129">TXT Value</span></span> <br/> | <span data-ttu-id="46a72-130">TTL</span><span class="sxs-lookup"><span data-stu-id="46a72-130">TTL</span></span> <br/> |
   |<span data-ttu-id="46a72-131">Popolato automaticamente</span><span class="sxs-lookup"><span data-stu-id="46a72-131">Automatically populated</span></span>  <br/> |<span data-ttu-id="46a72-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="46a72-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="46a72-133">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="46a72-133">**Note:** This is an example.</span></span> <span data-ttu-id="46a72-134">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="46a72-134">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="46a72-135">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="46a72-135">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="46a72-136">1 ora</span><span class="sxs-lookup"><span data-stu-id="46a72-136">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="46a72-137">Selezionare il **pulsante Salva DNS** nella parte superiore dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="46a72-137">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="46a72-138">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="46a72-138">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="46a72-139">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="46a72-139">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="46a72-140">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="46a72-140">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="46a72-141">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="46a72-141">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="46a72-142">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="46a72-142">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
3. <span data-ttu-id="46a72-143">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="46a72-143">On the **Setup** page, select **Start setup**.</span></span>
   
4. <span data-ttu-id="46a72-144">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="46a72-144">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="46a72-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="46a72-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 

  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="46a72-148">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="46a72-148">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="46a72-149"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="46a72-149"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="46a72-150">Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="46a72-150">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="46a72-151">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="46a72-151">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="46a72-152">Nell'area Cassette postali  della pagina **My Domains** selezionare il collegamento Configure your **MX records.**</span><span class="sxs-lookup"><span data-stu-id="46a72-152">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="46a72-153">Scegliere **Altro** **dall'elenco** a discesa Provider di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="46a72-153">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="46a72-154">Selezionare **+ Aggiungi un altro**.</span><span class="sxs-lookup"><span data-stu-id="46a72-154">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="46a72-155">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="46a72-155">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="46a72-156">Nome host</span><span class="sxs-lookup"><span data-stu-id="46a72-156">Host Name</span></span> | <span data-ttu-id="46a72-157">Points to </span><span class="sxs-lookup"><span data-stu-id="46a72-157">Points to</span></span> | <span data-ttu-id="46a72-158">Priority</span><span class="sxs-lookup"><span data-stu-id="46a72-158">Priority</span></span> | <span data-ttu-id="46a72-159">TTL</span><span class="sxs-lookup"><span data-stu-id="46a72-159">TTL</span></span> |
   |:-----|:-----|:-----|:-----|
   |<span data-ttu-id="46a72-160">Popolato automaticamente</span><span class="sxs-lookup"><span data-stu-id="46a72-160">Automatically populated</span></span> <br/> | <span data-ttu-id="46a72-161">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="46a72-161">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="46a72-162">**Nota:** Ottenere il  *\<domain-key\>*  proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="46a72-162">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="46a72-163">Come trovarla</span><span class="sxs-lookup"><span data-stu-id="46a72-163">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="46a72-164">0</span><span class="sxs-lookup"><span data-stu-id="46a72-164">0</span></span>  <br/> <span data-ttu-id="46a72-165">Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="46a72-165">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="46a72-166">1 ora</span><span class="sxs-lookup"><span data-stu-id="46a72-166">1 Hour</span></span>|
   
6. <span data-ttu-id="46a72-167">Se sono elencati altri record MX, eliminarli ognuno.</span><span class="sxs-lookup"><span data-stu-id="46a72-167">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="46a72-168">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="46a72-168">Select **OK**.</span></span>
    
8. <span data-ttu-id="46a72-169">Nella finestra di dialogo di conferma selezionare **OK.**</span><span class="sxs-lookup"><span data-stu-id="46a72-169">In the confirmation dialog box, select **OK**.</span></span>
    
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="46a72-170">Aggiungere i cinque record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="46a72-170">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="46a72-171"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="46a72-171"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="46a72-p109">Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="46a72-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="46a72-174">Nell'area Avanzate della  pagina **My Domains** selezionare il pulsante **Edit DNS.**</span><span class="sxs-lookup"><span data-stu-id="46a72-174">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="46a72-175">Selezionare **+ Aggiungi un altro** nella riga **CNAME (Aliases)** dell'editor DNS per ogni record CNAME.</span><span class="sxs-lookup"><span data-stu-id="46a72-175">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="46a72-176">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="46a72-176">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="46a72-177">Nome host</span><span class="sxs-lookup"><span data-stu-id="46a72-177">Host Name</span></span> | <span data-ttu-id="46a72-178">Points to </span><span class="sxs-lookup"><span data-stu-id="46a72-178">Points to</span></span> | <span data-ttu-id="46a72-179">TTL</span><span class="sxs-lookup"><span data-stu-id="46a72-179">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="46a72-180">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="46a72-180">autodiscover</span></span>  <br/> |<span data-ttu-id="46a72-181">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="46a72-181">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="46a72-182">1 ora</span><span class="sxs-lookup"><span data-stu-id="46a72-182">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="46a72-183">sip</span><span class="sxs-lookup"><span data-stu-id="46a72-183">sip</span></span>  <br/> |<span data-ttu-id="46a72-184">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="46a72-184">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="46a72-185">1 ora</span><span class="sxs-lookup"><span data-stu-id="46a72-185">1 Hour</span></span> <br/> |
   |<span data-ttu-id="46a72-186">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="46a72-186">lyncdiscover</span></span>  <br/> |<span data-ttu-id="46a72-187">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="46a72-187">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="46a72-188">1 ora</span><span class="sxs-lookup"><span data-stu-id="46a72-188">1 Hour</span></span>  <br/> |
   |<span data-ttu-id="46a72-189">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="46a72-189">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="46a72-190">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="46a72-190">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="46a72-191">1 ora</span><span class="sxs-lookup"><span data-stu-id="46a72-191">1 Hour</span></span> <br/> |
   |<span data-ttu-id="46a72-192">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="46a72-192">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="46a72-193">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="46a72-193">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="46a72-194">1 Hour</span><span class="sxs-lookup"><span data-stu-id="46a72-194">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="46a72-195">Selezionare il **pulsante Salva DNS** nella parte superiore dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="46a72-195">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="46a72-196">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="46a72-196">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="46a72-197">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="46a72-197">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="46a72-198"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="46a72-198"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="46a72-199">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="46a72-199">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="46a72-200">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="46a72-200">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="46a72-201">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="46a72-201">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="46a72-202">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="46a72-202">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="46a72-203">Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="46a72-203">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="46a72-204">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="46a72-204">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="46a72-205">Nell'area Avanzate della  pagina **My Domains** selezionare il pulsante **Edit DNS.**</span><span class="sxs-lookup"><span data-stu-id="46a72-205">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="46a72-206">Selezionare **+ Aggiungi un altro** nella riga TXT **(Text)** dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="46a72-206">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="46a72-207">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="46a72-207">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="46a72-208">Nome host</span><span class="sxs-lookup"><span data-stu-id="46a72-208">Host Name</span></span> | <span data-ttu-id="46a72-209">TXT Value</span><span class="sxs-lookup"><span data-stu-id="46a72-209">TXT Value</span></span> | <span data-ttu-id="46a72-210">TTL</span><span class="sxs-lookup"><span data-stu-id="46a72-210">TTL</span></span> |
   |:-----|:-----|:-----|
   |<span data-ttu-id="46a72-211">[lasciare vuoto]</span><span class="sxs-lookup"><span data-stu-id="46a72-211">[leave this blank]</span></span>  <br/> |<span data-ttu-id="46a72-212">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="46a72-212">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="46a72-213">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="46a72-213">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="46a72-214">TXT</span><span class="sxs-lookup"><span data-stu-id="46a72-214">TXT</span></span>  <br/> | <span data-ttu-id="46a72-215">1 Hour</span><span class="sxs-lookup"><span data-stu-id="46a72-215">1 Hour</span></span> |
   
5. <span data-ttu-id="46a72-216">Selezionare il **pulsante Salva DNS** nella parte superiore dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="46a72-216">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="46a72-217">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="46a72-217">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="46a72-218">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="46a72-218">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="46a72-219"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="46a72-219"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="46a72-220">Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="46a72-220">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="46a72-221">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="46a72-221">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="46a72-222">Nell'area Avanzate della  pagina **My Domains** selezionare il pulsante **Edit DNS.**</span><span class="sxs-lookup"><span data-stu-id="46a72-222">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="46a72-223">Selezionare **+ Aggiungi un altro** nella riga **SRV** dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="46a72-223">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="46a72-224">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="46a72-224">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
   | <span data-ttu-id="46a72-225">Servizio</span><span class="sxs-lookup"><span data-stu-id="46a72-225">Service</span></span> | <span data-ttu-id="46a72-226">Protocollo</span><span class="sxs-lookup"><span data-stu-id="46a72-226">Protocol</span></span> | <span data-ttu-id="46a72-227">Nome</span><span class="sxs-lookup"><span data-stu-id="46a72-227">Name</span></span> | <span data-ttu-id="46a72-228">Peso</span><span class="sxs-lookup"><span data-stu-id="46a72-228">Weight</span></span> | <span data-ttu-id="46a72-229">Porta</span><span class="sxs-lookup"><span data-stu-id="46a72-229">Port</span></span> | <span data-ttu-id="46a72-230">Destinazione</span><span class="sxs-lookup"><span data-stu-id="46a72-230">Target</span></span> | <span data-ttu-id="46a72-231">Priority</span><span class="sxs-lookup"><span data-stu-id="46a72-231">Priority</span></span> | <span data-ttu-id="46a72-232">TTL</span><span class="sxs-lookup"><span data-stu-id="46a72-232">TTL</span></span> |
   |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
   |<span data-ttu-id="46a72-233">sip</span><span class="sxs-lookup"><span data-stu-id="46a72-233">sip</span></span>  |<span data-ttu-id="46a72-234">tls</span><span class="sxs-lookup"><span data-stu-id="46a72-234">tls</span></span>  |<span data-ttu-id="46a72-235">Popolato automaticamente</span><span class="sxs-lookup"><span data-stu-id="46a72-235">Automatically populated</span></span> |<span data-ttu-id="46a72-236">1 </span><span class="sxs-lookup"><span data-stu-id="46a72-236">1</span></span>  |<span data-ttu-id="46a72-237">443</span><span class="sxs-lookup"><span data-stu-id="46a72-237">443</span></span>   |<span data-ttu-id="46a72-238">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="46a72-238">sipdir.online.lync.com</span></span> |<span data-ttu-id="46a72-239">100</span><span class="sxs-lookup"><span data-stu-id="46a72-239">100</span></span> |<span data-ttu-id="46a72-240">1 Hour</span><span class="sxs-lookup"><span data-stu-id="46a72-240">1 Hour</span></span> |
   |<span data-ttu-id="46a72-241">sipfed</span><span class="sxs-lookup"><span data-stu-id="46a72-241">sipfed</span></span>|<span data-ttu-id="46a72-242">tcp</span><span class="sxs-lookup"><span data-stu-id="46a72-242">tcp</span></span> |<span data-ttu-id="46a72-243">Popolato automaticamente</span><span class="sxs-lookup"><span data-stu-id="46a72-243">Automatically populated</span></span>|<span data-ttu-id="46a72-244">1 </span><span class="sxs-lookup"><span data-stu-id="46a72-244">1</span></span> |<span data-ttu-id="46a72-245">5061</span><span class="sxs-lookup"><span data-stu-id="46a72-245">5061</span></span> |<span data-ttu-id="46a72-246">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="46a72-246">sipfed.online.lync.com</span></span>|<span data-ttu-id="46a72-247">100</span><span class="sxs-lookup"><span data-stu-id="46a72-247">100</span></span> | <span data-ttu-id="46a72-248">1 Hour</span><span class="sxs-lookup"><span data-stu-id="46a72-248">1 Hour</span></span> |
   
5. <span data-ttu-id="46a72-249">Selezionare il **pulsante Salva DNS** nella parte superiore dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="46a72-249">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="46a72-250">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="46a72-250">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
> <span data-ttu-id="46a72-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="46a72-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
