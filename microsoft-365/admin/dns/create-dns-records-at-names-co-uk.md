---
title: Creare record DNS in Names.co.uk per Microsoft
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Names.co.uk per Microsoft.
ms.openlocfilehash: 91c328877d583f415ffd2b8312ff1dc899a05bcc
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/29/2020
ms.locfileid: "43939168"
---
# <a name="create-dns-records-at-namescouk-for-microsoft"></a><span data-ttu-id="5d61d-103">Creare record DNS in Names.co.uk per Microsoft</span><span class="sxs-lookup"><span data-stu-id="5d61d-103">Create DNS records at Names.co.uk for Microsoft</span></span>

 <span data-ttu-id="5d61d-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5d61d-105">Se il provider di hosting DNS è Names.co.uk, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="5d61d-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="5d61d-106">Dopo aver aggiunto questi record in Names.co.uk, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5d61d-106">After you add these records at Names.co.uk, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
>  <span data-ttu-id="5d61d-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5d61d-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5d61d-110">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="5d61d-110">Add a TXT record for verification</span></span>
<span data-ttu-id="5d61d-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5d61d-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5d61d-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="5d61d-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5d61d-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="5d61d-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="5d61d-p104">Per iniziare, passare alla propria pagina dei domini su Names.co.uk usando [questo collegamento](https://account.names.co.uk/dashboard#/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5d61d-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="5d61d-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="5d61d-119">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="5d61d-120">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-120">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="5d61d-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5d61d-122">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5d61d-123">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-123">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="5d61d-124">Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-124">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="5d61d-125">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-125">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="5d61d-126">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="5d61d-126">**Host name**</span></span>|<span data-ttu-id="5d61d-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5d61d-127">**Type**</span></span>|<span data-ttu-id="5d61d-128">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="5d61d-128">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5d61d-129">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5d61d-130">TXT</span><span class="sxs-lookup"><span data-stu-id="5d61d-130">TXT</span></span>  <br/> |<span data-ttu-id="5d61d-131">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5d61d-131">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5d61d-132">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="5d61d-132">**Note:** This is an example.</span></span> <span data-ttu-id="5d61d-133">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="5d61d-133">Use your specific **Destination or Points to Address** value here, from the table.</span></span>           [<span data-ttu-id="5d61d-134">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="5d61d-134">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)    |
       
    ![NamesUK-BP-Verify-1-1](../../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="5d61d-136">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-136">Select **Save**.</span></span>
    
    <span data-ttu-id="5d61d-137">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-137">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="5d61d-139">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="5d61d-139">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5d61d-140">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="5d61d-140">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="5d61d-141">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="5d61d-141">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5d61d-142">Nell'interfaccia di amministrazione passare a **Impostazioni** \> pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="5d61d-142">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="5d61d-143">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="5d61d-143">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="5d61d-144">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-144">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="5d61d-145">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-145">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="5d61d-p106">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5d61d-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5d61d-149">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="5d61d-149">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5d61d-150"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5d61d-150"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5d61d-p107">Per iniziare, passare alla propria pagina dei domini su Names.co.uk usando [questo collegamento](https://account.names.co.uk/dashboard#/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5d61d-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="5d61d-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="5d61d-154">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="5d61d-155">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-155">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="5d61d-157">Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle del nuovo record nella sezione **Add/Modify DNS Zone**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-157">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5d61d-158">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-158">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5d61d-159">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="5d61d-159">**Host name**</span></span>|<span data-ttu-id="5d61d-160">**Priority**</span><span class="sxs-lookup"><span data-stu-id="5d61d-160">**Priority**</span></span>|<span data-ttu-id="5d61d-161">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="5d61d-161">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5d61d-162">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="5d61d-162">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5d61d-163">1</span><span class="sxs-lookup"><span data-stu-id="5d61d-163">1</span></span>  <br/> <span data-ttu-id="5d61d-164">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="5d61d-164">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="5d61d-165">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5d61d-165">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5d61d-166">> [!NOTE]> ottenere la propria \* \<chiave\> di dominio\* dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5d61d-166">> [!NOTE]> Get your  *\<domain-key\>*  from your Microsoft account.</span></span>           [<span data-ttu-id="5d61d-167">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="5d61d-167">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Configure-2-1](../../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="5d61d-169">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-169">Select **Save**.</span></span>
    
    <span data-ttu-id="5d61d-170">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-170">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-2](../../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="5d61d-172">Se sono presenti altri record MX nella sezione **Mail exchange records**, eliminarli uno alla volta selezionandoli e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-172">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Configure-2-3](../../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="5d61d-174">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-174">Select **Save**.</span></span>
    
    <span data-ttu-id="5d61d-175">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-175">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-4](../../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5d61d-177">Aggiungere i sei record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="5d61d-177">Add the six CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5d61d-178"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5d61d-178"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5d61d-p109">Per iniziare, passare alla propria pagina dei domini su Names.co.uk usando [questo collegamento](https://account.names.co.uk/dashboard#/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5d61d-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="5d61d-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="5d61d-182">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="5d61d-183">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-183">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="5d61d-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5d61d-185">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5d61d-186">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-186">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="5d61d-187">Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-187">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="5d61d-188">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-188">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5d61d-189">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="5d61d-189">**Host Name**</span></span>|<span data-ttu-id="5d61d-190">**Type**</span><span class="sxs-lookup"><span data-stu-id="5d61d-190">**Type**</span></span>|<span data-ttu-id="5d61d-191">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="5d61d-191">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5d61d-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5d61d-192">autodiscover</span></span>  <br/> |<span data-ttu-id="5d61d-193">CNAME</span><span class="sxs-lookup"><span data-stu-id="5d61d-193">CNAME</span></span>  <br/> |<span data-ttu-id="5d61d-194">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5d61d-194">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="5d61d-195">sip</span><span class="sxs-lookup"><span data-stu-id="5d61d-195">sip</span></span>  <br/> |<span data-ttu-id="5d61d-196">CNAME</span><span class="sxs-lookup"><span data-stu-id="5d61d-196">CNAME</span></span>  <br/> |<span data-ttu-id="5d61d-197">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5d61d-197">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5d61d-198">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5d61d-198">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5d61d-199">CNAME</span><span class="sxs-lookup"><span data-stu-id="5d61d-199">CNAME</span></span>  <br/> |<span data-ttu-id="5d61d-200">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5d61d-200">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5d61d-201">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5d61d-201">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5d61d-202">CNAME</span><span class="sxs-lookup"><span data-stu-id="5d61d-202">CNAME</span></span>  <br/> |<span data-ttu-id="5d61d-203">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="5d61d-203">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="5d61d-204">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5d61d-204">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5d61d-205">CNAME</span><span class="sxs-lookup"><span data-stu-id="5d61d-205">CNAME</span></span>  <br/> |<span data-ttu-id="5d61d-206">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="5d61d-206">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-configure-3-1](../../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="5d61d-208">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-208">Select **Save**.</span></span>
    
    ![NamesUK-BP-configure-3-2](../../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5d61d-210">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="5d61d-210">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5d61d-211"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5d61d-211"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5d61d-212">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="5d61d-212">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5d61d-213">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="5d61d-213">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5d61d-214">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5d61d-214">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="5d61d-215">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="5d61d-215">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="5d61d-p111">Per iniziare, passare alla propria pagina dei domini su Names.co.uk usando [questo collegamento](https://account.names.co.uk/dashboard#/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5d61d-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="5d61d-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="5d61d-219">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="5d61d-220">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-220">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="5d61d-222">Nella colonna **Domain Name** della pagina **DNS Zones on account** selezionare il nome del dominio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="5d61d-222">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Configure-1-2-1](../../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="5d61d-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5d61d-224">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5d61d-225">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-225">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="5d61d-226">Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-226">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="5d61d-227">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-227">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5d61d-228">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="5d61d-228">**Host name**</span></span>|<span data-ttu-id="5d61d-229">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5d61d-229">**Type**</span></span>|<span data-ttu-id="5d61d-230">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="5d61d-230">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5d61d-231">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-231">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5d61d-232">TXT</span><span class="sxs-lookup"><span data-stu-id="5d61d-232">TXT</span></span>  <br/> |<span data-ttu-id="5d61d-233">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5d61d-233">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5d61d-234">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="5d61d-234">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Configure-4-1](../../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="5d61d-236">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-236">Select **Save**.</span></span>
    
    <span data-ttu-id="5d61d-237">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-237">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-4-2](../../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5d61d-239">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="5d61d-239">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5d61d-240"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5d61d-240"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5d61d-p112">Per iniziare, passare alla propria pagina dei domini su Names.co.uk usando [questo collegamento](https://account.names.co.uk/dashboard#/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5d61d-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="5d61d-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="5d61d-244">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="5d61d-245">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5d61d-245">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="5d61d-247">Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle del nuovo record nella sezione **Service records**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-247">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5d61d-248">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5d61d-248">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5d61d-249">**Name**</span><span class="sxs-lookup"><span data-stu-id="5d61d-249">**Name**</span></span>|<span data-ttu-id="5d61d-250">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="5d61d-250">**Priority**</span></span>|<span data-ttu-id="5d61d-251">**Peso**</span><span class="sxs-lookup"><span data-stu-id="5d61d-251">**Weight**</span></span>|<span data-ttu-id="5d61d-252">**Porta**</span><span class="sxs-lookup"><span data-stu-id="5d61d-252">**Port**</span></span>|<span data-ttu-id="5d61d-253">**Result**</span><span class="sxs-lookup"><span data-stu-id="5d61d-253">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5d61d-254">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="5d61d-254">_sip._tls</span></span>  <br/> |<span data-ttu-id="5d61d-255">100</span><span class="sxs-lookup"><span data-stu-id="5d61d-255">100</span></span>  <br/> |<span data-ttu-id="5d61d-256">1</span><span class="sxs-lookup"><span data-stu-id="5d61d-256">1</span></span>  <br/> |<span data-ttu-id="5d61d-257">443</span><span class="sxs-lookup"><span data-stu-id="5d61d-257">443</span></span>  <br/> |<span data-ttu-id="5d61d-258">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5d61d-258">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="5d61d-259">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="5d61d-259">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5d61d-260">100</span><span class="sxs-lookup"><span data-stu-id="5d61d-260">100</span></span>  <br/> |<span data-ttu-id="5d61d-261">1</span><span class="sxs-lookup"><span data-stu-id="5d61d-261">1</span></span>  <br/> |<span data-ttu-id="5d61d-262">5061</span><span class="sxs-lookup"><span data-stu-id="5d61d-262">5061</span></span>  <br/> |<span data-ttu-id="5d61d-263">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="5d61d-263">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-5-1](../../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="5d61d-265">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5d61d-265">Select **Save**.</span></span>
    
    <span data-ttu-id="5d61d-266">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5d61d-266">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-5-2](../../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="5d61d-p113">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5d61d-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
