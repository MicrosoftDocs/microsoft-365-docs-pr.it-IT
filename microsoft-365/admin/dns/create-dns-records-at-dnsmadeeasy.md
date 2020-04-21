---
title: Creare record DNS in DNSMadeEasy per Microsoft
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
ms.assetid: e158b079-b054-4b7e-8e01-e55169ce18d7
description: Informazioni su come verificare il dominio e configurare i record DNS per la posta elettronica, Skype for business online e altri servizi in DNSMadeEasy per Microsoft.
ms.openlocfilehash: dde060b6e03eebb89029b742402558e95031b1d3
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629684"
---
# <a name="create-dns-records-at-dnsmadeeasy-for-microsoft"></a><span data-ttu-id="5c368-103">Creare record DNS in DNSMadeEasy per Microsoft</span><span class="sxs-lookup"><span data-stu-id="5c368-103">Create DNS records at DNSMadeEasy for Microsoft</span></span>

 <span data-ttu-id="5c368-104">**Se non si trova ciò che si sta cercando, [vedere le domande frequenti sui domini](../setup/domains-faq.md)**.</span><span class="sxs-lookup"><span data-stu-id="5c368-104">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="5c368-105">Se il proprio provider di hosting DNS è DNSMadeEasy, seguire i passaggi di questo articolo per verificare il dominio e configurare i record DNS per la posta elettronica, Skype for Business online e così via.</span><span class="sxs-lookup"><span data-stu-id="5c368-105">If DNSMadeEasy is your DNS hosting provider, follow the steps in this article to verify your domain and set up DNS records for email, Skype for Business Online, and so on.</span></span>
  
<span data-ttu-id="5c368-106">Dopo aver aggiunto questi record in DNSMadeEasy, il dominio sarà configurato per l'uso con i servizi Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c368-106">After you add these records at DNSMadeEasy, your domain will be set up to work with Microsoft services.</span></span>
  
<span data-ttu-id="5c368-107">Per ulteriori informazioni su Webhosting e DNS per i siti Web con Microsoft, vedere [utilizzare un sito Web pubblico con Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span><span class="sxs-lookup"><span data-stu-id="5c368-107">To learn about webhosting and DNS for websites with Microsoft, see [Use a public website with Microsoft](https://support.office.com/article/choose-a-public-website-3325d50e-d131-403c-a278-7f3296fe33a9).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c368-108">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="5c368-108">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="5c368-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="5c368-109">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="5c368-110">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5c368-110">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-a-txt-record-for-verification"></a><span data-ttu-id="5c368-111">Aggiungere un record TXT a scopo di verifica</span><span class="sxs-lookup"><span data-stu-id="5c368-111">Add a TXT record for verification</span></span>
<span data-ttu-id="5c368-112"><a name="BKMK_verify"> </a></span><span class="sxs-lookup"><span data-stu-id="5c368-112"><a name="BKMK_verify"> </a></span></span>

<span data-ttu-id="5c368-113">Prima di utilizzare il dominio con Microsoft, è necessario assicurarsi di possederlo.</span><span class="sxs-lookup"><span data-stu-id="5c368-113">Before you use your domain with Microsoft, we have to make sure that you own it.</span></span> <span data-ttu-id="5c368-114">La possibilità di eseguire l'accesso al proprio account presso il registrar e di creare il record DNS dimostra a Microsoft che si è proprietari del dominio.</span><span class="sxs-lookup"><span data-stu-id="5c368-114">Your ability to log in to your account at your domain registrar and create the DNS record proves to Microsoft that you own the domain.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5c368-p103">Questo record viene usato esclusivamente per verificare di essere proprietari del dominio e non ha altri effetti. È possibile eliminarlo in un secondo momento, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="5c368-p103">This record is used only to verify that you own your domain; it doesn't affect anything else. You can delete it later, if you like.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5c368-117">Per gli account DNSMadeEasy, il dominio aggiunto è stato acquistato da un registrar diverso.</span><span class="sxs-lookup"><span data-stu-id="5c368-117">For DNSMadeEasy accounts, the domain you added was purchased from a separate domain registrar.</span></span> <span data-ttu-id="5c368-118">DNSMadeEasy non offre servizi di registrazione di domini.</span><span class="sxs-lookup"><span data-stu-id="5c368-118">DNSMadeEasy does not offer domain registration services.</span></span> <span data-ttu-id="5c368-119">La possibilità di accedere a DNSMadeEasy e di creare il record DNS è una prova sufficiente della proprietà.</span><span class="sxs-lookup"><span data-stu-id="5c368-119">Your ability to log in at DNSMadeEasy and create the DNS record is sufficient proof of ownership.</span></span> 
  
1. <span data-ttu-id="5c368-120">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="5c368-120">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="5c368-121">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5c368-121">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5c368-122">Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="5c368-122">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5c368-123">Nell'area **txt Records** della pagina **+** **Managed DNS** selezionare il controllo () ( **Aggiungi nuovo**).</span><span class="sxs-lookup"><span data-stu-id="5c368-123">On the **Managed DNS** page, in the **TXT Records** area, select the ( **+**) control ( **Add new**).</span></span>
    
    <span data-ttu-id="5c368-124">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5c368-124">(You may have to scroll down.)</span></span>
    
4. <span data-ttu-id="5c368-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5c368-125">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    ||||
    |:-----|:-----|:-----|
    |<span data-ttu-id="5c368-126">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5c368-126">**Name**</span></span> <br/> |<span data-ttu-id="5c368-127">**Valore**</span><span class="sxs-lookup"><span data-stu-id="5c368-127">**Value**</span></span> <br/> |<span data-ttu-id="5c368-128">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5c368-128">**TTL**</span></span> <br/> |
    |<span data-ttu-id="5c368-129">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="5c368-129">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5c368-130">MS=ms *XXXXXXXX*</span><span class="sxs-lookup"><span data-stu-id="5c368-130">MS=ms *XXXXXXXX*</span></span>  <br/> <span data-ttu-id="5c368-131">**Note:** questo è un esempio.</span><span class="sxs-lookup"><span data-stu-id="5c368-131">**Note:** This is an example.</span></span> <span data-ttu-id="5c368-132">Utilizzare il valore **di indirizzo di destinazione o puntamento** specifico qui, dalla tabella.</span><span class="sxs-lookup"><span data-stu-id="5c368-132">Use your specific **Destination or Points to Address** value here, from the table.</span></span> [<span data-ttu-id="5c368-133">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="5c368-133">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5c368-134">1800</span><span class="sxs-lookup"><span data-stu-id="5c368-134">1800</span></span>  <br/> |
   
5. <span data-ttu-id="5c368-135">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="5c368-135">Select **Submit**.</span></span>
    
6. <span data-ttu-id="5c368-136">Attendere alcuni minuti prima di continuare, in modo che il record appena creato venga aggiornato in Internet.</span><span class="sxs-lookup"><span data-stu-id="5c368-136">Wait a few minutes before you continue, so that the record you just created can update across the Internet.</span></span>
    
<span data-ttu-id="5c368-137">Dopo aver aggiunto il record al sito del registrar, è possibile tornare a Microsoft e richiedere il record.</span><span class="sxs-lookup"><span data-stu-id="5c368-137">Now that you've added the record at your domain registrar's site, you'll go back to Microsoft and request the record.</span></span>
  
<span data-ttu-id="5c368-138">Quando Microsoft trova il record TXT corretto, il dominio è verificato.</span><span class="sxs-lookup"><span data-stu-id="5c368-138">When Microsoft finds the correct TXT record, your domain is verified.</span></span>
  
1. <span data-ttu-id="5c368-139">Nell'interfaccia di amministrazione di Microsoft, andare alla pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> **Settings** \> .</span><span class="sxs-lookup"><span data-stu-id="5c368-139">In the Microsoft admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

    
2. <span data-ttu-id="5c368-140">Nella pagina **Domini** selezionare il dominio da verificare.</span><span class="sxs-lookup"><span data-stu-id="5c368-140">On the **Domains** page, select the domain that you are verifying.</span></span> 
    
3. <span data-ttu-id="5c368-141">Nella pagina **Configurazione** selezionare **Avvia configurazione**.</span><span class="sxs-lookup"><span data-stu-id="5c368-141">On the **Setup** page, select **Start setup**.</span></span>
    
4. <span data-ttu-id="5c368-142">Nella pagina **Verifica dominio** selezionare **Verifica**.</span><span class="sxs-lookup"><span data-stu-id="5c368-142">On the **Verify domain** page, select **Verify**.</span></span>
    
> [!NOTE]
> <span data-ttu-id="5c368-143">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="5c368-143">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="5c368-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="5c368-144">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="5c368-145">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5c368-145">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  
## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a><span data-ttu-id="5c368-146">Aggiungere un record MX in modo che la posta elettronica per il dominio venga a Microsoft</span><span class="sxs-lookup"><span data-stu-id="5c368-146">Add an MX record so email for your domain will come to Microsoft</span></span>
<span data-ttu-id="5c368-147"><a name="BKMK_add_MX"> </a></span><span class="sxs-lookup"><span data-stu-id="5c368-147"><a name="BKMK_add_MX"> </a></span></span>

1. <span data-ttu-id="5c368-p108">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5c368-p108">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5c368-150">Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="5c368-150">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    <span data-ttu-id="5c368-151">Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="5c368-151">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-1-2](../../media/8d8f403e-d7cd-429e-913b-dacb1f4644a2.png)
  
3. <span data-ttu-id="5c368-153">Nell'area **MX Records** della pagina **Managed DNS** selezionare il controllo **(+)** ( **Aggiungi nuovo**).</span><span class="sxs-lookup"><span data-stu-id="5c368-153">On the **Managed DNS** page, in the **MX Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5c368-154">(You may have to scroll down.)</span><span class="sxs-lookup"><span data-stu-id="5c368-154">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-1](../../media/404c73bf-1db4-4d68-82d8-68303f418ed4.png)
  
4. <span data-ttu-id="5c368-156">Nelle caselle del nuovo record nell'area **Add MX Records** digitare oppure copiare e incollare i valori della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5c368-156">In the **Add MX Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    <span data-ttu-id="5c368-157">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5c368-157">(You may have to scroll down.)</span></span>
    
    |<span data-ttu-id="5c368-158">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5c368-158">**Name**</span></span>|<span data-ttu-id="5c368-159">**Server**</span><span class="sxs-lookup"><span data-stu-id="5c368-159">**Server**</span></span>|<span data-ttu-id="5c368-160">**MX Level**</span><span class="sxs-lookup"><span data-stu-id="5c368-160">**MX Level**</span></span>|<span data-ttu-id="5c368-161">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5c368-161">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5c368-162">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="5c368-162">(Leave this field empty.)</span></span>  <br/> | <span data-ttu-id="5c368-163">*\<chiave-dominio\>*  .mail.protection.outlook.com</span><span class="sxs-lookup"><span data-stu-id="5c368-163">*\<domain-key\>*  .mail.protection.outlook.com</span></span>  <br/> <span data-ttu-id="5c368-164">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="5c368-164">**This value MUST end with a period (.)**</span></span> <br/> <span data-ttu-id="5c368-165">**Nota:** Ottenere la \<propria *chiave* \> di dominio dal proprio account Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c368-165">**Note:** Get your \<*domain-key*\> from your Microsoft account.</span></span> [<span data-ttu-id="5c368-166">Come trovarlo</span><span class="sxs-lookup"><span data-stu-id="5c368-166">How do I find this?</span></span>](../get-help-with-domains/information-for-dns-records.md)          |<span data-ttu-id="5c368-167">10 </span><span class="sxs-lookup"><span data-stu-id="5c368-167">10</span></span>  <br/> <span data-ttu-id="5c368-168">Per altre informazioni sulla priorità, vedere [Informazioni sulla priorità MX](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx).</span><span class="sxs-lookup"><span data-stu-id="5c368-168">For more information about priority, see [What is MX priority?](https://support.office.com/article/2784cc4d-95be-443d-b5f7-bb5dd867ba83.aspx)</span></span> <br/> |<span data-ttu-id="5c368-169">1800</span><span class="sxs-lookup"><span data-stu-id="5c368-169">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-2-2](../../media/69b53af9-1eec-435c-8434-1b6058c1ec82.png)
  
5. <span data-ttu-id="5c368-171">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="5c368-171">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-3](../../media/381054a6-bb85-4ebb-b576-42cbba78ed1b.png)
  
6. <span data-ttu-id="5c368-173">Se sono presenti altri record MX nella sezione **MX Records**, eliminarli tutti selezionandoli uno alla volta.</span><span class="sxs-lookup"><span data-stu-id="5c368-173">If there are any other MX records listed in the **MX Records** section, delete all of them by selecting each one.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-4-1](../../media/58a07769-0b30-4111-b555-bfc3b82a7d4c.png)
  
7. <span data-ttu-id="5c368-175">Quando vengono selezionati tutti i record, selezionare **Elimina selezionato**.</span><span class="sxs-lookup"><span data-stu-id="5c368-175">When all records are selected, select **Delete selected**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-2-4-2](../../media/e9064c07-1ce7-4387-b47a-90d4193da374.png)
  
8. <span data-ttu-id="5c368-177">Nella finestra di dialogo **Delete MX Records** selezionare **Delete** per confermare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="5c368-177">In the **Delete MX Records** dialog box, select **Delete** to confirm your changes.</span></span> 
    
    ![DNSMadeEasy-BP-Configure-2-5](../../media/03c405e5-868f-468f-b6d2-046d27b201fb.png)
  
## <a name="add-the-five-cname-records-that-are-required-for-microsoft"></a><span data-ttu-id="5c368-179">Aggiungere i cinque record CNAME necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="5c368-179">Add the five CNAME records that are required for Microsoft</span></span>
<span data-ttu-id="5c368-180"><a name="BKMK_add_CNAME"> </a></span><span class="sxs-lookup"><span data-stu-id="5c368-180"><a name="BKMK_add_CNAME"> </a></span></span>

1. <span data-ttu-id="5c368-p110">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5c368-p110">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5c368-183">Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="5c368-183">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5c368-184">Nell'area **CNAME Records** della pagina **Managed DNS** selezionare il controllo **(+)** ( **Aggiungi nuovo**).</span><span class="sxs-lookup"><span data-stu-id="5c368-184">On the **Managed DNS** page, in the **CNAME Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5c368-185">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5c368-185">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-configure-3-1](../../media/a5feb238-690d-4b64-a625-91a82b3f4068.png)
  
4. <span data-ttu-id="5c368-187">Aggiungere il primo dei cinque record CNAME.</span><span class="sxs-lookup"><span data-stu-id="5c368-187">Add the first of the five CNAME records.</span></span>
    
    <span data-ttu-id="5c368-188">Nelle caselle del nuovo record nell'area **Add CNAME Records** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5c368-188">In the **Add CNAME Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="5c368-189">**Name**</span><span class="sxs-lookup"><span data-stu-id="5c368-189">**Name**</span></span>|<span data-ttu-id="5c368-190">**Alias to**</span><span class="sxs-lookup"><span data-stu-id="5c368-190">**Alias to**</span></span>|<span data-ttu-id="5c368-191">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5c368-191">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5c368-192">autodiscover</span><span class="sxs-lookup"><span data-stu-id="5c368-192">autodiscover</span></span>  <br/> |<span data-ttu-id="5c368-193">autodiscover.outlook.com.</span><span class="sxs-lookup"><span data-stu-id="5c368-193">autodiscover.outlook.com.</span></span>  <br/> <span data-ttu-id="5c368-194">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="5c368-194">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5c368-195">1800</span><span class="sxs-lookup"><span data-stu-id="5c368-195">1800</span></span>  <br/> |
    |<span data-ttu-id="5c368-196">sip</span><span class="sxs-lookup"><span data-stu-id="5c368-196">sip</span></span>  <br/> |<span data-ttu-id="5c368-197">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5c368-197">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5c368-198">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="5c368-198">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5c368-199">1800</span><span class="sxs-lookup"><span data-stu-id="5c368-199">1800</span></span>  <br/> |
    |<span data-ttu-id="5c368-200">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="5c368-200">lyncdiscover</span></span>  <br/> |<span data-ttu-id="5c368-201">webdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5c368-201">webdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5c368-202">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="5c368-202">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5c368-203">1800</span><span class="sxs-lookup"><span data-stu-id="5c368-203">1800</span></span>  <br/> |
    |<span data-ttu-id="5c368-204">enterpriseregistration</span><span class="sxs-lookup"><span data-stu-id="5c368-204">enterpriseregistration</span></span>  <br/> |<span data-ttu-id="5c368-205">enterpriseregistration.windows.net.</span><span class="sxs-lookup"><span data-stu-id="5c368-205">enterpriseregistration.windows.net.</span></span>  <br/> <span data-ttu-id="5c368-206">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="5c368-206">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5c368-207">1800</span><span class="sxs-lookup"><span data-stu-id="5c368-207">1800</span></span>  <br/> |
    |<span data-ttu-id="5c368-208">enterpriseenrollment</span><span class="sxs-lookup"><span data-stu-id="5c368-208">enterpriseenrollment</span></span>  <br/> |<span data-ttu-id="5c368-209">enterpriseenrollment-s.manage.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="5c368-209">enterpriseenrollment-s.manage.microsoft.com.</span></span>  <br/> <span data-ttu-id="5c368-210">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="5c368-210">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5c368-211">1800</span><span class="sxs-lookup"><span data-stu-id="5c368-211">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-configure-3-2](../../media/de6dddcd-bf0a-4993-ab4c-a6d10167bf34.png)
  
5. <span data-ttu-id="5c368-213">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="5c368-213">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-configure-3-3](../../media/e44ef73e-99cb-41ce-a3f2-549cb2f29eef.png)
  
6. <span data-ttu-id="5c368-215">Aggiungere ognuno degli altri quattro record CNAME.</span><span class="sxs-lookup"><span data-stu-id="5c368-215">Add each of the other four CNAME records.</span></span>
    
    <span data-ttu-id="5c368-216">Nella sezione **CNAME Records** selezionare il controllo **(+)** ( **Aggiungi nuovo**), creare un record usando i valori della riga successiva della tabella e quindi fare di nuovo clic su **Submit** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="5c368-216">In the **CNAME Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
    <span data-ttu-id="5c368-217">Ripetere questa procedura fino a creare tutti e cinque i record CNAME.</span><span class="sxs-lookup"><span data-stu-id="5c368-217">Repeat this process until you have created all five CNAME records.</span></span>
    
## <a name="add-a-txt-record-for-spf-to-help-prevent-email-spam"></a><span data-ttu-id="5c368-218">Aggiungere un record TXT per SPF per evitare di ricevere posta indesiderata</span><span class="sxs-lookup"><span data-stu-id="5c368-218">Add a TXT record for SPF to help prevent email spam</span></span>
<span data-ttu-id="5c368-219"><a name="BKMK_add_TXT"> </a></span><span class="sxs-lookup"><span data-stu-id="5c368-219"><a name="BKMK_add_TXT"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="5c368-220">Non può essere presente più di un record TXT per SPF per un dominio.</span><span class="sxs-lookup"><span data-stu-id="5c368-220">You cannot have more than one TXT record for SPF for a domain.</span></span> <span data-ttu-id="5c368-221">Se il dominio ha più record SPF, si verificheranno errori nella gestione della posta elettronica, oltre a problemi di recapito e di classificazione della posta indesiderata.</span><span class="sxs-lookup"><span data-stu-id="5c368-221">If your domain has more than one SPF record, you'll get email errors, as well as delivery and spam classification issues.</span></span> <span data-ttu-id="5c368-222">Se si dispone già di un record SPF per il dominio, non crearne uno nuovo per Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5c368-222">If you already have an SPF record for your domain, don't create a new one for Microsoft.</span></span> <span data-ttu-id="5c368-223">Al contrario, aggiungere i valori Microsoft necessari al record corrente in modo da disporre di un *singolo* record SPF che includa entrambi i set di valori.</span><span class="sxs-lookup"><span data-stu-id="5c368-223">Instead, add the required Microsoft values to the current record so that you have a  *single*  SPF record that includes both sets of values.</span></span> <span data-ttu-id="5c368-224">Servono esempi?</span><span class="sxs-lookup"><span data-stu-id="5c368-224">Need examples?</span></span> <span data-ttu-id="5c368-225">Estrarre questi [record di sistema per il nome di dominio esterno per Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span><span class="sxs-lookup"><span data-stu-id="5c368-225">Check out these [External Domain Name System records for Microsoft](https://support.office.com/article/c0531a6f-9e25-4f2d-ad0e-a70bfef09ac0).</span></span> <span data-ttu-id="5c368-226">Per convalidare il record SPF, è possibile utilizzare uno di questi[strumenti di convalida SPF](../setup/domains-faq.md).</span><span class="sxs-lookup"><span data-stu-id="5c368-226">To validate your SPF record, you can use one of these[SPF validation tools](../setup/domains-faq.md).</span></span> 
  
1. <span data-ttu-id="5c368-227">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/).</span><span class="sxs-lookup"><span data-stu-id="5c368-227">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/).</span></span> <span data-ttu-id="5c368-228">Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5c368-228">You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5c368-229">Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="5c368-229">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5c368-230">Nell'area **txt Records** della pagina **Managed DNS** selezionare il controllo **(+)** ( **Aggiungi nuovo**).</span><span class="sxs-lookup"><span data-stu-id="5c368-230">On the **Managed DNS** page, in the **TXT Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5c368-231">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5c368-231">(You may have to scroll down.)</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-1](../../media/657b87a5-dcb4-4ae7-8f27-bd857f0f4189.png)
  
4. <span data-ttu-id="5c368-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span><span class="sxs-lookup"><span data-stu-id="5c368-233">In the **Add TXT Records** area, in the boxes for the new record, type or copy and paste the values from the following table.</span></span> 
    
    |<span data-ttu-id="5c368-234">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5c368-234">**Name**</span></span>|<span data-ttu-id="5c368-235">**Valore**</span><span class="sxs-lookup"><span data-stu-id="5c368-235">**Value**</span></span>|<span data-ttu-id="5c368-236">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5c368-236">**TTL**</span></span>|
    |:-----|:-----|:-----|
    |<span data-ttu-id="5c368-237">Lasciare vuoto questo campo.</span><span class="sxs-lookup"><span data-stu-id="5c368-237">(Leave this field empty.)</span></span>  <br/> |<span data-ttu-id="5c368-238">v=spf1 include:spf.protection.outlook.com -all</span><span class="sxs-lookup"><span data-stu-id="5c368-238">v=spf1 include:spf.protection.outlook.com -all</span></span>  <br/> <span data-ttu-id="5c368-239">**Nota:** è consigliabile copiare e incollare questa voce, in modo che tutti i caratteri di spaziatura siano corretti.</span><span class="sxs-lookup"><span data-stu-id="5c368-239">**Note:** We recommend copying and pasting this entry, so that all of the spacing stays correct.</span></span>           |<span data-ttu-id="5c368-240">1800</span><span class="sxs-lookup"><span data-stu-id="5c368-240">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-4-2](../../media/b317bcb9-18c6-4609-a8f4-963823032669.png)
  
5. <span data-ttu-id="5c368-242">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="5c368-242">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-4-3](../../media/8a1c53c3-1222-4127-a190-70f6f5059433.png)
  
## <a name="add-the-two-srv-records-that-are-required-for-microsoft"></a><span data-ttu-id="5c368-244">Aggiungere i due record SRV necessari per Microsoft</span><span class="sxs-lookup"><span data-stu-id="5c368-244">Add the two SRV records that are required for Microsoft</span></span>
<span data-ttu-id="5c368-245"><a name="BKMK_add_SRV"> </a></span><span class="sxs-lookup"><span data-stu-id="5c368-245"><a name="BKMK_add_SRV"> </a></span></span>

1. <span data-ttu-id="5c368-p113">Per iniziare, passare alla propria pagina dei domini su DNSMadeEasy usando [questo collegamento](https://cp.dnsmadeeasy.com/). Verrà richiesto di eseguire l'accesso.</span><span class="sxs-lookup"><span data-stu-id="5c368-p113">To get started, go to your domains page at DNSMadeEasy by using [this link](https://cp.dnsmadeeasy.com/). You'll be prompted to login first.</span></span>
    
2. <span data-ttu-id="5c368-248">Nella pagina **console di gestione** , nell'area **domini aggiornati di recente** , selezionare il dominio che si desidera aggiornare.</span><span class="sxs-lookup"><span data-stu-id="5c368-248">On the **Management Console** page, in the **Recently Updated Domains** area, select the domain that you want to update.</span></span> 
    
3. <span data-ttu-id="5c368-249">Nell'area **SRV Records** della pagina **Managed DNS** selezionare il controllo **(+)** ( **Aggiungi nuovo**).</span><span class="sxs-lookup"><span data-stu-id="5c368-249">On the **Managed DNS** page, in the **SRV Records** area, select the **(+)** control ( **Add new**).</span></span>
    
    <span data-ttu-id="5c368-250">Può essere necessario scorrere la pagina.</span><span class="sxs-lookup"><span data-stu-id="5c368-250">(You may have to scroll down)</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-1](../../media/5c9e8f50-adbd-4f23-8ce3-2844b2896f3f.png)
  
4. <span data-ttu-id="5c368-252">Aggiungere il primo dei due record SRV.</span><span class="sxs-lookup"><span data-stu-id="5c368-252">Add the first of the two SRV records.</span></span>
    
    <span data-ttu-id="5c368-253">Nelle caselle del nuovo record nell'area **Add SRV Records** digitare oppure copiare e incollare i valori della prima riga della tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5c368-253">In the **Add SRV Records** area, in the boxes for the new record, type or copy and paste the values from the first row in the following table.</span></span> 
    
    |<span data-ttu-id="5c368-254">**Name**</span><span class="sxs-lookup"><span data-stu-id="5c368-254">**Name**</span></span>|<span data-ttu-id="5c368-255">**Priorità**</span><span class="sxs-lookup"><span data-stu-id="5c368-255">**Priority**</span></span>|<span data-ttu-id="5c368-256">**Peso**</span><span class="sxs-lookup"><span data-stu-id="5c368-256">**Weight**</span></span>|<span data-ttu-id="5c368-257">**Porta**</span><span class="sxs-lookup"><span data-stu-id="5c368-257">**Port**</span></span>|<span data-ttu-id="5c368-258">**Host**</span><span class="sxs-lookup"><span data-stu-id="5c368-258">**Host**</span></span>|<span data-ttu-id="5c368-259">**TTL**</span><span class="sxs-lookup"><span data-stu-id="5c368-259">**TTL**</span></span>|
    |:-----|:-----|:-----|:-----|:-----|:-----|
    |<span data-ttu-id="5c368-260">_sip. _tls</span><span class="sxs-lookup"><span data-stu-id="5c368-260">_sip._tls</span></span>  <br/> |<span data-ttu-id="5c368-261">100</span><span class="sxs-lookup"><span data-stu-id="5c368-261">100</span></span>  <br/> |<span data-ttu-id="5c368-262">1 </span><span class="sxs-lookup"><span data-stu-id="5c368-262">1</span></span>  <br/> |<span data-ttu-id="5c368-263">443</span><span class="sxs-lookup"><span data-stu-id="5c368-263">443</span></span>  <br/> |<span data-ttu-id="5c368-264">sipdir.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5c368-264">sipdir.online.lync.com.</span></span>  <br/> <span data-ttu-id="5c368-265">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="5c368-265">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5c368-266">1800</span><span class="sxs-lookup"><span data-stu-id="5c368-266">1800</span></span>  <br/> |
    |<span data-ttu-id="5c368-267">_sipfederationtls. _tcp</span><span class="sxs-lookup"><span data-stu-id="5c368-267">_sipfederationtls._tcp</span></span>  <br/> |<span data-ttu-id="5c368-268">100</span><span class="sxs-lookup"><span data-stu-id="5c368-268">100</span></span>  <br/> |<span data-ttu-id="5c368-269">1 </span><span class="sxs-lookup"><span data-stu-id="5c368-269">1</span></span>  <br/> |<span data-ttu-id="5c368-270">5061</span><span class="sxs-lookup"><span data-stu-id="5c368-270">5061</span></span>  <br/> |<span data-ttu-id="5c368-271">sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="5c368-271">sipfed.online.lync.com.</span></span>  <br/> <span data-ttu-id="5c368-272">**Questo valore DEVE terminare con un punto (.)**</span><span class="sxs-lookup"><span data-stu-id="5c368-272">**This value MUST end with a period (.)**</span></span> <br/> |<span data-ttu-id="5c368-273">1800</span><span class="sxs-lookup"><span data-stu-id="5c368-273">1800</span></span>  <br/> |
   
    ![DNSMadeEasy-BP-Configure-5-2](../../media/e1155f94-575f-441a-9a61-d948391d42ca.png)
  
5. <span data-ttu-id="5c368-275">Selezionare **Invia**.</span><span class="sxs-lookup"><span data-stu-id="5c368-275">Select **Submit**.</span></span>
    
    ![DNSMadeEasy-BP-Configure-5-3](../../media/7eae54e1-08bd-4902-afdf-fd5cc251ab59.png)
  
6. <span data-ttu-id="5c368-277">Aggiungere l'altro record SRV.</span><span class="sxs-lookup"><span data-stu-id="5c368-277">Add the other SRV record.</span></span>
    
    <span data-ttu-id="5c368-278">Nella sezione **SRV Records** selezionare il controllo **(+)** ( **Aggiungi nuovo**), creare un record usando i valori della riga successiva della tabella e quindi fare di nuovo clic su **Submit** per completare il record.</span><span class="sxs-lookup"><span data-stu-id="5c368-278">In the **SRV Records** section, select the **(+)** control ( **Add new**), create a record by using the values from the next row in the table, and then again select **Submit** to complete that record.</span></span> 
    
> [!NOTE]
> <span data-ttu-id="5c368-279">Typically it takes about 15 minutes for DNS changes to take effect.</span><span class="sxs-lookup"><span data-stu-id="5c368-279">Typically it takes about 15 minutes for DNS changes to take effect.</span></span> <span data-ttu-id="5c368-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span><span class="sxs-lookup"><span data-stu-id="5c368-280">However, it can occasionally take longer for a change you've made to update across the Internet's DNS system.</span></span> <span data-ttu-id="5c368-281">In caso di problemi con il flusso di posta o altri problemi dopo l'aggiunta di record DNS, vedere [individuare e correggere i problemi dopo l'aggiunta del dominio o dei record DNS](../get-help-with-domains/find-and-fix-issues.md).</span><span class="sxs-lookup"><span data-stu-id="5c368-281">If you're having trouble with mail flow or other issues after adding DNS records, see [Find and fix issues after adding your domain or DNS records](../get-help-with-domains/find-and-fix-issues.md).</span></span> 
  

