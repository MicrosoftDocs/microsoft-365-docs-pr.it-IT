---
title: Creare record DNS in DNSMadeEasy per Microsoft
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business Online e altri servizi in DNSMadeEasy per Microsoft.
ms.openlocfilehash: 11e8072ab3c798ed550043370d0e6e79c7370b4d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910391"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="eaabf-103">Creare record DNS in DNSMadeEasy per Microsoft</span><span class="sxs-lookup"><span data-stu-id="eaabf-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="eaabf-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.yml)**.</span><span class="sxs-lookup"><span data-stu-id="eaabf-104">**[Check the Domains FAQ](../setup/domains-faq.yml)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="eaabf-105">Se il proprio provider di hosting DNS è DNSMadeEasy, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="eaabf-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="eaabf-106">Dopo aver aggiunto questi record in DNSMadeEasy, il dominio verrà configurato per l'utilizzo con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eaabf-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  

  
> [!NOTE]
> <span data-ttu-id="eaabf-p101">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="eaabf-p101">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="eaabf-110">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="eaabf-110">Add a TXT record for verification</span></span>
<span data-ttu-id="eaabf-111"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="eaabf-111"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="eaabf-p102">Prima di usare il proprio dominio con Microsoft, è necessario dimostrare di esserne il proprietario. La capacità di accedere al proprio account nel registrar e di creare il record DNS dimostra a Microsoft che si è il proprietario del dominio.</span><span class="sxs-lookup"><span data-stu-id="eaabf-p102">Before you use your domain with Microsoft, we have to make sure that you own it. Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="eaabf-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="eaabf-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="eaabf-116">Per gli account DNSMadeEasy, il dominio aggiunto è stato acquistato da un registrar diverso.</span><span class="sxs-lookup"><span data-stu-id="eaabf-116">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="eaabf-117">DNSMadeEasy non offre servizi di registrazione di domini.</span><span class="sxs-lookup"><span data-stu-id="eaabf-117">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="eaabf-118">La possibilità di accedere a DNSMadeEasy e di creare il record DNS è una prova sufficiente della proprietà.</span><span class="sxs-lookup"><span data-stu-id="eaabf-118">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="eaabf-119">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="eaabf-119">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="eaabf-120">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="eaabf-120">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="eaabf-121">**Nell'area** **Domini** aggiornati di recente della pagina Console di gestione selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="eaabf-121">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="eaabf-122">Nell'area **TXT Records** della pagina **Managed DNS** selezionare il controllo ( ) ( ) ( **+** Add **new**).</span><span class="sxs-lookup"><span data-stu-id="eaabf-122">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="eaabf-123">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="eaabf-123">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="eaabf-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="eaabf-124">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="eaabf-125">**Name**</span><span class="sxs-lookup"><span data-stu-id="eaabf-125">**Name**</span></span> <br/> |<span data-ttu-id="eaabf-126">**Valore**</span><span class="sxs-lookup"><span data-stu-id="eaabf-126">**Value**</span></span> <br/> |<span data-ttu-id="eaabf-127">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eaabf-127">**TTL**</span></span> <br/> |
    |<span data-ttu-id="eaabf-128">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="eaabf-128">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="eaabf-129">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="eaabf-129">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="eaabf-130">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="eaabf-130">**Note:** This is an example.</span></span> <span data-ttu-id="eaabf-131">Usare il valore specifico di **Indirizzo di destinazione o puntamento** indicato nella tabella.</span><span class="sxs-lookup"><span data-stu-id="eaabf-131">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="eaabf-132">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="eaabf-132">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="eaabf-133">1800</span><span class="sxs-lookup"><span data-stu-id="eaabf-133">1800</span></span>  <br/> |
   
5. <span data-ttu-id="eaabf-134">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="eaabf-134">Select **Submit**.</span></span>
    
6. <span data-ttu-id="eaabf-135">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="eaabf-135">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="eaabf-136">Una volta che il record è stato aggiunto al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="eaabf-136">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="eaabf-137">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="eaabf-137">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="eaabf-138">Nell'interfaccia di amministrazione di Microsoft, passare alla pagina **Impostazioni** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domini</a>.</span><span class="sxs-lookup"><span data-stu-id="eaabf-138">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="eaabf-139">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="eaabf-139">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="eaabf-140">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="eaabf-140">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="eaabf-141">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="eaabf-141">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="eaabf-p107">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="eaabf-p107">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="eaabf-145">Aggiungere un record MX in modo che la posta elettronica del dominio venga recapitata in Microsoft</span><span class="sxs-lookup"><span data-stu-id="eaabf-145">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="eaabf-146"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="eaabf-146"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="eaabf-p108">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="eaabf-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="eaabf-149">**Nell'area** **Domini** aggiornati di recente della pagina Console di gestione selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="eaabf-149">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="eaabf-150">**Nell'area** **Domini** aggiornati di recente della pagina Console di gestione selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="eaabf-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="eaabf-152">Nell'area **MX Records** della pagina **Managed DNS** selezionare il **controllo (+)** ( **Add new**).</span><span class="sxs-lookup"><span data-stu-id="eaabf-152">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="eaabf-153">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="eaabf-153">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="eaabf-155">Nelle caselle del nuovo record nell'area **Add MX Records** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="eaabf-155">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="eaabf-156">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="eaabf-156">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="eaabf-157">**Name**</span><span class="sxs-lookup"><span data-stu-id="eaabf-157">**Name**</span></span>|<span data-ttu-id="eaabf-158">**Server**</span><span class="sxs-lookup"><span data-stu-id="eaabf-158">**Server**</span></span>|<span data-ttu-id="eaabf-159">**MX Level**</span><span class="sxs-lookup"><span data-stu-id="eaabf-159">**MX Level**</span></span>|<span data-ttu-id="eaabf-160">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eaabf-160">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="eaabf-161">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="eaabf-161">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="eaabf-162">*\<domain-key\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="eaabf-162">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="eaabf-163">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="eaabf-163">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="eaabf-164">**Nota:** ottenere il valore \<*domain-key*\> dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eaabf-164">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="eaabf-165">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="eaabf-165">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="eaabf-166">10  </span><span class="sxs-lookup"><span data-stu-id="eaabf-166">10</span></span>  <br/> <span data-ttu-id="eaabf-167">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](../setup/domains-faq.yml).</span><span class="sxs-lookup"><span data-stu-id="eaabf-167">For more information about priority, see [What is MX priority?](../setup/domains-faq.yml)</span></span> <br/> |<span data-ttu-id="eaabf-168">1800</span><span class="sxs-lookup"><span data-stu-id="eaabf-168">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="eaabf-170">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="eaabf-170">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="eaabf-172">Se sono presenti altri record MX nella sezione **MX Records**, eliminarli tutti selezionandoli uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="eaabf-172">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="eaabf-174">Quando tutti i record sono selezionati, selezionare **Elimina selezionato.**</span><span class="sxs-lookup"><span data-stu-id="eaabf-174">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="eaabf-176">Nella finestra **di dialogo Elimina record MX** selezionare Elimina **per** confermare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="eaabf-176">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="eaabf-178">Aggiungere i cinque record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="eaabf-178">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="eaabf-179"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="eaabf-179"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="eaabf-p110">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="eaabf-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="eaabf-182">**Nell'area** **Domini** aggiornati di recente della pagina Console di gestione selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="eaabf-182">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="eaabf-183">**Nell'area** **CNAME Records** della pagina Managed DNS selezionare il controllo **(+)** ( **Add new**).</span><span class="sxs-lookup"><span data-stu-id="eaabf-183">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="eaabf-184">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="eaabf-184">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="eaabf-186">Aggiungere il primo dei cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="eaabf-186">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="eaabf-187">Nelle caselle del nuovo record nell'area **Add CNAME Records** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="eaabf-187">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="eaabf-188">**Name**</span><span class="sxs-lookup"><span data-stu-id="eaabf-188">**Name**</span></span>|<span data-ttu-id="eaabf-189">**Alias to**</span><span class="sxs-lookup"><span data-stu-id="eaabf-189">**Alias to**</span></span>|<span data-ttu-id="eaabf-190">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eaabf-190">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="eaabf-191">autodiscover</span><span class="sxs-lookup"><span data-stu-id="eaabf-191">autodiscover</span></span>  <br/> |<span data-ttu-id="eaabf-192">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="eaabf-192">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="eaabf-193">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="eaabf-193">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="eaabf-194">1800</span><span class="sxs-lookup"><span data-stu-id="eaabf-194">1800</span></span>  <br/> |
    |<span data-ttu-id="eaabf-195">sip</span><span class="sxs-lookup"><span data-stu-id="eaabf-195">sip</span></span>  <br/> |<span data-ttu-id="eaabf-196">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="eaabf-196">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="eaabf-197">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="eaabf-197">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="eaabf-198">1800</span><span class="sxs-lookup"><span data-stu-id="eaabf-198">1800</span></span>  <br/> |
    |<span data-ttu-id="eaabf-199">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="eaabf-199">lyncdiscover</span></span>  <br/> |<span data-ttu-id="eaabf-200">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="eaabf-200">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="eaabf-201">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="eaabf-201">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="eaabf-202">1800</span><span class="sxs-lookup"><span data-stu-id="eaabf-202">1800</span></span>  <br/> |
    |<span data-ttu-id="eaabf-203">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="eaabf-203">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="eaabf-204">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="eaabf-204">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="eaabf-205">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="eaabf-205">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="eaabf-206">1800</span><span class="sxs-lookup"><span data-stu-id="eaabf-206">1800</span></span>  <br/> |
    |<span data-ttu-id="eaabf-207">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="eaabf-207">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="eaabf-208">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="eaabf-208">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="eaabf-209">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="eaabf-209">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="eaabf-210">1800</span><span class="sxs-lookup"><span data-stu-id="eaabf-210">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="eaabf-212">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="eaabf-212">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="eaabf-214">Aggiungere ognuno degli altri quattro record CNAME.</span><span class="sxs-lookup"><span data-stu-id="eaabf-214">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="eaabf-215">Nella sezione **CNAME Records** selezionare il controllo **(+)** ( **Add new**), creare un record utilizzando i valori della riga successiva della tabella e quindi selezionare di nuovo **Submit** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="eaabf-215">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="eaabf-216">Ripetere questo processo finché non sono stati creati tutti e cinque i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="eaabf-216">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="eaabf-217">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="eaabf-217">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="eaabf-218"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="eaabf-218"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="eaabf-219">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="eaabf-219">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="eaabf-220">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="eaabf-220">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="eaabf-221">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="eaabf-221">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="eaabf-222">Aggiungere invece i valori Microsoft necessari al record corrente in modo da disporre di un singolo record  *SPF*  che include entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="eaabf-222">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="eaabf-223">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="eaabf-223">Need examples?</span></span> <span data-ttu-id="eaabf-224">Consultare [Record Domain Name System (DNS) esterni per Microsoft](../../enterprise/external-domain-name-system-records.md).</span><span class="sxs-lookup"><span data-stu-id="eaabf-224">Check out these [External Domain Name System records for Microsoft](../../enterprise/external-domain-name-system-records.md).</span></span> <span data-ttu-id="eaabf-225">Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF.](../setup/domains-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="eaabf-225">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.yml).</span></span> 
  
1. <span data-ttu-id="eaabf-226">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="eaabf-226">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="eaabf-227">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="eaabf-227">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="eaabf-228">**Nell'area** **Domini** aggiornati di recente della pagina Console di gestione selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="eaabf-228">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="eaabf-229">**Nell'area TXT** **Records** della pagina Managed DNS selezionare il **controllo (+)** ( **Add new**).</span><span class="sxs-lookup"><span data-stu-id="eaabf-229">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="eaabf-230">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="eaabf-230">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="eaabf-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="eaabf-232">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="eaabf-233">**Name**</span><span class="sxs-lookup"><span data-stu-id="eaabf-233">**Name**</span></span>|<span data-ttu-id="eaabf-234">**Valore**</span><span class="sxs-lookup"><span data-stu-id="eaabf-234">**Value**</span></span>|<span data-ttu-id="eaabf-235">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eaabf-235">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="eaabf-236">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="eaabf-236">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="eaabf-237">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="eaabf-237">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="eaabf-238">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="eaabf-238">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="eaabf-239">1800</span><span class="sxs-lookup"><span data-stu-id="eaabf-239">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="eaabf-241">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="eaabf-241">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="eaabf-243">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="eaabf-243">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="eaabf-244"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="eaabf-244"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="eaabf-p113">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="eaabf-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="eaabf-247">**Nell'area** **Domini** aggiornati di recente della pagina Console di gestione selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="eaabf-247">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="eaabf-248">Nell'area **Record SRV** della pagina **DNS** gestito selezionare il **controllo (+)** ( **Aggiungi nuovo**).</span><span class="sxs-lookup"><span data-stu-id="eaabf-248">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="eaabf-249">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="eaabf-249">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="eaabf-251">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="eaabf-251">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="eaabf-252">Nelle caselle del nuovo record nell'area **Add SRV Records** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="eaabf-252">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="eaabf-253">**Name**</span><span class="sxs-lookup"><span data-stu-id="eaabf-253">**Name**</span></span>|<span data-ttu-id="eaabf-254">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="eaabf-254">**Priority**</span></span>|<span data-ttu-id="eaabf-255">**Peso**</span><span class="sxs-lookup"><span data-stu-id="eaabf-255">**Weight**</span></span>|<span data-ttu-id="eaabf-256">**Porta**</span><span class="sxs-lookup"><span data-stu-id="eaabf-256">**Port**</span></span>|<span data-ttu-id="eaabf-257">**Host**</span><span class="sxs-lookup"><span data-stu-id="eaabf-257">**Host**</span></span>|<span data-ttu-id="eaabf-258">**TTL**</span><span class="sxs-lookup"><span data-stu-id="eaabf-258">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="eaabf-259">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="eaabf-259">_sip._tls</span></span>  <br/> |<span data-ttu-id="eaabf-260">100</span><span class="sxs-lookup"><span data-stu-id="eaabf-260">100</span></span>  <br/> |<span data-ttu-id="eaabf-261">1</span><span class="sxs-lookup"><span data-stu-id="eaabf-261">1</span></span>  <br/> |<span data-ttu-id="eaabf-262">443</span><span class="sxs-lookup"><span data-stu-id="eaabf-262">443</span></span>  <br/> |<span data-ttu-id="eaabf-263">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="eaabf-263">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="eaabf-264">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="eaabf-264">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="eaabf-265">1800</span><span class="sxs-lookup"><span data-stu-id="eaabf-265">1800</span></span>  <br/> |
    |<span data-ttu-id="eaabf-266">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="eaabf-266">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="eaabf-267">100</span><span class="sxs-lookup"><span data-stu-id="eaabf-267">100</span></span>  <br/> |<span data-ttu-id="eaabf-268">1</span><span class="sxs-lookup"><span data-stu-id="eaabf-268">1</span></span>  <br/> |<span data-ttu-id="eaabf-269">5061</span><span class="sxs-lookup"><span data-stu-id="eaabf-269">5061</span></span>  <br/> |<span data-ttu-id="eaabf-270">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="eaabf-270">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="eaabf-271">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="eaabf-271">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="eaabf-272">1800</span><span class="sxs-lookup"><span data-stu-id="eaabf-272">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="eaabf-274">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="eaabf-274">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="eaabf-276">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="eaabf-276">Add the other SRV record.</span></span>
    
    <span data-ttu-id="eaabf-277">Nella sezione **Record SRV** selezionare il controllo **(+)** ( **Aggiungi** nuovo ), creare un record utilizzando i  valori della riga successiva della tabella e quindi selezionare di nuovo Invia per completare il record.</span><span class="sxs-lookup"><span data-stu-id="eaabf-277">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="eaabf-p114">In genere, l'applicazione delle modifiche al DNS richiede circa 15 minuti. Tuttavia, a volte può capitare che l'aggiornamento di una modifica nel sistema DNS di Internet richieda più tempo. In caso di problemi con il flusso di posta o di altro tipo dopo l'aggiunta dei record DNS, vedere [Individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="eaabf-p114">Typically it takes about 15 minutes for DNS changes to take effect. However, it can occasionally take longer for a change you've made to update across the Internet's DNS system. If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
