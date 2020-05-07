---
title: Creare record DNS in WiX per Microsoft
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
ms.assetid: 7173c635-58b3-400f-95e0-97abe915565e
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in WiX per Microsoft.
ms.openlocfilehash: 6f88cc65ae19f747a9fc3740ea1578f30d18b5e2
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2020
ms.locfileid: "44048856"
---
# <a name="create-dns-records-at-wix-for-microsoft"></a><span data-ttu-id="dca42-103">Creare record DNS in WiX per Microsoft</span><span class="sxs-lookup"><span data-stu-id="dca42-103">Create DNS records at Wix for Microsoft</span></span>

 <span data-ttu-id="dca42-104">Se non si trova ciò che si sta cercando, **[vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="dca42-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="dca42-105">Se Wix è il provider di hosting DNS in uso, seguire i passaggi indicati in questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="dca42-105">If Wix is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="dca42-106">Ecco i principali record da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="dca42-106">These are the main records to add.</span></span> 
  
- <span data-ttu-id="dca42-107">[Aggiungere un record TXT a scopo di verifica](#add-a-txt-record-for-verification).</span><span class="sxs-lookup"><span data-stu-id="dca42-107">[Add a TXT record for verification](#add-a-txt-record-for-verification).</span></span>
    
- <span data-ttu-id="dca42-108">[Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span><span class="sxs-lookup"><span data-stu-id="dca42-108">[Add an MX record so email for your domain will come to Microsoft](#add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft).</span></span>
    
- <span data-ttu-id="dca42-109">[Aggiungere i cinque record CNAME necessari per Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="dca42-109">[Add the five CNAME records that are required for Microsoft](#add-the-five-cname-records-that-are-required-for-microsoft).</span></span>
    
- <span data-ttu-id="dca42-110">[Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span><span class="sxs-lookup"><span data-stu-id="dca42-110">[Add a TXT record for SPF to help prevent email spam](#add-a-txt-record-for-spf-to-help-prevent-email-spam).</span></span>
    
- <span data-ttu-id="dca42-111">[Aggiungere i due record SRV necessari per Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span><span class="sxs-lookup"><span data-stu-id="dca42-111">[Add the two SRV records that are required for Microsoft](#add-the-two-srv-records-that-are-required-for-microsoft).</span></span>
    
<span data-ttu-id="dca42-112">Dopo aver aggiunto questi record in WiX, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dca42-112">After you add these records at Wix, your domain will be set up to work with Microsoft services.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="dca42-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dca42-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="dca42-116">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="dca42-116">Add a TXT record for verification</span></span>
<span data-ttu-id="dca42-117"><a name="BKMK_txt"> </a></span><span class="sxs-lookup"><span data-stu-id="dca42-117"><a name="BKMK_txt"> </a></span></span>

<span data-ttu-id="dca42-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="dca42-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dca42-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="dca42-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="dca42-122">Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="dca42-122">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="dca42-123">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="dca42-123">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="dca42-124">Nella pagina **domini personali** , nell'area **Avanzate** , selezionare il pulsante **modifica DNS** .</span><span class="sxs-lookup"><span data-stu-id="dca42-124">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="dca42-125">Selezionare **+ Aggiungi un altro** nella riga **txt (testo)** dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="dca42-125">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="dca42-126">In the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="dca42-126">In the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
||||
|:-----|:-----|:-----|
|<span data-ttu-id="dca42-127">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="dca42-127">**Host Name**</span></span> <br/> |<span data-ttu-id="dca42-128">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="dca42-128">**TXT Value**</span></span> <br/> |<span data-ttu-id="dca42-129">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dca42-129">**TTL**</span></span> <br/> |
|<span data-ttu-id="dca42-130">Popolamento automatico</span><span class="sxs-lookup"><span data-stu-id="dca42-130">Automatically populated</span></span>  <br/> |<span data-ttu-id="dca42-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="dca42-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="dca42-132">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="dca42-132">**Note:** This is an example.</span></span> <span data-ttu-id="dca42-133">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="dca42-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>  [<span data-ttu-id="dca42-134">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="dca42-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)|<span data-ttu-id="dca42-135">1 Hour</span><span class="sxs-lookup"><span data-stu-id="dca42-135">1 Hour</span></span> <br/> |          |
   
5. <span data-ttu-id="dca42-136">Selezionare il pulsante **Salva DNS** nella parte superiore dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="dca42-136">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="dca42-137">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="dca42-137">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="dca42-138">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="dca42-138">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="dca42-139">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="dca42-139">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="dca42-140">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="dca42-140">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="dca42-141">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="dca42-141">On the **Domains** page, select the domain that you are verifying.</span></span> 
  
  
3. <span data-ttu-id="dca42-142">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="dca42-142">On the **Setup** page, select **Start setup**.</span></span>
   
  
4. <span data-ttu-id="dca42-143">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="dca42-143">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="dca42-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dca42-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="dca42-147">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="dca42-147">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="dca42-148"><a name="BKMK_mx"> </a></span><span class="sxs-lookup"><span data-stu-id="dca42-148"><a name="BKMK_mx"> </a></span></span>

1. <span data-ttu-id="dca42-149">Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="dca42-149">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="dca42-150">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="dca42-150">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="dca42-151">Nella sezione **cassette postali** della pagina **My Domains** selezionare il collegamento **Configure Your MX Records** .</span><span class="sxs-lookup"><span data-stu-id="dca42-151">On the **My Domains** page, in the **Mailboxes** area, select the **Configure your MX records** link.</span></span> 
    
3. <span data-ttu-id="dca42-152">Scegliere **altro** dall'elenco a discesa **provider di posta elettronica** .</span><span class="sxs-lookup"><span data-stu-id="dca42-152">Choose **Other** from the **Your Email Provider** drop-down list.</span></span> 
    
4. <span data-ttu-id="dca42-153">Seleziona **+ Aggiungi un altro**.</span><span class="sxs-lookup"><span data-stu-id="dca42-153">Select **+ Add another**.</span></span>
    
5. <span data-ttu-id="dca42-154">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="dca42-154">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="dca42-155">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="dca42-155">**Host Name**</span></span>|<span data-ttu-id="dca42-156">**Points to**</span><span class="sxs-lookup"><span data-stu-id="dca42-156">**Points to**</span></span>|<span data-ttu-id="dca42-157">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="dca42-157">**Priority**</span></span>|<span data-ttu-id="dca42-158">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dca42-158">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dca42-159">Popolamento automatico</span><span class="sxs-lookup"><span data-stu-id="dca42-159">Automatically populated</span></span> <br/> | <span data-ttu-id="dca42-160">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dca42-160">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="dca42-161">**Nota:** Ottenere la propria \* \<chiave\> di dominio\* dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dca42-161">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>   [<span data-ttu-id="dca42-162">Come trovarla</span><span class="sxs-lookup"><span data-stu-id="dca42-162">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md) |<span data-ttu-id="dca42-163">0</span><span class="sxs-lookup"><span data-stu-id="dca42-163">0</span></span>  <br/> <span data-ttu-id="dca42-164">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="dca42-164">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> | <span data-ttu-id="dca42-165">1 Hour</span><span class="sxs-lookup"><span data-stu-id="dca42-165">1 Hour</span></span>|
   
6. <span data-ttu-id="dca42-166">Se sono elencati altri record MX, eliminarli tutti.</span><span class="sxs-lookup"><span data-stu-id="dca42-166">If there are any other MX records listed, delete each of them.</span></span> 
    
7. <span data-ttu-id="dca42-167">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="dca42-167">Select **OK**.</span></span>
    
8. <span data-ttu-id="dca42-168">Nella finestra di dialogo di conferma fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="dca42-168">In the confirmation dialog box, select **OK**.</span></span>
    
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="dca42-169">Aggiungere i cinque record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="dca42-169">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="dca42-170"><a name="BKMK_cname"> </a></span><span class="sxs-lookup"><span data-stu-id="dca42-170"><a name="BKMK_cname"> </a></span></span>

1. <span data-ttu-id="dca42-p109">Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="dca42-p109">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="dca42-173">Nella pagina **domini personali** , nell'area **Avanzate** , selezionare il pulsante **modifica DNS** .</span><span class="sxs-lookup"><span data-stu-id="dca42-173">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="dca42-174">Selezionare **+ Aggiungi un altro** nella riga **CNAME (aliases)** dell'editor DNS per ogni record CNAME.</span><span class="sxs-lookup"><span data-stu-id="dca42-174">Select **+ Add another** in the **CNAME (Aliases)** row of the DNS editor for each CNAME record.</span></span> 
    
4. <span data-ttu-id="dca42-175">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="dca42-175">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="dca42-176">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="dca42-176">**Host Name**</span></span>|<span data-ttu-id="dca42-177">**Punta a**</span><span class="sxs-lookup"><span data-stu-id="dca42-177">**Points to**</span></span>|<span data-ttu-id="dca42-178">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dca42-178">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dca42-179">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="dca42-179">autodiscover</span></span>  <br/> |<span data-ttu-id="dca42-180">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="dca42-180">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="dca42-181">1 Hour</span><span class="sxs-lookup"><span data-stu-id="dca42-181">1 Hour</span></span>  <br/> |
|<span data-ttu-id="dca42-182">sip</span><span class="sxs-lookup"><span data-stu-id="dca42-182">sip</span></span>  <br/> |<span data-ttu-id="dca42-183">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dca42-183">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="dca42-184">1 Hour</span><span class="sxs-lookup"><span data-stu-id="dca42-184">1 Hour</span></span> <br/> |
|<span data-ttu-id="dca42-185">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="dca42-185">lyncdiscover</span></span>  <br/> |<span data-ttu-id="dca42-186">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dca42-186">webdir.online.lync.com</span></span>   <br/> |<span data-ttu-id="dca42-187">1 Hour</span><span class="sxs-lookup"><span data-stu-id="dca42-187">1 Hour</span></span>  <br/> |
|<span data-ttu-id="dca42-188">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="dca42-188">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="dca42-189">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="dca42-189">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="dca42-190">1 ora</span><span class="sxs-lookup"><span data-stu-id="dca42-190">1 Hour</span></span> <br/> |
|<span data-ttu-id="dca42-191">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="dca42-191">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="dca42-192">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="dca42-192">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="dca42-193">1 Hour</span><span class="sxs-lookup"><span data-stu-id="dca42-193">1 Hour</span></span>  <br/> |
   
5. <span data-ttu-id="dca42-194">Selezionare il pulsante **Salva DNS** nella parte superiore dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="dca42-194">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="dca42-195">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="dca42-195">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="dca42-196">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="dca42-196">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="dca42-197"><a name="BKMK_spf"> </a></span><span class="sxs-lookup"><span data-stu-id="dca42-197"><a name="BKMK_spf"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="dca42-198">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="dca42-198">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="dca42-199">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="dca42-199">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="dca42-200">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="dca42-200">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="dca42-201">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="dca42-201">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>  
  
1. <span data-ttu-id="dca42-202">Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="dca42-202">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="dca42-203">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="dca42-203">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="dca42-204">Nella pagina **domini personali** , nell'area **Avanzate** , selezionare il pulsante **modifica DNS** .</span><span class="sxs-lookup"><span data-stu-id="dca42-204">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="dca42-205">Selezionare **+ Aggiungi un altro** nella riga **txt (testo)** dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="dca42-205">Select **+ Add another** in the **TXT (Text)** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="dca42-206">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="dca42-206">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="dca42-207">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="dca42-207">**Host Name**</span></span>|<span data-ttu-id="dca42-208">**TXT Value**</span><span class="sxs-lookup"><span data-stu-id="dca42-208">**TXT Value**</span></span>|<span data-ttu-id="dca42-209">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dca42-209">**TTL**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dca42-210">[lasciare vuota questa pagina]</span><span class="sxs-lookup"><span data-stu-id="dca42-210">[leave this blank]</span></span>  <br/> |<span data-ttu-id="dca42-211">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="dca42-211">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="dca42-212">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="dca42-212">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span><br/> |<span data-ttu-id="dca42-213">TXT</span><span class="sxs-lookup"><span data-stu-id="dca42-213">TXT</span></span>  <br/> | <span data-ttu-id="dca42-214">1 Hour</span><span class="sxs-lookup"><span data-stu-id="dca42-214">1 Hour</span></span> |
   
5. <span data-ttu-id="dca42-215">Selezionare il pulsante **Salva DNS** nella parte superiore dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="dca42-215">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="dca42-216">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="dca42-216">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="dca42-217">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="dca42-217">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="dca42-218"><a name="BKMK_srv"> </a></span><span class="sxs-lookup"><span data-stu-id="dca42-218"><a name="BKMK_srv"> </a></span></span>

1. <span data-ttu-id="dca42-219">Per iniziare, passare alla propria pagina dei domini su Wix usando [questo collegamento](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span><span class="sxs-lookup"><span data-stu-id="dca42-219">To get started, go to your domains page at Wix by using [this link](https://premium.wix.com/wix/api/mpContainerStaticController#/domains?referralAdditionalInfo=account).</span></span> <span data-ttu-id="dca42-220">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="dca42-220">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="dca42-221">Nella pagina **domini personali** , nell'area **Avanzate** , selezionare il pulsante **modifica DNS** .</span><span class="sxs-lookup"><span data-stu-id="dca42-221">On the **My Domains** page, in the **Advanced** area, select the **Edit DNS** button.</span></span> 
    
3. <span data-ttu-id="dca42-222">Selezionare **+ Aggiungi un altro** nella riga **SRV** dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="dca42-222">Select **+ Add another** in the **SRV** row of the DNS editor.</span></span> 
    
4. <span data-ttu-id="dca42-223">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente:</span><span class="sxs-lookup"><span data-stu-id="dca42-223">In the boxes for the new record, type or copy and paste the values from the following table:</span></span>
    
|<span data-ttu-id="dca42-224">**Servizio**</span><span class="sxs-lookup"><span data-stu-id="dca42-224">**Service**</span></span>|<span data-ttu-id="dca42-225">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="dca42-225">**Protocol**</span></span>|<span data-ttu-id="dca42-226">**Name**</span><span class="sxs-lookup"><span data-stu-id="dca42-226">**Name**</span></span>|<span data-ttu-id="dca42-227">**Peso**</span><span class="sxs-lookup"><span data-stu-id="dca42-227">**Weight**</span></span>|<span data-ttu-id="dca42-228">**Porta**</span><span class="sxs-lookup"><span data-stu-id="dca42-228">**Port**</span></span>|<span data-ttu-id="dca42-229">**Destinazione**</span><span class="sxs-lookup"><span data-stu-id="dca42-229">**Target**</span></span>|<span data-ttu-id="dca42-230">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="dca42-230">**Priority**</span></span>|<span data-ttu-id="dca42-231">**TTL**</span><span class="sxs-lookup"><span data-stu-id="dca42-231">**TTL**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dca42-232">sip</span><span class="sxs-lookup"><span data-stu-id="dca42-232">sip</span></span>  |<span data-ttu-id="dca42-233">tls</span><span class="sxs-lookup"><span data-stu-id="dca42-233">tls</span></span>  |<span data-ttu-id="dca42-234">Popolamento automatico</span><span class="sxs-lookup"><span data-stu-id="dca42-234">Automatically populated</span></span> |<span data-ttu-id="dca42-235">1</span><span class="sxs-lookup"><span data-stu-id="dca42-235">1</span></span>  |<span data-ttu-id="dca42-236">443</span><span class="sxs-lookup"><span data-stu-id="dca42-236">443</span></span>   |<span data-ttu-id="dca42-237">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dca42-237">sipdir.online.lync.com</span></span> |<span data-ttu-id="dca42-238">100</span><span class="sxs-lookup"><span data-stu-id="dca42-238">100</span></span> |<span data-ttu-id="dca42-239">1 Hour</span><span class="sxs-lookup"><span data-stu-id="dca42-239">1 Hour</span></span> |
|<span data-ttu-id="dca42-240">sipfed</span><span class="sxs-lookup"><span data-stu-id="dca42-240">sipfed</span></span>|<span data-ttu-id="dca42-241">tcp</span><span class="sxs-lookup"><span data-stu-id="dca42-241">tcp</span></span> |<span data-ttu-id="dca42-242">Popolamento automatico</span><span class="sxs-lookup"><span data-stu-id="dca42-242">Automatically populated</span></span>|<span data-ttu-id="dca42-243">1</span><span class="sxs-lookup"><span data-stu-id="dca42-243">1</span></span> |<span data-ttu-id="dca42-244">5061</span><span class="sxs-lookup"><span data-stu-id="dca42-244">5061</span></span> |<span data-ttu-id="dca42-245">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="dca42-245">sipfed.online.lync.com</span></span>|<span data-ttu-id="dca42-246">100</span><span class="sxs-lookup"><span data-stu-id="dca42-246">100</span></span> | <span data-ttu-id="dca42-247">1 Hour</span><span class="sxs-lookup"><span data-stu-id="dca42-247">1 Hour</span></span> |
   
5. <span data-ttu-id="dca42-248">Selezionare il pulsante **Salva DNS** nella parte superiore dell'editor DNS.</span><span class="sxs-lookup"><span data-stu-id="dca42-248">Select the **Save DNS** button at the top of the DNS editor.</span></span> 
    
6. <span data-ttu-id="dca42-249">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="dca42-249">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
> [!NOTE]
>  <span data-ttu-id="dca42-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="dca42-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

