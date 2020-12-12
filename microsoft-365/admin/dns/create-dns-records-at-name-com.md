---
title: Creare record DNS in name.com per Microsoft
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
ms.assetid: 9ddcc2fc-9433-4335-8192-6ffb1f541087
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in name.com per Microsoft.
ms.openlocfilehash: 2330755412abfe262ac79c4acbfc12e33af76fe2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/11/2020
ms.locfileid: "49657828"
---
# <a name="create-dns-records-at-namecom-for-microsoft"></a><span data-ttu-id="cd39d-103">Creare record DNS in name.com per Microsoft</span><span class="sxs-lookup"><span data-stu-id="cd39d-103">Create DNS records at name.com for Microsoft</span></span>

 <span data-ttu-id="cd39d-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="cd39d-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="cd39d-105">Se il proprio provider di hosting DNS è name.com, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="cd39d-105">If name.com is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="cd39d-106">Dopo aver aggiunto questi record in name.com, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cd39d-106">After you add these records at name.com, your domain will be set up to work with Microsoft services.</span></span>

  
> [!NOTE]
> <span data-ttu-id="cd39d-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cd39d-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="cd39d-110">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="cd39d-110">Add a TXT record for verification</span></span>
<span data-ttu-id="cd39d-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="cd39d-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="cd39d-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="cd39d-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd39d-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="cd39d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="cd39d-p104">Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="cd39d-p104">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="cd39d-119">In **My Domains** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="cd39d-119">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="cd39d-121">Nella colonna **Details** selezionare **DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="cd39d-121">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="cd39d-123">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cd39d-123">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="cd39d-124">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="cd39d-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |||||
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cd39d-125">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cd39d-125">**Type**</span></span> <br/> |<span data-ttu-id="cd39d-126">**Host**</span><span class="sxs-lookup"><span data-stu-id="cd39d-126">**Host**</span></span> <br/> |<span data-ttu-id="cd39d-127">**Answer**</span><span class="sxs-lookup"><span data-stu-id="cd39d-127">**Answer**</span></span> <br/> |<span data-ttu-id="cd39d-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cd39d-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="cd39d-129">TXT</span><span class="sxs-lookup"><span data-stu-id="cd39d-129">TXT</span></span>  <br/> |<span data-ttu-id="cd39d-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="cd39d-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cd39d-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="cd39d-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="cd39d-132">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="cd39d-132">**Note:** This is an example.</span></span> <span data-ttu-id="cd39d-133">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="cd39d-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="cd39d-134">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="cd39d-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="cd39d-135">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="cd39d-135">Use the default value (300).</span></span>  <br/> |
   
    ![Nome-BP-Verify-1-1](../../media/0c352fd3-cf84-439f-a481-0705e225cc54.png)
  
5. <span data-ttu-id="cd39d-137">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="cd39d-137">Select **Add Record**.</span></span>
    
    ![Name-BP-Verify-1-2](../../media/816fc60b-17ab-4982-8849-6c3fcf3ca3d6.png)
  
6. <span data-ttu-id="cd39d-139">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="cd39d-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="cd39d-140">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="cd39d-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="cd39d-141">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="cd39d-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="cd39d-142">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="cd39d-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="cd39d-143">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="cd39d-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="cd39d-144">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="cd39d-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="cd39d-145">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="cd39d-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
> <span data-ttu-id="cd39d-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cd39d-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="cd39d-149">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="cd39d-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="cd39d-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="cd39d-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="cd39d-p107">Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="cd39d-p107">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="cd39d-154">In **My Domains** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="cd39d-154">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="cd39d-156">Nella colonna **Details** selezionare **DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="cd39d-156">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="cd39d-158">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cd39d-158">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="cd39d-159">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="cd39d-159">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cd39d-160">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cd39d-160">**Type**</span></span>|<span data-ttu-id="cd39d-161">**Host**</span><span class="sxs-lookup"><span data-stu-id="cd39d-161">**Host**</span></span>|<span data-ttu-id="cd39d-162">**Answer**</span><span class="sxs-lookup"><span data-stu-id="cd39d-162">**Answer**</span></span>|<span data-ttu-id="cd39d-163">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cd39d-163">**TTL**</span></span>|<span data-ttu-id="cd39d-164">**Prio**</span><span class="sxs-lookup"><span data-stu-id="cd39d-164">**Prio**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cd39d-165">MX</span><span class="sxs-lookup"><span data-stu-id="cd39d-165">MX</span></span>  <br/> |<span data-ttu-id="cd39d-166">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="cd39d-166">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="cd39d-167">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cd39d-167">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="cd39d-168">**Nota:** Ottenere il vostro  *\<domain-key\>*  dal vostro account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cd39d-168">**Note:** Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="cd39d-169">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="cd39d-169">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="cd39d-170">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="cd39d-170">Use the default value (300).</span></span>  <br/> |<span data-ttu-id="cd39d-171">0</span><span class="sxs-lookup"><span data-stu-id="cd39d-171">0</span></span>  <br/> <span data-ttu-id="cd39d-172">Per altre informazioni sulla priorità, vedere [Che cos'è la priorità MX](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq).</span><span class="sxs-lookup"><span data-stu-id="cd39d-172">For more information about priority, see [What is MX priority?](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)</span></span> <br/> |
   
   ![Nome-BP-Configure-2-1](../../media/11ba2160-fc8e-4196-bb15-2b7c6d49c8fc.png)
  
5. <span data-ttu-id="cd39d-174">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="cd39d-174">Select **Add Record**.</span></span>
    
    ![Name-BP-Configurazione-2-2](../../media/fd09f161-7cc4-4723-aec2-5fa801bd19e9.png)
  
6. <span data-ttu-id="cd39d-176">Se sono presenti altri record MX, usare il processo in due passaggi seguente per rimuovere ognuno di essi:</span><span class="sxs-lookup"><span data-stu-id="cd39d-176">If there are any other MX records, delete each of them by using the following two-step procedure:</span></span>
    
    <span data-ttu-id="cd39d-177">Per ogni altro record MX, selezionare **Elimina** nella colonna **azioni** .</span><span class="sxs-lookup"><span data-stu-id="cd39d-177">For each other MX record, select **Delete** in the **Actions** column.</span></span> 
    
    ![Name-BP-Configurazione-2-3](../../media/16734a98-31c4-4023-a2a5-10b7c95bc58e.png)
  
    <span data-ttu-id="cd39d-179">Per confermare ogni eliminazione, selezionare di nuovo **Delete** nella colonna **Actions** .</span><span class="sxs-lookup"><span data-stu-id="cd39d-179">To confirm each deletion, select **Delete** in the **Actions** column again.</span></span> 
    
    ![Name-BP-Configure-2-4](../../media/409c21c5-51f4-4244-bb84-5d32084224b2.png)
  
    <span data-ttu-id="cd39d-181">Ripetere questa procedura in due passaggi fino a eliminare ogni altro record MX.</span><span class="sxs-lookup"><span data-stu-id="cd39d-181">Repeat this two-step procedure until you have deleted each of the other MX records.</span></span>
    
## <a name="add-the-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="cd39d-182">Aggiungere i record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="cd39d-182">Add the CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="cd39d-183"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="cd39d-183"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="cd39d-p109">Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="cd39d-p109">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="cd39d-187">In **My Domains** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="cd39d-187">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="cd39d-189">Nella colonna **Details** selezionare **DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="cd39d-189">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="cd39d-191">Aggiungere il primo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="cd39d-191">Add the first CNAME record.</span></span>
    
    <span data-ttu-id="cd39d-192">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cd39d-192">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="cd39d-193">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="cd39d-193">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cd39d-194">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cd39d-194">**Type**</span></span>|<span data-ttu-id="cd39d-195">**Host**</span><span class="sxs-lookup"><span data-stu-id="cd39d-195">**Host**</span></span>|<span data-ttu-id="cd39d-196">**Answer**</span><span class="sxs-lookup"><span data-stu-id="cd39d-196">**Answer**</span></span>|<span data-ttu-id="cd39d-197">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cd39d-197">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cd39d-198">CNAME</span><span class="sxs-lookup"><span data-stu-id="cd39d-198">CNAME</span></span>  <br/> |<span data-ttu-id="cd39d-199">individuazione automatica</span><span class="sxs-lookup"><span data-stu-id="cd39d-199">autodiscover</span></span>  <br/> |<span data-ttu-id="cd39d-200">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="cd39d-200">autodiscover.outlook.com</span></span>  <br/> |<span data-ttu-id="cd39d-201">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="cd39d-201">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="cd39d-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="cd39d-202">CNAME</span></span>  <br/> |<span data-ttu-id="cd39d-203">sip</span><span class="sxs-lookup"><span data-stu-id="cd39d-203">sip</span></span>  <br/> |<span data-ttu-id="cd39d-204">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cd39d-204">sipdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="cd39d-205">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="cd39d-205">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="cd39d-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="cd39d-206">CNAME</span></span>  <br/> |<span data-ttu-id="cd39d-207">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="cd39d-207">lyncdiscover</span></span>  <br/> |<span data-ttu-id="cd39d-208">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cd39d-208">webdir.online.lync.com</span></span>  <br/> |<span data-ttu-id="cd39d-209">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="cd39d-209">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="cd39d-210">CNAME</span><span class="sxs-lookup"><span data-stu-id="cd39d-210">CNAME</span></span>  <br/> |<span data-ttu-id="cd39d-211">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="cd39d-211">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="cd39d-212">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="cd39d-212">enterpriseregistration.windows.net</span></span>  <br/> |<span data-ttu-id="cd39d-213">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="cd39d-213">Use the default value (300).</span></span>  <br/> |
    |<span data-ttu-id="cd39d-214">CNAME</span><span class="sxs-lookup"><span data-stu-id="cd39d-214">CNAME</span></span>  <br/> |<span data-ttu-id="cd39d-215">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="cd39d-215">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="cd39d-216">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="cd39d-216">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |<span data-ttu-id="cd39d-217">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="cd39d-217">Use the default value (300).</span></span>  <br/> |
   
   ![Nome-BP-configure-3-1](../../media/4e34caaf-b418-40ec-abfa-fe62175a87c2.png)
  
5. <span data-ttu-id="cd39d-219">Selezionare **Aggiungi record** per aggiungere il primo record.</span><span class="sxs-lookup"><span data-stu-id="cd39d-219">Select **Add Record** to add the first record.</span></span> 
    
    ![Name-BP-Configure-3-2](../../media/1053c2a7-07c3-4c1b-b54a-1c02881fb0ec.png)
  
6. <span data-ttu-id="cd39d-221">Aggiungere il secondo record CNAME.</span><span class="sxs-lookup"><span data-stu-id="cd39d-221">Add the second CNAME record.</span></span>
    
    <span data-ttu-id="cd39d-222">Utilizzare i valori della seconda riga della tabella precedente e quindi fare clic su **Aggiungi record** per aggiungere il secondo record.</span><span class="sxs-lookup"><span data-stu-id="cd39d-222">Use the values from the second row of the table above, and then select **Add Record** to add the second record.</span></span> 
    
    <span data-ttu-id="cd39d-223">Aggiungere i record rimanenti allo stesso modo, usando i valori dalla terza, quarta, quinta e sesta riga della tabella.</span><span class="sxs-lookup"><span data-stu-id="cd39d-223">Add the remaining records in the same way, using the values from the third, fourth, fifth, and sixth rows of the table.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="cd39d-224">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="cd39d-224">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="cd39d-225"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="cd39d-225"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="cd39d-226">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="cd39d-226">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="cd39d-227">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="cd39d-227">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="cd39d-228">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="cd39d-228">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="cd39d-229">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un  *singolo*  record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="cd39d-229">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> 
  
1. <span data-ttu-id="cd39d-p111">Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="cd39d-p111">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="cd39d-233">In **My Domains** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="cd39d-233">Under **My Domains**, select the name of the domain that you want to modify.</span></span>

    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="cd39d-235">Nella colonna **Details** selezionare **DNS Records**.</span><span class="sxs-lookup"><span data-stu-id="cd39d-235">In the **Details** column, select **DNS Records**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="cd39d-237">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cd39d-237">In the boxes for the new record, type or copy and paste the values from the following table.</span></span>
    
    <span data-ttu-id="cd39d-238">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="cd39d-238">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cd39d-239">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cd39d-239">**Type**</span></span>|<span data-ttu-id="cd39d-240">**Host**</span><span class="sxs-lookup"><span data-stu-id="cd39d-240">**Host**</span></span>|<span data-ttu-id="cd39d-241">**Answer**</span><span class="sxs-lookup"><span data-stu-id="cd39d-241">**Answer**</span></span>|<span data-ttu-id="cd39d-242">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cd39d-242">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cd39d-243">TXT</span><span class="sxs-lookup"><span data-stu-id="cd39d-243">TXT</span></span>  <br/> |<span data-ttu-id="cd39d-244">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="cd39d-244">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="cd39d-245">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="cd39d-245">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="cd39d-246">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="cd39d-246">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="cd39d-247">Use the default value (300).</span><span class="sxs-lookup"><span data-stu-id="cd39d-247">Use the default value (300).</span></span>  <br/> |
   
   ![Nome-BP-Configure-4-1](../../media/cbbfc071-840a-4ffa-a59e-0dfce03063cc.png)
  
5. <span data-ttu-id="cd39d-249">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="cd39d-249">Select **Add Record**.</span></span>
    
    ![Name-BP-Configure-4-2](../../media/db1e0e09-2b95-4fc1-88bd-e86da536921f.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="cd39d-251">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="cd39d-251">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="cd39d-252"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="cd39d-252"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="cd39d-p112">Per iniziare, passare alla propria pagina dei domini su name.com usando [questo collegamento](https://www.name.com/account/domain). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="cd39d-p112">To get started, go to your domains page at name.com by using [this link](https://www.name.com/account/domain). You'll be prompted to log in first.</span></span>
    
    ![Name-BP-Configure-1-1](../../media/1869b416-1d3f-4fb1-99c6-62b74ca7a4c7.png)
  
2. <span data-ttu-id="cd39d-256">In **My Domains** selezionare il nome del dominio che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="cd39d-256">Under **My Domains**, select the name of the domain that you want to modify.</span></span>
    
    ![Name-BP-Configure-1-2](../../media/c8b96e1e-aa35-4fb1-8209-450f587fec4d.png)
  
3. <span data-ttu-id="cd39d-258">Nella colonna **Details** selezionare **DNS Records +**.</span><span class="sxs-lookup"><span data-stu-id="cd39d-258">In the **Details** column, select **DNS Records+**.</span></span> 
    
    ![Name-BP-Configure-1-3](../../media/c5da31e2-2f77-4d0c-b31d-189e6fb7b205.png)
  
4. <span data-ttu-id="cd39d-260">Aggiungere il primo record SRV:</span><span class="sxs-lookup"><span data-stu-id="cd39d-260">Add the first SRV record:</span></span>
    
    <span data-ttu-id="cd39d-261">Nelle caselle del nuovo record digitare oppure copiare e incollare i valori dalla prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="cd39d-261">In the boxes for the new record, type or copy and paste the values from the first row of the following table.</span></span>
    
    <span data-ttu-id="cd39d-262">Selezionare il valore **Type** nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="cd39d-262">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    |<span data-ttu-id="cd39d-263">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cd39d-263">**Type**</span></span>|<span data-ttu-id="cd39d-264">**Service**</span><span class="sxs-lookup"><span data-stu-id="cd39d-264">**Service**</span></span>|<span data-ttu-id="cd39d-265">**Weight**</span><span class="sxs-lookup"><span data-stu-id="cd39d-265">**Weight**</span></span>|<span data-ttu-id="cd39d-266">**TTL**</span><span class="sxs-lookup"><span data-stu-id="cd39d-266">**TTL**</span></span>|<span data-ttu-id="cd39d-267">**Prio**</span><span class="sxs-lookup"><span data-stu-id="cd39d-267">**Prio**</span></span>|<span data-ttu-id="cd39d-268">**Protocol**</span><span class="sxs-lookup"><span data-stu-id="cd39d-268">**Protocol**</span></span>|<span data-ttu-id="cd39d-269">**Port**</span><span class="sxs-lookup"><span data-stu-id="cd39d-269">**Port**</span></span>|<span data-ttu-id="cd39d-270">**Target**</span><span class="sxs-lookup"><span data-stu-id="cd39d-270">**Target**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="cd39d-271">SRV</span><span class="sxs-lookup"><span data-stu-id="cd39d-271">SRV</span></span>|<span data-ttu-id="cd39d-272">sip</span><span class="sxs-lookup"><span data-stu-id="cd39d-272">sip</span></span>|<span data-ttu-id="cd39d-273">1 </span><span class="sxs-lookup"><span data-stu-id="cd39d-273">1</span></span>|<span data-ttu-id="cd39d-274">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="cd39d-274">Use the default value (300).</span></span>|<span data-ttu-id="cd39d-275">100</span><span class="sxs-lookup"><span data-stu-id="cd39d-275">100</span></span>|<span data-ttu-id="cd39d-276">tls</span><span class="sxs-lookup"><span data-stu-id="cd39d-276">tls</span></span>|<span data-ttu-id="cd39d-277">443</span><span class="sxs-lookup"><span data-stu-id="cd39d-277">443</span></span>|<span data-ttu-id="cd39d-278">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cd39d-278">sipdir.online.lync.com</span></span> <br> <span data-ttu-id="cd39d-279">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="cd39d-279">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
    |<span data-ttu-id="cd39d-280">SRV</span><span class="sxs-lookup"><span data-stu-id="cd39d-280">SRV</span></span>|<span data-ttu-id="cd39d-281">sipfederationtls</span><span class="sxs-lookup"><span data-stu-id="cd39d-281">sipfederationtls</span></span>|<span data-ttu-id="cd39d-282">1 </span><span class="sxs-lookup"><span data-stu-id="cd39d-282">1</span></span>|<span data-ttu-id="cd39d-283">Usare il valore predefinito (300).</span><span class="sxs-lookup"><span data-stu-id="cd39d-283">Use the default value (300).</span></span>|<span data-ttu-id="cd39d-284">100</span><span class="sxs-lookup"><span data-stu-id="cd39d-284">100</span></span>|<span data-ttu-id="cd39d-285">tcp</span><span class="sxs-lookup"><span data-stu-id="cd39d-285">tcp</span></span>|<span data-ttu-id="cd39d-286">5061</span><span class="sxs-lookup"><span data-stu-id="cd39d-286">5061</span></span>|<span data-ttu-id="cd39d-287">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="cd39d-287">sipfed.online.lync.com</span></span> <br><span data-ttu-id="cd39d-288">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="cd39d-288">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
   
   ![Nome-BP-Configure-5-1](../../media/d9a885fd-7300-45b6-ad4c-0b4bf1067560.png)
  
5. <span data-ttu-id="cd39d-290">Selezionare **Aggiungi record**.</span><span class="sxs-lookup"><span data-stu-id="cd39d-290">Select **Add Record**.</span></span>

    ![Name-BP-Configure-5-2](../../media/a804d51d-8f57-4b0b-8bd6-a52eb1c87a97.png)
  
6. <span data-ttu-id="cd39d-292">Aggiungere il secondo record SRV:</span><span class="sxs-lookup"><span data-stu-id="cd39d-292">Add the second SRV record:</span></span>

<span data-ttu-id="cd39d-293">Utilizzare i valori della riga successiva della tabella precedente e quindi fare clic su **Aggiungi record** per aggiungere il secondo record.</span><span class="sxs-lookup"><span data-stu-id="cd39d-293">Use the values from the next row of the table above, and then select **Add Record** to add the second record.</span></span>

>[!NOTE]
><span data-ttu-id="cd39d-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="cd39d-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span>
