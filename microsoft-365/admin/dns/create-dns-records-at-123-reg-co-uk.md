---
title: Creare record DNS in 123-reg.co.uk per Microsoft
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
ms.assetid: 1f2d08c9-2a88-4d2f-ae1f-e39f9e358b17
description: Informazioni su come verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e altri servizi 123-reg.co.uk per Microsoft.
ms.openlocfilehash: bde8003ad343680e8f499dd8ec1fb638f15080b1
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658316"
---
# <a name="create-dns-records-at-123-regcouk-for-microsoft"></a><span data-ttu-id="3b51c-103">Creare record DNS in 123-reg.co.uk per Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b51c-103">Create DNS records at 123-reg.co.uk for Microsoft</span></span>

 <span data-ttu-id="3b51c-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="3b51c-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3b51c-105">Se il provider di hosting DNS è 123-reg.co.uk, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="3b51c-105">If 123-reg.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="3b51c-106">Dopo aver aggiunto questi record in 123-reg.co.uk, il dominio sarà configurato per l'utilizzo con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b51c-106">After you add these records at 123-reg.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  
  
> [!NOTE]
> <span data-ttu-id="3b51c-p101">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3b51c-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="3b51c-110">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="3b51c-110">Add a TXT record for verification</span></span>
<span data-ttu-id="3b51c-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="3b51c-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="3b51c-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="3b51c-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="3b51c-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="3b51c-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="3b51c-p104">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3b51c-p104">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3b51c-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="3b51c-118">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3b51c-119">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="3b51c-119">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="3b51c-120">Nella pagina **Manage your DNS** selezionare la scheda Advanced **DNS.**</span><span class="sxs-lookup"><span data-stu-id="3b51c-120">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="3b51c-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3b51c-121">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3b51c-122">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3b51c-122">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="3b51c-123">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="3b51c-123">**Hostname**</span></span> <br/> |<span data-ttu-id="3b51c-124">**Type**</span><span class="sxs-lookup"><span data-stu-id="3b51c-124">**Type**</span></span> <br/> |<span data-ttu-id="3b51c-125">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="3b51c-125">**Destination TXT/SPF**</span></span> <br/> |
    |@  <br/> |<span data-ttu-id="3b51c-126">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="3b51c-126">TXT/SPF</span></span>  <br/> |<span data-ttu-id="3b51c-127">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="3b51c-127">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="3b51c-128">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="3b51c-128">**Note:** This is an example.</span></span> <span data-ttu-id="3b51c-129">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="3b51c-129">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="3b51c-130">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="3b51c-130">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
6. <span data-ttu-id="3b51c-131">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3b51c-131">Select **Add**.</span></span>
    
7. <span data-ttu-id="3b51c-132">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="3b51c-132">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="3b51c-133">Dopo aver aggiunto il record nel sito del registrar, si tornerà a Microsoft e si richiederà una ricerca per il record.</span><span class="sxs-lookup"><span data-stu-id="3b51c-133">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request a search for the record.</span></span>
  
<span data-ttu-id="3b51c-134">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="3b51c-134">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="3b51c-135">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="3b51c-135">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="3b51c-136">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="3b51c-136">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="3b51c-137">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="3b51c-137">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="3b51c-138">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="3b51c-138">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="3b51c-p106">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3b51c-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="3b51c-142">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b51c-142">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="3b51c-143"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="3b51c-143"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="3b51c-p107">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3b51c-p107">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3b51c-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="3b51c-146">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3b51c-147">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="3b51c-147">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="3b51c-148">Nella pagina **Manage your DNS** selezionare la scheda Advanced **DNS.**</span><span class="sxs-lookup"><span data-stu-id="3b51c-148">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="3b51c-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3b51c-149">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3b51c-150">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3b51c-150">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3b51c-151">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="3b51c-151">**Hostname**</span></span>|<span data-ttu-id="3b51c-152">**Type**</span><span class="sxs-lookup"><span data-stu-id="3b51c-152">**Type**</span></span>|<span data-ttu-id="3b51c-153">**Priority**</span><span class="sxs-lookup"><span data-stu-id="3b51c-153">**Priority**</span></span>|<span data-ttu-id="3b51c-154">**Destination MX**</span><span class="sxs-lookup"><span data-stu-id="3b51c-154">**Destination MX**</span></span>|
    |:-----|:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3b51c-155">MX</span><span class="sxs-lookup"><span data-stu-id="3b51c-155">MX</span></span>  <br/> |<span data-ttu-id="3b51c-156">1 </span><span class="sxs-lookup"><span data-stu-id="3b51c-156">1</span></span>  <br/> <span data-ttu-id="3b51c-157">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="3b51c-157">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> | <span data-ttu-id="3b51c-158">*\<domain-key\>*  .mail.protection.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3b51c-158">*\<domain-key\>*  .mail.protection.outlook.com.</span></span>  <br/> <span data-ttu-id="3b51c-159">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3b51c-159">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="3b51c-160">**Nota:** ottenere il valore \<domain-key\> dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="3b51c-160">**Note:** Get your \<domain-key\> from your Microsoft account.</span></span> [<span data-ttu-id="3b51c-161">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="3b51c-161">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
   
    ![Copiare e incollare valori dalla tabella](../../media/65366165-85a6-4a39-b9a7-6c5f47fbe790.png)
  
6. <span data-ttu-id="3b51c-163">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3b51c-163">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi.](../../media/a8ae6c0c-4365-4137-af8a-6e003996e3d0.png)
  
7. <span data-ttu-id="3b51c-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span><span class="sxs-lookup"><span data-stu-id="3b51c-165">If there are any other MX records, remove each one by choosing the **Delete (trash can)** icon for that record.</span></span> 
    
    ![Selezionare Elimina (icona del cestino)](../../media/3be635e6-b591-49af-8430-a158272834b4.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="3b51c-167">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b51c-167">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="3b51c-168"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="3b51c-168"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="3b51c-p109">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3b51c-p109">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3b51c-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="3b51c-171">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3b51c-172">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="3b51c-172">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="3b51c-173">Nella pagina **Manage your DNS** selezionare la scheda Advanced **DNS.**</span><span class="sxs-lookup"><span data-stu-id="3b51c-173">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="3b51c-174">Aggiungere il primo dei sei record CNAME.</span><span class="sxs-lookup"><span data-stu-id="3b51c-174">Add the first of the six CNAME records.</span></span>
    
    <span data-ttu-id="3b51c-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3b51c-175">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3b51c-176">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3b51c-176">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3b51c-177">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="3b51c-177">**Hostname**</span></span>|<span data-ttu-id="3b51c-178">**Type**</span><span class="sxs-lookup"><span data-stu-id="3b51c-178">**Type**</span></span>|<span data-ttu-id="3b51c-179">**Destination CNAME**</span><span class="sxs-lookup"><span data-stu-id="3b51c-179">**Destination CNAME**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="3b51c-180">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="3b51c-180">autodiscover</span></span>  <br/> |<span data-ttu-id="3b51c-181">CNAME</span><span class="sxs-lookup"><span data-stu-id="3b51c-181">CNAME</span></span>  <br/> |<span data-ttu-id="3b51c-182">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="3b51c-182">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="3b51c-183">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3b51c-183">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3b51c-184">sip</span><span class="sxs-lookup"><span data-stu-id="3b51c-184">sip</span></span>  <br/> |<span data-ttu-id="3b51c-185">CNAME</span><span class="sxs-lookup"><span data-stu-id="3b51c-185">CNAME</span></span>  <br/> |<span data-ttu-id="3b51c-186">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3b51c-186">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3b51c-187">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3b51c-187">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3b51c-188">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="3b51c-188">lyncdiscover</span></span>  <br/> |<span data-ttu-id="3b51c-189">CNAME</span><span class="sxs-lookup"><span data-stu-id="3b51c-189">CNAME</span></span>  <br/> |<span data-ttu-id="3b51c-190">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3b51c-190">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="3b51c-191">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3b51c-191">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3b51c-192">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="3b51c-192">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="3b51c-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="3b51c-193">CNAME</span></span>  <br/> |<span data-ttu-id="3b51c-194">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="3b51c-194">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="3b51c-195">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3b51c-195">**This value MUST end with a period (.)**</span></span> <br/> |
    |<span data-ttu-id="3b51c-196">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="3b51c-196">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="3b51c-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="3b51c-197">CNAME</span></span>  <br/> |<span data-ttu-id="3b51c-198">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="3b51c-198">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="3b51c-199">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3b51c-199">**This value MUST end with a period (.)**</span></span> <br/> |
   
    ![Copiare e incollare i valori dalla tabella](../../media/24bf388c-5f7f-4fc0-b4ec-4b17226b6246.png)
  
6. <span data-ttu-id="3b51c-201">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3b51c-201">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi.](../../media/825a9854-559d-4a22-90ac-5e7a0a54269a.png)
  
7. <span data-ttu-id="3b51c-203">Aggiungere gli altri cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="3b51c-203">Add the other five CNAME records.</span></span>
    
    <span data-ttu-id="3b51c-204">Nella sezione **Advanced DNS** creare un record utilizzando i valori della riga successiva della tabella e quindi selezionare di nuovo **Add** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="3b51c-204">In the **Advanced DNS** section, create a record using the values from the next row in the table, and then again select **Add** to complete that record.</span></span> 
    
    <span data-ttu-id="3b51c-205">Ripetere questa procedura fino a creare tutti e sei i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="3b51c-205">Repeat this process until you have created all six CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="3b51c-206">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="3b51c-206">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="3b51c-207"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="3b51c-207"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="3b51c-208">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="3b51c-208">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="3b51c-209">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="3b51c-209">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="3b51c-210">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsfot.</span><span class="sxs-lookup"><span data-stu-id="3b51c-210">If you already have an SPF record for your domain, don't create a new one for Microsfot.</span></span> <span data-ttu-id="3b51c-211">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="3b51c-211">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="3b51c-212">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="3b51c-212">Need examples?</span></span> <span data-ttu-id="3b51c-213">Consultare [Record Domain Name System (DNS) esterni per Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span><span class="sxs-lookup"><span data-stu-id="3b51c-213">Check out these [External Domain Name System records for Microsoft](https://docs.microsoft.com/microsoft-365/enterprise/external-domain-name-system-records#external-dns-records-required-for-spf).</span></span> <span data-ttu-id="3b51c-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="3b51c-214">To validate your SPF record, you can use one of these [SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="3b51c-215">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span><span class="sxs-lookup"><span data-stu-id="3b51c-215">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview).</span></span> <span data-ttu-id="3b51c-216">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3b51c-216">You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3b51c-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="3b51c-217">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3b51c-218">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="3b51c-218">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="3b51c-219">Nella pagina **Manage your DNS** selezionare la scheda Advanced **DNS.**</span><span class="sxs-lookup"><span data-stu-id="3b51c-219">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="3b51c-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3b51c-220">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3b51c-221">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3b51c-221">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="3b51c-222">**Hostname**</span><span class="sxs-lookup"><span data-stu-id="3b51c-222">**Hostname**</span></span>|<span data-ttu-id="3b51c-223">**Type**</span><span class="sxs-lookup"><span data-stu-id="3b51c-223">**Type**</span></span>|<span data-ttu-id="3b51c-224">**Destination TXT/SPF**</span><span class="sxs-lookup"><span data-stu-id="3b51c-224">**Destination TXT/SPF**</span></span>|
    |:-----|:-----|:-----|
    |@  <br/> |<span data-ttu-id="3b51c-225">TXT/SPF</span><span class="sxs-lookup"><span data-stu-id="3b51c-225">TXT/SPF</span></span>  <br/> |<span data-ttu-id="3b51c-226">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="3b51c-226">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="3b51c-227">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="3b51c-227">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![123Reg-BP-Configure-4-1](../../media/4697701c-eba0-4b03-8d75-4f7fc3bef94a.png)
  
6. <span data-ttu-id="3b51c-229">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3b51c-229">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi.](../../media/7906dd91-fd23-44c3-bb37-ef185655c6eb.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="3b51c-231">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="3b51c-231">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="3b51c-232"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="3b51c-232"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="3b51c-p112">Per iniziare, passare alla propria pagina dei domini su 123-reg.co.uk usando [questo collegamento](https://www.123-reg.co.uk/secure/cpanel/domain/overview). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="3b51c-p112">To get started, go to your domains page at 123-reg.co.uk by using [this link](https://www.123-reg.co.uk/secure/cpanel/domain/overview). You'll be prompted to log in first.</span></span>
    
2. <span data-ttu-id="3b51c-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span><span class="sxs-lookup"><span data-stu-id="3b51c-235">On the **Domain name overview** page, select the name of the domain that you want to edit.</span></span> 
    
3. <span data-ttu-id="3b51c-236">Choose **DNS** from the **Select action** drop-down list.</span><span class="sxs-lookup"><span data-stu-id="3b51c-236">Choose **DNS** from the **Select action** drop-down list.</span></span> 
    
4. <span data-ttu-id="3b51c-237">Nella pagina **Manage your DNS** selezionare la scheda Advanced **DNS.**</span><span class="sxs-lookup"><span data-stu-id="3b51c-237">On the **Manage your DNS** page, select the **Advanced DNS** tab.</span></span> 
    
5. <span data-ttu-id="3b51c-238">Aggiungere il primo dei due record SRV:</span><span class="sxs-lookup"><span data-stu-id="3b51c-238">Add the first of the two SRV records:</span></span>
    
    <span data-ttu-id="3b51c-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="3b51c-239">In the **Advanced DNS** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="3b51c-240">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="3b51c-240">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    ||||||
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="3b51c-241">Hostname</span><span class="sxs-lookup"><span data-stu-id="3b51c-241">Hostname</span></span>|<span data-ttu-id="3b51c-242">Type</span><span class="sxs-lookup"><span data-stu-id="3b51c-242">Type</span></span>|<span data-ttu-id="3b51c-243">Priority</span><span class="sxs-lookup"><span data-stu-id="3b51c-243">Priority</span></span>|<span data-ttu-id="3b51c-244">TTL</span><span class="sxs-lookup"><span data-stu-id="3b51c-244">TTL</span></span>|<span data-ttu-id="3b51c-245">Destination SRV</span><span class="sxs-lookup"><span data-stu-id="3b51c-245">Destination SRV</span></span>|
    |<span data-ttu-id="3b51c-246">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="3b51c-246">_sip._tls</span></span>|<span data-ttu-id="3b51c-247">SRV</span><span class="sxs-lookup"><span data-stu-id="3b51c-247">SRV</span></span>|<span data-ttu-id="3b51c-248">100</span><span class="sxs-lookup"><span data-stu-id="3b51c-248">100</span></span>|<span data-ttu-id="3b51c-249">3600</span><span class="sxs-lookup"><span data-stu-id="3b51c-249">3600</span></span>|<span data-ttu-id="3b51c-250">1 443 sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3b51c-250">1 443 sipdir.online.lync.com.</span></span> <span data-ttu-id="3b51c-251">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3b51c-251">**This value MUST end with a period (.)**</span></span><br> <span data-ttu-id="3b51c-252">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="3b51c-252">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="3b51c-253">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="3b51c-253">_sipfederationtls._tcp</span></span>|<span data-ttu-id="3b51c-254">SRV</span><span class="sxs-lookup"><span data-stu-id="3b51c-254">SRV</span></span>|<span data-ttu-id="3b51c-255">100</span><span class="sxs-lookup"><span data-stu-id="3b51c-255">100</span></span>|<span data-ttu-id="3b51c-256">3600</span><span class="sxs-lookup"><span data-stu-id="3b51c-256">3600</span></span>|<span data-ttu-id="3b51c-257">1 5061 sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="3b51c-257">1 5061 sipfed.online.lync.com.</span></span> <span data-ttu-id="3b51c-258">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="3b51c-258">**This value MUST end with a period (.)**</span></span> <br> <span data-ttu-id="3b51c-259">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="3b51c-259">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
    ![Copiare e incollare i valori dalla tabella](../../media/c1786b86-52ef-4dca-8b99-b479554fa531.png)
  
6. <span data-ttu-id="3b51c-261">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="3b51c-261">Select **Add**.</span></span>
    
    ![Selezionare Aggiungi.](../../media/5fd9d3a2-a8bb-466b-829f-b3a6e54b5104.png)
  
7. <span data-ttu-id="3b51c-263">Per aggiungere l'altro record SRV:</span><span class="sxs-lookup"><span data-stu-id="3b51c-263">To add the other SRV record:</span></span>
    
    <span data-ttu-id="3b51c-264">Nella sezione **Advanced DNS** creare un record utilizzando i valori della seconda riga della tabella e quindi selezionare di nuovo **Add** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="3b51c-264">In the **Advanced DNS** section, create a record by using the values from the second row in the table, and then again select **Add** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="3b51c-p115">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="3b51c-p115">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
