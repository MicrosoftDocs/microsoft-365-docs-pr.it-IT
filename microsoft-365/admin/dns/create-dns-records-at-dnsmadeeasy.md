---
title: Creare record DNS in DNSMadeEasy per Office 365
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in DNSMadeEasy per Office 365.
ms.openlocfilehash: 7b94b8d4b3a02a0f436ba2af314eece8b7606ec2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/24/2020
ms.locfileid: "42244661"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-office-365"></a><span data-ttu-id="9e00e-103">Creare record DNS in DNSMadeEasy per Office 365</span><span class="sxs-lookup"><span data-stu-id="9e00e-103">Create DNS records at DNSMadeEasy for Office 365</span></span>

 <span data-ttu-id="9e00e-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="9e00e-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="9e00e-105">Se il proprio provider di hosting DNS è DNSMadeEasy, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="9e00e-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="9e00e-106">Dopo aver aggiunto questi record in DNSMadeEasy, il domino sarà configurato per l'uso con i servizi di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e00e-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Office 365 services.</span></span>
  
<span data-ttu-id="9e00e-107">Per informazioni su hosting Web e DNS per i siti Web con Office 365, vedere [Usare un sito Web pubblico con Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="9e00e-107">To learn about webhosting and DNS for websites with Office 365, see [Use a public website with Office 365](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e00e-p101">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e00e-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="9e00e-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="9e00e-111">Add a TXT record for verification</span></span>
<span data-ttu-id="9e00e-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="9e00e-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="9e00e-p102">Prima di usare il proprio dominio con Office 365, è necessario dimostrare di esserne proprietari. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Office 365 che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="9e00e-p102">Before you use your domain with Office 365, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Office 365 that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9e00e-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="9e00e-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="9e00e-117">Per gli account DNSMadeEasy, il dominio aggiunto è stato acquistato da un registrar diverso.</span><span class="sxs-lookup"><span data-stu-id="9e00e-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="9e00e-118">DNSMadeEasy non offre servizi di registrazione di domini.</span><span class="sxs-lookup"><span data-stu-id="9e00e-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="9e00e-119">La possibilità di accedere a DNSMadeEasy e di creare il record DNS è una prova sufficiente della proprietà.</span><span class="sxs-lookup"><span data-stu-id="9e00e-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="9e00e-120">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="9e00e-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="9e00e-121">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="9e00e-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="9e00e-122">Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="9e00e-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="9e00e-123">Nell'area **txt Records** della pagina **+** **Managed DNS** selezionare il controllo () ( **Aggiungi nuovo**).</span><span class="sxs-lookup"><span data-stu-id="9e00e-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="9e00e-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9e00e-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="9e00e-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9e00e-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="9e00e-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9e00e-126">**Name**</span></span> <br/> |<span data-ttu-id="9e00e-127">**Value**</span><span class="sxs-lookup"><span data-stu-id="9e00e-127">**Value**</span></span> <br/> |<span data-ttu-id="9e00e-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e00e-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="9e00e-129">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="9e00e-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9e00e-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="9e00e-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="9e00e-131">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="9e00e-131">**Note:** This is an example.</span></span> <span data-ttu-id="9e00e-132">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella in Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e00e-132">Use your specific **Destination or Points to Address** value here, from the table in Office 365.</span></span> [<span data-ttu-id="9e00e-133">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="9e00e-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="9e00e-134">1800</span><span class="sxs-lookup"><span data-stu-id="9e00e-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="9e00e-135">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="9e00e-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="9e00e-136">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="9e00e-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="9e00e-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span><span class="sxs-lookup"><span data-stu-id="9e00e-137">Now that you've added the record at your domain registrar's site, you'll go back to Office 365 and request Office 365 to look for the record.</span></span>
  
<span data-ttu-id="9e00e-138">When Office 365 finds the correct TXT record, your domain is verified.</span><span class="sxs-lookup"><span data-stu-id="9e00e-138">When Office 365 finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="9e00e-139">Nell'interfaccia di amministrazione, andare alla pagina \*\*\*\* \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> Settings.</span><span class="sxs-lookup"><span data-stu-id="9e00e-139">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="9e00e-140">Nella pagina **Domains** selezionare il dominio che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="9e00e-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="9e00e-141">Nella pagina **configurazione** , selezionare **Avvia installazione**.</span><span class="sxs-lookup"><span data-stu-id="9e00e-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="9e00e-142">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="9e00e-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="9e00e-p107">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e00e-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-office-365"></a><span data-ttu-id="9e00e-146">Aggiungere un record MX in modo che la posta elettronica per il dominio venga recapitata in Office 365</span><span class="sxs-lookup"><span data-stu-id="9e00e-146">Add an MX record so email for your domain will come to Office 365</span></span>
<span data-ttu-id="9e00e-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="9e00e-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="9e00e-p108">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="9e00e-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="9e00e-150">Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="9e00e-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="9e00e-151">Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="9e00e-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-1-2](../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="9e00e-153">Nell'area **MX Records** della pagina **Managed DNS** selezionare il controllo **(+)** ( **Aggiungi nuovo**).</span><span class="sxs-lookup"><span data-stu-id="9e00e-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="9e00e-154">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="9e00e-154">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-1](../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="9e00e-156">Nelle caselle del nuovo record nell'area **Add MX Records** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9e00e-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="9e00e-157">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9e00e-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="9e00e-158">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9e00e-158">**Name**</span></span>|<span data-ttu-id="9e00e-159">**Server**</span><span class="sxs-lookup"><span data-stu-id="9e00e-159">**Server**</span></span>|<span data-ttu-id="9e00e-160">**MX Level**</span><span class="sxs-lookup"><span data-stu-id="9e00e-160">**MX Level**</span></span>|<span data-ttu-id="9e00e-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e00e-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9e00e-162">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="9e00e-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="9e00e-163">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="9e00e-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="9e00e-164">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9e00e-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="9e00e-165">**Nota:** Ottenere la \<propria *chiave* \> di dominio dall'account di Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e00e-165">**Note:** Get your \<*domain-key*\> from your Office 365 account.</span></span> [<span data-ttu-id="9e00e-166">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="9e00e-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="9e00e-167">10 </span><span class="sxs-lookup"><span data-stu-id="9e00e-167">10</span></span>  <br/> <span data-ttu-id="9e00e-168">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="9e00e-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="9e00e-169">1800</span><span class="sxs-lookup"><span data-stu-id="9e00e-169">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="9e00e-171">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="9e00e-171">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="9e00e-173">Se sono presenti altri record MX nella sezione **MX Records**, eliminarli tutti selezionandoli uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="9e00e-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="9e00e-175">Quando vengono selezionati tutti i record, selezionare **Elimina selezionato**.</span><span class="sxs-lookup"><span data-stu-id="9e00e-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="9e00e-177">Nella finestra di dialogo **Delete MX Records** selezionare **Delete** per confermare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="9e00e-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-office-365"></a><span data-ttu-id="9e00e-179">Aggiungere i cinque record CNAME necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="9e00e-179">Add the five CNAME records that are required for Office 365</span></span>
<span data-ttu-id="9e00e-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="9e00e-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="9e00e-p110">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="9e00e-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="9e00e-183">Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="9e00e-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="9e00e-184">Nell'area **CNAME Records** della pagina **Managed DNS** selezionare il controllo **(+)** ( **Aggiungi nuovo**).</span><span class="sxs-lookup"><span data-stu-id="9e00e-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="9e00e-185">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9e00e-185">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-3-1](../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="9e00e-187">Aggiungere il primo dei cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="9e00e-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="9e00e-188">Nelle caselle del nuovo record nell'area **Add CNAME Records** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9e00e-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="9e00e-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="9e00e-189">**Name**</span></span>|<span data-ttu-id="9e00e-190">**Alias to**</span><span class="sxs-lookup"><span data-stu-id="9e00e-190">**Alias to**</span></span>|<span data-ttu-id="9e00e-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e00e-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9e00e-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="9e00e-192">autodiscover</span></span>  <br/> |<span data-ttu-id="9e00e-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="9e00e-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="9e00e-194">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9e00e-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9e00e-195">1800</span><span class="sxs-lookup"><span data-stu-id="9e00e-195">1800</span></span>  <br/> |
    |<span data-ttu-id="9e00e-196">sip</span><span class="sxs-lookup"><span data-stu-id="9e00e-196">sip</span></span>  <br/> |<span data-ttu-id="9e00e-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9e00e-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="9e00e-198">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9e00e-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9e00e-199">1800</span><span class="sxs-lookup"><span data-stu-id="9e00e-199">1800</span></span>  <br/> |
    |<span data-ttu-id="9e00e-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9e00e-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="9e00e-201">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9e00e-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="9e00e-202">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9e00e-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9e00e-203">1800</span><span class="sxs-lookup"><span data-stu-id="9e00e-203">1800</span></span>  <br/> |
    |<span data-ttu-id="9e00e-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="9e00e-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="9e00e-205">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="9e00e-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="9e00e-206">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9e00e-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9e00e-207">1800</span><span class="sxs-lookup"><span data-stu-id="9e00e-207">1800</span></span>  <br/> |
    |<span data-ttu-id="9e00e-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="9e00e-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="9e00e-209">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="9e00e-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="9e00e-210">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9e00e-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9e00e-211">1800</span><span class="sxs-lookup"><span data-stu-id="9e00e-211">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-3-2](../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="9e00e-213">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="9e00e-213">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-3-3](../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="9e00e-215">Aggiungere ognuno degli altri quattro record CNAME.</span><span class="sxs-lookup"><span data-stu-id="9e00e-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="9e00e-216">Nella sezione **CNAME Records** selezionare il controllo **(+)** ( **Aggiungi nuovo**), creare un record usando i valori della riga successiva della tabella e quindi fare di nuovo clic su **Submit** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="9e00e-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="9e00e-217">Ripetere questa procedura fino a creare tutti e cinque i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="9e00e-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="9e00e-218">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="9e00e-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="9e00e-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="9e00e-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="9e00e-220">You cannot have more than one TXT record for SPF for a domain.</span><span class="sxs-lookup"><span data-stu-id="9e00e-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="9e00e-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span><span class="sxs-lookup"><span data-stu-id="9e00e-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="9e00e-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span><span class="sxs-lookup"><span data-stu-id="9e00e-222">If you already have an SPF record for your domain, don't create a new one for Office 365.</span></span> <span data-ttu-id="9e00e-223">Al contrario, aggiungere i valori di Office 365 necessari al record corrente in modo che sia presente un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="9e00e-223">Instead, add the required Office 365 values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="9e00e-224">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="9e00e-224">Need examples?</span></span> <span data-ttu-id="9e00e-225">Vedere queste [informazioni dettagliate e record SPF di esempio](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="9e00e-225">Check out these [External Domain Name System records for Office 365](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="9e00e-226">Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="9e00e-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="9e00e-227">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="9e00e-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="9e00e-228">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="9e00e-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="9e00e-229">Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="9e00e-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="9e00e-230">Nell'area **txt Records** della pagina **Managed DNS** selezionare il controllo **(+)** ( **Aggiungi nuovo**).</span><span class="sxs-lookup"><span data-stu-id="9e00e-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="9e00e-231">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9e00e-231">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-1](../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="9e00e-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="9e00e-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="9e00e-234">**Nome**</span><span class="sxs-lookup"><span data-stu-id="9e00e-234">**Name**</span></span>|<span data-ttu-id="9e00e-235">**Value**</span><span class="sxs-lookup"><span data-stu-id="9e00e-235">**Value**</span></span>|<span data-ttu-id="9e00e-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e00e-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="9e00e-237">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="9e00e-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="9e00e-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="9e00e-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="9e00e-239">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="9e00e-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="9e00e-240">1800</span><span class="sxs-lookup"><span data-stu-id="9e00e-240">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="9e00e-242">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="9e00e-242">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-3](../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-office-365"></a><span data-ttu-id="9e00e-244">Aggiungere i due record SRV necessari per Office 365</span><span class="sxs-lookup"><span data-stu-id="9e00e-244">Add the two SRV records that are required for Office 365</span></span>
<span data-ttu-id="9e00e-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="9e00e-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="9e00e-p113">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="9e00e-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="9e00e-248">Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="9e00e-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="9e00e-249">Nell'area **SRV Records** della pagina **Managed DNS** selezionare il controllo **(+)** ( **Aggiungi nuovo**).</span><span class="sxs-lookup"><span data-stu-id="9e00e-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="9e00e-250">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="9e00e-250">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="9e00e-252">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="9e00e-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="9e00e-253">Nelle caselle del nuovo record nell'area **Add SRV Records** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="9e00e-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="9e00e-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="9e00e-254">**Name**</span></span>|<span data-ttu-id="9e00e-255">**Priority**</span><span class="sxs-lookup"><span data-stu-id="9e00e-255">**Priority**</span></span>|<span data-ttu-id="9e00e-256">**Peso**</span><span class="sxs-lookup"><span data-stu-id="9e00e-256">**Weight**</span></span>|<span data-ttu-id="9e00e-257">**Port**</span><span class="sxs-lookup"><span data-stu-id="9e00e-257">**Port**</span></span>|<span data-ttu-id="9e00e-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="9e00e-258">**Host**</span></span>|<span data-ttu-id="9e00e-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="9e00e-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="9e00e-260">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="9e00e-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="9e00e-261">100</span><span class="sxs-lookup"><span data-stu-id="9e00e-261">100</span></span>  <br/> |<span data-ttu-id="9e00e-262">1</span><span class="sxs-lookup"><span data-stu-id="9e00e-262">1</span></span>  <br/> |<span data-ttu-id="9e00e-263">443</span><span class="sxs-lookup"><span data-stu-id="9e00e-263">443</span></span>  <br/> |<span data-ttu-id="9e00e-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9e00e-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="9e00e-265">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9e00e-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9e00e-266">1800</span><span class="sxs-lookup"><span data-stu-id="9e00e-266">1800</span></span>  <br/> |
    |<span data-ttu-id="9e00e-267">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="9e00e-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="9e00e-268">100</span><span class="sxs-lookup"><span data-stu-id="9e00e-268">100</span></span>  <br/> |<span data-ttu-id="9e00e-269">1</span><span class="sxs-lookup"><span data-stu-id="9e00e-269">1</span></span>  <br/> |<span data-ttu-id="9e00e-270">5061</span><span class="sxs-lookup"><span data-stu-id="9e00e-270">5061</span></span>  <br/> |<span data-ttu-id="9e00e-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="9e00e-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="9e00e-272">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="9e00e-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="9e00e-273">1800</span><span class="sxs-lookup"><span data-stu-id="9e00e-273">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="9e00e-275">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="9e00e-275">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="9e00e-277">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="9e00e-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="9e00e-278">Nella sezione **SRV Records** selezionare il controllo **(+)** ( **Aggiungi nuovo**), creare un record usando i valori della riga successiva della tabella e quindi fare di nuovo clic su **Submit** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="9e00e-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="9e00e-p114">In genere l'applicazione delle modifiche al DNS richiede circa 15 minuti. A volte può tuttavia capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="9e00e-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records in Office 365](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

