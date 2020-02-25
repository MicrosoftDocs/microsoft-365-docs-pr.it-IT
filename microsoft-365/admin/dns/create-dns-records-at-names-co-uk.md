---
title: Creare record DNS in Names.co.uk per Office 365
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
ms.assetid: b6c15128-b456-49b4-8b5e-5b823c700f26
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in Names.co.uk per Office 365.
ms.openlocfilehash: f77ab8560eb078f096600b9bf8558fd0f4a194ce
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252572"
---
# <a name="create-dns-records-at-namescouk-for-office-365"></a><span data-ttu-id="79d96-103">Creare record DNS in Names.co.uk per Office 365</span><span class="sxs-lookup"><span data-stu-id="79d96-103">Create DNS records at Names.co.uk for Office 365</span></span>

 <span data-ttu-id="79d96-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="79d96-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="79d96-105">Se il provider di hosting DNS è Names.co.uk, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="79d96-105">If Names.co.uk is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
    
<span data-ttu-id="79d96-106">Dopo aver aggiunto questi record in Names.co.uk, il dominio sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="79d96-106">After you add these records at Names.co.uk, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="79d96-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="79d96-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="79d96-p101">In genere, l'applicazione delle modifiche ai record DNS richiede circa 15 minuti. A volte, tuttavia, l'aggiornamento di una modifica nel sistema DNS di Internet può richiedere più tempo. In caso di problemi relativi al flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="79d96-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="79d96-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="79d96-111">Add a TXT record for verification</span></span>
<span data-ttu-id="79d96-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="79d96-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="79d96-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="79d96-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="79d96-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="79d96-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
1. <span data-ttu-id="79d96-p104">Per iniziare, passare alla propria pagina dei domini su Names.co.uk usando [questo collegamento](https://account.names.co.uk/dashboard#/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="79d96-p104">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="79d96-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="79d96-120">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="79d96-121">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79d96-121">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="79d96-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="79d96-123">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="79d96-124">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="79d96-124">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="79d96-125">Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.</span><span class="sxs-lookup"><span data-stu-id="79d96-125">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="79d96-126">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79d96-126">(You may have to scroll down.)</span></span>
        
    |<span data-ttu-id="79d96-127">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="79d96-127">**Host name**</span></span>|<span data-ttu-id="79d96-128">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="79d96-128">**Type**</span></span>|<span data-ttu-id="79d96-129">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="79d96-129">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="79d96-130">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="79d96-130">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="79d96-131">TXT</span><span class="sxs-lookup"><span data-stu-id="79d96-131">TXT</span></span>  <br/> |<span data-ttu-id="79d96-132">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="79d96-132">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="79d96-p105">**Note:** questo è un esempio. Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.           [Come trovarlo](../get-help-with-domains/information-for-dns-records.md)</span><span class="sxs-lookup"><span data-stu-id="79d96-p105">**Note:** This is an example. Use your specific **Destination or Points to Address** value here, from the table in Office 365.           [How do I find this?](../get-help-with-domains/information-for-dns-records.md)</span></span>    |
       
    ![NamesUK-BP-Verify-1-1](../media/91ed1f22-a796-418d-bbb0-345e2cd99bde.png)
  
4. <span data-ttu-id="79d96-137">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="79d96-137">Select **Save**.</span></span>
    
    <span data-ttu-id="79d96-138">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79d96-138">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Verify-1-2](../media/40e991f9-2209-4210-8762-981cca670d70.png)
  
5. <span data-ttu-id="79d96-140">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="79d96-140">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="79d96-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="79d96-141">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="79d96-142">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="79d96-142">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="79d96-143">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="79d96-143">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>
    
2. <span data-ttu-id="79d96-144">Nella pagina **Domains** selezionare il dominio che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="79d96-144">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
    
  
3. <span data-ttu-id="79d96-145">Nella pagina **configurazione** , selezionare **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="79d96-145">On the **Setup** page, select **Start setup**.</span></span>
    
    
  
4. <span data-ttu-id="79d96-146">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="79d96-146">On the **Verify domain** page, select **Verify**.</span></span>
    
    
  
> [!NOTE]
>  <span data-ttu-id="79d96-p106">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="79d96-p106">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="79d96-150">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="79d96-150">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="79d96-151"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="79d96-151"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="79d96-p107">Per iniziare, passare alla propria pagina dei domini su Names.co.uk usando [questo collegamento](https://account.names.co.uk/dashboard#/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="79d96-p107">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="79d96-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="79d96-155">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="79d96-156">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79d96-156">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="79d96-158">Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle del nuovo record nella sezione **Add/Modify DNS Zone**.</span><span class="sxs-lookup"><span data-stu-id="79d96-158">On the **Add/Modify DNS Zone** page, in the **Mail exchange records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="79d96-159">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="79d96-159">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="79d96-160">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="79d96-160">**Host name**</span></span>|<span data-ttu-id="79d96-161">**Priority**</span><span class="sxs-lookup"><span data-stu-id="79d96-161">**Priority**</span></span>|<span data-ttu-id="79d96-162">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="79d96-162">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="79d96-163">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="79d96-163">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="79d96-164">1</span><span class="sxs-lookup"><span data-stu-id="79d96-164">1</span></span>  <br/> <span data-ttu-id="79d96-165">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="79d96-165">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> | <span data-ttu-id="79d96-166">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="79d96-166">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="79d96-167">> [!NOTE]> ottenere la propria \* \<chiave\> di dominio\* dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="79d96-167">> [!NOTE]> Get your  *\<domain-key\>*  from your Office 365 account.</span></span>           [<span data-ttu-id="79d96-168">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="79d96-168">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |
       
    ![NamesUK-BP-Configure-2-1](../media/e211d73d-864f-4114-864b-8e636c69f595.png)
  
4. <span data-ttu-id="79d96-170">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="79d96-170">Select **Save**.</span></span>
    
    <span data-ttu-id="79d96-171">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79d96-171">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-2](../media/01e6c801-daa2-40ca-84f9-dcac6422257c.png)
  
5. <span data-ttu-id="79d96-173">Se sono presenti altri record MX nella sezione **Mail exchange records**, eliminarli uno alla volta selezionandoli e premendo **CANC**.</span><span class="sxs-lookup"><span data-stu-id="79d96-173">If there are any other MX records listed in the **Mail exchange records** section, delete each one by selecting it and then pressing the **Delete** key on your keyboard.</span></span> 
    
    ![NamesUK-BP-Configure-2-3](../media/f8e43926-b724-4690-94e7-ec4b8d7a8da5.png)
  
6. <span data-ttu-id="79d96-175">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="79d96-175">Select **Save**.</span></span>
    
    <span data-ttu-id="79d96-176">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79d96-176">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-2-4](../media/cd705919-d0bd-408f-82be-b54e732cb05c.png)
  
## <a name="add-the-six-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="79d96-178">Aggiungere i sei record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="79d96-178">Add the six CNAME records that are required for Office 365</span></span>
<span data-ttu-id="79d96-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="79d96-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="79d96-p109">Per iniziare, passare alla propria pagina dei domini su Names.co.uk usando [questo collegamento](https://account.names.co.uk/dashboard#/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="79d96-p109">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="79d96-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="79d96-183">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="79d96-184">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79d96-184">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="79d96-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="79d96-186">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="79d96-187">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="79d96-187">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="79d96-188">Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.</span><span class="sxs-lookup"><span data-stu-id="79d96-188">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="79d96-189">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79d96-189">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="79d96-190">**Host Name**</span><span class="sxs-lookup"><span data-stu-id="79d96-190">**Host Name**</span></span>|<span data-ttu-id="79d96-191">**Type**</span><span class="sxs-lookup"><span data-stu-id="79d96-191">**Type**</span></span>|<span data-ttu-id="79d96-192">**Result**</span><span class="sxs-lookup"><span data-stu-id="79d96-192">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="79d96-193">autodiscover</span><span class="sxs-lookup"><span data-stu-id="79d96-193">autodiscover</span></span>  <br/> |<span data-ttu-id="79d96-194">CNAME</span><span class="sxs-lookup"><span data-stu-id="79d96-194">CNAME</span></span>  <br/> |<span data-ttu-id="79d96-195">autodiscover.outlook.com</span><span class="sxs-lookup"><span data-stu-id="79d96-195">autodiscover.outlook.com</span></span>  <br/> |
    |<span data-ttu-id="79d96-196">sip</span><span class="sxs-lookup"><span data-stu-id="79d96-196">sip</span></span>  <br/> |<span data-ttu-id="79d96-197">CNAME</span><span class="sxs-lookup"><span data-stu-id="79d96-197">CNAME</span></span>  <br/> |<span data-ttu-id="79d96-198">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="79d96-198">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="79d96-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="79d96-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="79d96-200">CNAME</span><span class="sxs-lookup"><span data-stu-id="79d96-200">CNAME</span></span>  <br/> |<span data-ttu-id="79d96-201">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="79d96-201">webdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="79d96-202">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="79d96-202">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="79d96-203">CNAME</span><span class="sxs-lookup"><span data-stu-id="79d96-203">CNAME</span></span>  <br/> |<span data-ttu-id="79d96-204">enterpriseregistration.windows.net</span><span class="sxs-lookup"><span data-stu-id="79d96-204">enterpriseregistration.windows.net</span></span>  <br/> |
    |<span data-ttu-id="79d96-205">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="79d96-205">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="79d96-206">CNAME</span><span class="sxs-lookup"><span data-stu-id="79d96-206">CNAME</span></span>  <br/> |<span data-ttu-id="79d96-207">enterpriseenrollment-s.manage.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="79d96-207">enterpriseenrollment-s.manage.microsoft.com</span></span>  <br/> |
       
    ![NamesUK-BP-configure-3-1](../media/392772bf-2ed3-4959-9a9a-bb1611905e86.png)
  
4. <span data-ttu-id="79d96-209">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="79d96-209">Select **Save**.</span></span>
    
    ![NamesUK-BP-configure-3-2](../media/c009795e-7eef-4804-bf23-556f498306cc.png)
  
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="79d96-211">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="79d96-211">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="79d96-212"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="79d96-212"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="79d96-213">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="79d96-213">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="79d96-214">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="79d96-214">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="79d96-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="79d96-215">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="79d96-216">Al contrario, aggiungere i valori di Office 365 necessari al record corrente in modo che sia presente un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="79d96-216">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span>
  
1. <span data-ttu-id="79d96-p111">Per iniziare, passare alla propria pagina dei domini su Names.co.uk usando [questo collegamento](https://account.names.co.uk/dashboard#/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="79d96-p111">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="79d96-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="79d96-220">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="79d96-221">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79d96-221">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="79d96-223">Nella colonna **Domain Name** della pagina **DNS Zones on account** selezionare il nome del dominio da aggiornare.</span><span class="sxs-lookup"><span data-stu-id="79d96-223">On the **DNS Zones on Account** page, in the **Domain name** column, select the name of the domain that you are updating.</span></span> 
    
    ![NamesUK-BP-Configure-1-2-1](../media/20254eec-6952-47ba-b12b-da32860ee7ef.png)
  
4. <span data-ttu-id="79d96-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="79d96-225">On the **Add/Modify DNS Zone** page, in the **A, CNAME, AAAA, TXT and NS records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="79d96-226">(Choose the **Type** value from the drop-down list.)</span><span class="sxs-lookup"><span data-stu-id="79d96-226">(Choose the **Type** value from the drop-down list.)</span></span> 
    
    <span data-ttu-id="79d96-227">Se è necessario aggiungere una riga, selezionare **Aggiungi record a/CNAME (+)**.</span><span class="sxs-lookup"><span data-stu-id="79d96-227">(If you need to add a row, select **ADD A/CNAME RECORDS (+)**.)</span></span>
    
    <span data-ttu-id="79d96-228">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79d96-228">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="79d96-229">**Nome host**</span><span class="sxs-lookup"><span data-stu-id="79d96-229">**Host name**</span></span>|<span data-ttu-id="79d96-230">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="79d96-230">**Type**</span></span>|<span data-ttu-id="79d96-231">**Risultato**</span><span class="sxs-lookup"><span data-stu-id="79d96-231">**Result**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="79d96-232">(Leave this field empty.)</span><span class="sxs-lookup"><span data-stu-id="79d96-232">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="79d96-233">TXT</span><span class="sxs-lookup"><span data-stu-id="79d96-233">TXT</span></span>  <br/> |<span data-ttu-id="79d96-234">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="79d96-234">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="79d96-235">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="79d96-235">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |
       
    ![NamesUK-BP-Configure-4-1](../media/cfc61387-630e-4aa0-8762-ef36eaeda44a.png)
  
5. <span data-ttu-id="79d96-237">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="79d96-237">Select **Save**.</span></span>
    
    <span data-ttu-id="79d96-238">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="79d96-238">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-4-2](../media/b4d445a1-09c0-46c3-8141-672cc2831a9b.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="79d96-240">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="79d96-240">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="79d96-241"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="79d96-241"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="79d96-p112">Per iniziare, passare alla propria pagina dei domini su Names.co.uk usando [questo collegamento](https://account.names.co.uk/dashboard#/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="79d96-p112">To get started, go to your domains page at Names.co.uk by using [this link](https://account.names.co.uk/dashboard#/). You'll be prompted to log in first.</span></span>
    
    ![NamesUK-BP-Configure-1-1](../media/e5cd0e0c-57f9-4b3d-b1c2-0d6b260f5524.png)
  
2. <span data-ttu-id="79d96-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span><span class="sxs-lookup"><span data-stu-id="79d96-245">On the **Dashboard** page, find the name of the domain that you are updating, and then choose **DNS Settings** from the drop-down list.</span></span> 
    
    <span data-ttu-id="79d96-246">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="79d96-246">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-1-2](../media/b618f8e5-404e-466a-9e71-acd7479f3994.png)
  
3. <span data-ttu-id="79d96-248">Nella pagina **Add/Modify DNS Zone** digitare oppure copiare e incollare i valori della tabella seguente nelle caselle del nuovo record nella sezione **Service records**.</span><span class="sxs-lookup"><span data-stu-id="79d96-248">On the **Add/Modify DNS Zone** page, in the **Service records** section, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="79d96-249">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="79d96-249">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="79d96-250">**Name**</span><span class="sxs-lookup"><span data-stu-id="79d96-250">**Name**</span></span>|<span data-ttu-id="79d96-251">**Priority**</span><span class="sxs-lookup"><span data-stu-id="79d96-251">**Priority**</span></span>|<span data-ttu-id="79d96-252">**Peso**</span><span class="sxs-lookup"><span data-stu-id="79d96-252">**Weight**</span></span>|<span data-ttu-id="79d96-253">**Port**</span><span class="sxs-lookup"><span data-stu-id="79d96-253">**Port**</span></span>|<span data-ttu-id="79d96-254">**Result**</span><span class="sxs-lookup"><span data-stu-id="79d96-254">**Result**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="79d96-255">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="79d96-255">_sip._tls</span></span>  <br/> |<span data-ttu-id="79d96-256">100</span><span class="sxs-lookup"><span data-stu-id="79d96-256">100</span></span>  <br/> |<span data-ttu-id="79d96-257">1</span><span class="sxs-lookup"><span data-stu-id="79d96-257">1</span></span>  <br/> |<span data-ttu-id="79d96-258">443</span><span class="sxs-lookup"><span data-stu-id="79d96-258">443</span></span>  <br/> |<span data-ttu-id="79d96-259">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="79d96-259">sipdir.online.lync.com</span></span>  <br/> |
    |<span data-ttu-id="79d96-260">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="79d96-260">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="79d96-261">100</span><span class="sxs-lookup"><span data-stu-id="79d96-261">100</span></span>  <br/> |<span data-ttu-id="79d96-262">1</span><span class="sxs-lookup"><span data-stu-id="79d96-262">1</span></span>  <br/> |<span data-ttu-id="79d96-263">5061</span><span class="sxs-lookup"><span data-stu-id="79d96-263">5061</span></span>  <br/> |<span data-ttu-id="79d96-264">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="79d96-264">sipfed.online.lync.com</span></span>  <br/> |
       
    ![NamesUK-BP-Configure-5-1](../media/97a96523-005a-4058-9e12-19f6c3bf9b3b.png)
  
4. <span data-ttu-id="79d96-266">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="79d96-266">Select **Save**.</span></span>
    
    <span data-ttu-id="79d96-267">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="79d96-267">(You may have to scroll down.)</span></span>
    
    ![NamesUK-BP-Configure-5-2](../media/bb617a5f-14f9-44b7-9256-bdef34d22d6b.png)
  
> [!NOTE]
>  <span data-ttu-id="79d96-p113">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o altro dopo l'aggiunta dei record DNS, vedere [Risolvere i problemi dopo la modifica del nome di dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="79d96-p113">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Troubleshoot issues after changing your domain name or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
